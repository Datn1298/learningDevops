## Kubernetes command-line tools

### Node
1. Liệt kê các tài nguyên
````
$ kubectl get node
````

2. Hiển thị thông tin chi tiết về 1 tài nguyên
````
$ kubectl describe
````

3. In logs từ 1 container trong 1 pod
````
$ kubectl logs
````

4. Thực hiện 1 lệnh trên 1 container trong 1 pod
````
$ kubectl exec
````

### Pod
1. Liệt kê các pods
````
$ kubectl get pods
```` 

2. Tạo 1 pod mới
	Sử dụng data trong pod.json
	````
	$ kubectl create -f ./pod.json
	````

	Start 1 pod
	````
	# nginx
	$ kubectl run nginx --image=nginx
	````

Ref:
1: https://jamesdefabia.github.io/docs/user-guide/kubectl/kubectl_delete/