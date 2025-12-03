---
name: daily-brief
description: Generate a 7-day-fresh intelligence brief tied to the user's interests and watchlist.
entrypoint: codex
version: 2.0
---

# Purpose
Deliver an actionable morning brief using the user's interests, preferred sources, and competitive watchlist.

# Invocation Signals
- User asks for "daily brief", "morning update", or "news"
- Scheduled morning routine

# Guardrails
- Only include stories with sources and publication dates within the last 7 days.
- Keep to 5-7 items max; prioritize by impact and user interests.
- If no sources available, state that clearly instead of fabricating.

# Steps
1. **Load profile**: read `00-inbox/MY-INTERESTS.md` and optional `03-professional/COMPETITIVE-WATCHLIST.md`.
2. **Collect quick preferences**: ask for today's focus area and time budget (short/standard/deep).
3. **Assemble brief** using `06-templates/daily-brief-template.md`.
4. **Citations**: include explicit sources with date for every story.
5. **Save** to `01-daily/briefs/YYYY-MM-DD-brief.md`.
6. **Summarize**: list top 3 actions and any files updated.
