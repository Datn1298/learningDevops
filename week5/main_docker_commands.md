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
- List: liệt kê các container
````
$ docker ps
````
- Remove: xoá các container
````
$ docker rm [OPTION] CONTAINER_ID
````
- Stop/ Start: dừng/ chạy 1 container
````
$ docker stop/start [OPTION] CONTAINER
````
- Pause/ unpause: dừng/ tất các process trong 1 hoặc nhiều container
`````
$ docker pause/unpause CONTAINER
`````
- Rename: đổi tên 1 container
````
$ docker rename CONTAINER NEW_NAME
````
- Commit: tạo 1 image mới từ sự thay đổi của container
````
$ docker commit [OPTION] CONTAINER [REPO[:TAG]]
````



4. Volume
- List: liệt kê tất cả volume
````
$ docker volume ls
````
- Create: tạo 1 volume
````
$ docker volume create [OPTION] VOLUME
````
- Prune: xoá tất cả volume k sử dụng
````
$ docker volume prune
````
- Remove: xoá 1 hoặc nhiều volume
````
$ docker volume rm [OPTION] VOLUME
````
- Inspect: hiển thị thông tin chi tiết của 1 hoặc nhiều volume
````
$ docker volume inspect [OPTION] VOLUME
````