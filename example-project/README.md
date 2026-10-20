# [Project name]

[What it does, who it is for, and a screenshot or demo link.]

## Getting started
```bash
[install command]
cp .env.example .env   # then fill in the values
[dev command]
```

## Tests
```bash
[test command]
```

---

## Working on this repo with AI agents

This repo is set up for AI-assisted development (Claude Code, but most of it works with any agent).

### File map
```text
CLAUDE.md                 Loaded into every session. Short: essentials and links to everything else.
AGENTS.md                 Same role for other tools (Codex, Cursor, Copilot...). It points to CLAUDE.md.
ROADMAP.md                The plan as checkboxes, plus "Notes for next session". Lets a new session resume the work.
DESIGN.md                 How the system is built: stack, components, data model, interfaces.
docs/
  PROJECT.md              Goal, problem, users, constraints, requirements. The "plan" phase.
  CONVENTIONS.md          Code style, naming, git workflow, dependency policy.
  TESTING.md              Test strategy, how to run tests, rules for AI-written tests.
  decisions/              Architecture Decision Records (ADRs): why things are the way they are.
.claude/
  settings.json           Shared permissions: what the agent may do without asking, and what it may never do.
  agents/                 Subagents: code-reviewer (opus), test-runner (haiku), researcher (sonnet).
  commands/               Slash commands: /kickoff, /next, /wrap-up.
  skills/adr/             A skill with a supporting file. Claude loads it on its own when a decision is made.
.mcp.json                 Example MCP server (Playwright browser). Delete it if you don't need it.
.env.example              The shape of .env, without the secrets. The real .env is gitignored.
```

### Why CLAUDE.md is short
Everything in CLAUDE.md is loaded into **every** session and takes up context whether it is needed or not. So it contains only:
- what the project is (one line),
- how to run, test and lint it,
- the hard rules,
- **a map of where to find the rest** ("Read when needed").

The agent reads DESIGN.md, TESTING.md or the ADRs only when the task needs them. It knows where they are from the map.

There are two ways to reference a file from CLAUDE.md:
| Syntax | When it is loaded | Use for |
|---|---|---|
| `[DESIGN.md](DESIGN.md)` (a normal link) | Only when the agent decides to read it | Most docs |
| `@docs/CONVENTIONS.md` (an import) | Always, at session start, as if it were pasted in | Short files that every session really needs |

What does **not** belong in CLAUDE.md: things the agent can find in the code (the file list, function signatures), long tutorials, history ("we used to..."), and anything that is only true for one task.

### Workflow
1. **`/kickoff <idea>`**: the agent interviews you and fills in PROJECT.md, DESIGN.md, the first ADR and ROADMAP.md. No code is written yet.
2. **`/next`**: the agent picks the next roadmap step, proposes a plan (you approve it), implements and tests it, runs `code-reviewer`, and ticks the step off.
3. **`/wrap-up`**: before you close the session, the agent updates "Notes for next session" in ROADMAP.md.
4. A new session starts by reading ROADMAP.md, so nothing is lost. Repeat step 2.

### Personal (not committed) files
- `CLAUDE.local.md`: your own notes and preferences for this project.
- `.claude/settings.local.json`: your own permissions.
- `~/.claude/CLAUDE.md`, `~/.claude/agents/`, `~/.claude/commands/`: personal settings for all your projects.

### Next steps
- **Hooks** in `.claude/settings.json`, e.g. run the formatter after every edit (deterministic, unlike instructions in a prompt).
- **CI** with an agent, e.g. an automatic review of every pull request.
- **Worktrees** for running several agents in parallel without collisions.
