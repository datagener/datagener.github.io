---
layout: default
title: Types
parent: Usage
has_children: true
nav_order: 3
permalink: /usage/types
---

# Types

This section describes all existing types for columns and details their configuration.

## Generalities

- Every configuration has a detailed documentation by clicking on `Info` button on the right
- Save a model when not sure and run tests to make sure output conforms to what is expected
- All types (except some specific ones) have default configuration that makes them work out of the box.

## General Configuration across multiple types:

### Ghost

By default, all types have a common configuration: `ghost` which is true or false.

This is to determine whether or not this column should be outputed to the final dataset while it is still computed.

_This is useful for such cases where some other columns will depend on its output._

### Possible Values

Some types will propose to configure their values as "possible values".

It means that value for this column will be one of these values (and only one of these).

Probability of this value to occur will be its "weight" (defined as 1 by default) divided by the sum of all weights.


### Compute

Some types will propoose to configure their values as "Compute".

It means that its value is determined by a compute from other columns.

It is using a JS evaluator, hence letting to use any kind of operators to compute a formula, or to even use coding function like if, for etc...

Other columns are referenced using a ${}.

Examples:

        '(${hour} +6)/24'

        'if( ${test} > 15) { true } else { false }'

### Injection

Instead of generating random value, value is generated using other column values, by making an injection of theses values inside this column.

Other columns are referenced using a ${}.

Example:

        ${name}@${company}.com 

will generate (depending on values of columns 'name' & 'company' previous ly defined.)

        'francois@cloudera.com'
        'michael@company.com' 
