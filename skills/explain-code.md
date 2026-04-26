---
type: skill
id: explain-code
title: Explain Code
description: "Quick action — explains what a code snippet does in plain language"
tags: [Production, Code]
connections:
  - target: llm-service
    type: runs_on
context_params:
  voice_profile:
    label: "Voice Profile"
    description: "Your preferred explanation style"
    required: false
  explanation_depth:
    label: "Explanation Depth"
    description: "How detailed — Beginner, Intermediate, or Expert"
    default: "Intermediate"
    required: false
---

## Capability

Takes a code snippet and explains what it does in plain language. Adapts to your experience level — from "what is a variable" to "explain the concurrency model".

## When to Use

- Quick panel: select code, choose "Explain this code"
- When reviewing unfamiliar code in a PR or codebase
- When onboarding to a new project and encountering unfamiliar patterns

## What It Does

1. Identifies the language and framework
2. Explains what the code does, step by step
3. Adapts depth to the configured level:
   - **Beginner** — assumes no familiarity with the language. Explains syntax, concepts, and patterns from first principles.
   - **Intermediate** — assumes working knowledge of the language. Focuses on what the code does, not how the language works. The default.
   - **Expert** — assumes deep familiarity. Focuses on the interesting parts: design decisions, performance implications, edge cases, and potential issues.

## Inputs

One code input: the snippet to explain. Any language.

## Outputs

Plain-language explanation at the configured depth.
