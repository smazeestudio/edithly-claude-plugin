# Solvesheet / Worked Example

IMPORTANT: Use create_solvesheet() — NOT create_visual(). Do not invent solution steps.

The backend extracts the question, solves it, and renders a worked example (method,
timeline steps, boxed answer, try-yourself). Pass the source as plain text.

Content rules:
- content: the problem, worksheet, notes, or document extract (required)
- question: set this when content has more than one problem; otherwise omit and the
  pipeline uses content as the question
- sheet_theme: studio | notebook | chalk | sticky | legal | graph | sketchnote (optional)

When to use: user says "solve this", "worked example", "solvesheet", "show the method",
or pastes an exam question / homework problem.
When NOT to use: dense reference of facts with no problem to solve → cheatcode.

Tool call: create_solvesheet(content, question) — costs 1 credit. Omit save_path unless
the user asks to save locally.
