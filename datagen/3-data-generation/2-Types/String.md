---
layout: default
title: String
parent: Types
grand_parent: Data Generation
has_children: false
nav_order: 1
---

# String

A String of alpha-numeric characters with a defined size.


## Parameters

Possible parameters for this type are:

- **length**: Number of characters to generate
- **possible_values**: an array of possible values as string
- **possible_values_weighted**: a key - value with string as possible keys and values being a number representing probability.
- **conditionals**: See section below for more information
- **ghost**: To compute this field but does not output it. (This is useful foor generating more complex fields using one or multiple ghost fields)

*Note: It is not possible to combine length with possible_values or possible_values_weighted.*
*Note: It is also not possible to combine possible_values & possible_values_weighted.*

## Examples

A String of 10 characters:

```json
    {
      "name": "limitedName",
      "type": "STRING",
      "length": 10
    }
```

A String among these possibilities: hr, consulting, marketing, finance

```json
    {
      "name": "department",
      "type": "STRING",
      "possible_values": ["hr", "consulting", "marketing", "finance"]
    }
```

A String among different possibilities with 64% of BRONZE, 16% of SILVER, 9% of GOLD, 11% of PLATINUM:

```json
    {
      "name": "membership",
      "type": "STRING",
      "possible_values_weighted": {
        "BRONZE": 64,
        "SILVER": 16,
        "GOLD": 9,
        "PLATINUM": 11
      }
    }
```

## Conditionals: Special Case

Conditionals is an object that allows you to define fields that are depending from others.


### Formula 

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
  "type": "STRING",
  "conditionals": {
    "formula": "${starting_hour} + 8"
  }
}
```

__ A formula is evaluated using a java script evaluator (inside an Engine Manager of Java), hence it can have complex compute and even if else statements__


### Injection

Injection, is a string where _${field_name}_ are replaced with their values, for example:

```json
{
  "name": "email",
  "type": "STRING",
  "conditionals": {
    "injection": "${name}@company.it"
  }
}
```

### Conditions Line

Conditions Lines are a bunch of lines evaluated one after the other, if one is true, then value is set to right expression.

Each conditional line is composed of conditions in the form of a field name (reported by a $) which is substituted by its value and operators (`<`,`>`,`=`,`!=`) that will check against a defined value or a field (which is also substituted). The condition line can be composed of multiple checks using `&` (AND) or `|` (OR) operators.

An example:

```json
{
  "name": "rain",
  "type": "STRING",
  "conditionals": {
    "$humidity_9_am>70 & $temperature_9_am<20 & $wind_force_9_am<80" : "true",
    "$humidity_9_pm>70 & $temperature_9_pm<20 & $wind_force_9_am<80" : "true",
    "$wind_provenance_9_am=NORTH & $wind_force_9_am>80" : "true",
    "$wind_provenance_9_pm=NORTH & $wind_force_9_pm>80" : "true",
    "$humidity_9_pm>70 & $temperature_9_pm<25 & $pressure_9_pm<1010": "true",
    "$humidity_9_am>70 & $temperature_9_am<25 & $pressure_9_am<1010": "true",
    "default" : "false"
  }
}
```