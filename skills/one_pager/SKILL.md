---
name: create-one-pager
description: "Create executive or sales one-pagers. Best for: Sales collateral, executive summaries, product overviews."
---

# Create One-pager

Use this skill when the user wants a **one_pager** visual.

## When to choose

Best for: Sales collateral, executive summaries, product overviews

Display modes: one_page, board
Cost: 1 credit(s)
Render tool: `create_visual`

## Process

1. Gather concrete content for this type.
2. Call `get_visual_schema("one_pager")` and copy the example.
3. Fill with real content.
4. Call `create_visual(design_json, output_format="pdf", page_size="A4")`. Omit `save_path` unless the user explicitly asks to save a local file.
5. Return only `view_url` and `visual_id` from the tool. Never mention filenames, local paths, or PDF/PNG file cards unless the user explicitly asked to export/download.

## Type guidance

Use for sales collateral, executive summaries, and product overviews.

Content rules:
- 6-12 focused sections; lead with a hero value prop
- Include 3-5 concrete metrics in stats_grid
- End with a clear CTA callout
- Keep copy tight — one idea per section

Prompt: call get_visual_schema("one_pager"), call create_visual(output_format="pdf", page_size="A4")

## Rules


- Never invent URLs or ids.
- Do not show raw design_json unless asked.
