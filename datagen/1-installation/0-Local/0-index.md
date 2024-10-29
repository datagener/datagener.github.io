---
layout: default
title: Local
parent: Installation
nav_order: 1
has_children: false
permalink: /installation/local
---

## Pre-requisites

To run it locally, **Java 17** must be installed.

If it is not installed, use corresponding command to your OS:

```shell
    yum install java-17-openjdk
    apt get java-17-openjdk
```


## Download the latest version of Datagen

Go to the repository of Datagen mentionned in Introduction > Links and download the tar.gz file named _datagen-standalone-files.tar.gz_:

```shell
wget https://datagen-repo.s3.eu-west-3.amazonaws.com/1.0.0/standalone/datagen-standalone-files.tar.gz 
```

then untar it:

```shell
tar -xvzf datagen-standalone-files.tar.gz
cd datagen_standalone-1.0.0/ 
```

Finally, use the script _launch.sh_, to launch it:

```shell
./launch.sh
```

Now, datagen is accessible on: [https://localhost:4242/](https://localhost:4242/)

Swagger is accessible on: [https://localhost:4242/swagger-ui.html](https://localhost:4242/swagger-ui.html)


## Configuration

All Applicative configurations are set in the file **application-standalone.properties**.

Some configuration, such as port to use, heap memory and configuration file are set in the file **launch.sh** and can be chanegd there.

## Logging

Logging is configured in the file **logback-spring.xml**.
