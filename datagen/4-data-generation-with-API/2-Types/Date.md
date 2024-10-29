---
layout: default
title: Date
parent: Types
grand_parent: Usage - API
has_children: false
nav_order: 1
---

# Date

A Date.

Specification for format is here: [https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html)

## Parameters

Possible parameters for this type are:

- **use_now**: true or false to use date of data generation
- **possible_values**: an array of date in java specific format YYYY-MM-dd HH:mm:ss
- **min**: Minimum date in format YYYY-MM-dd HH:mm:ss
- **max** : Maximum date in format YYYY-MM-dd HH:mm:ss
- **ghost**: To compute this field but does not output it. (This is useful foor generating more complex fields using one or multiple ghost fields)


## Examples

A date now:

```json
    {
      "name": "date_now",
      "type": "DATE",
      "use_now": true
    }
```

A date between 1st February 2022 at 10 AM 15 minutes and 30 seconds and 31st March 2022 at 11 PM 5 minutes and 4 seconds:
```json
    {
      "name": "date_now",
      "type": "DATE",
      "min": "2022-02-01 10:15:30",
      "max": "2022-03-31 23:05:04"   
    }
```

