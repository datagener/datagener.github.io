---
layout: default
title: Ollama
parent: Types
grand_parent: Usage
has_children: false
nav_order: 1
---

# Ollama

It is a way to interact with LLM by using a model running with Ollama.


## Parameters 

It has one mandatory parameter:

- **Request**: Fill-in with any text that will be sent to the LLM model ti generate data. It can include references to other field using `${other_col_name}`.

It has multiple configurable parameters:

- **URL**: URL to the Ollama running (default to the one set in configuration)
- **Model**
- **Context**
- **Temperature**
- **Frequency Penalty**
- **Presence Penalty**
- **Top P**

