---
layout: default
title: Options
parent: Models
grand_parent: Usage - API
has_children: false
nav_order: 4
---

# Options

There are many options available depending on the connector where to generate data and what format used (if this is a file).

Most of them are optionnal (unless specified as mandatory), as they have default values.


## General

- **DELETE_PREVIOUS** : 
- **ONE_FILE_PER_ITERATION** : 


## ADLS 

- **ADLS_MAX_CONCURRENCY** : 
- **ADLS_MAX_UPLOAD_SIZE** : 
- **ADLS_BLOCK_SIZE** : 

## CSV

- **CSV_HEADER** : 


## HDFS

- **HDFS_REPLICATION_FACTOR** : 


## HBase

These are **MANDATORY**: 

- **HBASE_PRIMARY_KEY** :
- **HBASE_COLUMN_FAMILIES_MAPPING** : 


## HIVE

- **HIVE_TABLE_TYPE** :
- **HIVE_TABLE_FORMAT** :

- **HIVE_TABLE_PARTITIONS_COLS** :
- **HIVE_TABLE_BUCKETS_COLS** :
- **HIVE_TABLE_BUCKETS_NUMBER** :

- **HIVE_THREAD_NUMBER** :
- **HIVE_ON_HDFS** :
- **HIVE_TEZ_QUEUE_NAME** :


## KAFKA

This one setting is **MANDATORY**:
- **KAFKA_MSG_KEY** :

- **KAFKA_MESSAGE_TYPE** :
- **KAFKA_REPLICATION_FACTOR** :
- **KAFKA_PARTITIONS_NUMBER** :
- **KAFKA_JAAS_FILE_PATH** :
- **KAFKA_ACKS_CONFIG** :
- **KAFKA_RETRIES_CONFIG** :

## OZONE

- **OZONE_REPLICATION_FACTOR** :


## SOLR

- **SOLR_SHARDS** :
- **SOLR_REPLICAS** :
- **SOLR_JAAS_FILE_PATH** :

## KUDU

These are **MANDATORY**: 
- **KUDU_PRIMARY_KEYS** :
- **KUDU_HASH_KEYS** :
- **KUDU_RANGE_KEYS** :

- **KUDU_REPLICAS** :
- **KUDU_BUCKETS** :
- **KUDU_BUFFER** :
- **KUDU_FLUSH** :


## PARQUET

- **PARQUET_PAGE_SIZE** :
- **PARQUET_ROW_GROUP_SIZE** :
- **PARQUET_DICTIONARY_PAGE_SIZE** :
- **PARQUET_DICTIONARY_ENCODING** :
- **LOCAL_FILE_NAME** :


# Example

Below is a full example with all set:

```json
  "Options": {
    
    "ONE_FILE_PER_ITERATION":  true,
    "DELETE_PREVIOUS":  true,

    "HBASE_PRIMARY_KEY":  "bool,progression",
    "HBASE_COLUMN_FAMILIES_MAPPING": "c:randomName,abbreviation,size,bool,progression,percentage,limitedName,userEmail,department;d:bytesLittleArray,bigSize,startDate,bytesArray,hash,birthdate,name,country,restrictedHash,category;e:longPercent,onePlusOne,onePlusTwo,formula_1,condition_2,recording_time",

    "SOLR_SHARDS":  1,
    "SOLR_REPLICAS":  1,
    "SOLR_JAAS_FILE_PATH":  "/tmp/solr.jaas",

    "KUDU_REPLICAS":  1,
    "KUDU_PRIMARY_KEYS":  "size,category,department",
    "KUDU_HASH_KEYS":  "size,department",
    "KUDU_RANGE_KEYS":  "category",
    "KUDU_BUCKETS":  32,
    "KUDU_BUFFER":  100001,
    "KUDU_FLUSH":  "MANUAL_FLUSH",

    "KAFKA_MSG_KEY": "bigSize",
    "KAFKA_MESSAGE_TYPE":  "json",
    "KAFKA_REPLICATION_FACTOR":  3,
    "KAFKA_PARTITIONS_NUMBER":  3,
    "KAFKA_JAAS_FILE_PATH":  "/tmp/kafka.jaas",
    "KAFKA_ACKS_CONFIG":  "all",
    "KAFKA_RETRIES_CONFIG":  3,

    "HIVE_THREAD_NUMBER":  1,
    "HIVE_TABLE_TYPE":  "EXTERNAL",
    "HIVE_TABLE_FORMAT":  "PARQUET",
    "HIVE_ON_HDFS":  true,
    "HIVE_TEZ_QUEUE_NAME":  "root.default",
    "HIVE_TABLE_PARTITIONS_COLS": "person_department",
    "HIVE_TABLE_BUCKETS_COLS": "city",
    "HIVE_TABLE_BUCKETS_NUMBER": 32,

    "CSV_HEADER":  true,
    
    "PARQUET_PAGE_SIZE":  1048576,
    "PARQUET_ROW_GROUP_SIZE":  134217728,
    "PARQUET_DICTIONARY_PAGE_SIZE":  1048576,
    "PARQUET_DICTIONARY_ENCODING":  true,

    "OZONE_REPLICATION_FACTOR":  3,

    "HDFS_REPLICATION_FACTOR":  3,

    "ADLS_MAX_CONCURRENCY": 4,
    "ADLS_MAX_UPLOAD_SIZE": 16777216,
    "ADLS_BLOCK_SIZE": 8388608
  }
```