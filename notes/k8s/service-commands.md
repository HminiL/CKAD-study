# kubectl service commands

### create service(expose)
> kubectl expose pod (pod name) --port=(port number) --name=(service name) </br>
> *e.g. kubectl expose pod redis --port=6379 --name redis-service*

> **create service with pod** </br>
> kubectl run (pod name) --image=(image name) --port=(port number) --expose=true </br>
> *e.g. kubectl run redis --image=redis --port=6379 --expose=true*