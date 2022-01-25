# Docker
- Docker là nền tảng phần mềm, cho phép xây dựng, triển khai, kiểm thử 1 cách dễ dàng.

## Containers with Docker
1. Images
- Image chứa các source code, thư viện, dependencies, tool, và các files khác cần thiết cho 1 ứng dụng để chạy
- Images có tính chất chỉ đọc (read-only)
  - đôi khi được gọi là snapshot - đại diện cho 1 ứng dụng - virtual environment tại 1 thời điểm cụ thể
- Không thể run hay start 1 image
  - image chỉ để build ra container

2. Container?
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

5. Main Docker Commands
  1. Network
  - List: Liệt kê danh sách network
  ````
  $ docker network list
  ````
  - Connect: nối 1 container vs 1 network
  ````
  $ docker network connect [OPTION] NETWORK CONTAINER
  ````
  - Create: tạo 1 network
  ````
  $ docker network create [OPTION] NETWORK
  ````
  - Disconnect: ngắt kết nối 1 container vs 1 network
  ````
  $ docker network disconnect [OPTION] NETWORK CONTAINER
  ````
  - Inspect: hiện thị thông tin chi tiết của 1 hoặc nhiều network
  ````
  $ docker network inspect [OPTION] NETWORK
  ````
  - Prune: xoá tất cả network đang không sử dụng
  ````
  $ docker network prune
  ````
  - Remote: xoá 1 hoặc nhiều networks
  ````
  $ docker network rm [OPTION] NETWORK
  ````

  2. Image
  - List: liệt kê danh sách image
  ````
  $ docker image ls
  ````
  - Build: build 1 image từ Dockerfile
  ````
  $ docker build [OPTION] PATH|URL|-
  ````
  - History: hiện thị lịch sử của 1 image
  ````
  $ docker image history [OPTION] IMAGE
  ````
  - Inspect: hiện thi thông tin chi tiết của 1 hoặc nhiều images
  ````
  $ docker image inspect [OPTION] IMAGE
  ````
  - Prune: xoá tất cả images không sử dụng
  ````
  $ docker image prune
  ````
  - Pull: pull 1 image hoặc 1 repo từ 1 registry
  ````
  $ docker pull [OPTION] IMAGE[:TAG|@DIGEST]
  ````
  - Push: push 1 image hoặc 1 repo đến 1 registry
  ````
  $ docker push [OPTION] IMAGE[:TAG]
  ````
  - Remove: xoá 1 hoặc nhiều images
  ````
  $ docker rmi [OPTION] IMAGE
  ````
  - Save: lưu 1 image thành file .tar (chuyển image từ chỗ này sang chỗ khác 1 cách thủ công)
  ````
  $ docker save [OPTION] IMAGE
  ````
  - Load: tải 1 image từ file .tar (sau khi copy)
  ````
  $ docker load [OPTION]
  ````
  - Tag: tạo tag cho 1 image
  ````
  $ docker tag SOURCE_IMAGE[:TAG] TARGET_IMAGE[:TAG]
  ````

  3. Container
  -

5. Debugging a Docker Container
6. Demo Project Overview - Docker in Practice (Nodejs App with MongoDB and MongoExpress UI)
7. Developing with Containers
8. Docker Compose - Running multiple services
9. Dockerfile - Building our own Docker Image
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