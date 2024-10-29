---
layout: default
title: Ollama
parent: AI Models
grand_parent: Configuration
has_children: false
nav_order: 1
---

# Ollama

Following configurations are required to interact with Ollama:

- **spring.ai.ollama.base-url**=localhost:11434 : Can be let as is with no impact (othersise set it to Ollama HOST:PORT)
- **spring.ai.ollama.chat.enabled**=true : let it as is
- **spring.ai.ollama.chat.options.format**=json : let is as is
- **ollama.model.default**=llama3 : model exposed by Ollama
- **ollama.temperature.default**=1.0 : temperature for the model
- **ollama.frequency_penalty.default**=2.0 : frequency penalty for the model
- **ollama.presence_penalty.default**=2.0 : presence penalty for the model
- **ollama.top_p.default**=2.0 : top p for the model

