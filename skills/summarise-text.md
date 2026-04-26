---
type: skill
id: summarise-text
title: Summarise Text
description: "Quick action — condenses any text into a brief summary"
tags: [Production, Quality]
connections:
  - target: llm-service
    type: runs_on
context_params:
  voice_profile:
    label: "Voice Profile"
    description: "Your writing style — the summary will match your voice"
    required: false
  summary_length:
    label: "Summary Length"
    description: "How concise — One Line, Brief, or Detailed"
    default: "Brief"
    required: false
---

## Capability

Takes any text — email, article, document, chat thread — and returns a concise summary. Extracts key points and decisions, discards filler.

## When to Use

- Quick panel: paste or select text, choose "Summarise this"
- When you need the gist of a long email or document
- Before forwarding content to someone who needs the short version

## What It Does

- **One Line** — a single sentence capturing the essential point
- **Brief** — 2–4 sentences covering key points and any decisions or actions. The default.
- **Detailed** — a structured summary with sections: key points, decisions, action items, context

## Inputs

One text input. Any length — from a paragraph to a full document.

## Outputs

Summary at the configured length.
