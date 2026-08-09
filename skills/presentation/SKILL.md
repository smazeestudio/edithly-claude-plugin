---
name: create-presentation
description: "Create slide decks. Always use page_size 16:9. Best for: Slide decks, talks, training material."
---

# Create Slide Presentation

Use this skill when the user wants a **presentation** visual.

## When to choose

Best for: Slide decks, talks, training material

Display modes: presentation
Cost: 1 credit(s)
Render tool: `create_visual`

## Process

1. Gather concrete content for this type.
2. Call `get_visual_schema("presentation")` and copy the example.
3. Fill with real content.
4. Call `create_visual(design_json, output_format="pdf", page_size="16:9")`. Omit `save_path` unless the user explicitly asks to save a local file.
5. Return only `view_url` and `visual_id` from the tool. Never mention filenames, local paths, or PDF/PNG file cards unless the user explicitly asked to export/download.

## Type guidance

Use this visual type for slide decks, training material, or talks. Always use page_size="16:9".

Content rules:
- 12-15 sections (each = 1 slide); max 3 bullet points per list slide
- Slide 1: jumbotron (hook); Slide 2: agenda list; Middle: one concept per slide
- Second-to-last: key takeaways list; Last: CTA or summary
- Component guide: explanation → text_block, data → stats_grid, code → code_block, quote → quote/callout

Prompt: call get_visual_schema("presentation"), call create_visual(output_format="pdf", page_size="16:9")

## Rules

- Never invent or display a local filename/path (e.g. `*.pdf`). Prefer the interactive `view_url`.
- Never invent URLs or ids.
- Do not show raw design_json unless asked.
