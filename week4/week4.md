# Gitlab - CICD

## Tìm hiểu chung về Gitlab
1. Gitlab là gì?
- Mã nguồn mở, dựa trên hệ thống máy chủ Git
- Dùng để quản lý mã nguồn
2. Cấu trúc của Gitlab
- Local
	- Code
- Gitlab
	- Repo: lưu trữ code
	- Gitlab registry: lưu trữ images sau khi build
- Server
	- Gitlab runner
	- Docker
3. Cơ chế hoạt động
- B1: Push code từ Local đến Repo
- B2: Từ Repo, build Image => Đẩy image lên Gitlab Registry
- B3: Kết nối với Gitlab Runner thông qua SSH + Command Line
- B4: Gitlab Runner gửi request để pull image về
- B5: Gitlab Registry gửi image đến Gitlab Runner
- B6: Docker chạy image vừa pull về
## Setup Gitlab trên máy local
1. Cài đặt Gitlab trên máy local trên hệ điều hành Linux
- Tạo file docker-compose.yml

````
version: '3.7'
services:
  web:
    image: 'gitlab/gitlab-ce:latest'
    restart: always
    hostname: 'localhost'
    container_name: gitlab-ce
    environment:
      GITLAB_OMNIBUS_CONFIG: |
        external_url 'http://localhost'
    ports:
      - '8080:80'
      - '8443:443'
    volumes:
      - '$GITLAB_HOME/config:/etc/gitlab'
      - '$GITLAB_HOME/logs:/var/log/gitlab'
      - '$GITLAB_HOME/data:/var/opt/gitlab'
    networks:
      - gitlab

  gitlab-runner:
    image: gitlab/gitlab-runner:alpine
    container_name: gitlab-runner    
    restart: always
    depends_on:
      - web
    volumes:
      - /var/run/docker.sock:/var/run/docker.sock
      - '$GITLAB_HOME/gitlab-runner:/etc/gitlab-runner'
    networks:
      - gitlab

networks:
  gitlab:
    name: gitlab-network
````

	- Trong services gồm 2 images:
		- Gitlab-ce: đóng vai trò Gitlab, nơi lưu trữ code và build image
		- Gitlab-runner: nơi kết nối với Docker để có thể run image

Sau đó sử dụng câu lệnh sau:
````
docker-compose up -d
````

- Vào http://localhost:8080/ để truy cập vào Gitlab
	- Lần đầu tiên đăng nhập sẽ đăng nhập với user "root" và password sẽ lấy từ thư mực /etc/gitlab/initial_root_password trong container của gitlab-ce

	````
	docker exec -it gitlab-ce grep 'Password:' /etc/gitlab/initial_root_password
	````

## Tìm hiểu chung về CICD
1. CI là gì?
- CI = Countinous Intergration
	- liên tục tích hợp những thay đổi của dự án và test lại thường xuyên

- Ưu điểm
	- Commint code sớm, thường xuyên => phát hiện lỗi => sửa lỗi
	- Không phụ thuộc vào IDE
	- Tự động hoá việc build và kiểm tra code khi code thay đổi
	- 

2. CD là gì?
- CD = Countinous Development
	- 

## Setup CICD Gitlab
1. Setup môi trường
- Tạo Dockerfile để build souce code thành image

- Tạo file .gitlab-ci.yml để chạy những lệnh của Gitlab
	- Định nghĩa cho Gitlab, sau khi push code lên thì Gitlab sẽ làm gì

- Tạo file deploy.sh để
	- pull image từ registry
	- start container