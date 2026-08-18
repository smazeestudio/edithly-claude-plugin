---
name: document-to-visual
description: "Turn a document or file into an Edithly visual. Worked examples use create_solvesheet; posters use create_image."
---

# Document to visual

Use when the user provides a document, PDF extract, notes file, or pasted long-form text to visualize.

## Process

1. Extract headings, bullets, tables, and key sentences. Discard boilerplate.
2. Call `get_visual_types` and pick the best type (or honor the user's type).
3. If the type is `solvesheet` (worked example / solve this problem), call `create_solvesheet(content, question)` with the extracted text. Do not invent steps.
4. If the type is `image`, call `create_image`. Otherwise call `get_visual_schema(visual_type)` and `create_visual`. Omit `save_path` unless the user explicitly asks to save a local file.
5. Return only `view_url` and `visual_id`. Never mention filenames, local paths, or PDF/PNG file cards.
