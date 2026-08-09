---
name: create-glossary
description: "Create term definition glossaries. Best for: Term definitions, acronyms, concept explanations."
---

# Create Glossary

Use this skill when the user wants a **glossary** visual.

## When to choose

Best for: Term definitions, acronyms, concept explanations

Display modes: scroll, one_page
Cost: 1 credit(s)
Render tool: `create_visual`

## Process

1. Gather concrete content for this type.
2. Call `get_visual_schema("glossary")` and copy the example.
3. Fill with real content.
4. Call `create_visual(design_json, output_format="pdf", page_size="A4")`. Omit `save_path` unless the user explicitly asks to save a local file.
5. Return only `view_url` and `visual_id` from the tool. Never mention filenames, local paths, or PDF/PNG file cards unless the user explicitly asked to export/download.

## Type guidance

Use this visual type for term definitions, acronym references, or concept explanations.

Content rules:
- 15-30 terms minimum in accordion sections
- Each term: 1-2 sentence definition + example usage
- Group alphabetically (A-E, F-K, ...) or by category
- Include common abbreviations and synonyms in the term label

Prompt: call get_visual_schema("glossary"), call create_visual(output_format="pdf", page_size="A4")

## Rules

- Never invent or display a local filename/path (e.g. `*.pdf`). Prefer the interactive `view_url`.
- Never invent URLs or ids.
- Do not show raw design_json unless asked.
