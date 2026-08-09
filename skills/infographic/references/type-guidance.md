# Infographic

Use this visual type for stats-heavy content, process summaries, or comparisons.

Content rules:
- 6-10 sections; open with 3-5 headline stats in stats_grid
- Every section needs a visual anchor: stat, icon label, or short bold fact
- No walls of text — max 2 sentences per content field
- At least 1 chart with real data points (bar, pie, or donut)

Layout: jumbotron → stats_grid → chart → feature_grid → callout

Prompt: call get_visual_schema("infographic"), call create_visual(output_format="pdf", page_size="A4")
