# Project Workflow

## Principle

GitHub is the control plane. Chat is used for discussion; repository artifacts record decisions and execution.

## Lifecycle of a task

### 1. Discovery

The Project Manager researches the problem, records assumptions and identifies missing business data.

Output may include:

- market findings;
- user journey;
- domain model;
- open questions;
- decision options;
- product gate criteria.

No product code is written during Discovery unless explicitly approved.

### 2. Task preparation

The Project Manager creates one GitHub Issue with:

- task ID (`T-XXX`);
- problem and user value;
- current context;
- in-scope work;
- out-of-scope work;
- constraints;
- acceptance criteria;
- required tests;
- required evidence;
- documentation updates;
- dependencies and blockers.

A task is not ready if the acceptance criteria are subjective or necessary business data are missing.

### 3. Owner decision when required

Issues involving price policy, brand, legal commitments, customer promises, user experience trade-offs or business process changes are marked as waiting for Product Owner decision.

Codex must not decide these questions by implementation.

### 4. Codex execution

Codex:

1. reads `AGENTS.md`, the Issue and relevant docs;
2. creates `codex/T-XXX-short-slug`;
3. confirms the scope in a short issue comment;
4. implements only the approved scope;
5. adds or updates tests;
6. updates project documentation;
7. runs all checks;
8. opens a Pull Request;
9. provides the required report.

### 5. Manager review

The Project Manager checks:

#### Product correctness

- solves the stated user problem;
- matches product principles;
- does not introduce fake certainty;
- handles error and incomplete-data states;
- avoids dark patterns.

#### Scope

- all acceptance criteria are covered;
- no hidden expansion;
- deferred items remain deferred.

#### Engineering

- architecture is proportionate;
- data model and migrations are safe;
- failures are visible;
- permissions are enforced server-side;
- personal data is minimized;
- tests cover important behavior;
- observability and recovery are adequate.

#### UX evidence

- mobile and desktop states;
- loading, empty, error and success states;
- keyboard and accessibility basics;
- screenshots or recordings;
- exact reproduction steps.

#### Documentation

- `CURRENT_STATE.md` reflects reality;
- `TASKS.md` is updated;
- decisions are recorded;
- setup instructions still work.

### 6. Review result

- `APPROVE`: merge allowed.
- `REQUEST_CHANGES`: Codex fixes in the same branch and posts a delta report.
- `RE-SCOPE`: PR is closed or converted to draft; manager rewrites the Issue.

### 7. Merge and state transition

Preferred strategy: squash merge with task ID in commit title.

After merge:

- the Issue is closed;
- `CURRENT_STATE.md` becomes authoritative;
- only then is the next implementation Issue activated.

## Efficiency rules

### Small vertical slices

Prefer a complete narrow capability over disconnected layers. Example:

- good: visitor completes a small navigator, receives useful result, and a structured case is created;
- bad: build all database tables, then all APIs, then all screens with no usable flow.

### One source for each concept

- product vision: `PRODUCT_VISION.md`;
- current truth: `CURRENT_STATE.md`;
- future work: Issues and `TASKS.md`;
- decisions: `DECISIONS.md`;
- implementation evidence: Pull Request.

### No silent assumptions

Every material assumption is either:

- confirmed by evidence;
- recorded as an assumption with validation plan;
- escalated to Product Owner.

### Evidence over narrative

A completion report without tests, screenshots, logs or reproduction steps is incomplete.

### Stop-the-line conditions

Codex stops and reports a blocker when:

- required business rule is unknown;
- implementation would create a legal or privacy commitment;
- acceptance criteria conflict;
- data migration could destroy information;
- external credentials or production access are required;
- the task would cross the Product Gate.

## Task template

```md
# T-XXX — Task title

## Problem

## User value

## Context

## In scope

## Out of scope

## Constraints

## Acceptance criteria

- [ ] ...

## Required tests

## Required evidence

## Documentation updates

## Dependencies / blockers
```

## Codex report template

```md
## Completion report — T-XXX

### Implemented

### Not implemented / intentionally deferred

### Files and modules

### Decisions

### Tests and checks

### UI evidence

### Security and privacy impact

### Known limitations

### Local verification

### Proposed follow-up
```
