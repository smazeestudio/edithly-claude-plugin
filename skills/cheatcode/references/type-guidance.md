# Cheatcode / Reference Sheet

Use this visual type for programming syntax, CLI commands, API references, formulas,
or any dense factual reference material.

Content rules:
- 15-25 sections total; cover overview, core syntax, common patterns, gotchas, quick examples
- Mix: at least 4 code_block, 3 list, 2 table, 1 stats_grid
- code_block examples must be minimal and runnable (3-8 lines each)
- Each list item: command or fact only — no long sentences

Layout: jumbotron → stats_grid → alternate code_block (col_span 6) + list (col_span 6) → table for comparisons → callout for gotchas

Prompt: call get_visual_schema("cheatcode"), fill in real content, call create_visual(output_format="pdf", page_size="A4")
