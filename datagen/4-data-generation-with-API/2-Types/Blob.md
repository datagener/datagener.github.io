---
layout: default
title: Blob
parent: Types
grand_parent: Usage - API
has_children: false
nav_order: 1
---

# Blob

A binary large object (blob) represented as a random array of bytes of default size 1MB.

## Parameters

Possible parameters for this type are:

- **length**: size of the BLOB in bytes (default is 1 000 000).
- **possible_values**: an array of bytes array
- **ghost**: To compute this field but does not output it. (This is useful foor generating more complex fields using one or multiple ghost fields)


## Examples

Random bytes array of 1MB:

```json
    {
      "name": "blob",
      "type": "BLOB",
      "length" : 10
    },
```

Random bytes array of 1KB:

```json
    {
      "name": "little_blob",
      "type": "BLOB",
      "length" : 10000
    },
```