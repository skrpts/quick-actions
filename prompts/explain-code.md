---
type: prompt
id: run-explain-code
title: Run Explain Code
description: "Explains what a code snippet does in plain language"
tags: [Production, Code]
inputs:
  code:
    label: "Code"
    description: "The code snippet to explain"
    example: "const debounce = (fn, ms) => { let id; return (...args) => { clearTimeout(id); id = setTimeout(() => fn(...args), ms); }; };"
    required: true
    type: text
connections:
  - target: explain-code
    type: derived_from
metadata:
  output_format: text
  prompt_type: task
---

## Purpose

Quick-action prompt: takes a code snippet and explains it in plain language.

## Voice Profile

{{step.context.voice_profile}}

If a voice profile is provided above, match the explanation style. If not, use clear, accessible language.

## Configuration

- **Explanation depth:** {{step.context.explanation_depth}}

## Prompt

Explain the code below. Return only the explanation — no preamble.

### Depth

- **Beginner:** assume the reader has never seen this language. Explain syntax, concepts, and patterns from scratch. Use analogies.
- **Intermediate:** assume working knowledge of the language. Explain what the code does and why, not how the language works.
- **Expert:** assume deep familiarity. Focus on: design decisions, performance characteristics, edge cases, potential bugs, and what you'd change.

### Rules

- Use British English throughout
- Identify the language and framework (if recognisable) at the start
- Walk through the code logically, not necessarily line by line
- If the code has bugs or issues, mention them
- If the code is trivial, keep the explanation short

### Input

{{input.code}}
