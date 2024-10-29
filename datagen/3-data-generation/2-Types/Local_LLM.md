---
layout: default
title: Local LLM
parent: Types
grand_parent: Usage
has_children: false
nav_order: 1
---

# Local LLM

It is a way to interact with LLM by letting Datagen instantiate and deploy a local LLM (provided as a gguf file).


## Parameters 

It has two mandatory parameters:

- **Model File Path**: Provide a path to a gguf file (it is standard format for LLM) present locally on the machien or to an http:// adress where it can be downloaded from. 
- **Request**: Fill-in with any text that will be sent to the LLM model ti generate data. It can include references to other field using `${other_col_name}`.

It has multiple configurable parameters:

- **Context**
- **Temperature**
- **Frequency Penalty**
- **Presence Penalty**
- **Top P**

