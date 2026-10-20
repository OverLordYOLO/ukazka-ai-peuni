# Conventions

Read this when you write or review code. Only rules that a linter or formatter can't enforce belong here. Put everything else in the linter config.

## Code
- Follow the existing code. Match the naming, structure and comment density of the surrounding files.
- [Naming: e.g. `camelCase` functions, `PascalCase` components and types, `kebab-case` file names]
- [Structure: e.g. one module per folder in `src/`, with a public API through `index.ts` only]
- [Errors: e.g. throw typed errors in the domain layer and turn them into HTTP responses only in the API layer]
- Comments explain *why*, not *what*. Delete dead code; don't comment it out.
- No secrets, URLs of real environments, or personal data in the code or the tests.

## Dependencies
- Prefer the standard library and what is already installed.
- Before you add a package, check that it is the right package (watch for name typos and look-alikes), that it is maintained, and what its license is. Mention it in the commit message.

## Git
- One roadmap step per branch: `feature/<short-name>`, `fix/<short-name>`.
- Small commits. Message format: `<type>: <what and why>`, where type is `feat`, `fix`, `refactor`, `test`, `docs` or `chore`.
- Review the diff before every commit (`git diff --staged`).
- `main` must always build and pass the tests.
