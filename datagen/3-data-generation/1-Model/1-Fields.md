---
layout: default
title: Fields
parent: Models
grand_parent: Data Generation
has_children: false
nav_order: 1
---

# Fields

Fields is a list of Field object.

A **field** is an object consisting of at least two required parameters:

- **name**: name of the field 
- **type**: Type of the field

Then, multiple optional parameters depending on the type of the field:

- **min**
- **max**
- **length**
- **possible_values**
- **possible_values_weighted**
- **filters**
- **conditionals**

_Note: All field Types and how to use them is described in next section_


## Examples

Few basic examples of field definitions:

```json
{
    "name": "size",
    "type": "INTEGER"
}
```

```json
{
    "name": "bool",
    "type": "BOOLEAN"
}
```

```json
{
    "name": "startDate",
    "type": "TIMESTAMP"
}
```
