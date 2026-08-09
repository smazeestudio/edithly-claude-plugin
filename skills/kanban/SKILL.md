---
name: create-kanban
description: "Create kanban task boards. Best for: Task boards, workflow columns, project status."
---

# Create Kanban Board

Use this skill when the user wants a **kanban** visual.

## When to choose

Best for: Task boards, workflow columns, project status

Display modes: scroll, one_page
Cost: 1 credit(s)
Render tool: `create_visual`

## Process

1. Gather concrete content for this type.
2. Call `get_visual_schema("kanban")` and copy the example.
3. Fill with real content.
4. Call `create_visual(design_json, output_format="pdf", page_size="A4")`. Omit `save_path` unless the user explicitly asks to save a local file.
5. Return only `view_url` and `visual_id` from the tool. Never mention filenames, local paths, or PDF/PNG file cards unless the user explicitly asked to export/download.

## Type guidance

Use for task boards and workflow status.

Content rules:
- 3-5 columns (e.g. Todo / Doing / Done)
- Cards: short titles, optional owner/priority
- Keep board scannable — avoid essay-length card text

Prompt: call get_visual_schema("kanban"), call create_visual(output_format="pdf", page_size="A4")

## Rules


- Never invent URLs or ids.
- Do not show raw design_json unless asked.
