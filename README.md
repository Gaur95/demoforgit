# Kubernetes
<img src=jecrck8sintro1.jpg>
<img src=jecrck8sintro2.jpg>

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
### to create secret 
```
kubectl create secret docker-registry mycred --docker-username demo  --docker-password 123
```
### replace your user name and password
```
akash@akash:~/Desktop/kubernetes$ kubectl get secret
NAME     TYPE                             DATA   AGE
mycred   kubernetes.io/dockerconfigjson   1      14m
```

### private pod yaml 
```
apiVersion: v1
kind: Pod
metadata:
 name: pripod
spec:
  imagePullSecrets:
    - name: mycred
  containers:
    - name: pric
      image: aakashgaur57/web2
      ports:
      - containerPort: 80

```
```
akash@akash:~/Desktop/kubernetes$ kubectl apply -f privatepod.yaml 
pod/pripod created
akash@akash:~/Desktop/kubernetes$ kubectl get pod
NAME     READY   STATUS    RESTARTS   AGE
pripod   1/1     Running   0          62s
```
