---
layout: default
title: Incremental Long
parent: Types
grand_parent: Usage - API
has_children: false
nav_order: 1
---

# Incremental Long

A Long that is incrementing for each row (leading to unique value foreach row).

## Parameters

Possible parameters for this type are:

- **min**: starting value for the increment.
- **ghost**: To compute this field but does not output it. (This is useful foor generating more complex fields using one or multiple ghost fields)


## Examples

An increment long:

```json
    {
      "name": "increment",
      "type": "INCREMENT_LONG"
    }
```

An increment integer starting at 1000:

```json
    {
      "name": "increment_at_thousand",
      "type": "INCREMENT_LONG",
      "min": 1000
    }
```

