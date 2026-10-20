---
description: End the session cleanly. Update ROADMAP.md so the next session, or a colleague, can resume without the chat history.
---

1. Run `git status` and `git diff` to see what changed in this session.
2. Update [ROADMAP.md](../../ROADMAP.md):
   - Tick off the finished steps (`- [x] ~~step~~`).
   - Mark the unfinished step with 🚧 and write where you stopped.
   - **Rewrite** (don't append to) "Notes for next session", in at most 10 lines: the current state, the exact next action, open questions, and pitfalls you discovered (a flaky test, a non-obvious setup step).
3. Check whether CLAUDE.md, DESIGN.md or docs/ are now out of date (new commands, a changed structure). Fix the small things. List the bigger ones as roadmap steps.
4. Propose a commit message. Don't commit unless the user asks.
