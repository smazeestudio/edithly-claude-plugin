# Slide Presentation

Use this visual type for slide decks, training material, or talks. Always use page_size="16:9".

Content rules:
- 12-15 sections (each = 1 slide); max 3 bullet points per list slide
- Slide 1: jumbotron (hook); Slide 2: agenda list; Middle: one concept per slide
- Second-to-last: key takeaways list; Last: CTA or summary
- Component guide: explanation → text_block, data → stats_grid, code → code_block, quote → quote/callout

Prompt: call get_visual_schema("presentation"), call create_visual(output_format="pdf", page_size="16:9")
