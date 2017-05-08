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

