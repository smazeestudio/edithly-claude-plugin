---
name: create-timeline-story
description: "Create chronological timeline visuals. Best for: Historical events, project milestones, chronological facts."
---

# Create Timeline

Use this skill when the user wants a **timeline_story** visual.

## When to choose

Best for: Historical events, project milestones, chronological facts

Display modes: scroll, one_page
Cost: 1 credit(s)
Render tool: `create_visual`

## Process

1. Gather concrete content for this type.
2. Call `get_visual_schema("timeline_story")` and copy the example.
3. Fill with real content.
4. Call `create_visual(design_json, output_format="pdf", page_size="A4")`. Omit `save_path` unless the user explicitly asks to save a local file.
5. Return only `view_url` and `visual_id` from the tool. Never mention filenames, local paths, or PDF/PNG file cards unless the user explicitly asked to export/download.

## Type guidance

Use this visual type for historical events, project milestones, or chronological sequences.

Content rules:
- 6-12 timeline items; strictly chronological (oldest first)
- Each item: specific date or period, title (max 8 words), 1-2 sentence context
- Include cause-and-effect connections; mix macro (years) and micro (specific dates)
- Highlight 2-4 high-importance turning points when the source supports them
- Use era or phase grouping when the chronology has clear periods
- date field: "1969", "1969-1972", or "March 1969"
- Set `recommended_layout` in timeline content using:
  - `roadmap` for future-focused plans
  - `parallel_tracks` for 2-3 categories evolving together
  - `era_chapters` for 2+ clear eras
  - `horizontal_milestones` for 7 or fewer short milestones
  - `featured_turning_points` for timelines dominated by major pivots
  - `compact_chronicle` for 10+ very short events
  - `story_path` for journey-style narratives
  - otherwise `alternating_vertical`
- Do not emit pixel coordinates or manual geometry

Layout: hero_section → timeline (all items in one section) → optional callout for key insight

Prompt: call get_visual_schema("timeline_story"), call create_visual(output_format="pdf", page_size="A4")

## Rules

- Never invent or display a local filename/path (e.g. `*.pdf`). Prefer the interactive `view_url`.
- Never invent URLs or ids.
- Do not show raw design_json unless asked.
