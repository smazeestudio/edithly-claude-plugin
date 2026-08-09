---
name: create-image-poster
description: "Create AI poster images via create_image. Best for: Visual poster, cheatsheet image."
---

# Create AI Poster Image (WebP)

Use this skill when the user wants a **image** visual.

## When to choose

Best for: Visual poster, cheatsheet image

Display modes: one_page
Cost: 4 credit(s)
Render tool: `create_image`

## Process

1. Gather concrete content for this type.
2. Call `get_visual_schema("image")` and copy the example.
3. Fill with real content.
4. Call `create_image(page_title, content)`. Omit `save_path` unless the user explicitly asks to save a local file.
5. Return only `view_url` and `visual_id` from the tool. Never mention filenames, local paths, or PDF/PNG file cards unless the user explicitly asked to export/download.

## Type guidance

IMPORTANT: Use create_image() — NOT create_visual(). No sections needed.

The backend sends your content to an AI image model (GPT-4o-mini) which produces a 1024x1024
WebP poster. output_format and page_size are ignored.

Content rules:
- page_title: concise title (required)
- content: ALL facts, stats, formulas, concepts as plain text — 500-1500 words (more = richer image)
- page_description: 3-6 sentence summary (optional but recommended)
- Do NOT include a sections array

When to use: user says "create an image", "make a poster", "generate a picture"
When NOT to use: user wants structured PDF with sections → use create_visual() instead

Tool call: create_image(page_title, content) — costs 4 credits. Omit save_path unless user asks to save locally.

## Rules

- Never invent or display a local filename/path (e.g. `*.pdf`). Prefer the interactive `view_url`.
- Never invent URLs or ids.
- Do not show raw design_json unless asked.
- Never call create_visual for image type.
