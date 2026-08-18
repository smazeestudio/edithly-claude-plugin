---
name: create-solvesheet-worked-example
description: "Create a worked-example solvesheet via create_solvesheet. Best for: exam problems, homework, step-by-step derivations."
---

# Create Solvesheet / Worked Example

Use this skill when the user wants a **solvesheet** visual.

## When to choose

Best for: Worked solutions, exam problems, step-by-step derivations

Display modes: one_page
Cost: 1 credit(s)
Render tool: `create_solvesheet`

## Process

1. Gather the problem statement or document text.
2. Call `create_solvesheet(content, question)`. Omit `save_path` unless the user explicitly asks to save a local file.
3. Return only `view_url` and `visual_id` from the tool. Never mention filenames, local paths, or PDF/PNG file cards unless the user explicitly asked to export/download.

## Type guidance

IMPORTANT: Use create_solvesheet() — NOT create_visual(). Do not invent solution steps.

The backend extracts the question, solves it, and renders a worked example (method,
timeline steps, boxed answer, try-yourself). Pass the source as plain text.

Content rules:
- content: the problem, worksheet, notes, or document extract (required)
- question: set this when content has more than one problem; otherwise omit
- sheet_theme: studio | notebook | chalk | sticky | legal | graph | sketchnote (optional)

When to use: user says "solve this", "worked example", "solvesheet", "show the method"
When NOT to use: dense reference of facts with no problem to solve → cheatcode

Tool call: create_solvesheet(content, question) — costs 1 credit.

## Rules

- Never invent or display a local filename/path (e.g. `*.pdf`). Prefer the interactive `view_url`.
- Never invent URLs or ids.
- Do not show raw design_json unless asked.
- Never call create_visual for solvesheet type.
