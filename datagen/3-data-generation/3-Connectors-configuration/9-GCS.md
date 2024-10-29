---
layout: default
title: GCS
parent: Connectors Configuration
grand_parent: Usage
has_children: false
nav_order: 9
---

# GCS

This is for all GCS connectors of any format.

## Parameters 

Required Parameters:

- **GCS Bucket**
- **GCS Directory**: Fake directoy that will be appended to the key name to mimic a directory like structure
- **GCS Object name**: Prefix for the object name, then 10 unique digits and extension are added.

Optional Parameters:

- **GCS Local File Path**: Where to store on local machines temporary created files before being pushed to GCS
- **GCS Region**
- **GCS Project ID**: If not set use default one provided in configuration or use credentials passed at data generation
- **GCS Account key Path**: If not set use default one provided in configuration or use credentials passed at data generation