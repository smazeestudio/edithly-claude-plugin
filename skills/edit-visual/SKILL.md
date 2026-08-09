---
name: edit-visual
description: "Modify an existing Edithly visual by id using instructions or a design_json patch, then re-render."
---

# Edit an Edithly visual

Use when the user wants to change, update, fix, or revise an existing visual.

## Process

1. Obtain `visual_id` (from prior create result or user).
2. Call `get_visual(visual_id)` to load current metadata.
3. Call `update_visual` with either:
   - `instructions` (natural language changes), and/or
   - `design_patch` (partial PageSpec overrides)
   Omit `save_path` unless the user explicitly asks to save a local file.
4. Return only `view_url` and `visual_id` from the tool. Do not mention filenames or local paths.

## Rules

- Never invent or display a local filename/path. Prefer the interactive `view_url`.
- Do not invent a successful update. If the tool fails, report the error.
- Prefer small targeted edits over regenerating from scratch unless the user asks.
