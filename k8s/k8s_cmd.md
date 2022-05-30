# kubectl cmd

```shell
[root@guangbao-10-190-90-202 ~]# kubectl get nodes
NAME                     STATUS   ROLES    AGE   VERSION
guangbao-10-190-90-202   Ready    master   35d   v1.18.19+k3s1
```

```shell
[root@guangbao-10-190-90-202 ~]# kubectl get pod
No resources found in default namespace.


[root@guangbao-10-190-90-202 ~]# kubectl get services
NAME         TYPE        CLUSTER-IP   EXTERNAL-IP   PORT(S)   AGE
kubernetes   ClusterIP   10.43.0.1    <none>        443/TCP   35d
```



```shell
# -it: interactive terminal
# 进入pod中的容器：get the terminal of container in the pod
kubectl exec -it [podname] -- bin/bash  
```

