---
name: create-image
description: "Generate an Edithly AI poster image (WebP) from raw content. Costs 4 credits."
---

# Create an Edithly image poster

Use when the user asks for an image, poster, picture, or visual cheatsheet image.

## Process

1. Collect `page_title` and a rich plain-text `content` body (500–1500 words of facts).
2. Call `create_image(page_title, content)`. Omit `save_path` unless the user explicitly asks to save a local file.
3. Return only `view_url` and `visual_id` from the tool. Do not mention filenames or local paths.

## Rules

- Never invent or display a local filename/path. Prefer the interactive `view_url`.
- Do **not** call `create_visual` for image type.
- Do **not** build a `sections` array.
- Never invent URLs — only use tool output.
