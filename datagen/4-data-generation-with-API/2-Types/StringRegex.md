---
layout: default
title: String Regex
parent: Types
grand_parent: Usage - API
has_children: false
nav_order: 1
---

# String Regex

A string whose creation is driven by a regex.

## Parameters

Possible parameters for this type are:

- **regex**: The regex to apply to generate data. See below section for details.
- **ghost**: To compute this field but does not output it. (This is useful foor generating more complex fields using one or multiple ghost fields)


## Regex Specification

All characters are accepted and will be printed out, to insert a regex, it must be between [], and followed with a number between {} to determine the repetition of this expression.

Inside the [], all values are accepted (including special characters), and must be separated by a ','. +
Example:
[B, dba, %, zz] will output either: __B__ or __dba__ or __%__ or __zz__.

To make a range, 3 types of range are available: A-Z for upper, a-z for lower and 0-9 for numbers. +
Example:
[A-Z] will output an uppercase case letter between A & Z (included).
[b-g] will output a lowercase case letter between b & g (included).
[1-6] will output a number between 1 & 6 (included).

*Note: special characters [, ], {, } can be set but must be escaped to not be interpreted*

## Examples

A string that will be: 1 character between A & G, a '-', 2 characters between b and l, a '-', 4 characters between 3 and 7:

```json
    {
      "name": "one_regex",
      "type": "STRING_REGEX",
      "regex": "[A-G]{1}-[b-l]{2}-[3-7]{4}"
    }
```
Outputs:
A-bb-3457

Few examples:
```json
    {
      "name": "plate",
      "type": "STRING_REGEX",
      "regex": "[A-G]{2}-[0-9]{3}-[A-Z]{2}"
    }
```
Outputs:
EF-305-PK ; FA-839-RT ; AG-589-YR

```json
    {
      "name": "another_regex",
      "type": "STRING_REGEX",
      "regex": "D-[A-V]{1}[1-7]{1}_C"
    }
```
Outputs:
D-F6_C ; D-K1_C ; D-C1_C

A complex ecample
```json
    {
        "name": "complex_regex",
        "type": "STRING_REGEX",
        "regex": "[A-G]{4}-[b-l]{1}-[3-7]{2}_[A,1,Z,%]{1}-text-not interpreted here"
    }
```
Outputs:
CCBE-c-77_Z-text-not interpreted here
GFEB-k-44_%-text-not interpreted here
GACD-b-33_1-text-not interpreted here
EEBD-l-34_A-text-not interpreted here
