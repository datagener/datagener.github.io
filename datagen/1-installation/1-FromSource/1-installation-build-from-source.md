---
layout: default
title: Local from source code
parent: From Source
grand_parent: Installation
nav_order: 1
---

# Installation from source code

It is possible also for development, test purposes to create and deploy the Datagen service from the code.

## Setup the project

First, clone the Git project located here: [https://github.com/frischHWC/datagen](https://github.com/frischHWC/datagen) 

Then create your own branch: 

```shell
git clone https://github.com/frischHWC/datagen
cd datagen
git checkout -b my-branch
```

You can then develop, change the code, the configuration etc... and deploy this local version to any cluster.

You must just push your changes to your git branch.

It is advises that you have your own git repository be either doing a fork directly on github or adding an internal repository.


## Run locally

Before pushing the new code to Cloudera Manager, you can run and test locally.

It is mandatory when running locally to create file **application-test.properties** based on a copy of _application.properties_ with following command:
```shell
    cp src/main/resources/application.properties src/main/resources/application-test.properties
```

This new file can then be changed to configure some services (as it is ignored by git, it is safe to add credentials in it).

You can either: 

* Import the project to your favorite IDE and run it from their (IntelliJ comes with a start command for spring boot java project).
  However, it requires to add these settings in the Configuration of the command in your ide:
  
  _--spring.profiles.active=test_
  _--spring.config.location=file:src/main/resources/application-test.properties_

* Run it using command line provided in the file under _src/main/resources/scripts/launch-locally.sh_
