---
name: document-to-visual
description: "Turn a document or file into an Edithly visual via extract → type select → design_json → create_visual."
---

# Document to visual

Use when the user provides a document, PDF extract, notes file, or pasted long-form text to visualize.

## Process

1. Extract headings, bullets, tables, and key sentences. Discard boilerplate.
2. Call `get_visual_types` and pick the best type (or honor the user's type).
3. Call `get_visual_schema(visual_type)` and fill the example with extracted content.
4. Call `create_visual` (or `create_image` if they want a poster). Omit `save_path` unless the user explicitly asks to save a local file.
5. Return only `view_url` and `visual_id`. Never mention filenames, local paths, or PDF/PNG file cards.
