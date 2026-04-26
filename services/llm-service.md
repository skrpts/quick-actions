---
type: service
id: llm-service
title: LLM Service
description: "Language model service for quick text processing tasks"
tags: [Production, Tested]
connections: []
metadata:
  serviceType: llm
  auth_type: api_key
---

## LLM Service

This skrpt uses a language model for quick, single-step text processing. Each action takes one input, runs a single LLM call, and returns the result immediately.

### Configuration

- **Temperature:** 0.3 for polish and explain, 0.5 for summarise and reply
- **Max tokens:** 2,000 per action (these are lightweight by design)

### Requirements

- A configured LLM provider in skrptiq settings
- No external network access required beyond your AI provider's endpoint
