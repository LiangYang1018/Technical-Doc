开发 Helm Chart 需要使用预定义的目录结构组织文件。可以用 Helm 命令 helm create 创建一个 Helm chart，它是预定义的目录结构，包含一些示例文件。生成的 chart 包含几个 YAML 文件。一个 Kubernetes 部署通常需要多个要部署的 Kubernetes 资源描述，在许多情况下，这些部署必须有一个优先级顺序。当手动部署时，必须知道顺序。**而 Helm 则不必如此，因为 Helm 知道 Kubernetes 资源描述的优先顺序。**

https://blog.csdn.net/isea533/article/details/106353253/

~~~go
// InstallOrder is the order in which manifests should be installed (by Kind).
//
// Those occurring earlier in the list get installed before those occurring later in the list.
var InstallOrder KindSortOrder = []string{
	"Namespace",
	"NetworkPolicy",
	"ResourceQuota",
	"LimitRange",
	"PodSecurityPolicy",
	"PodDisruptionBudget",
	"Secret",
	"ConfigMap",
	"StorageClass",
	"PersistentVolume",
	"PersistentVolumeClaim",
	"ServiceAccount",
	"CustomResourceDefinition",
	"ClusterRole",
	"ClusterRoleList",
	"ClusterRoleBinding",
	"ClusterRoleBindingList",
	"Role",
	"RoleList",
	"RoleBinding",
	"RoleBindingList",
	"Service",
	"DaemonSet",
	"Pod",
	"ReplicationController",
	"ReplicaSet",
	"Deployment",
	"HorizontalPodAutoscaler",
	"StatefulSet",
	"Job",
	"CronJob",
	"Ingress",
	"APIService",
}

~~~

