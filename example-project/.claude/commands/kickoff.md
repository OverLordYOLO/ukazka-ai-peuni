---
description: Plan a new project with the user. Interview them, then fill in PROJECT.md, DESIGN.md, the first ADR, ROADMAP.md and the CLAUDE.md placeholders.
argument-hint: <short description of the project idea>
---

Help the user start a new project. Their idea: $ARGUMENTS

Do not write application code in this command. Stop and wait for the user at every ⏸.

1. **Interview.** Ask questions in small batches (at most 5 at a time) to fill in [docs/PROJECT.md](../../docs/PROJECT.md): the goal, the problem, the users, the deliverables, the constraints (deadline, budget, people), the requirements and metrics, and what is out of scope. Point out important areas the user has not mentioned. ⏸
2. **Write docs/PROJECT.md.** Show a 5-line summary. ⏸
3. **Tech stack.** Propose 2–3 options that fit the constraints, with trade-offs, and recommend one. Use the `researcher` agent to check current versions and that each library is maintained. ⏸
4. **Design.** Fill in [DESIGN.md](../../DESIGN.md): the components, directory layout, data model and interfaces. Record the stack choice as ADR 0002 with the `adr` skill. ⏸
5. **Roadmap.** Break the work into phases and steps in [ROADMAP.md](../../ROADMAP.md). Each step must fit in one session and have a verifiable "done when". Tick off the Phase 0 items you have completed. ⏸
6. **Wire up.** Replace the placeholders in CLAUDE.md (the project name, the one-line description, the commands), README.md and docs/TESTING.md. Add the project's test and lint commands to `allow` in `.claude/settings.json`. Delete what doesn't apply, e.g. `.mcp.json` if there is no browser UI.
7. Summarize what you created and suggest running `/next`.
