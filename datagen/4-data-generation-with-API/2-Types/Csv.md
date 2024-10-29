---
layout: default
title: CSV
parent: Types
grand_parent: Usage - API
has_children: false
nav_order: 1
---

# CSV

It is a special Field that will read a CSV provided by its path, load it into memory, parse it.

It is able to apply filters on this, and you can create other fields derived from this one.


## Parameters

Required parameters for this type are:

- **file**: CSV file location on the remote machine where Datagen runs
- **field**: Field name in the CSV that will be used.

Possible parameters for this type are:

- **separator**: to specify field separator in the CSV (e.g: ,)
- **filters**: on array of filters on the CSV to read in the form of _'field_to_filter_on=value_to_to_keep'_
- **ghost**: To compute this field but does not output it. (This is useful foor generating more complex fields using one or multiple ghost fields)


## Examples

For example, we have this CSV in _/tmp/person_test.csv_ :

```csv
name;department;country
francois;PS;France
kamel;SE;France
thomas;RH;Germany
sebastian;PS;Spain
```

We can create two Fields:

- One will be the name of the person (filtered on the country that should be France)
- The department of this person

```json
{
  "name": "person",
  "type": "CSV",
  "filters": ["country=France"],
  "file": "/tmp/person_test.csv",
  "field": "name"
},
{
  "name": "person_department",
  "type": "LINK",
  "conditionals": {
    "link": "$person.department"
  }
}
```
