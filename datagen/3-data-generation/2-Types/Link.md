---
layout: default
title: Link
parent: Types
grand_parent: Usage
has_children: false
nav_order: 1
---

# Link

A Link is a special field that is getting its value from other fields' linked field.

Its current use is in City and CSV field.
For City, LINK is getting a value from latitude, longitude or country of a city.
For CSV, from any other fields defined in the CSV read.


## Parameters

There is on requrie parameter:

- **Link**: The link to get value from in format: `$city_or_csv_col_name.col_name_to_get_value_from`


Example:

  `$city_col.lat` will give the latitude of a city picked by another column named `city_col`.

  `$csv_col.a_nice_col` will give the value of the column `a_nice_col` from the CSV file referenced in column `csv_col`.

For City, links are: `lat`, `long`, `country`.

For CSV, links are other columns present in the CSV file.

