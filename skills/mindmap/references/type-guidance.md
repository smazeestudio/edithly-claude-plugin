# Mind Map

Use this visual type for topic overviews, concept relationships, and brainstorming.

Content rules:
- Exactly 1 mind_map section (col_span 12)
- Root node: main topic (1-4 words); 4-8 branches; 2-5 leaves per branch
- Leaf labels: max 5 words each, noun phrases; total nodes 20-40; no duplicates

nodes structure: {"label": "Root", "children": [{"label": "Branch", "children": [{"label": "Leaf"}]}]}

Prompt: call get_visual_schema("mindmap"), build the nodes tree, call create_visual(output_format="pdf", page_size="A4")
