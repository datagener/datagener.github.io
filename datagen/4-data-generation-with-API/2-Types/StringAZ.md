---
layout: default
title: String AZ
parent: Types
grand_parent: Usage - API
has_children: false
nav_order: 1
---

# String AZ

A String with only alphabetical characters (in lower and upper case).

## Parameters

Possible parameters for this type are:

- **length**: number of characters to generate (default is 20).
- **possible_values**: an array of possible values as string
- **ghost**: To compute this field but does not output it. (This is useful foor generating more complex fields using one or multiple ghost fields)

*Note: It is not possible to combine length with possible_values.*

## Examples

A String of 3 alpha-numerical characters:

```json
    {
      "name": "abbreviation",
      "type": "STRINGAZ",
      "length": 3
    }
```

