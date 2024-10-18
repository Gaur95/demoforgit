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
## controller
<img src=controller1.png>
<img src=controller2.png>
<img src=controller3.png>

```
apiVersion: v1
kind: ReplicationController
metadata:
  name: myrc
spec:
  replicas: 5
  selector:
    cup: tea
  template:
    metadata:
      name: rcpod
      labels:
        cup: tea
    spec:
      containers:
        - name: myappc
          image: httpd
          ports:
            - containerPort: 80 
```
```
akash@akash:~/Desktop/kubernetes$ kubectl apply -f rc.yaml 
replicationcontroller/myrc created
akash@akash:~/Desktop/kubernetes$ kubectl get rc
NAME   DESIRED   CURRENT   READY   AGE
myrc   5         5         5       14s
akash@akash:~/Desktop/kubernetes$ kubectl get pod
NAME         READY   STATUS    RESTARTS   AGE
akpod        1/1     Running   0          8m24s
myrc-4jtkc   1/1     Running   0          18s
myrc-8jf4l   1/1     Running   0          18s
myrc-8p5fm   1/1     Running   0          18s
myrc-f7cbz   1/1     Running   0          18s
myrc-w9kw6   1/1     Running   0          18s
pripod       1/1     Running   0          35m
akash@akash:~/Desktop/kubernetes$
akash@akash:~/Desktop/kubernetes$ kubectl get pod --show-labels
NAME         READY   STATUS    RESTARTS   AGE     LABELS
akpod        1/1     Running   0          11m     <none>
myrc-2bvxj   1/1     Running   0          97s     cup=tea
myrc-2jv9g   1/1     Running   0          38s     cup=tea
myrc-6w8q6   1/1     Running   0          97s     cup=tea
myrc-8gvpc   1/1     Running   0          38s     cup=tea
myrc-dld8c   1/1     Running   0          38s     cup=tea
myrc-f7cbz   1/1     Running   0          3m50s   cup=tea
myrc-kpth4   1/1     Running   0          97s     cup=tea
myrc-mgxpk   1/1     Running   0          38s     cup=tea
myrc-tvvpv   1/1     Running   0          38s     cup=tea
myrc-w9kw6   1/1     Running   0          3m50s   cup=tea
pripod       1/1     Running   0          38m     cup=coffee
akash@akash:~/Desktop/kubernetes$ kubectl delete -f rc.yaml 
replicationcontroller "myrc" deleted
akash@akash:~/Desktop/kubernetes$ kubectl get pod --show-labels
NAME     READY   STATUS    RESTARTS   AGE   LABELS
akpod    1/1     Running   0          13m   <none>
pripod   1/1     Running   0          39m   cup=coffee
akash@akash:~/Desktop/kubernetes$
```
