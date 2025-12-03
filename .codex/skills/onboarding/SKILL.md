---
name: onboarding
description: Stand up a Codex-native COG vault, collect preferences, and seed project scaffolds.
entrypoint: codex
version: 2.0
---

# Purpose
Create a clean COG workspace for Codex CLI by gathering essentials (identity, interests, projects) and generating the starting files from templates. Keep everything editable as Markdown.

# Invocation Signals
- User says "onboarding", "set up COG", or "reset workspace"
- No `00-inbox/MY-PROFILE.md` exists
- User asks to add/update projects or interests

# Guardrails
- Never overwrite existing files without confirmation; append or create new versions with suffix `-v2` when unsure.
- Keep questions minimal (name, role, 3-5 interests, news sources, optional projects/watchlist).
- Always use templates from `06-templates/` when creating files.

# Steps
1. **Workspace scan**
   - Ensure base folders exist: `00-inbox`, `01-daily/{briefs,checkins}`, `02-personal/braindumps`, `03-professional/braindumps`, `04-projects`, `05-knowledge/{consolidated,patterns,timeline}`, `06-templates`.
   - If missing, create them.

2. **Collect profile**
   - Ask for: preferred name, role, top 3-5 interests, preferred news sources.
   - Optional: active project list (names only) and competitors/people to watch.

3. **Generate core files** using templates as starting point:
   - `00-inbox/MY-PROFILE.md`: include name, role, date, and project links (if any).
   - `00-inbox/MY-INTERESTS.md`: include interests and preferred sources.
   - `03-professional/COMPETITIVE-WATCHLIST.md` only if watchlist provided.

4. **Project scaffolds** (if projects given)
   - For each project name, slugify to `project-slug`.
   - Create folder `04-projects/<project-slug>/notes/` and drop `PROJECT-OVERVIEW.md` seeded from `06-templates/project-overview-template.md`.

5. **Confirm and summarize**
   - List created files with paths.
   - Remind user they can edit Markdown directly or rerun onboarding.

# Outputs
- Updated Markdown files in `00-inbox`, optional `03-professional`, and per-project folders.
- Clear summary of created/updated files with next recommended skill (usually `braindump`).
