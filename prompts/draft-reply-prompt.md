---
type: prompt
id: draft-reply-prompt
title: Draft Reply
description: "Drafts a reply to any message or email"
tags: [Production, Quality]
inputs:
  text:
    label: "Message"
    description: "The message you want to reply to"
    example: "Hi, could you send me the latest project timeline? The client is asking for an update by end of day and I need to include your team's milestones. Also, are we still on track for the beta release next Thursday?"
    required: true
    type: text
connections:
  - target: draft-reply
    type: derived_from
metadata:
  output_format: text
  prompt_type: task
---

## Purpose

Quick-action prompt: takes a message and drafts a reply.

## Voice Profile

{{step.context.voice_profile}}

If a voice profile is provided above, write the reply in that voice — matching sentence patterns, vocabulary, and tone. If not, use a clear, professional style.

## Configuration

- **Reply tone:** {{step.context.reply_tone}}

## Prompt

Draft a reply to the message below. Return only the reply — no subject line, no "here's a draft".

### Tone

- **Formal:** professional and structured. "Dear…" / "Kind regards". Suitable for external stakeholders.
- **Friendly:** warm and conversational. First names, contractions, light humour where appropriate. Suitable for colleagues.
- **Neutral:** clear and direct. No particular warmth or formality. The default.

### Rules

- Use British English throughout
- Address all points and questions raised in the original message
- Keep it concise — match the length and formality of the original
- Do not over-apologise or use filler phrases ("I hope this email finds you well")
- If the message requires information you don't have, note what's missing rather than inventing

### Input

{{input.text}}
