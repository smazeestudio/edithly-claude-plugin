---
name: create-roi-calculator
description: "Create ROI / value model visuals. Best for: Business value models, cost savings, investment justification."
---

# Create ROI Calculator

Use this skill when the user wants a **roi_calculator** visual.

## When to choose

Best for: Business value models, cost savings, investment justification

Display modes: scroll, one_page
Cost: 1 credit(s)
Render tool: `create_visual`

## Process

1. Gather concrete content for this type.
2. Call `get_visual_schema("roi_calculator")` and copy the example.
3. Fill with real content.
4. Call `create_visual(design_json, output_format="pdf", page_size="A4")`. Omit `save_path` unless the user explicitly asks to save a local file.
5. Return only `view_url` and `visual_id` from the tool. Never mention filenames, local paths, or PDF/PNG file cards unless the user explicitly asked to export/download.

## Type guidance

Use for business value models and investment justification.

Content rules:
- Lead with headline ROI stats
- Show assumptions in a table
- Optional chart for savings over time
- Label estimates clearly — never invent precise customer finances without source

Prompt: call get_visual_schema("roi_calculator"), call create_visual(output_format="pdf", page_size="A4")

## Rules


- Never invent URLs or ids.
- Do not show raw design_json unless asked.
