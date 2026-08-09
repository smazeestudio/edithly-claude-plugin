---
name: create-showcase
description: "Create portfolio / profile showcase pages. Best for: Skills portfolio, project highlights, professional profile."
---

# Create Portfolio / Showcase

Use this skill when the user wants a **showcase** visual.

## When to choose

Best for: Skills portfolio, project highlights, professional profile

Display modes: scroll, one_page
Cost: 1 credit(s)
Render tool: `create_visual`

## Process

1. Gather concrete content for this type.
2. Call `get_visual_schema("showcase")` and copy the example.
3. Fill with real content.
4. Call `create_visual(design_json, output_format="pdf", page_size="A4")`. Omit `save_path` unless the user explicitly asks to save a local file.
5. Return only `view_url` and `visual_id` from the tool. Never mention filenames, local paths, or PDF/PNG file cards unless the user explicitly asked to export/download.

## Type guidance

Use this visual type for skills portfolios, project highlights, or professional profiles.

Content rules:
- 8-12 sections; must include jumbotron, chip_group (skills), stats_grid (metrics), feature_grid (projects)
- Metrics: concrete numbers (e.g. "50k requests/day", "1.2k stars")
- feature_grid items: title + 2-3 sentence description + 2-4 bullet highlights
- chip_group: 6-15 skill/technology names

Prompt: call get_visual_schema("showcase"), call create_visual(output_format="pdf", page_size="A4")

## Rules

- Never invent or display a local filename/path (e.g. `*.pdf`). Prefer the interactive `view_url`.
- Never invent URLs or ids.
- Do not show raw design_json unless asked.
