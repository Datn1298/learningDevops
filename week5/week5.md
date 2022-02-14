# Docker
- Docker là nền tảng phần mềm, cho phép xây dựng, triển khai, kiểm thử 1 cách dễ dàng.

## Containers with Docker
1. Images
- Image chứa các source code, thư viện, dependencies, tool, và các files khác cần thiết cho 1 ứng dụng để chạy
- Images có tính chất chỉ đọc (read-only)
  - đôi khi được gọi là snapshot - đại diện cho 1 ứng dụng - virtual environment tại 1 thời điểm cụ thể
- Không thể run hay start 1 image
  - image chỉ để build ra container

2. Container
- Container là 1 run-time environment - có thể chạy 1 ứng dụng đọc lập
- Các container hoạt động độc lập, không ảnh hưởng đến các container khác

3. Docker Components and architecture explained
- Phần chính của Docker bao gồm:
  - Docker Daemon
    - Lắng nghe các yêu cầu từ Docker API, và quản lý Docker Objects
    - 1 Daemon có thể giao tiếp với nhiều Daemons khác để quản lý các dịch vụ Docker
  - Docker Client
    - Là các chính để người dùng docker có thể tương tác với docker
  - Docker Desktop
  - Docker Registries
    - Nơi lưu trữ Docker images
    - DockerHub = Public registry
    - Có thể pull hoặc run images từ registry
  - Docker Object
    - Images
    - Contaniers

4. Docker vs. Virtual Machine
- VM
  - Ảo hoá phần cứng
  - Phần mềm chạy trên HĐH ảo ( mỗi 1 VM có 1 HĐH riêng)
  - Chạy nhiều HĐH ảo trên 1 máy thật
  - HĐH ảo chiếm tài nguyên lớn
  - Hỗ trợ phần mềm có giao diện
  - Cách ly giữa các HĐH

- Docker
  - PM chạy trên HĐH chủ
  - Chỉ có 1 HĐH chủ
  - PM sử dụng trực tiếp HĐH từ HĐH chủ
  - Cách ly tài nguyên
  - Cách ly giữa các process
 
 Docker sẽ sử dụng chung Kernel (ví dụ: Window, Linux). Các container sẽ chứa những thư viện, ... và sử dụng chung kernel của máy chủ. Còn VM thì tách biệt, mỗi máy ảo sẽ có 1 HĐH riêng. Nên sẽ gây lãng phí 1 phần tài nguyên.

5. [Main Docker Commands](https://github.com/Datn1298/learningDevops/blob/master/week5/main_docker_commands.md)
6. Debugging a Docker Container
7. Demo Project Overview - Docker in Practice (Nodejs App with MongoDB and MongoExpress UI)
8. Developing with Containers
9. Docker Compose - Running multiple services
- Là 1 tool để định nghĩa và chạy multi-container Docker application
- sử dụng .yml file
-

- Các commands:
  - Up: chạy docker-compose file
  ````
  $ docker-compose up [OPTION]
  ````
  - Down: dừng containers và xoá các containers, networks, volumes, và images được tạo từ 'up'
  ````
  $ docker-compose dowm [OPTION]
  ````
  - Exec: execute 1 command trong 1 container đang chạy
  ````
  $ docker exec [OPTION (-it)] CONTAINER COMMAND  
  ````
10. Dockerfile - Building our own Docker Image
- Là 1 text document, chứa các câu lệnh cho người dùng có thể gọi trong CLI để tạo ra 1 image
- Sd *docker build* để build 1 image từ Dockerfile. 
- Dockerfile instructions
  1. FROM
  - Khởi tạo 1 stage mới
  - Chỉ định Image cơ sở để thực hiện các câu lệnh tiếp theo. Các Image có thể lấy từ DockerHub
  - Dockerfile hợp lệ khi bắt đầu bằng *FROM*
  ````
  $ FROM ubuntu
  ````
  2. ARG
  - Khai báo biến nào đó
  - Có thể đứng trước *FROM*
  - Chỉ hoạt động trong quá trình build image (build-time)
  ````
  $ ARG $version=lastest
  $ FROM ubuntu:${version}
  ````
  3. LABEL
  - Để thêm metadata cho 1 image, ghi lại thông tin licension,...
  - Dưới dạng key-value
  ````
  $ LABEL com.example.version="0.0.1-beta"
  ````
  4. CMD
  - Chỉ chạy khi chạy container
  - Có thể khai báo nhiều CMD, nhưng chỉ CMD cuối cùng mới được thực hiện
  ````
  $ CMD ["executable","param1","param2"] (exec form, this is the preferred form)
  $ CMD ["param1","param2"] (as default parameters to ENTRYPOINT)
  $ CMD command param1 param2 (shell form)
  ````
  5. ENV
  - Khai báo biến môi trường
  - Dưới dạng key-value
  ````
  $ ENV <key>=<value> ...

  $ docker run --env <key>=<value>
  ````
  6. EXPOSE
  - Thông báo Port
  ````
  $ EXPOSE 80/udp

  # overwrite
  $ docker run -p 80:80/tcp -p 80:80/udp
  ````
  7. RUN
  - Chạy các câu lệnh trong quá trình build images
  - Thường là các câu lệnh Linux
  ````
  $ RUN <command>
  # RUN apt-get update
  $ RUN ["executable", "param1", "param2"]
  # RUN ["/bin/bash", "-c", "echo hello"]
  ````
  8. WORKDIR
  - Nên luôn sử dụng *WORKDIR* để khai báo đường dẫn
  ````
  $ WORKDIR /path/to/workdir
  # WORKDIR /abc
  # RUN pwd
  ````
  9. COPY
  - Copy từ máy local đi vào trong container
  10. ADD
  - Giống *COPY*
  - Có thể tải file về. Nếu file là file nén thì sẽ tự động giải nén

10. Private Docker Repository - Pushing our built Docker Image into a private Registry on AWS
11. Deploy containerized app
12. Docker Volumes - Persist data in Docker
13. Volumes Demo - Configure persistence for our demo project
## Docker & Nexus
1. Create Docker Images Repository on Nexus
2. Push/Pull Docker Image from/to Nexus Repository Manager
3. Install Nexus with Docker
4. Configure insecure repositories in Docker Engine

## Ref
1. https://docs.docker.com/engine/reference/commandline/docker/
2. https://docs.docker.com/get-started/overview/