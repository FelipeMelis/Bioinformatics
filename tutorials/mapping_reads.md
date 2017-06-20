# Mapping reads against a reference

## 1.- Index the reference

`bwa index -a is -p index_name /path/to/ref/file.fasta`

Options <br />
`-a is`: is for small genome, default is for big genomes.<br />
`-p`: is the name of the index (use the same of the fasta).

## 2.- Mapping the reads

`bwa mem /path/to/index /path/to/read_1 /path/to/read_2 -t 20 > output.sam`

Options:<br />
`-t 20`: Number of threads used in the mapping.

## 3.- Tunning the sam

Fix some usual problems with the sam files. <br /> 
`samtools fixmate -O bam output.sam output_fixmate.bam`

Sort the bam using a temporal file.<br /> 
`samtools sort -O bam -o output_sorted.bam -T ./out_temp output_fixmate.bam`

## 4.- Get the mapped or unmapped reads 

Get the mapped reads in sam or bam format. <br />
`samtools view -F 4 output_sorted.bam > mapped.sam` <br />
`samtools view -b -F 4 output_sorted.bam > mapped.bam`

Get the unmapped reads in sam or bam format. <br />
`samtools view -f 4 output_sorted.bam > unmapped.sam` <br />
`samtools view -b -f 4 output_sorted.bam > unmapped.bam`

## 5.- Get the counts
 
 Using the sam file. <br />
 `awk '{print $3}' mapped.sam | sort | uniq -c | awk '{print $2, $1}' | sed 's/ /\t/g'`
 
 Using idxstat and the bam file. <br />
 `samtools idxstats output_sorted.bam > out.stat`
