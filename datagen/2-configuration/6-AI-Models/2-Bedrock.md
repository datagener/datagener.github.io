---
layout: default
title: Bedrock
parent: AI Models
grand_parent: Configuration
has_children: false
nav_order: 1
---

# Bedrock

Following configurations are required to interact with Bedrock:

- **bedrock.region**=us-east-1 : AWS Region
- **bedrock.model.default**=amazon.titan-text-lite-v1 : AWS Model to use
- **bedrock.temperature.default**=1.0 : Temperature to set
- **bedrock.max_tokens.default**=256 : Max Tokens to set
- **bedrock.access_key.id**= : AWS Access Key ID with rights to use bedrock models
- **bedrock.access_key.secret**= : AWS Access Key Secret