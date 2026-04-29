---
type: prompt
id: summarise-text-prompt
title: Summarise Text
description: "Condenses any text into a brief summary"
tags: [Production, Quality]
inputs:
  text:
    label: "Text"
    description: "The text to summarise — any length, any format"
    example: "We held the Q2 planning meeting on Friday. Attendees: Sarah (Engineering), Mike (Product), Lisa (Design). Key decisions: 1) Ship the new onboarding flow by June 15th. Sarah to lead. 2) Defer the analytics dashboard to Q3 — not enough design capacity. 3) Hire two frontend developers by end of May. Mike to write the job specs. Open question: should we use the existing component library or build custom? Lisa to prototype both approaches by next Friday."
    required: true
    type: text
connections:
  - target: summarise-text
    type: derived_from
metadata:
  output_format: text
  prompt_type: task
---

## Purpose

Quick-action prompt: takes any text and returns a concise summary.

## Voice Profile

{{step.context.voice_profile}}

If a voice profile is provided above, write the summary in that voice. If not, use clear, direct language.

## Configuration

- **Summary length:** {{step.context.summary_length}}

## Prompt

Summarise the text below. Return only the summary — no preamble, no "here's a summary of".

### Length

- **One Line:** a single sentence capturing the essential point.
- **Brief:** 2–4 sentences covering key points, decisions, and action items.
- **Detailed:** a structured summary with headings: Key Points, Decisions, Action Items, Context.

### Rules

- Use British English throughout
- Extract facts and decisions, not opinions about the text
- If the text contains action items or deadlines, always include them
- If the text is too short to meaningfully summarise, say so

### Input

{{input.text}}
