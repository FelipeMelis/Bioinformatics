# Bioinformatics Utilities :facepunch:

## Bash

**Create screen**
```
screen -S screen_name
```
**Enter the screen** 
```
screen -r screen_name
```
**Convert _fastq_ to _fasta_**
```
sed -n '1~4s/^@/>/p;2~4p’ file.fastq > file.fasta
```
**Rename files from different folders**
```
ls | while read line ; do cp ./${line}/file.fl ./${line} ; done
```
**Find files**
```
find / -name "file.txt"
```
**Find zero bytes files and erase them from the face of the earth!**
```
find . -type f -size 0 | while read line; do rm ${line} ; done 
```

## GitHub

**Create a Branch**
```
git pull origin master
git checkout -b branchname
```

**Commit changes**
```
git add -A (or ./file.fl)
git commit -m 'this change is for rucula'
git push origin branchname (or master (never do master))
```

**Solution when you something to big to GitHub**
```
git filter-branch --tree-filter 'rm -f file-too.big' HEAD
```

## Dockers

**Download Docker**
```
docker pull docker_repo/docker_name
```
**Open Docker**
```
run --rm -it -v /path/to/volume:/volume docker_repo/docker_name
```
**Open Docker for Basemount from Illumina** (https://basemount.basespace.illumina.com/)
```
run --privileged --cap-add=MKNOD --cap-add=SYS_ADMIN --device=/dev/fuse --rm -it -v /path/to/volume:/volume docker_repo/docker_name
```
