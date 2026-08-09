# Edithly Claude plugin

Claude Code plugin for creating and editing Edithly visuals via the shared Edithly MCP server.

## Layout

```text
edithly-claude-plugin/
├── .claude-plugin/plugin.json
├── skills/                 # flat: workflows + visual types
├── .mcp.json
├── README.md
├── LICENSE
└── CHANGELOG.md
```

## Setup

```bash
export EDITHLY_ACCESS_TOKEN=your_edithly_api_key_jwt
```

Install / point Claude Code at this repository root (or your Claude marketplace entry).

MCP uses Bearer auth in `.mcp.json`. Hosts that require OAuth use the Edithly OAuth AS instead.

## Syncing skills from sketch-backend

Skill **source of truth** lives in `sketch-backend/plugins/packages/skills`.

From sketch-backend:

```bash
cd plugins
python scripts/build_claude_plugin.py
```

Then in this repo:

```bash
git add skills
git commit -m "Sync skills from sketch-backend"
git push
```

Update the submodule pointer in sketch-backend afterward:

```bash
cd /path/to/sketch-backend
git add plugins/edithly-claude-plugin
git commit -m "Bump edithly-claude-plugin submodule"
```

## Auth

```text
Authorization: Bearer <EDITHLY_ACCESS_TOKEN>
```
