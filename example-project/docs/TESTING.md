# Testing

When an agent writes most of the code, tests are the main proof that the code works. They are also the feedback loop that lets the agent fix its own mistakes.

## How to run
| What | Command | When |
|---|---|---|
| Unit (fast) | `[test command]` | after every change |
| A single file | `[test command] path/to/file` | while working on it |
| E2E | `[e2e command]` | before a roadmap step counts as done (use the `test-runner` agent) |

[E2E prerequisites, e.g. `docker compose up -d` first.]

## Layers
- **Unit:** pure logic, no network or database. Tests live in `tests/unit/` (or next to the code; pick one in DESIGN.md).
- **Integration:** a module together with a real database or API (in a container).
- **E2E:** the whole app in a browser, as a user uses it. The Playwright MCP server in `.mcp.json` lets the agent drive the browser.

## Rules for AI-written tests
- Test **behavior** (inputs and outputs, what the user sees), not implementation details.
- If possible, write the test **before** the code (TDD) and watch it fail first.
- When a test fails, fix the code. Change the test only if the test itself is wrong, and say so explicitly.
- Don't mock the thing under test. Mock only the boundaries (network, clock, randomness).
- Every bug fix comes with a test that would have caught the bug.
- "Tests pass" means you ran them in this session and saw the output.
