---
layout: default
title: Timestamp
parent: Types
grand_parent: Usage - API
has_children: false
nav_order: 1
---

# Timestamp

Timestamp (from 1st January 1970).

It takes by default the time when data is generated.

## Parameters

Possible parameters for this type are:

- **possible_values**: an array of timestamp values.
- **ghost**: To compute this field but does not output it. (This is useful foor generating more complex fields using one or multiple ghost fields)


## Examples

A Timestamp:

```json
    {
      "name": "timestamp_now",
      "type": "TIMESTAMP"
    }
```

