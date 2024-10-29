---
layout: default
title: String Regex
parent: Types
grand_parent: Usage
has_children: false
nav_order: 1
---

# String Regex

A string whose creation is driven by a regex.

## Parameters

Possible parameters for this type are:

- **Regex**: The regex to apply to generate data. See below section for details.


### Regex Specification

All characters are accepted and will be printed out, to insert a regex, it must be between [], and followed with a number between {} to determine the repetition of this expression.

Inside the [], all values are accepted (including special characters), and must be separated by a ','.

Example:

`[B, dba, %, zz]` will output either: __B__ or __dba__ or __%__ or __zz__.

To make a range, 3 types of range are available: A-Z for upper, a-z for lower and 0-9 for numbers.

Example:

`[A-Z]` will output an uppercase case letter between A & Z (included).
`[b-g]` will output a lowercase case letter between b & g (included).
`[1-6]` will output a number between 1 & 6 (included).

*Note: special characters `[` and `]` cannot be used inside [] to specify a potential value*


## Examples

Regex: `[A-G]{1}-[b-l]{2}-[3-7]{4}` outputs:

      C-lh-6466
      D-id-6734
      E-fb-3333


Regex: `[A-G]{4}-[b-l]{1}-[3-7]{2}_[A,1,Z,%]{1}-text-not interpreted here` outputs:

      EDBA-l-45_A-text-not interpreted here
      GADB-d-55_A-text-not interpreted here
      BFDE-b-74_1-text-not interpreted here


Regex: `[A-G,I-V]{4}--[1-4,6-8]{4}-[\,@,?,0-5]{1}` outputs:

      CFCR--8721-\
      LMLI--7843-?
      LOMT--7488-4
      GKJJ--7774-@