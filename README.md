# Kubernetes
<img src=jecrck8sintro1>
<img src=jecrck8sintro2>

```
akash@akash:~$ kubectl get node
NAME       STATUS   ROLES           AGE    VERSION
minikube   Ready    control-plane   115s   v1.31.0
akash@akash:~$ 
```
### pod.yaml
```
apiVersion: v1
kind: Pod
metadata:
  name: akpod
spec:
  containers:
  - name: akc
    image: httpd
    ports:
      - containerPort: 80
```

```
akash@akash:~/Desktop/kubernetes$ kubectl apply -f pod.yaml 
pod/akpod created
akash@akash:~/Desktop/kubernetes$ kubectl get pod
NAME    READY   STATUS              RESTARTS   AGE
akpod   0/1     ContainerCreating   0          12s
akash@akash:~/Desktop/kubernetes$ kubectl get pod 
NAME    READY   STATUS    RESTARTS   AGE
akpod   1/1     Running   0          23s

akash@akash:~/Desktop/kubernetes$ kubectl delete pod akpod
pod "akpod" deleted

```
