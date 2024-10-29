---
layout: default
title: Hash MD5
parent: Types
grand_parent: Usage - API
has_children: false
nav_order: 1
---

# Hash MD5

A hash value.

It is generating an alpha numeric random value of defined size and then hashing it.

## Parameters

Possible parameters for this type are:

- **length** : number of characters to hash.
- **possible_values** : an array of possible values as bytes  
- **ghost**: To compute this field but does not output it. (This is useful foor generating more complex fields using one or multiple ghost fields)


## Examples

A hash of 20 characters hashed:

```json
    {
      "name": "restrictedHash",
      "type": "HASHMD5"
    }
```

A hash of 16 characters hashed:

```json
    {
      "name": "restrictedHash",
      "type": "HASHMD5",
      "length" : 16
    }
```

