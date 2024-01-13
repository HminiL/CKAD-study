# docker commands

### get image
> docker images

### build image
> docker build -t (image name) (directory)
> *e.g. docker build -t webabb-color .*

### run image
> docker run (image name) -p (host port):(container port)
> *e.g. docker run -p 8080:8080 webapp-color*