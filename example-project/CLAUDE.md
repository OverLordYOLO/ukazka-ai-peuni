# [Project name]

[One sentence: what this project is and who it is for.] Full brief: [docs/PROJECT.md](docs/PROJECT.md).

## Every session
1. Read [ROADMAP.md](ROADMAP.md) first: the current focus, the next unchecked step, and "Notes for next session".
2. Work on one roadmap step at a time. When it is done, tick it off (`- [x] ~~step~~`) and update the notes.
3. `/next` runs this loop for you. `/wrap-up` updates the roadmap before you end the session.

## Commands
- `[install command]`: install dependencies
- `[dev command]`: run locally
- `[test command]`: run the fast test suite
- `[lint command]`: lint, format check and typecheck

## Hard rules
- Run lint and tests before you say a task is done. Never claim that tests pass without running them.
- Never weaken or delete a test to make it pass. Fix the code, or ask.
- Before adding a dependency, check that it exists, is maintained and is the right package. Say why it is needed.
- Never read or print `.env`. Secrets live in `.env`, and the shape of that file is in `.env.example`.
- Do not commit or push unless the user asks.

## Read when needed (don't load these up front)
| When you are... | Read |
|---|---|
| deciding where code goes, adding a module, changing an interface | [DESIGN.md](DESIGN.md) |
| writing or reviewing code | [docs/CONVENTIONS.md](docs/CONVENTIONS.md) |
| writing tests or debugging a failing one | [docs/TESTING.md](docs/TESTING.md) |
| wondering "why is it done this way?" or about to make a big choice | [docs/decisions/](docs/decisions/) |
| unsure about the goal, scope or requirements | [docs/PROJECT.md](docs/PROJECT.md) |

## Subagents
Defined in [.claude/agents/](.claude/agents/). Read the definition of the one you use; don't repeat its rules in the brief.

| Agent | Model | Use it for |
|---|---|---|
| `code-reviewer` | opus | Final check of the diff before a roadmap step counts as done. |
| `test-runner` | haiku | Full or E2E suite runs and failure triage. Run quick single tests yourself. |
| `researcher` | sonnet | Current library docs, versions, and whether a package really exists. |
