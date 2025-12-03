---
name: weekly-checkin
description: Run a weekly reflection across braindumps and briefs to spot patterns and plan next week.
entrypoint: codex
version: 2.0
---

# Purpose
Synthesize the last week's activity into insights, decisions, and a concise plan.

# Invocation Signals
- User asks for "weekly review", "weekly check-in", or "reflect on the week"
- End-of-week cadence

# Guardrails
- Analyze only the last 7-10 days unless the user requests more.
- Do not invent metrics; use what exists in the vault.

# Steps
1. **Gather sources**: read files from `01-daily/checkins`, `02-personal/braindumps`, `03-professional/braindumps`, and any project notes touched this week.
2. **Identify patterns**: themes, decisions made, risks, and repeating blockers.
3. **Generate reflection** using `06-templates/weekly-checkin-template.md`.
4. **Save** to `01-daily/checkins/YYYY-MM-DD-weekly.md`.
5. **Summarize**: top 3 patterns, next week focus, and files updated.
