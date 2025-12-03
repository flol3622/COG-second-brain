# COG: Codex-First Second Brain (Voice- & Transcript-Ready)

COG is a Markdown-only second brain tuned for **Codex CLI**. Drop in an audio transcript from your day or a meeting, and Codex ingests it into structured notes, routes todos, and keeps everything searchable for both you and the model.

## Why COG
- **Built for transcripts**: Daily recaps and meeting captures start from raw audio text and turn into linked notes.
- **Task routing baked in**: Actions automatically flow into personal and work todo lists, plus per-project tasks.
- **Markdown everywhere**: No databases or services—open in Obsidian, git, or any editor.
- **Opinionated flows**: Skills guide onboarding, capture, briefing, reflection, and synthesis.

## What You Can Do
- Send an end-of-day transcript (personal + work) and get a dated log plus routed todos.
- Drop a meeting transcript and receive a clean summary, decisions, and tasks filed to the right lists.
- Capture quick ideas, then consolidate scattered notes into frameworks.
- Keep daily briefs and weekly check-ins alongside your own notes.

## Quick Start
1. Install [Codex CLI](https://platform.openai.com/) and optional [Obsidian](https://obsidian.md/).
2. Clone the vault:
   ```bash
   git clone https://github.com/huytieu/COG-second-brain.git
   cd COG-second-brain
   ```
3. In Codex CLI, run onboarding: **"Start COG onboarding"**.
4. When ready each day, say **"Run daily recap"** and paste your audio transcript.

Onboarding creates your profile, interests, optional projects, todo lists, and base folders. Everything remains editable Markdown.

## Skills
| Skill | What it does | Output |
| --- | --- | --- |
| `onboarding` | Collects name, role, interests, projects; seeds structure and templates. | `00-inbox/MY-PROFILE.md`, project scaffolds |
| `daily-recap` | Ingests end-of-day audio/transcripts, splits personal/work, routes todos. | `01-daily/logs/YYYY-MM-DD-log.md` + todo updates |
| `meeting-capture` | Turns meeting audio/transcripts into summaries, decisions, and tasks. | `03-professional/meetings/...` or `04-projects/.../meetings/...` |
| `braindump` | Fast capture with routing to personal/professional/projects. | `02-personal/…` / `03-professional/…` / `04-projects/<slug>/notes/…` |
| `daily-brief` | 7-day-fresh news tied to interests and watchlist. | `01-daily/briefs/YYYY-MM-DD-brief.md` |
| `weekly-checkin` | Reflects on the last week, surfaces patterns, plans next steps. | `01-daily/checkins/YYYY-MM-DD-weekly.md` |
| `knowledge-consolidation` | Distills scattered notes into frameworks and cross-links. | `05-knowledge/consolidated/YYYY-MM-DD-synthesis.md` |

See skill logic in `.codex/skills/*/SKILL.md`.

## Vault Layout
```
COG-second-brain/
├── .codex/skills/          # Codex skill definitions
├── 00-inbox/               # Profile, interests, personal todo list
├── 01-daily/
│   ├── briefs/
│   ├── checkins/
│   └── logs/               # Nightly transcript recaps
├── 02-personal/
│   ├── braindumps/
│   └── meetings/
├── 03-professional/
│   ├── braindumps/
│   ├── meetings/
│   └── WORK-TODO.md
├── 04-projects/            # Each project gets /notes/ and optional /notes/meetings/
├── 05-knowledge/
│   ├── consolidated/
│   ├── patterns/
│   └── timeline/
├── 06-templates/           # Markdown templates used by skills
└── 00-inbox/PERSONAL-TODO.md
```

## Templates
Reusable Markdown starting points live in `06-templates/`:
- `braindump-template.md`
- `daily-brief-template.md`
- `daily-recap-template.md`
- `meeting-template.md`
- `weekly-checkin-template.md`
- `knowledge-consolidation-template.md`
- `project-overview-template.md`
- `todo-template.md`

Skills always write from these templates to keep files consistent.

## How to Use (Emoji Walkthrough)
- 🚀 **Kick off onboarding**: Ask Codex, "Start COG onboarding." It prompts for your profile, interests, projects, and seeds todo lists.
- 🌙 **End-of-day recap**: Say "Run daily recap" and paste your audio transcript. Codex writes `01-daily/logs/...` and routes actions into personal/work/project todo files.
- 🧑‍💼 **Meeting capture**: Tell Codex "Log this meeting" with the transcript. It saves a meeting note, pulls out decisions, and updates `WORK-TODO.md` and project tasks.
- 🧠 **Capture fast**: Say "Run braindump" whenever an idea pops up. Notes land in personal/professional/project folders.
- 📰 **Stay briefed**: Run "daily-brief" to get a 7-day-fresh news brief tied to your interests.
- 🔁 **Weekly reflection**: Trigger "weekly-checkin" at week’s end; Codex saves a dated weekly note.
- 🔗 **Synthesize knowledge**: Use "knowledge-consolidation" to merge scattered notes and add cross-links.
- ✍️ **Edit freely**: All outputs are plain Markdown; open them in your editor or Obsidian to tweak formatting, add links, or rearrange sections.

## Voice & Transcript Tips
- Prefer full transcripts so Codex can ground summaries and tasks.
- Mention project/customer names so tasks and meeting notes file into the right project folder.
- Use owners and due dates in speech ("Alice to deliver by Friday") to improve task routing.

## Sync & Backup
- **Obsidian**: Open the repo folder as a vault for browsing.
- **Git**: Commit to your own remote for history.
- **Cloud sync**: iCloud/Dropbox/Drive all work because everything is plain Markdown.

## Contributing
Improvements to skills, templates, and docs are welcome. See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

## License
MIT. Build on it freely.
