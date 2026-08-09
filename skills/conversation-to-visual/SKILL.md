---
name: conversation-to-visual
description: "Summarize the current conversation into an Edithly visual."
---

# Conversation to visual

Use when the user asks to turn this chat, discussion, or meeting notes into a visual.

## Process

1. Summarize decisions, action items, topics, and concrete facts from the conversation.
2. Select visual type (`get_visual_types` if unclear). Common picks: `action_plan`, `mindmap`, `infographic`, `presentation`, `one_pager`.
3. Build `design_json` from `get_visual_schema` example.
4. Call `create_visual` (omit `save_path` unless the user asks to save locally) and return only `view_url` and `visual_id`.
