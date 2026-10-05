# MCP workflow

1. `get_visual_types`
2. `get_visual_schema(visual_type)` — guidance only
3. `create_visual(content, visual_type)` — backend ContentWorkflow (same as app)
   - Sales GTM: also pass `playbook_slug` + prospect fields
   - Or `create_image` / `create_solvesheet`
4. Optional: `get_visual`, `update_visual`, `export_visual`
5. `get_credit_balance` when needed

Never invent URLs or visual ids.
Never hand-build `design_json` sections for `create_visual`.
