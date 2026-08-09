# Study Aids

Use this visual type for a digital study workbook: overview + explanation + recall + practice + review.

Content rules:
- Aim for 6-10 visible sections, hard max 14
- Must include: 1 hero, 1 mind_map, 1 flashcard section, 1 checklist review section
- Must include 1 explanation zone: accordion or tabs
- Include `fill_blanks` and `match_pairs` in every study_aids workbook; add `jumble_words` when the topic benefits from term recall
- mind_map: 4-6 branches, 2-4 leaves each; flashcard: 10-20 cards minimum
- accordion/tabs: 6-10 key concepts with short explanations

Prompt: call get_visual_schema("study_aids"), call create_visual(output_format="pdf", page_size="A4")
