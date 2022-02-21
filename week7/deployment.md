# 
## Tạo 1 deployment
Tạo file: deployment-definition.yaml
- Tương tự như Replicas, nhưng ở trường ___kind___ giá trị là "Deployment"
```file
apiVersion: apps/v1
kind: Deployment
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
Sau đó chạy lệnh:
```cmd
$ kubectl create -f deployment-definition.yaml
```

Để lấy danh sách deployments đã tạo:
```cmd
kubectl get deployments
```

## Simmarize Commands
1. Create
```cmd
$ kubectl create -f deployment-definition.yaml
```

2. Get
```cmd
$ kubectl get deployments
```

3. Update
```cmd
$ kubectl apply deployment-definition.yaml
```

```cmd
$ kubectl set image deployment/myapp-deployment nginx=nginx:1.9.1
```

4. Status
```cmd
$ kubectl rollout status deployment/myapp-deployment
```

```cmd
$ kubectl rollout history deployment/myapp-deployment
```

5. Rollback
```cmd
$ kubectl rollout undo deployment/myapp-deployment
```
