---
layout: default
title: Bedrock
parent: Types
grand_parent: Usage
has_children: false
nav_order: 1
---

# Bedrock

It is a way to interact with LLM deployed in AWS Bedrock.


## Parameters 

It has one mandatory parameter that must be filled:

- **Request**: Fill-in with any text that will be sent to the LLM model ti generate data. It can include references to other field using `${other_col_name}`.

It has multiple configurable parameters:

- **AWS Access Key ID**: (If not set, it will use one defined in configuration file)
- **AWS Access Key Secret**: (If not set, it will use one defined in configuration file)
- **Model**
- **Context**
- **Temperature**
- **Max Tokens**

