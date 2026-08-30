# AGENTS.md

Instructions for agents working in this repository.

## Automatic checks

**Do not run typechecking or linters unless you are explicitly asked to.**

That includes, among others:

- `pnpm astro check` / `astro check`
- `tsc`, `tsc --noEmit`, `pnpm packages:typecheck`
- `eslint`, `pnpm lint`, or any other lint command
- `pnpm test` / `vitest` unless explicitly requested

Reason: these commands are slow in this project and rarely tell the agent anything that `ReadLints` on the edited files would not. Trust `ReadLints` and manual inspection unless the user asks otherwise.

If the user says something like "check types", "run the typecheck", "run the tests", "lint the project", or equivalent, then you should run them.

## Package manager

Always use `pnpm` unless a `bun.lock` exists in the subpackage (then use `bun`). Never `npm`.
