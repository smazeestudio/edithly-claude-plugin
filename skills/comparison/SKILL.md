---
name: create-comparison
description: "Create side-by-side comparison tables. Best for: Side-by-side comparisons, pros/cons, feature matrices."
---

# Create Comparison Table

Use this skill when the user wants a **comparison** visual.

## When to choose

Best for: Side-by-side comparisons, pros/cons, feature matrices

Display modes: scroll, one_page
Cost: 1 credit(s)
Render tool: `create_visual`

## Process

1. Gather concrete content for this type.
2. Call `get_visual_schema("comparison")` and copy the example.
3. Fill with real content.
4. Call `create_visual(design_json, output_format="pdf", page_size="A4")`. Omit `save_path` unless the user explicitly asks to save a local file.
5. Return only `view_url` and `visual_id` from the tool. Never mention filenames, local paths, or PDF/PNG file cards unless the user explicitly asked to export/download.

## Type guidance

Use this visual type for side-by-side comparisons, pros/cons, or feature matrices.

Content rules:
- 1-2 table sections; 6-15 rows; each cell: 1-5 words max
- Headers: first column = criterion, remaining = options being compared
- End with a callout: "Use X when... / Use Y when..."
- Optional: feature_grid or list for "When to use each" summary

Prompt: call get_visual_schema("comparison"), call create_visual(output_format="pdf", page_size="A4")

## Rules

- Never invent or display a local filename/path (e.g. `*.pdf`). Prefer the interactive `view_url`.
- Never invent URLs or ids.
- Do not show raw design_json unless asked.
