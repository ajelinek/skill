---
name: handoff
description: Create, list, and resume handoff documents for session continuity. Manual commands only.
disable-model-invocation: true
---

# Handoff

Manual-only skill for session handoff management. Execute these commands explicitly:

## Commands

### `/handoff create {name}`
Creates a handoff document and saves to `$TEMP/handoff-{name}.md`.
- Summarize session status, decisions, and current work
- Reference artifacts by path/URL (don't duplicate content)
- Note suggested skills and immediate next step
- Redact sensitive data (keys, passwords, PII)

If the user passes additional arguments (e.g., `/handoff create project-x "focus on auth flow"`), treat them as a description of what the next session will focus on and tailor the handoff doc accordingly.

### `/handoff list`
Lists all handoff files in `$TEMP/` matching `handoff-*.md`.
- Shows filename, creation time, and brief summary

### `/handoff resume {name}`
Loads and displays `$TEMP/handoff-{name}.md` to resume work.

## File Convention

Handoffs are stored as: `handoff-{name}.md` in OS temp directory (`/tmp` on Unix, `%TEMP%` on Windows).
