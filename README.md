# Edithly for Claude

Turn conversations and content into interactive visuals.

## Features

- Infographics
- Flashcards
- Cheatcodes
- Presentations
- Timelines
- MCQs
- Question papers
- Mind maps
- GTM one-pagers
- ROI calculators
- Case studies
- Use cases
- Action plans
- Brochures, glossaries, study aids, kanban boards, and AI poster images

## Installation

In Claude Code, add this repository as a marketplace, then install the plugin:

```text
/plugin marketplace add smazeestudio/edithly-claude-plugin
/plugin install edithly@edithly-plugins
```

This repo is both the **marketplace catalog** (`.claude-plugin/marketplace.json`) and the **plugin** (`.claude-plugin/plugin.json`). Adding the plugin URL as a marketplace without `marketplace.json` fails with “no manifest found.”

Local development (from the directory above the plugin):

```bash
claude --plugin-dir ./edithly-claude-plugin
```

If using the git submodule from sketch-backend:

```bash
git submodule update --init plugins/edithly-claude-plugin
```

## Authentication

Connect your Edithly account when prompted.

MCP uses **OAuth** against Edithly’s authorization server. In Claude Code, open `/mcp` and authenticate the `edithly` server (browser sign-in). No API key environment variable is required.

- MCP (Streamable HTTP): `https://api.edithly.com/api/v1/mcp`
- OAuth discovery: `https://api.edithly.com/.well-known/oauth-authorization-server`

## Example prompts

Create an infographic explaining FastAPI CORS.

Create 10 Python flashcards with 5 medium and 5 hard questions.

Create a GTM one-pager from this document.

Turn this conversation into a presentation.

Build a mind map of machine learning fundamentals.

Make a cheatcode sheet for Docker CLI.

## How it works

Edithly skills guide Claude to call the shared Edithly MCP tools (`get_visual_types`, `get_visual_schema`, `create_visual`, `create_image`, `update_visual`, `export_visual`, and related helpers). Visuals open in Edithly via a shareable link after generation.

## Layout

```text
edithly-claude-plugin/
├── .claude-plugin/
│   ├── marketplace.json    # required for /plugin marketplace add
│   └── plugin.json
├── skills/                 # flat: workflows + visual types
├── .mcp.json
├── README.md
├── LICENSE
└── CHANGELOG.md
```

## Maintaining this plugin (developers)

Skill source of truth lives in [sketch-backend](https://github.com/smazeestudio/sketch_backend) at `plugins/packages/skills`.

```bash
cd sketch-backend/plugins
python scripts/build_claude_plugin.py

cd edithly-claude-plugin
git add skills
git commit -m "Sync skills from sketch-backend"
git push origin main
```

Then bump the submodule pointer in sketch-backend. See `plugins/CLAUDE_SUBMODULE.md` in sketch-backend.

## License

MIT — see [LICENSE](LICENSE).

## Links

- Website: [edithly.com](https://edithly.com)
- Repository: [github.com/smazeestudio/edithly-claude-plugin](https://github.com/smazeestudio/edithly-claude-plugin)
