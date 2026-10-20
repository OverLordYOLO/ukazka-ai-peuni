# 0001: Record architecture decisions as ADRs

- **Status:** Accepted
- **Date:** [YYYY-MM-DD]

## Context
Agents start every session without memory of previous ones. Without a written reason behind a decision, an agent (or a new teammate) may "improve" the code by undoing a choice that was made deliberately.

## Options considered
1. Keep the reasons in chat history or in people's heads. These are lost between sessions.
2. Put all the reasoning into DESIGN.md. It grows too large, and its history gets mixed with its current state.
3. One short file per decision in `docs/decisions/`.

## Decision
Option 3. DESIGN.md describes the current state and links to the ADRs for the *why*.

## Consequences
- Each significant choice costs about 5 minutes of writing. The `adr` skill makes the agent do it.
- An ADR is never edited after it is accepted. A new ADR supersedes it instead.
