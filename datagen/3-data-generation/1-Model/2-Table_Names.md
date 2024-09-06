---
layout: default
title: Table Names
parent: Models
grand_parent: Data Generation
has_children: false
nav_order: 2
---

# Table Names

In this array, a list of keys must be specified to precise where data should be generated.

## ADLS 

- **ADLS_CONTAINER** : 
- **ADLS_DIRECTORY** : 
- **ADLS_FILE_NAME** : 
- **ADLS_LOCAL_FILE_PATH** : 

## GCS

- **GCS_BUCKET** : 
- **GCS_DIRECTORY** : 
- **GCS_OBJECT_NAME** : 
- **GCS_LOCAL_FILE_PATH** : 


## HDFS

- **HDFS_FILE_PATH** : Directory where files will be generated
- **HDFS_FILE_NAME** : Suffix for files generated 

Full file path + name will be: HDFS_FILE_PATHHDFS_FILE_NAME-XXXXXXXXXX.extension ; where XXXXXXXXXX a 10-digit number representing order of the file generated and extension depends on file type (.json, .csv, .orc, .parquet, .avro).


## HBase

- **HBASE_TABLE_NAME** :
- **HBASE_NAMESPACE** : 


## HIVE

- **HIVE_DATABASE** :
- **HIVE_TABLE_NAME** :

- **HIVE_HDFS_FILE_PATH** :
- **HIVE_TEMPORARY_TABLE_NAME** :

## KAFKA

- **KAFKA_TOPIC** :

## OZONE

- **OZONE_VOLUME** :
- **OZONE_BUCKET** :
- **OZONE_KEY_NAME** :
- **OZONE_LOCAL_FILE_PATH** :

## SOLR

- **SOLR_COLLECTION** ;

## KUDU

- **KUDU_TABLE_NAME** :

## LOCAL

- **LOCAL_FILE_PATH** :
- **LOCAL_FILE_NAME** :

## S3

- **S3_BUCKET** : 
- **S3_DIRECTORY** : 
- **S3_KEY_NAME** : 
- **S3_LOCAL_FILE_PATH** : 

## Optional: Specific for Avro format

- **AVRO_NAME** :

# Example

Below a Full example with all possibilities that can be passed:

```json
  "Table_Names": {
    "HDFS_FILE_PATH": "/user/datagen/hdfs/full/",
    "HDFS_FILE_NAME": "full",

    "HBASE_TABLE_NAME": "full",
    "HBASE_NAMESPACE": "datagen",

    "KAFKA_TOPIC": "datagen_full",

    "OZONE_VOLUME": "datagen",
    "OZONE_BUCKET":  "full",
    "OZONE_KEY_NAME":  "full",
    "OZONE_LOCAL_FILE_PATH":  "/tmp/datagen/temp/full/",

    "SOLR_COLLECTION": "datagen_full",

    "HIVE_DATABASE": "datagen",
    "HIVE_TABLE_NAME":  "full",
    "HIVE_TEMPORARY_TABLE_NAME":  "full_tmp",
    "HIVE_HDFS_FILE_PATH": "/user/datagen/hive/full/",

    "KUDU_TABLE_NAME":  "datagen.full",

    "LOCAL_FILE_PATH":  "/tmp/datagen/full/",
    "LOCAL_FILE_NAME":  "datagen-full",

    "S3_BUCKET": "datagen-test-fri",
    "S3_DIRECTORY": "datagen/full",
    "S3_KEY_NAME": "full-key",
    "S3_LOCAL_FILE_PATH":  "/tmp/datagen/temp/full/",

    "ADLS_CONTAINER": "dgtest",
    "ADLS_DIRECTORY": "datagen/full",
    "ADLS_FILE_NAME": "full",
    "ADLS_LOCAL_FILE_PATH": "/tmp/datagen/temp/full/",

    "GCS_BUCKET": "datagenfri",
    "GCS_DIRECTORY": "datagen/full",
    "GCS_OBJECT_NAME": "full",
    "GCS_LOCAL_FILE_PATH": "/tmp/datagen/temp/full/",

    "AVRO_NAME":  "datagenfull"
  },
```