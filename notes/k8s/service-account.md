# Service Account

### Difference between service account and user account
#### User Account
- used by human
- administrator accessing to preform administrative tasks
- developer accessing to deploy applications

#### Service Account
- used by application to interact with kubernetes API
- e.g. Jenkins, Prometheus, etc.

### Service Account Token
- Service account token is a secret
- created automatically when service account is created

### Service Account Token Volume
- Service account token is mounted as a volume inside a pod
- Service account token is mounted at /var/run/secrets/kubernetes.io/serviceaccount
- Service account token is mounted inside a pod by default


### Default Service Account
- Every namespace has a default service account
- very restrictive permissions(only has permission to run basic k8s API queries)
- has only one token

### Remember
- Cannot edit service account token of an existing pod, only delete and recreate
- Can edit service account token of a deployment(automatically triggers roll out of new pods)