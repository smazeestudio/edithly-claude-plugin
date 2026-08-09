---
name: create-flashcard
description: "Create flip-card or MCQ study decks. Best for: MCQ quizzes, vocabulary, definitions, Q&A study cards."
---

# Create Flashcard / MCQ Deck

Use this skill when the user wants a **flashcard** visual.

## When to choose

Best for: MCQ quizzes, vocabulary, definitions, Q&A study cards

Display modes: scroll, one_page
Cost: 1 credit(s)
Render tool: `create_visual`

## Process

1. Gather concrete content for this type.
2. Call `get_visual_schema("flashcard")` and copy the example.
3. Fill with real content.
4. Call `create_visual(design_json, output_format="pdf", page_size="A4")`. Omit `save_path` unless the user explicitly asks to save a local file.
5. Return only `view_url` and `visual_id` from the tool. Never mention filenames, local paths, or PDF/PNG file cards unless the user explicitly asked to export/download.

## Type guidance

Use this visual type for MCQ quizzes, vocabulary, Q&A study cards, or definition drills.
Each flashcard section becomes a separate deck tab in the rendered output.

Content rules:
- 1+ flashcard sections; 15-30 cards total across all decks
- front: question or term — max 15 words; back: direct answer — max 40 words
- No yes/no fronts — use "what", "how", "why", "explain"
- MCQ format: include A/B/C/D options in front, correct answer + reason in back
- Group related cards into sections (each section = one deck tab)

Prompt: call get_visual_schema("flashcard"), keep component_type "flashcard" for every section, call create_visual(output_format="pdf", page_size="A4")

## Rules

- Never invent or display a local filename/path (e.g. `*.pdf`). Prefer the interactive `view_url`.
- Never invent URLs or ids.
- Do not show raw design_json unless asked.
