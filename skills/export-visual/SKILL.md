---
name: export-visual
description: "Export an existing Edithly visual as PDF or PNG (and surface HTML URLs when available)."
---

# Export an Edithly visual

Use when the user asks to download, export, or convert a visual to PDF/PNG.

## Process

1. Resolve `visual_id`.
2. Call `export_visual(visual_id, output_format, page_size?)`. Omit `save_path` unless the user explicitly asks to save a local file.
3. Report `download_url` and `view_url` from the tool. Do not invent or display a local filename/path unless `local_path` is returned by the tool because the user requested a save path.

## Rules

- Default `output_format` is `pdf`.
- HTML is available via `html_url` / `view_url` from `get_visual` when present.
- Image posters (`webp`) come from `create_image`, not this skill.
