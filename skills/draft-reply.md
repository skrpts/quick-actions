---
type: skill
id: draft-reply
title: Draft Reply
description: "Quick action — drafts a reply to any message or email"
tags: [Production, Quality]
connections:
  - target: llm-service
    type: runs_on
context_params:
  voice_profile:
    label: "Voice Profile"
    description: "Your writing style — the reply will sound like you"
    required: false
  reply_tone:
    label: "Reply Tone"
    description: "Tone of the reply — Formal, Friendly, or Neutral"
    default: "Neutral"
    required: false
---

## Capability

Takes a message (email, Slack message, comment) and drafts a reply in your voice. You review and send — it handles the first draft.

## When to Use

- Quick panel: select a message, choose "Reply to this"
- When you know what you want to say but don't want to write it from scratch
- For routine replies where tone matters but the content is straightforward

## What It Does

1. Reads the original message to understand the context, questions, and tone
2. Drafts a reply that addresses all points raised
3. Matches the configured tone:
   - **Formal** — professional, structured, appropriate for external stakeholders
   - **Friendly** — warm, conversational, appropriate for colleagues and collaborators
   - **Neutral** — clear and direct, no particular warmth or formality. The default.

## Inputs

One text input: the message you're replying to.

## Outputs

Draft reply, ready to review and send.
