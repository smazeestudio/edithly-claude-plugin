---
name: create-visual
description: "Create an Edithly visual from a topic, conversation, document, or structured content using PageSpec design_json."
---

# Create an Edithly visual

Use this skill when the user asks to create, generate, convert, visualize, present, summarize visually, or turn content into an interactive visual (except pure image/poster requests — use create-image; except worked solutions — use create-solvesheet).

## Process

1. Identify the source: current conversation, topic, document, structured data, or existing Edithly visual.
2. Gather concrete facts before calling tools. Do not invent statistics.
3. Call `get_visual_types` when the best visual type is unclear.
4. Call `get_visual_schema(visual_type)` and copy the example as your `design_json` base.
5. Fill the example with real content. Keep required fields (`page_title`, `visual_type`, `sections`).
6. Call `create_visual(design_json, output_format, page_size)`. Omit `save_path` unless the user explicitly asks to save a local file.
7. Return only `view_url` and `visual_id` from the tool. Never invent URLs. Do not mention filenames, local paths, or PDF/PNG file cards.

## Rules

- Never invent or display a local filename/path (e.g. `*.pdf`). Prefer the interactive `view_url`.
- For `visual_type == "image"` use the **create-image** skill / `create_image` tool instead.
- For `visual_type == "solvesheet"` use the **create-solvesheet** skill / `create_solvesheet` tool instead. Do not invent solution steps.
- For presentations use `page_size="16:9"`.
- Do not show raw `design_json` to the user unless they ask.
- Ask only for information that materially affects generation (type preference, theme). Do not ask for a save path unless the user wants a local file.
