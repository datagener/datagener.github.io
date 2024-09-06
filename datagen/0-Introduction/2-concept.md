---
layout: default
title: Concepts
parent: Introduction
nav_order: 2
---

# Concepts


## Run

Datagen is a standalone program coded in **Java 11**, using **SpringBoot** framework.


## Interact

Datagen exposes a set of **APIs** and a Swagger (and soon a webUI) to let a user generates data.


## Where to generate data ? - Connectors 

Datagen has a **rich set of connectors** to generate data directly into various services such as: HDFS, AWS S3, Hive etc...

To generate data in any services, Datagen must be configured to know how to interact with such service and where they are located. 

All connectors are configured in the _application.properties_ configuration file, before starting the program.

_Note: If deployed with CDP, Datagen is automatically configured by CDP_

New connectors can be easily added to the project (see developers section for more details).


## What Data to Generate ? 

### Model

To know what kind of data to generate, Datagen use what is called a model.

A **model** is a **simple JSON file** that:
 - Shapes how the data looks like 
 - Describes in what tables/files/queue it should be generated 
 - Adds specific options to data generated such as primary keys, replication factors etc...

_Details on how to create a model is made under section Data Generation_

### Fields

Inside a Model, to shape how data is generated, a **set of Fields** are defined.

A **Field** is defined simply in **JSON** format inside a model file with few parameters:
- Name
- Type of Data: String, Integer, Name, City, IP etc...
- Filters, Formulas, Conditions, Dependencies to other fields etc... 

_Details on all fields and how to use them, is made under section Data Generation_
