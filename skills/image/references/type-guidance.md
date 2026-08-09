# AI Poster Image (WebP)

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
