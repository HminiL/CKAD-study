# Core Concepts


### Node(Minions)
- physical and virtual machine, container launch
Cluster
- set of nodes
Master
- response of cluster another node in k8s

### Components
- API Server
- etcd
- Scheduler
- Controller
- Container Runtime -> normally docker/ other option posiible
- Kubelet -> responsible for making sure container run expected

### Maser
- Api server
- etcd
- Controller
- Scheduler

### Worker Node
- Container Runtime
- Kubelet 

### Docker VS containerD
- Support “ctr” or not (support only in ContainerD)

### Pod
- Single instance
- Smallest object 
- One to one except when has a helper container(cause need to live/dead together)




