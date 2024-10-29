---
layout: default
title: CSV
parent: Types
grand_parent: Usage
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
- **filters**: filters on the CSV to only filter results based on equalities of colums from the CSV and value provided.

## Use CSV's in other fields

If a column is of type CSV, and its name is `my_csv`, one can use another column as LINK type and get:

- Any other column of the CSV: `$my_csv.any_other_col`