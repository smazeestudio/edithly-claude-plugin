---
name: create-question-paper
description: "Create exam-style question papers. Best for: Formal exams, worksheets, competitive test papers."
---

# Create Question Paper

Use this skill when the user wants a **question_paper** visual.

## When to choose

Best for: Formal exams, worksheets, competitive test papers

Display modes: scroll, one_page
Cost: 1 credit(s)
Render tool: `create_visual`

## Process

1. Gather concrete content for this type.
2. Call `get_visual_schema("question_paper")` and copy the example.
3. Fill with real content.
4. Call `create_visual(design_json, output_format="pdf", page_size="A4")`. Omit `save_path` unless the user explicitly asks to save a local file.
5. Return only `view_url` and `visual_id` from the tool. Never mention filenames, local paths, or PDF/PNG file cards unless the user explicitly asked to export/download.

## Type guidance

Use for formal exams, worksheets, and competitive test papers.

Content rules:
- State time allowed and max marks in the hero
- Split into clearly titled sections with mark weights
- Prefer numbered questions; keep stems unambiguous

Prompt: call get_visual_schema("question_paper"), call create_visual(output_format="pdf", page_size="A4")

## Rules


- Never invent URLs or ids.
- Do not show raw design_json unless asked.
