---
layout: default
title: Concepts
parent: Introduction
nav_order: 2
---

# Concepts


## Run

Datagen is a standalone program coded in **Java 17** compiled with **maven 3.6**, using **SpringBoot** & **Vaadin** frameworks.


## Interact

Datagen exposes a **webUI** and a set of **APIs** (with a swagger) to let a user generates data easily.


## Possibilities

Datagen is able to:

- **Push Data** to multiple systems (HDFS, S3, ADLS, GCS, Kafka, Hive, HBase etc...)
- Handle **multiple formats** (Avro, Parquet, ORC, JSON, CSV)
- Generate **structured data** of different types (string, integer, timestamp, uuid etc...)
- Provide **pre-defined data** filterable (countries, 40K+ cities, 35K+ names, phone pattern etc... )
- Make data **respecting rules** (min, max, repartition, pattern, regex etc...)
- Add **relations between data** generated (one column value depends on other's values with possible complex evaluation)
- Generate **unstructured data** leveraging AI (OpenAI, Bedrock, Ollama, and even any model locally embedded)
- **Schedule generation** of data
- **Analyze existing** data to mimic it (currently in alpha version)


## What Data to Generate ? 

### Model

To know what kind of data to generate, Datagen use what is called a **model**.

A **model** is under the hood a **simple JSON file** that:
 - **Shapes** how the data looks like 
 - **Describes** in what _tables/files/queues_ it should be generated 
 - Adds specific options to data generated such as _primary keys, replication factors_ etc...

When using the UI, user interactively creates a model. 

Once model saved, user can use it to generrate data according to its specification.

It can also be downloaded as a JSON file, modified (or not), and imported back (or to any other Datagen application).


### Columns

Inside a Model, to shape how data is generated, a **set of Columns** are defined.

A **Column** is under the hood defined **JSON** format inside a model file with few parameters:
- **Name**
- **Type** of Data: String, Integer, Name, City, IP etc...
- **Conditions** with Filters, Formulas, Conditions, Dependencies to other fields etc... 

When using the UI, user interactively shapes the set of columns for its model.


## Where to generate data ? 

### Connectors 

Datagen has a **rich set of connectors** to generate data directly into various services such as: _HDFS, AWS S3, Hive_ etc...

To generate data in any services, **Datagen must be configured** to know how to interact with such service and where they are located. 

All connectors are configured in the _application.properties_ configuration file, before starting the program.

_Note: If deployed with CDP, Datagen is automatically configured by Cloudera Manager_

However, a **model can hold**  also one or multiple **connector's configuration**, providing information on where to push data.


### Credentials

Datagen uses a concept of **Credentials** where a user can register its credentials (and manage them): _keytab, ADLS sas token, AWS S3 Access Key, GCP application credentials file, keystore_.

They are **safely stored and managed** by Datagen.

Then, these credentials can be used when generating data to **provide a way to authenticate** to the service where it is pushing data to.

Or they can also be **injected in the model** (in a safe way, with a reference to a safely stored file), so model holds also authentication part.


