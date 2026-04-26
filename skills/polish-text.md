---
type: skill
id: polish-text
title: Polish Text
description: "Quick action — cleans up spelling, grammar, and clarity in any text"
tags: [Production, Quality]
connections:
  - target: llm-service
    type: runs_on
context_params:
  voice_profile:
    label: "Voice Profile"
    description: "Your writing style — the polished text will match your voice"
    required: false
  polish_intensity:
    label: "Polish Intensity"
    description: "How much to change — Light, Standard, or Heavy"
    default: "Standard"
    required: false
---

## Capability

Takes any text and returns a polished version: spelling corrected, grammar fixed, sentences clarified. Preserves the original meaning and structure.

## When to Use

- Quick panel: select text, hit the hotkey, choose "Polish this"
- Before sending an email, message, or document
- After drafting anything that needs a quick cleanup

## What It Does

- **Light** — spelling and grammar only. Minimal changes.
- **Standard** — spelling, grammar, plus sentence clarity improvements. The default.
- **Heavy** — everything in Standard plus word choice upgrades, tighter phrasing, and redundancy removal.

## Inputs

One text input. No file uploads, no context required.

## Outputs

Polished text, ready to use.
