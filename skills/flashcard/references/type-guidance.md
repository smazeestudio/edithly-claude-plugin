# Flashcard / MCQ Deck

Use this visual type for MCQ quizzes, vocabulary, Q&A study cards, or definition drills.
Each flashcard section becomes a separate deck tab in the rendered output.

Content rules:
- 1+ flashcard sections; 15-30 cards total across all decks
- front: question or term — max 15 words; back: direct answer — max 40 words
- No yes/no fronts — use "what", "how", "why", "explain"
- MCQ format: include A/B/C/D options in front, correct answer + reason in back
- Group related cards into sections (each section = one deck tab)

Prompt: call get_visual_schema("flashcard"), keep component_type "flashcard" for every section, call create_visual(output_format="pdf", page_size="A4")
