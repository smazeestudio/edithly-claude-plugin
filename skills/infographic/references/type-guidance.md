# Infographic

Use this visual type for stats-heavy content, process summaries, or comparisons.

Content rules:
- 6-10 sections; open with 3-5 headline stats in stats_grid
- Every section needs a visual anchor: Font Awesome icon + short label, or a bold stat
- No walls of text — max 2 sentences per content field; node labels are a few words
- At least one pictorial motif (icon flow, hub-and-spoke, or chevron process)
- Add a chart (bar, pie, or donut) only when there are real comparison numbers

Layout: jumbotron → stats → pictorial motif (flow / hub / process) → callout

Prompt: call get_visual_schema("infographic"), call create_visual(output_format="pdf", page_size="A4")
