---
layout: default
title: Docker
parent: Installation
nav_order: 7
has_children: false
permalink: /installation/docker
---

# Docker

Datagen is provided as a packaged docker image.
Hence, this docker image can be use to run datagen on any docker environment.

## Download 

Download latest image and extract it with following commands:

```shell
wget https://datagen-repo.s3.eu-west-3.amazonaws.com/1.0.0/docker/datagen-k8s.tar.gz
tar -xvzf datagen-k8s.tar.gz
cd datagen_k8s-1.0.0/
```

Load the image with following command:

```shell
docker load --input datagen-docker-image-v1.0.0.tar
```


## Without a Docker registry

Finally, run datagen docker with following command:

```shell
docker run --memory=2g -p 4242:4242 localhost/datagen:v1.0.0 
```

_Note: Use -d parameter to run conatiner as a daemon_


## With a Docker registry

If there is an internal docker registry, easier method is to login to docker registry with following example command:

```shell
docker login ${INTERNAL_DOCKER_REGISTRY}
```

Then push image with following command:

```shell
docker image tag locahost/datagen:v1.0.0 ${INTERNAL_DOCKER_REGISTRY}/datagen:v1.0.0
docker push ${INTERNAL_DOCKER_REGISTRY}/datagen:v1.0.0
```


_Once image is pushed to internal registry, all machines connected to that registry can now pull this image, making it widely available_

Finally, run datagen docker with following command:

```shell
docker run --memory=2g -p 4242:4242 ${INTERNAL_DOCKER_REGISTRY}/datagen:v1.0.0 
```

_Note: Use -d parameter to run conatiner as a daemon_