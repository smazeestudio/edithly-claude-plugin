# Portfolio / Showcase

Use this visual type for skills portfolios, project highlights, or professional profiles.

Content rules:
- 8-12 sections; must include jumbotron, chip_group (skills), stats_grid (metrics), feature_grid (projects)
- Metrics: concrete numbers (e.g. "50k requests/day", "1.2k stars")
- feature_grid items: title + 2-3 sentence description + 2-4 bullet highlights
- chip_group: 6-15 skill/technology names

Prompt: call get_visual_schema("showcase"), call create_visual(output_format="pdf", page_size="A4")
