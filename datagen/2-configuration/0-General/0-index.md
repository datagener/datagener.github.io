---
layout: default
title: General Configuration
parent: Configuration
has_children: true
nav_order: 1
permalink: /configuration/general
---

# General Configurations

General Configurations and their default value:

- **server.port**=4242 : Port where web server will start. 
- **app.name**=Data Generator : Name of the application
- **generation.threads.default**=4 : Default number of threads when generating data
- **generation.batches.default**=20 : Default number of batches when generating data
- **generation.rows.default**=20 : Default number of rows when generating data

# Files

Configurations related to files and directories used by Datagen:

- **datagen.home.directory**=/tmp/datagen : home directory for datagen
- **datagen.model.path**=src/main/resources/test-models/ : path where based models are stored
- **datagen.model.received.path**=#{datagen.home.directory}/models-received : path where models received are stored
- **datagen.model.generated.path**=#{datagen.home.directory}/models-generated : path where models generated are stored
- **datagen.model.default**=full-model.json : default model used for generation
- **datagen.scheduler.file.path**=#{datagen.home.directory}/scheduler/commands.txt : file containing scheduled commands
