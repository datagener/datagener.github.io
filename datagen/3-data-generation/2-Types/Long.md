---
layout: default
title: Long
parent: Types
grand_parent: Data Generation
has_children: false
nav_order: 1
---

# Long

A Long.

## Parameters

Possible parameters for this type are:

- **min**: Minimum value
- **max**: Maximum value
- **possible_values**: an array of possible values as integer
- **possible_values_weighted**: a key - value with long as possible keys and values being a number representing probability.
- **conditionals**: See section below for more information
- **ghost**: To compute this field but does not output it. (This is useful foor generating more complex fields using one or multiple ghost fields)

*Note: It is not possible to combine min & max with possible_values or possible_values_weighted. It is also not possible to combine possible_values & possible_values_weighted.*



## Examples

A Long between 0 & 100:

```json
    {
      "name": "percentage",
      "type": "LONG",
      "min": 0,
      "max": 100
    }
```

A Long that has 70% chance to be 1 and 30% chance to be 5:
```json
    {
      "name": "integer_with_weights",
      "type": "LONG",
      "possible_values_weighted": {
        "1": 70,
        "5": 30
      }
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
  "type": "INTEGER",
  "conditionals": {
    "formula": "$starting_hour + 8"
  }
}
```

__ A formula is evaluated using a java script evaluator (inside an Engine Manager of Java), hence it can have complex compute and even if else statements__
