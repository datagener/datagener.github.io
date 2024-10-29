---
layout: default
title: Link
parent: Types
grand_parent: Usage - API
has_children: false
nav_order: 1
---

# Link

A Link is a special field that is getting its value from other fields' linked field.

Its current use is in City and CSV field.
For City, LINK is getting a value from latitude, longitude or country of a city.
For CSV, from any other fields defined in the CSV read.


## Parameters

Possible parameters for this type are:

- **conditionals**: with a link inside, it defined the link to which other field and what must be taken as a field of that other field.
- **ghost**: To compute this field but does not output it. (This is useful foor generating more complex fields using one or multiple ghost fields)


## Examples

```json
    {
      "name": "person_department",
      "type": "LINK",
      "conditionals": {
        "link": "$person.department"
      }
    }
```    

See these sections: City and CSV for concrete examples.

