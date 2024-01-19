# Service Account Commands

### create service account
> kubectl create serviceaccount <service-account-name> </br>
> *e.g. kubectl create serviceaccount my-service-account*

### create service account token
> kubectl create token (service-account-name) </br>
> *e.g. kubectl create token my-service-account*

### set service account for deployment
> kubectl set serviceaccount deploy/<deployment-name> <service-account-name> </br>
> *e.g. kubectl set serviceaccount deploy/web-dashboard dashboard-sa*

### short commands
> k create sa <service-account-name> </br>