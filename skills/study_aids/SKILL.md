---
name: create-study-aids
description: "Create multi-section study workbooks. Best for: Digital study workbook with overview, explanation, recall, practice, and review."
---

# Create Study Aids

Use this skill when the user wants a **study_aids** visual.

## When to choose

Best for: Digital study workbook with overview, explanation, recall, practice, and review

Display modes: scroll, one_page
Cost: 1 credit(s)
Render tool: `create_visual`

## Process

1. Gather concrete content for this type.
2. Call `get_visual_schema("study_aids")` and copy the example.
3. Fill with real content.
4. Call `create_visual(design_json, output_format="pdf", page_size="A4")`. Omit `save_path` unless the user explicitly asks to save a local file.
5. Return only `view_url` and `visual_id` from the tool. Never mention filenames, local paths, or PDF/PNG file cards unless the user explicitly asked to export/download.

## Type guidance

Use this visual type for a digital study workbook: overview + explanation + recall + practice + review.

Content rules:
- Aim for 6-10 visible sections, hard max 14
- Must include: 1 hero, 1 mind_map, 1 flashcard section, 1 checklist review section
- Must include 1 explanation zone: accordion or tabs
- Include `fill_blanks` and `match_pairs` in every study_aids workbook; add `jumble_words` when the topic benefits from term recall
- mind_map: 4-6 branches, 2-4 leaves each; flashcard: 10-20 cards minimum
- accordion/tabs: 6-10 key concepts with short explanations

Prompt: call get_visual_schema("study_aids"), call create_visual(output_format="pdf", page_size="A4")

## Rules

- Never invent or display a local filename/path (e.g. `*.pdf`). Prefer the interactive `view_url`.
- Never invent URLs or ids.
- Do not show raw design_json unless asked.
