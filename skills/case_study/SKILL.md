---
name: create-case-study
description: "Create customer / product case studies. Best for: Customer stories, problem-solution narratives, proof points."
---

# Create Case Study

Use this skill when the user wants a **case_study** visual.

## When to choose

Best for: Customer stories, problem-solution narratives, proof points

Display modes: scroll
Cost: 1 credit(s)
Render tool: `create_visual`

## Process

1. Gather concrete content for this type.
2. Call `get_visual_schema("case_study")` and copy the example.
3. Fill with real content.
4. Call `create_visual(design_json, output_format="pdf", page_size="A4")`. Omit `save_path` unless the user explicitly asks to save a local file.
5. Return only `view_url` and `visual_id` from the tool. Never mention filenames, local paths, or PDF/PNG file cards unless the user explicitly asked to export/download.

## Type guidance

Use for customer stories and problem-solution narratives.

Content rules:
- Structure: hero → challenge → solution → results → quote
- Include quantified outcomes in stats_grid
- Keep narrative factual; no invented customer metrics

Prompt: call get_visual_schema("case_study"), call create_visual(output_format="pdf", page_size="A4")

## Rules


- Never invent URLs or ids.
- Do not show raw design_json unless asked.
