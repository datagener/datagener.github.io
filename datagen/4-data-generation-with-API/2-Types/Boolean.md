---
layout: default
title: Boolean
parent: Types
grand_parent: Usage - API
has_children: false
nav_order: 1
---

# Boolean

A boolean value: true or false.

## Parameters

Possible parameters for this type are:

- **possible_values_weighted**: a key - value with true/false as possible keys and values being a number representing probability.
- **conditionals**: See section below for more information
- **ghost**: To compute this field but does not output it. (This is useful foor generating more complex fields using one or multiple ghost fields)

## Examples

A boolean:

```json
    {
      "name": "bool",
      "type": "BOOLEAN"
    }
```

A boolean with 70% of true and 30% of false:

```json
    {
      "name": "bool",
      "type": "BOOLEAN",
      "possible_values_weighted": {
        "true": 70,
        "false": 30
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
  "type": "BOOLEAN",
  "conditionals": {
    "formula": "if( $starting_hour > 8 ) then true; else false "
  }
}
```

__ A formula is evaluated using a java script evaluator (inside an Engine Manager of Java), hence it can have complex compute and even if else statements__
