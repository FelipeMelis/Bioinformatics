# Bioinformatics Utilities :facepunch:

## Bash

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
