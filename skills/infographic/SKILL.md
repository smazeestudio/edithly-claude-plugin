---
name: create-infographic
description: "Create stats-led infographics. Best for: Stats-heavy content, comparisons, process summaries."
---

# Create Infographic

Use this skill when the user wants a **infographic** visual.

## When to choose

Best for: Stats-heavy content, comparisons, process summaries

Display modes: scroll, one_page
Cost: 1 credit(s)
Render tool: `create_visual`

## Process

1. Gather concrete content for this type.
2. Call `get_visual_schema("infographic")` and copy the example.
3. Fill with real content.
4. Call `create_visual(design_json, output_format="pdf", page_size="A4")`. Omit `save_path` unless the user explicitly asks to save a local file.
5. Return only `view_url` and `visual_id` from the tool. Never mention filenames, local paths, or PDF/PNG file cards unless the user explicitly asked to export/download.

## Type guidance

Use this visual type for stats-heavy content, process summaries, or comparisons.

Content rules:
- 6-10 sections; open with 3-5 headline stats in stats_grid
- Every section needs a visual anchor: Font Awesome icon + short label, or a bold stat
- No walls of text — max 2 sentences per content field; node labels are a few words
- At least one pictorial motif (icon flow, hub-and-spoke, or chevron process)
- Add a chart (bar, pie, or donut) only when there are real comparison numbers

Layout: jumbotron → stats → pictorial motif (flow / hub / process) → callout

Prompt: call get_visual_schema("infographic"), call create_visual(output_format="pdf", page_size="A4")

## Rules

- Never invent or display a local filename/path (e.g. `*.pdf`). Prefer the interactive `view_url`.
- Never invent URLs or ids.
- Do not show raw design_json unless asked.
