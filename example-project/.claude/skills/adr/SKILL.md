---
name: adr
description: Records an architecture decision (ADR) in docs/decisions/. Use when a significant, hard-to-reverse choice has been made (tech stack, database, auth approach, a major library, API style, deployment target) or when the user asks to record or document a decision.
---

# Record an architecture decision

1. List `docs/decisions/` and take the next free number (4 digits, zero-padded, e.g. `0003`).
2. Create `docs/decisions/NNNN-short-kebab-title.md` with the structure from [template.md](template.md).
3. Fill it in from the conversation: the context, the options considered (at least 2), the decision, and the consequences. Keep it under one page. If something is unknown, ask the user instead of making it up.
4. If it replaces an older decision, change the older ADR's status to `Superseded by NNNN`. Don't edit anything else in it.
5. Add a row to the index in `docs/decisions/README.md`.
6. If the decision changes the stack or the structure, update the matching row or section in DESIGN.md and link the ADR there.
