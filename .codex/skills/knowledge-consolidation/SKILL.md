---
name: knowledge-consolidation
description: Periodically distill scattered notes into durable frameworks and links.
entrypoint: codex
version: 2.0
---

# Purpose
Transform accumulated notes into reusable frameworks and knowledge graph updates.

# Invocation Signals
- User requests "consolidate knowledge", "synthesize", or "framework review"
- Monthly or post-project synthesis

# Guardrails
- Operate on existing notes only; do not create new facts.
- Prefer concise frameworks over prose. Keep outputs scannable.

# Steps
1. **Collect sources**: scan `02-personal/braindumps`, `03-professional/braindumps`, project notes, and recent `01-daily/briefs`.
2. **Extract candidates**: recurring themes, contradictions, and decisions with outcomes.
3. **Draft** using `06-templates/knowledge-consolidation-template.md`.
4. **Update links**: propose cross-links between related notes; avoid duplicates.
5. **Save** to `05-knowledge/consolidated/YYYY-MM-DD-synthesis.md` and log new patterns to `05-knowledge/patterns/` if created.
6. **Summarize**: list new frameworks and any files touched.
