---
name: create-action-plan
description: "Create implementation action plans. Best for: Implementation roadmaps, sprint plans, next-step playbooks."
---

# Create Action Plan

Use this skill when the user wants a **action_plan** visual.

## When to choose

Best for: Implementation roadmaps, sprint plans, next-step playbooks

Display modes: scroll
Cost: 1 credit(s)
Render tool: `create_visual`

## Process

1. Gather concrete content for this type.
2. Call `get_visual_schema("action_plan")` and copy the example.
3. Fill with real content.
4. Call `create_visual(design_json, output_format="pdf", page_size="A4")`. Omit `save_path` unless the user explicitly asks to save a local file.
5. Return only `view_url` and `visual_id` from the tool. Never mention filenames, local paths, or PDF/PNG file cards unless the user explicitly asked to export/download.

## Type guidance

Use for implementation roadmaps and next-step playbooks.

Content rules:
- Timeline of phases with owners and outcomes
- Include a checklist of immediate next actions
- Keep dates/phases concrete

Prompt: call get_visual_schema("action_plan"), call create_visual(output_format="pdf", page_size="A4")

## Rules


- Never invent URLs or ids.
- Do not show raw design_json unless asked.
