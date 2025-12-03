# Publishing COG to Codex CLI Marketplaces

COG is packaged as a Codex CLI plugin. Use this guide to publish or sideload it.

## Included Artifacts
- **`.codex-plugin/plugin.json`** – manifest for Codex CLI
- **`marketplace-entry.json`** – reference entry for catalogs

## Manifest Highlights
- `name`: `cog-second-brain`
- `version`: `2.1.0`
- Skills: `onboarding`, `daily-recap`, `meeting-capture`, `braindump`, `daily-brief`, `weekly-checkin`, `knowledge-consolidation`
- Templates directory: `06-templates`
- License: MIT

## Submit to a Marketplace
1. Provide the repo URL: `https://github.com/huytieu/COG-second-brain`.
2. Ensure `plugin.json` validates (`python -m json.tool .codex-plugin/plugin.json`).
3. Confirm all skill paths exist under `.codex/skills/`.

## Manual Install (current)
```bash
cd /path/to/vault
git clone https://github.com/huytieu/COG-second-brain.git
cp -r COG-second-brain/.codex .
cp COG-second-brain/.codex-plugin/plugin.json ./plugin.json
```

## Versioning
Semantic versioning; update both manifest and marketplace entry when releasing.

## Support
- Issues: https://github.com/huytieu/COG-second-brain/issues
- Discussions: https://github.com/huytieu/COG-second-brain/discussions
