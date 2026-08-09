---
name: create-cheatcode
description: "Create dense reference / cheatsheet visuals. Best for: Programming syntax, CLI commands, API references, formulas."
---

# Create Cheatcode / Reference Sheet

Use this skill when the user wants a **cheatcode** visual.

## When to choose

Best for: Programming syntax, CLI commands, API references, formulas

Display modes: scroll, one_page
Cost: 1 credit(s)
Render tool: `create_visual`

## Process

1. Gather concrete content for this type.
2. Call `get_visual_schema("cheatcode")` and copy the example.
3. Fill with real content.
4. Call `create_visual(design_json, output_format="pdf", page_size="A4")`. Omit `save_path` unless the user explicitly asks to save a local file.
5. Return only `view_url` and `visual_id` from the tool. Never mention filenames, local paths, or PDF/PNG file cards unless the user explicitly asked to export/download.

## Type guidance

Use this visual type for programming syntax, CLI commands, API references, formulas,
or any dense factual reference material.

Content rules:
- 15-25 sections total; cover overview, core syntax, common patterns, gotchas, quick examples
- Mix: at least 4 code_block, 3 list, 2 table, 1 stats_grid
- code_block examples must be minimal and runnable (3-8 lines each)
- Each list item: command or fact only — no long sentences

Layout: jumbotron → stats_grid → alternate code_block (col_span 6) + list (col_span 6) → table for comparisons → callout for gotchas

Prompt: call get_visual_schema("cheatcode"), fill in real content, call create_visual(output_format="pdf", page_size="A4")

## Rules

- Never invent or display a local filename/path (e.g. `*.pdf`). Prefer the interactive `view_url`.
- Never invent URLs or ids.
- Do not show raw design_json unless asked.
