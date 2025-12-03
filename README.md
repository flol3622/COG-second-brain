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

## Sync & Backup
- **Obsidian**: Open the repo folder as a vault for browsing.
- **Git**: Commit to your own remote for history.
- **Cloud sync**: iCloud/Dropbox/Drive all work because everything is plain Markdown.

## Contributing
Improvements to skills, templates, and docs are welcome. See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

## License
MIT. Build on it freely.
