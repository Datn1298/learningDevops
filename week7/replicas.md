# Tạo Replicas
## Replicas Controller
Tạo rc-definition.yml
```file
apiVersion: v1
kind: ReplicationController
metada:
  name: myapp-rc
  labels:
    app: myapp
    type: FE
spec:
  template:
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
              value: mysecretpasswordod
  replicas: 3
```
Sau đó, chạy lệnh dưới để khởi tạo Replicas:
```cmd
$ kubectl create -f name_file
```

Để xem danh sách Replication đã tạo:
```cmd
$ kubectl get replicationcontroller
```

## Replica Set
1. Tạo
Tạo file: replicaset-definition.yml
```file
apiVersion: apps/v1
kind: ReplicaSet
metada:
  name: myapp-replicaset
  labels:
    app: myapp
    type: FE
spec:
  template:
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
              value: mysecretpasswordod
  replicas: 3
  selectior:
    matchLabels:
			type: FE
```
Sau đó chạy command:
```cmd
$ kubectl create -f replicaset-definition.yml
```

2. Xoá replicaset
```cmd
$ kubectl delete replicaset tên_command
```

3. Thay thế từ 1 file
```cmd
$ kubectl replace -f replicase-defie
```

4. Scale
```cmd
$ kubectl sacle -replication=6 -f replicaset-definition
```

5. Edit
```cmd
$ kubectl edit replicaset name-replicaset
```

kubectl get pods


