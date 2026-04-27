---
type: prompt
id: run-polish
title: Run Polish
description: "Cleans up spelling, grammar, and clarity in any text"
tags: [Production, Quality]
inputs:
  text:
    label: "Text"
    description: "The text to polish"
    example: "Their going to the shops tommorow, but I dont think there going to find what their looking for becuase the store is probaly closed."
    required: true
    type: text
connections:
  - target: polish-text
    type: derived_from
metadata:
  output_format: text
  prompt_type: task
---

## Purpose

Quick-action prompt: takes raw text and returns a polished version.

## Voice Profile

{{step.context.voice_profile}}

If a voice profile is provided above, match the polished text to that voice — vocabulary, sentence patterns, and tone. If not, preserve the original voice and just fix errors.

## Configuration

- **Polish intensity:** {{step.context.polish_intensity}}

## Prompt

Polish the text below. Return only the polished version — no commentary, no changelog, no "here's what I changed".

### Intensity

- **Light:** fix spelling and grammar only. Do not rephrase.
- **Standard:** fix spelling and grammar, plus improve sentence clarity. Simplify convoluted phrasing.
- **Heavy:** everything in Standard, plus tighten word choice, remove redundancy, and improve flow.

### Rules

- Use British English throughout
- Preserve the original meaning and structure
- Do not add content, remove content, or change the argument
- If the text is already clean, return it unchanged

### Input

{{input.text}}
