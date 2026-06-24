# AGENTS.md

## Operating model

This repository is managed through a strict loop:

1. Product Owner approves direction and business decisions.
2. Project Manager creates or updates a GitHub Issue with scope, constraints, acceptance criteria and required evidence.
3. Codex executes only that issue in a dedicated branch.
4. Codex opens a Pull Request and posts a structured completion report.
5. Project Manager reviews the diff, tests, UX evidence, security and documentation.
6. Codex addresses review comments in the same branch.
7. Project Manager approves merge or rejects the result.
8. Only after merge may the next implementation issue be activated.

## Hard rules for Codex

- Do not implement work that is not described in an approved Issue.
- Do not expand scope silently.
- Do not make irreversible product decisions without recording them in `docs/DECISIONS.md`.
- Use branch names `codex/T-XXX-short-slug`.
- One task = one focused branch = one Pull Request.
- Never commit secrets, personal data, production credentials or real customer data.
- Update `docs/CURRENT_STATE.md` and `docs/TASKS.md` in every implementation Pull Request.
- Add tests appropriate to the change.
- Run all available quality checks before reporting completion.
- Do not claim completion without evidence.
- During Discovery, do not create application code unless the Product Gate is explicitly marked `PASSED`.

## Required Pull Request report

Every Codex Pull Request must contain:

- Issue/task ID.
- What changed.
- What intentionally did not change.
- Files and modules affected.
- Decisions made and where recorded.
- Tests and checks run, with results.
- Screenshots or recordings for visible UI changes.
- Database migration notes, when applicable.
- Security/privacy impact.
- Known limitations and follow-up tasks.
- Exact instructions for local verification.

## Review outcome

The Project Manager uses one of three outcomes:

- **APPROVE** — acceptance criteria met, safe to merge.
- **REQUEST CHANGES** — concrete defects or missing evidence.
- **REJECT / RE-SCOPE** — implementation solves the wrong problem or violates product boundaries.
