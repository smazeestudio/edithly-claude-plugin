# Timeline

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
