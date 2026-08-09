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

## Setup / auth (OAuth)

Install / point Claude Code at this repository root (or your Claude marketplace entry).

MCP auth is **OAuth** via Edithly’s authorization server (dynamic client registration + PKCE).  
No API key env var is required.

1. Enable the plugin / connect the `edithly` MCP server.
2. In Claude Code run `/mcp` (or `claude mcp login edithly`) and complete the browser sign-in.
3. Tokens are stored by Claude Code; MCP calls use the OAuth access token as `Authorization: Bearer …`.

Config (`.mcp.json`):

- SSE: `https://api.edithly.com/api/v1/mcp/sse`
- AS metadata: `https://api.edithly.com/.well-known/oauth-authorization-server`
- Scopes: `visuals:read visuals:write projects:read exports:create`

See sketch-backend [`plugins/packages/docs/oauth.md`](https://github.com/smazeestudio/sketch_backend/blob/main/plugins/packages/docs/oauth.md).

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
