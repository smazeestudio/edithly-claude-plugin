---
name: check-credits
description: "Check Edithly visual credit balance and per-tool costs."
---

# Check credits

Use when the user asks about credits, balance, cost, or whether they can generate.

## Process

1. Call `get_credit_balance`.
2. Report `balance`, costs (`create_visual` = 1, `create_solvesheet` = 1, `create_image` = 4), and can_* flags.
