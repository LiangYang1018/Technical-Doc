# Node processes

## worker node

<img src="image/image-20220524172340671.png" alt="image-20220524172340671" style="zoom: 25%;" /> 

### 3 processes 

<img src="image/image-20220524173129681.png" alt="image-20220524173129681" style="zoom:25%;" align = "left"/>

+ container runtime

+ Kubelet

  <img src="image/image-20220524172441343.png" alt="image-20220524172441343" style="zoom: 25%;" />   

+ Kube proxy

​        <img src="image/image-20220524174142133.png" alt="image-20220524174142133" style="zoom:25%;" /> 



## master node

<img src="image/image-20220524181525149.png" alt="image-20220524181525149" style="zoom: 50%;" /> 

+ Api server
  + cluster gateway
  + act as a gatekeeper for authentication
  + load balancer
+ Scheduler
  + Schedule new pod
  + where to put the pod?
    + scheduler decides on which new pod should be scheduled
+ Controller manager
  + detects cluster state changes
+ etcd
  + ectd is a key-value store of the cluster state
    + cluster changes get stored in the key value store
  + etcd is the cluster brain: it knows (and provides these info to the other 3 processes)
    + what resources are available
    + did the cluster state change?
    + is the cluster healthy
