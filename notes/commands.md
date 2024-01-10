# kubectl commands


### get commands
> kubectl get pods

> kubectl get pods --help

> kubectl get pods description 

>kubectl get delete pods (pod name)

> kubectl get edit pods (pod name)

> kubectl get replicationcontroller

>kubectl get replicaset

### run commands
> kubectl run (create a pod) --image=(image name) </br>
> e.g. kubectl run nginx --image=nginx

> kubectl run (pod name) --image=(image name) >> (file name) </br>
e.g. kubectl run nginx --image=nginx >> nginx.yaml


### create commands
> kubectl create -f (file name) </br> 
e.g. kubectl create -f nginx.yaml