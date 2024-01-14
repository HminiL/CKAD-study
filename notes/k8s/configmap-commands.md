# kubectl configmap commands

### create
> kubectl create configmap (configmap name) --from-literal=(key)=(value) </br>
> *e.g. kubectl create configmap app-config --from-literal=APP_COLOR=blue*

> kubectl create configmap (configmap name) --from-file=(file name) </br>
> *e.g. kubectl create configmap app-config --from-file=app_config.properties*

