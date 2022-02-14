# Rollout - Versioning


## Rollout
- Mỗi khi tạo 1 deployment mới, hoặc update 1 image đã tồn tại trong deployment, sẽ kích hoạt Rollout
- 1 rollout mới sẽ tạo 1 Deployment Version (giống versioning)

- Để nhìn trạng thái của rollout
```cmd
$ kubectl rollout status deployment-name
```
- Để xem Versioning hoặc lịch sử chạy:
```cmd
$ kubectl rollout history deployment-name
```

### Kubectl apply
Có thể update bằng 2 cách
1. Sửa file yaml
- Sau khi sửa thông tin cần thay đổi trong file yaml, sử dụng câu lệnh:
```cmd
$ kubctl apply -f name-file
```
2. Sửa trực tiếp bằng cách sử dụng kubectl set
- Lưu ý, nếu sửa bằng cách này, 