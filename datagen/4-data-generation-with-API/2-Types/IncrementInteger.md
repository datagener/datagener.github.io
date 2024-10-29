---
layout: default
title: Incremental Integer
parent: Types
grand_parent: Usage - API
has_children: false
nav_order: 1
---

# Incremental Integer

An Integer that is incrementing for each row (leading to unique value foreach row).

_Note: increment step is 1_

## Parameters

Possible parameters for this type are:

- **min**: Starting value for the increment.
- **ghost**: To compute this field but does not output it. (This is useful foor generating more complex fields using one or multiple ghost fields)


## Examples

An increment integer:

```json
    {
      "name": "increment",
      "type": "INCREMENT_INTEGER"
    }
```

An increment integer starting at 1000:

```json
    {
      "name": "increment_at_thousand",
      "type": "INCREMENT_INTEGER",
      "min": 1000
    }
```

