# COG: Codex-First Second Brain

COG is a Markdown-only second brain tuned for **Codex CLI**. It ships with a clean vault layout, five Codex skills, and opinionated templates so you can capture, brief, reflect, and synthesize without extra tooling.

## Why COG
- **Codex-native**: Skills live in `.codex/skills` with clear entrypoints.
- **Markdown only**: No databases or services—everything is editable text.
- **Opinionated flows**: Braindumps, daily briefs, weekly reflections, and consolidations are templated and repeatable.
- **Portable**: Works with Obsidian, Git, or any editor. Sync via iCloud or your preferred system.

## Quick Start
1. Install [Codex CLI](https://platform.openai.com/) and optional [Obsidian](https://obsidian.md/).
2. Clone the vault:
   ```bash
   git clone https://github.com/huytieu/COG-second-brain.git
   cd COG-second-brain
   ```
3. In Codex CLI, run onboarding: "Start COG onboarding".

Onboarding creates your profile, interests, optional projects, and the base folders. Every file is Markdown you can edit directly.

## Skills
| Skill | What it does | Output |
| --- | --- | --- |
| `onboarding` | Collects name, role, interests, projects; seeds structure and templates. | `00-inbox/MY-PROFILE.md`, project scaffolds |
| `braindump` | Fast capture with routing to personal/professional/projects. | `02-personal/…` / `03-professional/…` / `04-projects/<slug>/notes/…` |
| `daily-brief` | 7-day-fresh news tied to interests and watchlist. | `01-daily/briefs/YYYY-MM-DD-brief.md` |
| `weekly-checkin` | Reflects on the last week, surfaces patterns, plans next steps. | `01-daily/checkins/YYYY-MM-DD-weekly.md` |
| `knowledge-consolidation` | Distills scattered notes into frameworks and cross-links. | `05-knowledge/consolidated/YYYY-MM-DD-synthesis.md` |

See skill logic in `.codex/skills/*/SKILL.md`.

## Vault Layout
```
COG-second-brain/
├── .codex/skills/          # Codex skill definitions
├── 00-inbox/               # Profile & interests
├── 01-daily/
│   ├── briefs/
│   └── checkins/
├── 02-personal/braindumps/
├── 03-professional/braindumps/
├── 04-projects/            # Each project gets /notes/
├── 05-knowledge/
│   ├── consolidated/
│   ├── patterns/
│   └── timeline/
└── 06-templates/           # Markdown templates used by skills
```

## Templates
Reusable Markdown starting points live in `06-templates/`:
- `braindump-template.md`
- `daily-brief-template.md`
- `weekly-checkin-template.md`
- `knowledge-consolidation-template.md`
- `project-overview-template.md`

Skills always write from these templates to keep files consistent.

## Working in Codex CLI
- Run skills by name (e.g., "Run braindump").
- Codex writes files relative to repo root; keep the CLI opened from this folder.
- When Codex offers to overwrite, choose append or version suffix to avoid data loss.

## How to Use (Emoji Walkthrough)
- 🚀 **Kick off onboarding**: Ask Codex, "Start COG onboarding." Codex will prompt for your profile, interests, and projects, then scaffold folders and starter notes.
- 🧠 **Capture fast**: Say "Run braindump" whenever an idea pops up. Codex will ask short questions, then drop the note into the right braindump folder with the braindump template.
- 📰 **Stay briefed**: Run "daily-brief" to get a 7-day-fresh news brief tied to your interests and watchlist. The UX is a Q&A flow that ends by writing a new dated brief in `01-daily/briefs/`.
- 🔁 **Weekly reflection**: Trigger "weekly-checkin" at the end of the week. Codex walks you through wins, blockers, and next actions, then saves a dated weekly note in `01-daily/checkins/`.
- 🔗 **Synthesize knowledge**: Use "knowledge-consolidation" when you have scattered notes. Codex will ask what to merge, summarize the threads, and save a synthesis in `05-knowledge/consolidated/` with cross-link prompts.
- ✍️ **Edit freely**: All outputs are plain Markdown; open them in your editor or Obsidian to tweak formatting, add links, or rearrange sections.

## Sync & Backup
- **Obsidian**: Open the repo folder as a vault for browsing.
- **Git**: Commit to your own remote for history.
- **Cloud sync**: iCloud/Dropbox/Drive all work because everything is plain Markdown.

## Contributing
Improvements to skills, templates, and docs are welcome. See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

## License
MIT. Build on it freely.
