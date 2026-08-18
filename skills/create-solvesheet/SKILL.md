---
name: create-solvesheet
description: "Turn a problem, worksheet, or document text into an Edithly worked-example solvesheet. The backend solves it."
---

# Create a solvesheet from document or text

Use when the user asks to solve a question, make a worked example, or turn homework / exam / notes into a solvesheet.

## Process

1. Collect the problem or document text as `content`. If the source has more than one problem, also set `question`.
2. Call `create_solvesheet(content, question)`. Omit `save_path` unless the user explicitly asks to save a local file.
3. Return only `view_url` and `visual_id` from the tool. Do not mention filenames or local paths.

## Rules

- Never invent or display a local filename/path. Prefer the interactive `view_url`.
- Do **not** call `create_visual` for solvesheet.
- Do **not** invent solution steps or fill `design_json`. The backend solves the problem.
- Never invent URLs — only use tool output.
