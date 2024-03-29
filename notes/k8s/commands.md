# kubectl commands


### get commands
> kubectl get pods

> kubectl get pods --help

> kubectl get replicationcontroller

> kubectl get replicaset / kubectl get rs

> kubectl get deployment

> kubectl get all
k
> **get all pods in all namespaces** </br>
> kubectl get pods --all-namespaces </br>
> kubectl get pods -A


> kubectl get pods --namespace=(namespace name) </br>
> *e.g. kubectl get pods --namespace=dev*

### run commands
> kubectl run (create a pod) --image=(image name) </br>
*e.g. kubectl run nginx --image=nginx*

> kubectl run (create a pod) --image=(image name) --port=(port number) </br>
> *e.g. kubectl run redis --image=redis --port=6379*

> kubectl run (pod name) --image=(image name) >> (file name) </br>
*e.g. kubectl run nginx --image=nginx >> nginx.yaml*

> **set tier in label** </br>
> kubectl run (pod name) --image=(image name) --labels=(label name)=(label value) </br>
 > *e.g. kubectl run nginx --image=nginx --labels="tier=frontend"*

> **using a custom arguments (arg1 .. argN) for that**</br>
> kubectl run (pod name) --image=(image name) -- (arg1) .. (argN) </br> 
> *e.g. kubectl run webapp-color --image=webapp-color/kodekloud -- --coler green*

> **using a different command and custom arguments**</br>
> kubectl run (pod name) --image=(image name) --command -- (cmd) (arg1) .. (argN) </br>
> *e.g. kubectl run nginx --image=nginx --command -- sleep 10*
> 
### describe commands
> kubectl describe pod (pod name) </br>
*e.g. kubectl describe pod nginx*

> kubectl describe replicationcontroller (replicationcontroller name) </br>
*e.g. kubectl describe replicationcontroller myapp-rc*

> kubectl describe replicaset (replicaset name) </br>
*e.g. kubectl describe replicaset myapp-replicaset*

### create commands
> kubectl create -f (file name) </br> 
*e.g. kubectl create -f nginx.yaml*k

> **create deployment** </br>
> kubectl create deployment (deployment name) --image=(image name) -- replicas=(number)</br>
*e.g. kubeclt create deployment httpd --image=httpd:2.4-alpine --replicas=3*

> **create namespace** </br>
> kubectl create namespace (namespace name) </br>
> *e.g. kubectl create namespace dev*


### edit commands
> kubectl edit (type) (name) </br>
*e.g. kubectl edit pod nginx </br>*
*e.g kubectl edit replicaset myapp-replicaset*
*e.g kubectl edit rs myapp-deployment*
### delete commands
> kubectl delete pod (pod name) </br>
*e.g. kubectl delete pod nginx*


### replace commands
> kubectl replace -f (file name) </br>
*e.g. kubectl replace -f replicaset-definition.yaml*


### scale
> kubectl scale --replicas=(number) -f (file name) </br>
*e.g. kubectl scale --replicas=6 -f replicaset-definition.yaml*

> kubectl scale --replicas=(number) (type) (name) </br>
*e.g. kubectl scale --replicas=6 replicaset myapp-replicaset*



### formatting output
*out put with format*
> kubectl create namespace test-123 --dry-run -o json
```json
{
    "kind": "Namespace",
    "apiVersion": "v1",
    "metadata": {
        "name": "test-123",
        "creationTimestamp": null
    },
    "spec": {},
    "status": {}
}
```

> kubectl create namespace test-123 --dry-run -o yaml
```yaml
apiVersion: v1
kind: Namespace
metadata:
  creationTimestamp: null
  name: test-123
spec: {}
status: {}
```

### config
> kubectl config set-context (context name) --namespace=(namespace name) </br>

### replace
> kubectl replace --force -f (file name) </br>
> *e.g. kubectl replace --force -f /tmp/replicaset-definition.yaml*