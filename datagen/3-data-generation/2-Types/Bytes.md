---
layout: default
title: Bytes
parent: Types
grand_parent: Data Generation
has_children: false
nav_order: 1
---

# Bytes

A random array of bytes of default size of 20 bytes.

## Parameters

Possible parameters for this type are:

- **length**: Number of bytes in this array of bytes.
- **possible_values**: an array of bytes array
- **ghost**: To compute this field but does not output it. (This is useful foor generating more complex fields using one or multiple ghost fields)

## Examples

A bytes array of default 20 bytes:

```json
    {
      "name": "bytesArray",
      "type": "BYTES"
    }
```

A bytes array of 10 bytes:
```json
    {
      "name": "bytesLittleArray",
      "type": "BYTES",
      "length" : 10
    }
```

