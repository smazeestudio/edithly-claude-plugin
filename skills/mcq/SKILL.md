---
name: create-mcq
description: "Create formal multiple-choice quizzes. Best for: Formal quizzes, practice tests, assessment sets."
---

# Create Multiple Choice Quiz

Use this skill when the user wants a **mcq** visual.

## When to choose

Best for: Formal quizzes, practice tests, assessment sets

Display modes: scroll, one_page
Cost: 1 credit(s)
Render tool: `create_visual`

## Process

1. Gather concrete content for this type.
2. Call `get_visual_schema("mcq")` and copy the example.
3. Fill with real content.
4. Call `create_visual(design_json, output_format="pdf", page_size="A4")`. Omit `save_path` unless the user explicitly asks to save a local file.
5. Return only `view_url` and `visual_id` from the tool. Never mention filenames, local paths, or PDF/PNG file cards unless the user explicitly asked to export/download.

## Type guidance

Use for formal multiple-choice quizzes and practice tests.

Content rules:
- 8-20 questions; 4 options each when possible
- Put the correct answer and a short rationale with each question
- Group by topic when the set is large

Prompt: call get_visual_schema("mcq"), call create_visual(output_format="pdf", page_size="A4")

## Rules


- Never invent URLs or ids.
- Do not show raw design_json unless asked.
