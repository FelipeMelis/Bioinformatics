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

## 3.- Filter and convert the sam to bam

`samtools view -bS -f 3 output.sam > output_filter.bam`

`-f 3`: this option deliver the properly mapped reads (in pairs)

## 4.- Sorting the sam

Sort the bam using a temporal file.<br /> 
`samtools sort -O bam -o output_sorted.bam -T ./out_temp output.bam`

## 4.- Indexing the sam

`samtools index output_filter_sorted.bam`

## 5.- Get the counts

 Using idxstat and the bam file. <br />
 `samtools idxstats output_sorted.bam > out.stat`
