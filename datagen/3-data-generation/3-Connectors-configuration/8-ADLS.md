---
layout: default
title: ADLS
parent: Connectors Configuration
grand_parent: Usage
has_children: false
nav_order: 8
---

# ADLS

This is for all ADLS connectors of any format.

## Parameters 

Required Parameters:

- **ADLS Container**
- **ADLS Directory**
- **ADLS File name**: Prefix for the file name, then 10 unique digits and extension are added.

Optional Parameters:

- **ADLS Local File Path**: Where to store on local machines temporary created files before being pushed to ADLS
- **ADLS Block Size**
- **ADLS Max Upload Size**
- **ADLS Max Concurrency**
- **ADLS Account Type**: either dfs or blob depending on container storage
- **ADLS Account Name**: If not set use default one provided in configuration or use credentials passed at data generation
- **ADLS SAS Token**: If not set use default one provided in configuration or use credentials passed at data generation