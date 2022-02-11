## Pods

Gồm 4 thành phần chính:
1. apiVersion
- là version của kubernetes API ta sử dụng để tạo object

2. kind
- Đề cập đến đối tượng ta đang tạo
	- trong trường hợp này là: Pod
- 1 số giá trị có thể có:
	- ReplicaSet
	- Deployment
	- Service

3. metadata
- Là data về object như:
	- name
	- labels
	- ...


4. spec

Ví dụ: pod.yaml
````
apiVersion: v1
kind: Pod
metadata:
  name: postgres
  labels:
    tier: db-tier
spec:
  containers:
    - name: postgres
      image: postgres
      env:
        - name: POSTGRES_PASSWORD
          value: mysecretpassword
````