# Changelog

## 1.0.0 — 2026-08-09

- Initial Claude Code plugin package.
- Flat `skills/` layout (workflow + visual-type skills).
- MCP SSE endpoint: `https://api.edithly.com/api/v1/mcp/sse`.
- `plugin.json` metadata: displayName, repository, license, keywords covering all MCP tools and visual types.
- MCP auth switched to **OAuth** (AS discovery + DCR/PKCE); removed Bearer `EDITHLY_ACCESS_TOKEN` header config.
- Removed unsupported `displayName` from `plugin.json` (`claude plugin validate` rejects it).
