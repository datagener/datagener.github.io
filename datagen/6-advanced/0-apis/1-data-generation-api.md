---
layout: default
title: Data Generation
nav_order: 1
has_children: false
parent: APIs
grand_parent: Advanced
---


# Data Generation APIs

All APIs for data generation are in **/datagen** path and ask for a POST.

Each service has its own API endpoint named like: _/datagen/servicename_ (ex: /datagen/hbase).


Two headers are required when interacting with them:

 - Content-Type: multipart/form-data
 - accept: */*

Some parameters are available foreach API call but **All parameters are optional !** and have default values.


## Parameters

All APIs calls for data generation have at least 5 parameters in common:

* **rows** = Number of rows to generate at each batch of data generation
* **batches** = Number of batches to launch (you will end up to have (rows x batches) total rows generated)
* **threads** = To speed up generation, you can multi thread this (by default it is single-threaded), it is recommended to go on 10 threads.
* model by specifiying either:
    * **model_file** = file path on the machine where a model is present (for example /opt/cloudera/parcels/DATAGEN/models/public_service/weather-model.json)
    * **model** = upload directly to the swagger your model file from your computer

There are also 2 other parameters that enables you to schedule a launch:

* **scheduled** = true or false
* **delay_between_executions_seconds** = The interval (in seconds) between two executions



## Example

An example of a curl command:

```shell
curl -X POST "https://ccycloud-1.lisbon.root.hwx.site:4242/datagen/hbase" -H  "accept: */*" -H  "Content-Type: multipart/form-data" -F "batches=1" -F "model_file=@example-model.json;type=application/json" -F "rows=1"
```

Batches and rows parameters are both set to 1 and a file example-model.json is uploaded to be the model.


## Returned data

Once an API call has been made, Datagen parses the model (check for any errors), get configuration (merging default and provided ones), creates a Command Object and queue it for processing.

It returns almost instantly to the user a simple JSON object made of: 

- a UUID of the command created (useful to get later info on the command)
- a string of error: empty if no error, and describing an error if there is one (for example if model file was not parseable because malformed)

Example:
```json
{ "commandUuid": "5c5b0dfb-a1f2-4e95-b76e-750e8d07aa92" , "error": "" }
```

See next section to know how to follow a command.

## Control Data Generation APIs

Once data generation has been launched, another set of APIs are helpful to follow the data generation process.

All APIs for data generation control are in **/command** path and ask for a POST.

### Follow up a command to generate data

To get the status of the command launched and basic information, use endpoint _/command/getCommandStatus_ with parameter the command UUID (received earlier).

Example:

```shell
curl -X POST "https://ccycloud-1.lisbon.root.hwx.site:4242/command/getCommandStatus?commandUuid=5c5b0dfb-a1f2-4e95-b76e-750e8d07aa92" -H  "accept: */*"
```

Answer is the JSON self-describing:

```json
{ "commandUuid": "5c5b0dfb-a1f2-4e95-b76e-750e8d07aa92" , "status": "FINISHED" , "comment": "" , "progress": "100.0" ,  "duration": "3ms" }
```

It is also possible to retrieve all configuration for a command and all related information by hitting: _/command/get_ with _commandUuid_ as a parameter.

Two other endpoints allows to retrieve more commands:

- _/command/getAll_ : No parameters, retrieves all commands (even finished commands)
- _/command/getByStatus_ : One parameter _status=_ that must equals: QUEUED, STARTING, RUNNING, FINISHED, FAILED. It will return all commands matching this status.


