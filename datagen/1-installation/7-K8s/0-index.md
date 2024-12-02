---
layout: default
title: Kubernetes
parent: Installation
nav_order: 8
has_children: false
permalink: /installation/kubernetes
---

# Kubernetes

Datagen is provided as a packaged docker image and along with deployment files.
Hence, this docker image can be use to run datagen on any kubernetes environment.

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

## (Optional): Login to docker registry

If there is an internal docker registry, easier method is to login to docker registry with following example command:

```shell
docker login ${INTERNAL_DOCKER_REGISTRY}
```

Then push image with following command:

```shell
docker image tag localhost/datagen:v1.0.0 ${INTERNAL_DOCKER_REGISTRY}/datagen:v1.0.0
docker push ${INTERNAL_DOCKER_REGISTRY}/datagen:v1.0.0
```

_Once image is pushed to internal registry, all machines connected to that registry can now pull this image, making it widely available_


One may need to register the docker registry to the kubernetes cluster:

```shell
kubectl create secret docker-registry my-secret --docker-server=DOCKER_REGISTRY_SERVER --docker-username=DOCKER_USER --docker-password=DOCKER_PASSWORD
```


## Run datagen

In the deployment, identify the part for the service and replace this <YOUR_K8S_DOMAIN> by your kubernetes domain.

Finally, run datagen docker with following commands:

```shell
kubectl create configmap app-properties --from-file=./application-standalone.properties
kubectl create configmap logback-xml --from-file=./logback-spring.xml
kubectl apply -f datagen_deployment.yml
```