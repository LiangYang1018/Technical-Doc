# kubectl cmd

**kubectl命令**

kubectl是kubernetes集群的命令行工具，通过它能够对集群本身进行管理，并能够在集群上进行容器化应用的安装部署。kubectl命令的语法如下：

```shell
kubectl [command] [type] [name] [flags]
```

**comand**：指定要对资源执行的操作，例如create、get、delete

**type**：指定资源类型，比如deployment、pod、service

**name**：指定资源的名称，名称大小写敏感

**flags**：指定额外的可选参数



## 全局查看

### 查看资源

~~~ shell
[root@master ~]# kubectl api-resources
NAME                              SHORTNAMES   APIGROUP                       NAMESPACED   KIND
bindings                                                                      true         Binding
componentstatuses                 cs                                          false        ComponentStatus
configmaps                        cm                                          true         ConfigMap
endpoints                         ep                                          true         Endpoints
events                            ev                                          true         Event
~~~



### 查看节点信息

```shell
[root@guangbao-10-190-90-202 ~]# kubectl get nodes
NAME                     STATUS   ROLES    AGE   VERSION
guangbao-10-190-90-202   Ready    master   35d   v1.18.19+k3s1
```



## namespace

### 查看默认namaspace下的pod信息 

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



## Pod

### 查看namespace下的nodes

~~~shell
[root@master ~]# kubectl get pods -n dev
NAME                    READY   STATUS    RESTARTS   AGE
nginx-dd6b5d745-7l97b   1/1     Running   0          42m

~~~

### 查看pod中的容器，用于debug

```shell
[root@master ~]# kubectl describe pods nginx-dd6b5d745-7l97b -n dev
Name:         nginx-dd6b5d745-7l97b
Namespace:    dev
Priority:     0
Node:         node1/192.168.120.101
Start Time:   Tue, 31 May 2022 14:35:49 +0800
Labels:       pod-template-hash=dd6b5d745

```



### 查看pod及子对象的属性（用于编写yaml）

```shell
[root@master ~]# kubectl explain pod.metadata
KIND:     Pod
VERSION:  v1

RESOURCE: metadata <Object>

DESCRIPTION:
     Standard object's metadata. More info:
     https://git.k8s.io/community/contributors/devel/sig-architecture/api-conventions.md#metadata

     ObjectMeta is metadata that all persisted resources must have, which
     includes all objects users must create.

FIELDS:
   annotations  <map[string]string>
     Annotations is an unstructured key value map stored with a resource that

```

## 查看pod信息以yaml格式输出

```shell
[root@master ~]# kubectl get pods nginx-dd6b5d745-7l97b -n dev -o yaml
apiVersion: v1
kind: Pod
metadata:
  creationTimestamp: "2022-05-31T06:35:49Z"
  generateName: nginx-dd6b5d745-
  labels:
    pod-template-hash: dd6b5d745
    run: nginx
  name: nginx-dd6b5d745-7l97b
  namespace: dev
  ownerReferences:

```

### 进入pod

```shell
[root@k8s-master01 pod]# kubectl exec pod-command -n dev -it -c busybox /bin/sh
```

