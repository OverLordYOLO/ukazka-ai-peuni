---
description: Resume work. Take the next unchecked ROADMAP step, plan it, implement it, test and review it, then tick it off.
argument-hint: [optional: the step to work on]
---

1. **Orient.** Read [ROADMAP.md](../../ROADMAP.md), including "Notes for next session". Work on this step: $ARGUMENTS. If no step is given, take the first unchecked step in the current phase. Run `git status`. If the working tree has uncommitted changes, ask the user what to do with them before you continue.
2. **Plan.** Read only the docs this step needs (see "Read when needed" in CLAUDE.md). Write a short plan: the files you will touch, the approach, how you will verify it, and open questions. ⏸ Wait for the user's approval.
3. **Implement**, with tests (see [docs/TESTING.md](../../docs/TESTING.md)). Run quick tests yourself. Use the `test-runner` agent for the full or E2E suite.
4. **Review.** Run the `code-reviewer` agent on the diff. Fix all BLOCKING findings. List the SUGGESTIONS for the user.
5. **Update the docs.** In ROADMAP.md, tick off the step (`- [x] ~~step~~`), add any new steps you discovered, and update "Notes for next session". If you made a significant decision, record it with the `adr` skill. If the design changed, update DESIGN.md.
6. **Report:** what changed, how it was verified (commands and results), and a proposed commit message. Don't commit unless the user asks.
