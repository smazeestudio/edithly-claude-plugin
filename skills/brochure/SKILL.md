---
name: create-brochure
description: "Create marketing brochure / landing visuals. Best for: Product landing page, service pitch, conversion-focused content."
---

# Create Marketing Brochure

Use this skill when the user wants a **brochure** visual.

## When to choose

Best for: Product landing page, service pitch, conversion-focused content

Display modes: scroll, one_page
Cost: 1 credit(s)
Render tool: `create_visual`

## Process

1. Gather concrete content for this type.
2. Call `get_visual_schema("brochure")` and copy the example.
3. Fill with real content.
4. Call `create_visual(design_json, output_format="pdf", page_size="A4")`. Omit `save_path` unless the user explicitly asks to save a local file.
5. Return only `view_url` and `visual_id` from the tool. Never mention filenames, local paths, or PDF/PNG file cards unless the user explicitly asked to export/download.

## Type guidance

Use this visual type for product landing pages, service pitches, or conversion-focused content.

Content rules:
- 6-10 sections; structure: hero → problem (callout warning) → features → social proof → CTA
- testimonial: real-sounding name, role, 1-2 sentence quote
- callout for value proposition (variant: "success"); button_group for CTAs
- Copy: benefit-first headlines, outcome-focused feature descriptions

Prompt: call get_visual_schema("brochure"), call create_visual(output_format="pdf", page_size="A4")

## Rules

- Never invent or display a local filename/path (e.g. `*.pdf`). Prefer the interactive `view_url`.
- Never invent URLs or ids.
- Do not show raw design_json unless asked.
