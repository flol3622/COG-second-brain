---
name: daily-recap
description: Ingest an end-of-day audio/transcript, extract highlights, and file a routed log with tasks.
entrypoint: codex
version: 2.1
---

# Purpose
Turn a raw daily audio/transcript into a structured log that separates personal and work signals, routes todos, and cross-links knowledge.

# Invocation Signals
- User says "daily recap", "log my day", or shares an audio/transcript blob
- Intent to capture both personal and professional happenings in one pass

# Guardrails
- Always ask if the input is a transcript or typed summary; prefer transcript to avoid hallucinations.
- Do not lose personal content when routing work items; keep both domains in the log.
- Route todos to `00-inbox/PERSONAL-TODO.md` or `03-professional/WORK-TODO.md` with owners/due dates when available.
- Use `06-templates/daily-recap-template.md` as the only starting structure.

# Steps
1. **Collect**
   - Confirm date, source type (audio transcript vs. notes), and any project names mentioned.
   - If audio, request the transcript text.
2. **Parse & classify**
   - Identify personal vs. professional moments, people, and resources.
   - Detect actions with owners/due dates; map to personal/work/project.
3. **Generate log** using `06-templates/daily-recap-template.md`.
   - Fill summaries, highlights, decisions, risks, actions, and routing fields.
4. **Save**
   - Write to `01-daily/logs/YYYY-MM-DD-log.md`.
   - If project mentioned, append project slug in filename: `01-daily/logs/YYYY-MM-DD-<slug>-log.md`.
5. **Route tasks**
   - Append or update checkboxes in `00-inbox/PERSONAL-TODO.md` and/or `03-professional/WORK-TODO.md`.
   - For projects, also append to `04-projects/<slug>/notes/PROJECT-TODO.md` (create if missing, use todo template).
6. **Summarize**
   - Confirm file paths written and counts of tasks routed per list.
   - Suggest next skill (e.g., `meeting-capture` or `knowledge-consolidation`) if signals exist.

# Outputs
- Dated daily log in `01-daily/logs/` with personal and professional sections.
- Updated todo lists with new actionable items.
- Cross-links to related notes or projects when mentioned.
