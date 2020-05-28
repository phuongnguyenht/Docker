# Một số thao tác cơ bản trong Docker
Sau khi cài đặt thành công Docker, ta sẽ tiếp tục làm quen một số thao tác cơ bản trên Docker như pull, list image, run container, list container…

##1. Basic Operations in Docker

* List local images
```
docker images
```
* Searching images (on default registry)
```
docker search centos
```
* Pull specific images
```
docker pull centos:centos6
docker pull centos
docker images

docker run [name|image-id]
```

* Inspect local images  
```
docker inspect centos
docker inspect hello-world
```

* List running containers 
```
docker ps
```
* List all containers
```
docker ps -a
```

* run docker interactive, terminal
```
docker run -it centos:latest
```

* run docker as deamon
```
docker run -d centos:lastest
```