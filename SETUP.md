# Setup

Follow this once to get a Codex-ready COG vault tuned for transcripts.

## Requirements
- [Codex CLI](https://platform.openai.com/) (required)
- [Obsidian](https://obsidian.md/) (optional but recommended)
- Git (optional for backup/versioning)

## Install
1. Clone the repo where you want the vault:
   ```bash
   git clone https://github.com/huytieu/COG-second-brain.git
   cd COG-second-brain
   ```
2. Open the folder in Codex CLI and say **"Start COG onboarding"**.
3. Answer the short questions (name, role, interests, sources, optional projects/watchlist).

Onboarding will create the folder structure, seed todo lists, and drop starter files using the templates.

## Daily Use
- **Nightly recap:** "Run daily recap" → paste transcript → saves to `01-daily/logs/` and updates todo lists.
- **Meetings:** "Log this meeting" → paste transcript → saves to `03-professional/meetings/` or project folders and routes tasks.
- **Capture:** "Run braindump" → saves to personal/professional/project folders.
- **Morning:** "Give me my daily brief" → writes to `01-daily/briefs/` with 7-day sources.
- **Weekly:** "Do my weekly check-in" → writes to `01-daily/checkins/`.
- **Monthly:** "Consolidate knowledge" → writes to `05-knowledge/consolidated/`.

## Obsidian (optional)
- Open the repo as a vault for browsing and linking.
- Enable file watching if you edit from multiple devices.

## Sync & Backup
- **Git**: `git add . && git commit -m "update"` for history.
- **Cloud**: iCloud/Dropbox/Drive all work because everything is Markdown.

## Troubleshooting
- Skill not found: verify `.codex/skills/` exists and you're in repo root.
- Files in wrong place: rerun onboarding to recreate missing folders.
- Brief has no sources: stories older than 7 days are intentionally excluded.
- Tasks missing: ensure owners/due dates are spoken; Codex routes checkboxes into todo lists.
