---
layout: default
title: Open AI
parent: AI Models
grand_parent: Configuration
has_children: false
nav_order: 1
---

# Open AI

Following configurations are required to interact with OpenAI:

-  **spring.ai.openai.api-key**=test : API Key name (can be let as test with no issues)
-  **openai.api.key**= : API KEY from OpenAI
-  **openai.temperature.default**=2.0 : Temperature for the model
-  **openai.model.default**=gpt-4o : model to use
-  **openai.frequency_penalty.default**=2.0 : frequency penalty for the model
-  **openai.presence_penalty.default**=2.0 : presence penalty for the model
-  **openai.max_tokens.default**=256 : max tokens for the model
-  **openai.top_p.default**=1.0 :  top P for the model
