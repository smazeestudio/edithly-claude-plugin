---
name: create-visual
description: "Create an Edithly visual from a topic, conversation, or document using the same ContentWorkflow as the Edithly app (content + visual_type)."
---

# Create an Edithly visual

Use this skill when the user asks to create, generate, convert, visualize, present, summarize visually, or turn content into an interactive visual (except pure image/poster requests — use create-image; except worked solutions — use create-solvesheet).

## Process

1. Identify the source: current conversation, topic, document, structured data, or existing Edithly visual.
2. Gather concrete facts before calling tools. Do not invent statistics.
3. Call `get_visual_types` when the best visual type is unclear.
4. Call `get_visual_schema(visual_type)` for guidance only — do **not** hand-build `design_json`.
5. Call `create_visual(content=<topic or source text>, visual_type=...)`. The backend runs ContentWorkflow (analyze → design → layout → HTML), same as the app.
6. For sales GTM quality, also pass `playbook_slug` and prospect fields (`prospect_company_name`, `prospect_website_url`, `prospect_contact_name`, `prospect_location`).
7. Return only `view_url` and `visual_id` from the tool. Never invent URLs. Do not mention filenames, local paths, or PDF/PNG file cards.

## Rules

- Never invent or display a local filename/path (e.g. `*.pdf`). Prefer the interactive `view_url`.
- For `visual_type == "image"` use the **create-image** skill / `create_image` tool instead.
- For `visual_type == "solvesheet"` use the **create-solvesheet** skill / `create_solvesheet` tool instead. Do not invent solution steps.
- Do not hand-build PageSpec sections for `create_visual`.
- Ask only for information that materially affects generation (type preference, theme, GTM prospect). Do not ask for a save path unless the user wants a local file.
