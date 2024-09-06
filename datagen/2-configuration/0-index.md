---
layout: default
title: Configuration
nav_order: 3
has_children: true
permalink: /configuration
---

# Configuration of Datagen

To let know Datagen how to connect to the various services where data will be generated, it requires some input configuration.

_Note: By default, Datagen will only be able to generate data to local file system_


## Application.properties file

All services are configured in one file called **application.properties**.

_Note: This file can be chanegd when launching application by changing the parameter --spring.config.location=file: in launch.sh_

There is one section foreach type of service where to load data, they can be empty with no risks.

This section deeps dive on each service's configuration (and also general configuration related to Datagen itself), and it lists all configurations available.


