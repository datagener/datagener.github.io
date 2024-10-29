---
layout: default
title: Control Data Generation
nav_order: 2
has_children: false
parent: APIs
grand_parent: Advanced
---


# Control Data Generation APIs

Once data generation has been launched, another set of APIs are helpful to follow the data generation process.

All APIs for data generation control are in **/command** path and ask for a POST.

## Follow up a command to generate data

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


