---
layout: default
title: Date With Pattern
parent: Types
grand_parent: Usage - API
has_children: false
nav_order: 1
---

# Date With a Pattern

A date that will be pushed as a string to the different connectors and not as a date format (contrary to Date type).

Especially, this date could be in any format as user specify the pattern how date should be created.

For specifications on all possibilities, see documentation: [https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html).



## Parameters

Possible parameters for this type are:

- **pattern**: The pattern specifying how date will be outputed. If not set, it defaults to pattern YYYY-MM-dd HH:mm:ss.

- **use_now**: true or false to use date of data generation
- **possible_values**: an array of date in format specify by the pattern.
- **min**: Minimum date in format specify by the pattern
- **max** : Maximum date in format specify by the pattern
- **ghost**: To compute this field but does not output it. (This is useful foor generating more complex fields using one or multiple ghost fields)


## Examples

A date now, that will be outputed in specified format:

```json
    {
      "name": "date_now",
      "type": "DATE_AS_STRING",
      "use_now": true,
      "pattern": "HH:mm:ss - yyyy/MM/dd"
    }
```

A date using a strange pattern between two dates that must be specified using this pattern:
```json
    {
      "name": "date_now",
      "type": "DATE_AS_STRING",
      "pattern": "yyyy_MM_dd-K a mm:ss.SSS ZZZ",
      "min": "2024_02_14-7 am 31:53.000 +0000",
      "max": "2024_03_14-7 pm 31:53.050 +0330" 
    }
```

