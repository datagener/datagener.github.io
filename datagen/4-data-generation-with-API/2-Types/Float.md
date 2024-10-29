---
layout: default
title: Float
parent: Types
grand_parent: Usage - API
has_children: false
nav_order: 1
---

# Float

A Float. 

## Parameters

Possible parameters for this type are:

- **min**: Minimum value
- **max**: Maximum value
- **possible_values**: an array of possible values
- **possible_values_weighted**: a key - value with float as possible keys and values being a number representing probability.
- **ghost**: To compute this field but does not output it. (This is useful foor generating more complex fields using one or multiple ghost fields)

*Note: It is not possible to combine min & max with possible_values or possible_values_weighted. It is also not possible to combine possible_values & possible_values_weighted.*

## Examples

A float:

```json
    {
      "name": "progression",
      "type": "FLOAT"
    }
```

## Conditionals: Special Case

Conditionals is an object that allows you to define fields that are depending from others.

Formula, is a formula to evaluate where _${field_name}_ are replaced with their values, for example:

```json
{
  "name": "starting_hour",
  "type": "INTEGER",
  "min": 0,
  "max": 16
},
{
  "name": "finished_hour",
  "type": "FLOAT",
  "conditionals": {
    "formula": "$starting_hour + 8"
  }
}
```

__ A formula is evaluated using a java script evaluator (inside an Engine Manager of Java), hence it can have complex compute and even if else statements__