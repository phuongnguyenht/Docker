# Một số thao tác cơ bản trong Docker
Sau khi cài đặt thành công Docker, ta sẽ tiếp tục làm quen một số thao tác cơ bản trên Docker như pull, list image, run container, list container…

##1. Basic Operations in Docker

### Docker image 
```
Docker image được tạo thành từ một loạt các lớp hệ thống tập tin tạo nên một ứng dụng phần mềm thực thi. Image là một tệp nhị phân bất biến bao gồm ứng dụng và tất cả các thành phần phụ thuộc khác như thư viện, tệp nhị phân và các hướng dẫn cần thiết để chạy ứng dụng.

Bạn có thể hiểu Docker Images như một ảnh chụp nhanh của Docker Container. Hầu hết các Docker Images có sẵn trên Docker Hub. Docker Hub là dịch vụ được sử dụng để lưu giữ Docker Images.
```

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
- Khi không chỉ định tag, Docker sẽ tải Image CentOS mới nhất
docker pull centos
- Có chỉ định tag
docker pull centos:centos6
docker images

docker run [name|image-id]
```
* Xoá Docker image
```
Nếu vì một số lý do, bạn muốn xóa một Image, bạn có thể làm điều đó với lệnh sau:
docker image rm image-name

Ví dụ để xoá Image centos sử dụng lệnh như sau
docker image rm centos

`Lưu ý`: Bạn sẽ không thể xoá Image nếu bạn đang chạy Container dựa trên Image đó
```

* Inspect local images  
```
docker inspect centos
docker inspect hello-world
```
### Docker Containers
```
Một thể hiện của Image được gọi là Container. Container đại diện cho thời gian chạy cho một ứng dụng, quy trình hoặc dịch vụ.
Bạn có thể hiểu Docker Image là lớp (Class) và Docker container là một thể hiện của một lớp (Class).
``` 
* Start Docker Container
```
Lệnh sau sẽ khởi động Container CentOS dựa trên Image centos. Nếu bạn Image centos, Docker sẽ tự động tải xuống Image centos trước khi chạy Container:
docker container run centos

Switch -it cho phép chúng ta tương tác với container thông qua dòng lệnh. Để bắt đầu một loại container tương tác sử dụng lệnh như sau:
docker container run -it centos /bin/bash

Option -i và -t sẽ cho chúng ta một giao diện shell để thao tác bên trong container, khi thoát khỏi giao diện shell này, các bạn sẽ stop luôn cả container.
```
* Liệt kê Docker Container
```
Để liệt kê các container đang hoạt động, sử dụng lệnh như sau:
docker container ls

Để xem cả Container đang hoạt động và không hoạt động, sử dụng lệnh như sau:
docker container ls -a
```
* Xoá bỏ Docker Container
```
Để xóa một hoặc nhiều container, sao chép ID container (hoặc ID) và dán chúng sau lệnh docker container rm:

docker container rm c55680af670c
```
```
Referrent: https://docs.docker.com/
```

### Push Image
```
Để mang các image các bạn đã commit đi khắp thế gian, chúng ta có thể Push chúng lên trên Docker Hub, sau khi image của bạn đã được lưu trên Docker Hub, bạn có thể pull về để sử dụng ở bất cứ đâu

Đầu tiên các bạn phải đăng ký một tài khoản tại Docker Hub, sau đó login như sau:

docker login -u [username]
Sau khi login thành công, bạn dùng lệnh sau để push image

docker push [username]/docker-1stcommit
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
