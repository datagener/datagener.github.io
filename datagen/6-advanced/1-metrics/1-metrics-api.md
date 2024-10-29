---
layout: default
title: Metrics API
nav_order: 1
has_children: false
parent: Metrics
grand_parent: Advanced
---

# Metrics API

An API: _/metrics/all_ allows you to get all current metrics about data generation:

- The total number of rows generated
- the total number of generation made

Foreach service:
- The number of rows generated
- The number of files generated (only for Ozone, HDFS & local)

This API call renders a raw JSON file with all metrics in base path and with values as numeric (no null, default is 0).

A GET Endpoint located at _/metrics/all_ retrieved all metrics from the server and return it as a simple JSON:

```json
{ 
"HDFS_JSON_ROWS_GENERATED" : 0,
"OZONE_ORC_ROWS_GENERATED" : 0,
"HDFS_AVRO_ROWS_GENERATED" : 0,
"OZONE_JSON_FILES_GENERATED" : 0,
"OZONE_AVRO_ROWS_GENERATED" : 0,
"PARQUET_FILES_GENERATED" : 0,
"JSON_FILES_GENERATED" : 0,
"HDFS_CSV_ROWS_GENERATED" : 0,
"OZONE_CSV_FILES_GENERATED" : 0,
"KUDU_ROWS_GENERATED" : 0,
"OZONE_JSON_ROWS_GENERATED" : 0,
"OZONE_PARQUET_FILES_GENERATED" : 0,
"OZONE_CSV_ROWS_GENERATED" : 0,
"KAFKA_ROWS_GENERATED" : 0,
"OZONE_ORC_FILES_GENERATED" : 0,
"HDFS_PARQUET_ROWS_GENERATED" : 0,
"PARQUET_ROWS_GENERATED" : 0,
"HDFS_ORC_FILES_GENERATED" : 0,
"SOLR_ROWS_GENERATED" : 1000000,
"AVRO_FILES_GENERATED" : 0,
"CSV_ROWS_GENERATED" : 22,
"JSON_ROWS_GENERATED" : 0,
"ORC_ROWS_GENERATED" : 0,
"HBASE_ROWS_GENERATED" : 0,
"OZONE_AVRO_FILES_GENERATED" : 0,
"HDFS_PARQUET_FILES_GENERATED" : 0,
"HDFS_AVRO_FILES_GENERATED" : 0,
"OZONE_PARQUET_ROWS_GENERATED" : 0,
"HIVE_ROWS_GENERATED" : 100000,
"ALL_ROWS_GENERATED" : 1100022,
"AVRO_ROWS_GENERATED" : 0,
"CSV_FILES_GENERATED" : 21,
"HDFS_CSV_FILES_GENERATED" : 0,
"GENERATIONS_MADE" : 4,
"HDFS_ORC_ROWS_GENERATED" : 0,
"HDFS_JSON_FILES_GENERATED" : 0,
"ORC_FILES_GENERATED" : 0
}
```