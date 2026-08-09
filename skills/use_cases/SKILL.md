---
name: create-use-cases
description: "Create product use-case pages. Best for: Product scenarios, persona workflows, how-to-apply guides."
---

# Create Use Cases

Use this skill when the user wants a **use_cases** visual.

## When to choose

Best for: Product scenarios, persona workflows, how-to-apply guides

Display modes: scroll, one_page
Cost: 1 credit(s)
Render tool: `create_visual`

## Process

1. Gather concrete content for this type.
2. Call `get_visual_schema("use_cases")` and copy the example.
3. Fill with real content.
4. Call `create_visual(design_json, output_format="pdf", page_size="A4")`. Omit `save_path` unless the user explicitly asks to save a local file.
5. Return only `view_url` and `visual_id` from the tool. Never mention filenames, local paths, or PDF/PNG file cards unless the user explicitly asked to export/download.

## Type guidance

Use for product scenarios and persona workflows.

Content rules:
- 3-6 use-case cards in feature_grid or tabs
- Each case: who, goal, how Edithly/product helps, outcome
- Optional callout for "best starting use case"

Prompt: call get_visual_schema("use_cases"), call create_visual(output_format="pdf", page_size="A4")

## Rules


- Never invent URLs or ids.
- Do not show raw design_json unless asked.
