---
layout: default
title: Models
parent: Data Generation
has_children: true
nav_order: 2
permalink: /data-generation/model
---

# Model

Model is one simple JSON file, describing what type of data should be generated, where and allows to specify some specific options.


## Structure of a model

A model file is composed of 3 sections:

```json
{
  "Fields": [],
  "Table_Names": {},
  "Options": {}
}
```

* **Fields** is an array of all fields (columns) you want to generate with their type etc...
* **Table_Names** is a list of keys/values to define where data should be generated
* **Options** is a list of keys/values to define some specific properties (such as replication factor, buffer, keys etc..) 


Following sections will deep dive into each section.
