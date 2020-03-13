
# Installation

* Install [Docker](https://www.docker.com/)

* Get automated build from public registry:

Latest version:

`docker pull naviat/gatling-simple:latest`

All versions:

`docker pull naviat/gatling-simple`

Specific version:

`docker pull naviat/gatling-simple:3.2.1`

* [Alternatively] Build an image from Dockerfile: `docker build -t="naviat/gatling-simple" github.com/naviat/gatling-simple`

# Usage

Use image to run container

```
docker run -it --rm naviat/gatling-simple
```

Mount configuration and simulation files from the host machine and run gatling in interactive mode

```
docker run -it --rm -v /home/core/gatling/conf:/opt/gatling/conf \
-v /home/core/gatling/user-files:/opt/gatling/user-files \
-v /home/core/gatling/results:/opt/gatling/results \
naviat/gatling-simple
```

Use the `-e` switch to use JAVA_OPTS to pass parameters to gatling tests

```
docker run -e JAVA_OPTS="-Dusers=10" -it --rm naviat/gatling-simple
```
g
# Run on K8S

`kubectl create deployment load-test --image=naviat/gatling-simple`
