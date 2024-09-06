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


## Download the latest version of Datagen

Go to the repository of Datagen mentionned in Introduction > Links and download the tar.gz file named _datagen-standalone-files.tar.gz_:

```shell
wget https://datagen-repo.s3.eu-west-3.amazonaws.com/0.5.1/standalone/datagen-standalone-files.tar.gz 
```

then untar it:

```shell
tar -xvzf datagen-standalone-files.tar.gz
cd datagen_standalone-0.5.1/ 
```

Finally, use the script _launch.sh_, to launch it:

```shell
./launch.sh
```

Now, datagen is accessible on [http://localhost:4242/](http://localhost:4242/) . 


## Configuration

All Applicative configurations are set in the file **application-standalone.properties**.

Some configuration, such as port to use, heap memory and configuration file are set in the file **launch.sh** and can be chanegd there.

## Logging

Logging is configured in the file **logback-spring.xml**.
