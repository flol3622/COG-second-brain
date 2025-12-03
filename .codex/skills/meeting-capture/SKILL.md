---
name: meeting-capture
description: Turn meeting audio/transcripts into structured notes, decisions, and routed tasks.
entrypoint: codex
version: 2.1
---

# Purpose
Give you clean, action-ready meeting notes from raw audio/transcripts, with automatic task routing and project filing.

# Invocation Signals
- User says "log this meeting", "summarize the call", or provides a meeting transcript/audio
- New meeting needs summary, decisions, and todos

# Guardrails
- Always capture title, date/time, attendees, and project/customer name before writing.
- Keep decisions and actions separate; include owners and due dates when mentioned.
- Route todos to `03-professional/WORK-TODO.md` and relevant project task lists. Never drop tasks.
- Use `06-templates/meeting-template.md` as the single layout.

# Steps
1. **Collect metadata**
   - Ask for: meeting title, date, attendees, project/customer, and whether transcript is final.
2. **Ingest content**
   - If only audio is given, request transcript text.
   - Parse for agenda points, outcomes, risks, and follow-ups.
3. **Generate note** using `06-templates/meeting-template.md`.
   - Fill summary, agenda highlights, decisions, actions, risks, and filing fields.
4. **File location**
   - Default: `03-professional/meetings/<date>-<slug>.md`.
   - If a project exists, prefer `04-projects/<slug>/notes/meetings/<date>-<slug>.md` (create folder if missing).
5. **Task routing**
   - Update `03-professional/WORK-TODO.md` with action items (owners/due dates).
   - If actions belong to a project, also update/create `04-projects/<slug>/notes/PROJECT-TODO.md` (using todo template).
6. **Summarize back**
   - Report file path, count of actions, and any blockers.
   - Suggest follow-up skills (e.g., `daily-recap` or `knowledge-consolidation`).

# Outputs
- Structured meeting note saved under professional or project meetings.
- Updated work/project todo lists with meeting-derived tasks.
- Links back to related briefs, watchlist items, or knowledge pages when mentioned.
