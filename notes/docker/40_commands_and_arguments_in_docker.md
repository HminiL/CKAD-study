# chap40. Commands and Arguments in Docker

### 1. sevral ways to run a command in docker 

#### 1.1. with CMD in Dockerfile
```dockerfile
FROM ubuntu

CMD sleep 5
(CMD command param1) -> o
(CMD ["command", "param1"]) -> o
(CMD ["sleep", "5"]) -> x
```
* the first element in the array should be the executable: CMD command param1
* do not specify the command and parameters together like this: CMD ["sleep 5"]
```bash
$ doker build -t ubuntu-sleeper .
$ doker run ubuntu-sleeper 
``` 

#### 1.2 change the command when running the container
```dockerfile
FROM ubuntu

ENTRYPOINT ["sleep"]
```
```bash
$ docker run ubuntu-sleeper sleep 10
```
- sleep 10 will be appended to the ENTRYPOINT (command at start up: sleep 10)
- if run without appending the number of seconds, it will get the error that the operant is missing
```dockerfile
FROM ubuntu

ENTRYPOINT ["sleep"]
CMD ["5"]
```
```bash
$ docker run ubuntu-sleeper
```
- CMD will be appended to the ENTRYPOINT (command at start up: sleep 5)
```bash
$ docker run ubuntu-sleeper 10
```
- 10 will be appended to the ENTRYPOINT, overriding the CMD (command at start up: sleep 10)


```yaml
apiVersion: v1
kind: Pod
metadata:
  name: ubuntu-sleeper-pod
spec:
  containers:
    - name: ubuntu-sleeper
      image: ubuntu-sleeper
      command: ["sleep2.0"]
      args: ["10"]
```
- args field in the pod definition file will override the CMD in the Dockerfile
- command field in the pod definition file will override the ENTRYPOINT in the Dockerfile