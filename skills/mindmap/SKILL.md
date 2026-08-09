---
name: create-mindmap
description: "Create hierarchical concept mind maps. Best for: Topic overviews, concept relationships, brainstorming."
---

# Create Mind Map

Use this skill when the user wants a **mindmap** visual.

## When to choose

Best for: Topic overviews, concept relationships, brainstorming

Display modes: scroll, one_page
Cost: 1 credit(s)
Render tool: `create_visual`

## Process

1. Gather concrete content for this type.
2. Call `get_visual_schema("mindmap")` and copy the example.
3. Fill with real content.
4. Call `create_visual(design_json, output_format="pdf", page_size="A4")`. Omit `save_path` unless the user explicitly asks to save a local file.
5. Return only `view_url` and `visual_id` from the tool. Never mention filenames, local paths, or PDF/PNG file cards unless the user explicitly asked to export/download.

## Type guidance

Use this visual type for topic overviews, concept relationships, and brainstorming.

Content rules:
- Exactly 1 mind_map section (col_span 12)
- Root node: main topic (1-4 words); 4-8 branches; 2-5 leaves per branch
- Leaf labels: max 5 words each, noun phrases; total nodes 20-40; no duplicates

nodes structure: {"label": "Root", "children": [{"label": "Branch", "children": [{"label": "Leaf"}]}]}

Prompt: call get_visual_schema("mindmap"), build the nodes tree, call create_visual(output_format="pdf", page_size="A4")

## Rules

- Never invent or display a local filename/path (e.g. `*.pdf`). Prefer the interactive `view_url`.
- Never invent URLs or ids.
- Do not show raw design_json unless asked.
