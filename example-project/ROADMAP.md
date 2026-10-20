# Roadmap

How to use this file:
- One checkbox is one step that fits in a single session and has a clear "done when".
- Mark a finished step `- [x] ~~step~~`, so it shows as crossed out. Mark the step in progress with 🚧.
- The agent reads this file at the start of a session (see CLAUDE.md) and updates it at the end (`/wrap-up`).
- If you use GitHub Issues instead, replace the steps with links to the issues. Keep "Current focus" and "Notes for next session".

## Current focus
Phase 0: Kickoff

## Notes for next session
_`/wrap-up` overwrites this section at the end of each session. Keep it to about 10 lines._
- State: the skeleton exists, and none of the placeholders are filled in yet.
- Next: run `/kickoff <your project idea>`.
- Open questions: none

## Phase 0: Kickoff (plan + architecture)
- [x] ~~Create the repo from the AI project skeleton~~
- [ ] Fill in [docs/PROJECT.md](docs/PROJECT.md). Done when: the user has approved the goal, scope and constraints.
- [ ] Choose the tech stack. Done when: ADR 0002 is in [docs/decisions/](docs/decisions/).
- [ ] Fill in [DESIGN.md](DESIGN.md). Done when: the components, interfaces and data model are described.
- [ ] Break the MVP into steps in Phase 2 below.
- [ ] Fill in the CLAUDE.md commands and the allow-list in `.claude/settings.json`.

## Phase 1: Foundation
- [ ] Scaffold the project (framework init, folder layout from DESIGN.md). Done when: `[dev command]` runs.
- [ ] Set up lint, format and typecheck. Done when: `[lint command]` passes.
- [ ] Set up a test framework with one real test. Done when: `[test command]` is green.
- [ ] Set up CI to run lint and tests on every push. Done when: the first run is green.

## Phase 2: MVP
- [ ] [Feature step]. Done when: [observable result + test]
- [ ] [Feature step]. Done when: [observable result + test]

## Phase 3: User testing and release
- [ ] Have 3 people who did not build the app use it. Write down where they got stuck. Done when: the findings are in the backlog below.
- [ ] Fix the blocking findings.
- [ ] Release v0.1.

## Backlog / ideas
_Not planned yet. Move an item into a phase when it becomes a priority._
- [idea]
