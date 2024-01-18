# Secret Commands

### create secret from literal
> kubectl create secret generic (secret name) --from-literal=(key)=(value) </br>
> *e.g. kubectl secret generic db-secret --from-literal=DB_HOST=test*
> - generic(type of secret): Create a secret from a local file, directory, or literal value


### execute command inside pod
> kubectl exec (pod name) -- (command) </br>
> *e.g. kubectl exec my-pod -- whoami* -> find user</br>
