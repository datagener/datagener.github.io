---
layout: default
title: Birthdate
parent: Types
grand_parent: Data Generation
has_children: false
nav_order: 1
---

# Birthdate

It is a date in format DD/MM/YYYY, by default between 01/01/1910 & 01/01/2024.


## Parameters

Possible parameters for this type are:

- **min**: in DD/MM/YYYY to specify a minimum date
- **max**: in DD/MM/YYYY to specify a maximum date
- **possible_values** : an array of possible dates in format DD/MM/YYYY
- **ghost**: To compute this field but does not output it. (This is useful foor generating more complex fields using one or multiple ghost fields)


## Examples

A date between 1st February 2010 & 5th september 2016:

```json
    {
      "name": "birthdate",
      "type": "BIRTHDATE",
      "min": "1/2/2010",
      "max": "02/09/2016"
    },
```

A date among the three ones proposed:

```json
    {
      "name": "special_date",
      "type": "BIRTHDATE",
      "possible_values": ["02/08/2005", "06/07/2012", "16/11/1982"]
    },
```
