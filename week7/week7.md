# Kubernetes
## Tìm hiểu kiến trúc K8s( 1 day)
1. K8S là gì?
- Mã nguồn mở
- Tạo bởi Google
- Có thể nằm trên on-premise, prive, public, hybrid clouds
- Dùng để:
	- Triển khai, quản lý các công việc các công việc đã được đóng gói
	- Mở rộng
	- Cung cấp chức năng LoadBalance và route traffice

2. Kiến trúc K8S
-
## Tìm hiểu K8S Master Node (2.5 day)
1. Etcd (0.5 day)
- Là database lưu trữ thông tin về các cluster dưới dạng key-value
2. Api Server (0.5 day)
- Là 1 phần của Kubernetes control plane
- Là giao diện của Kubernetes control plane
3. Controller Manager Service (0.5 day)
- Quản lý tất cả bộ điều khiển xử lý các tác vụ thông thường trong cluster
- Bao gồm:
	- Node Controller
	- Replication Controller
	
	- Controller Manager 
	- Endpoint Controller
	- Service Account
	- Token Controller
- Chi tiết của các hoạt động này được ghi vào etcd
4. Scheduler Service (0.5 day)
- Chịu trách nhiệm về scheduling applications hoặc container trên Node
	- Giám sát việc sử dụng tài nguyên trên mỗi máy chủ => đảm bảo k bị quá tải
	- 
5. Dashboard (0.5 day)
- Giao diện web Kubernetes giúp đơn giản hoá tương tác thông qua API
## Tìm hiểu K8s Worker Node (10.5 days)
1. Pod (0.5 day)
	1. Pod
	- Là đơn vị bé nhất có thể triển khai mà bạn có thể tạo và quản lý trong K8S
	- 1 Pod có thể có 1 hoặc nhiều containers, và 1 số tài nguyên được chia sẻ cho các container đó:
		- Lưu trữ được chia sẻ, dưới dạng volumes
		- Kết nối mạng, như 1 cluster IP duy nhất
		- Thông tin về cách chạy từng container
	- 1 Pod luôn chạy trên 1 Node

	2. Node
	- Là 1 máy worker trong K8S
	- Mỗi Node được quản lý bởi Master
	- 1 Node có thể chứa nhiều Pod
	- Mỗi 1 Node chạy ít nhất:
		- Kubelet: dùng để giao tiếp giữa Node vs Master; quản lý các Pods và các Containers đang chạy trên cùng 1 máy
		- 1 container runtime (vd: Docker) để lấy image từ registry, giải nén và chạy các container

	3. Master
	- Quản lý toàn bộ Worker
	- Mô hình: Master =(quản lý các Node)=> Node =(chứa nhiều pods)=> pods => containers

	4. Ref
	- https://kubernetes.io/vi/docs/tutorials/kubernetes-basics/explore/explore-intro/

Kubelet
- Listens for instructions from APIServer
- Manages container

Kubeproxy
- Giúp giao tiếp giữa service vs cluster

2. Image (0.5 day)
3. Service (svc) (0.5 day)
4. Persistent Volumes NFS, GlusterFS (1 day)
	1. Định nghĩa PV
	- Giống như docker, k lưu dữ liệu trên container
		- vì mỗi lần restart/ stop thì dữ liệu mất theo container
	- PV là 1 phần k gian lưu trữ dữ liệu trong cluster
		- Riêng biệt với Pod => k mất đi khi xoá Pod
	- Có thể triển khai nhiều loại như:
		- NFS
		- ClusterFS
5. Namespaces (0.5 day)
6. Ingress rules (0.5 day)
7. Network policies (0.5 day)
8. Network (1 day)
9. ConfigMaps and Secrets (0.5 day)
10. Controllers (0.5 day)
11. Dashboard and Monitoring (0.5 day)
## Kubernetes command-line tool(kubectl) (1 day)
## Kubernetes clusters(kubeadm)(1,5 days)
## Slide giới thiệu tông quan K8S(1.5 days)

## Ref
1. https://kubernetes.io/docs/home/
2. https://www.youtube.com/playlist?list=PL2We04F3Y_43dAehLMT5GxJhtk3mJtkl5