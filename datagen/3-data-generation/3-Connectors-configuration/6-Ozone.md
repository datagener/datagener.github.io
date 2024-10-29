---
layout: default
title: Ozone
parent: Connectors Configuration
grand_parent: Usage
has_children: false
nav_order: 6
---

# Ozone

This is for all Ozone connectors of any format.

## Parameters 

Required Parameters:

- **Ozone Volume**
- **Ozone Bucket**
- **Ozone Key name**: Prefix for the key name (that could contain a directory like structure), then 10 unique digits and extension are added.

Optional Parameters:

- **Ozone Local File Path**: Where to store on local machines temporary created files before being pushed to Ozone
- **Ozone Replication Factor**
