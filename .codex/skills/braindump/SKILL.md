---
name: braindump
description: Capture raw thoughts, classify domain, and file structured notes with actions.
entrypoint: codex
version: 2.0
---

# Purpose
Turn unstructured thinking into structured Markdown with minimal user effort while preserving voice.

# Invocation Signals
- User says "braindump", "brain dump", "capture thoughts", or similar
- Fast capture requests during the day

# Guardrails
- Stay concise; no essays. Use headings from the template only.
- Require citations for any external claims added by the model.
- Default domain routing: personal unless clearly professional or tied to a project folder.

# Steps
1. **Collect context** (1-2 quick questions max): What happened? What decision looms? Any people/companies mentioned?
2. **Classify domain**: choose personal, professional, or specific project slug (if referenced or already exists). Ask once if uncertain.
3. **Generate note** using `06-templates/braindump-template.md` and fill AI sections (Observations, Actions, Routing).
4. **Save location**
   - Personal → `02-personal/braindumps/YYYY-MM-DD-brain.md`
   - Professional → `03-professional/braindumps/YYYY-MM-DD-brain.md`
   - Project → `04-projects/<slug>/notes/YYYY-MM-DD-brain.md`
5. **Linking**
   - Cross-link to `00-inbox/MY-PROFILE` and any detected watchlist entities in `03-professional/COMPETITIVE-WATCHLIST`.
6. **Summarize**
   - Echo file path and 3 bullet takeaways.
