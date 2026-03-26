# Source Of Truth Policy

## Purpose

Define which repository files are authoritative when information conflicts.

## Priority Order

1. `PROJECT.md`
2. `CURRENT_STATE.md`
3. approved change requests in `plans/change-requests/`
4. decision records in `docs/decisions/`
5. role contracts in `agents/`
6. feature specs in `specs/features/`
7. work logs in `worklog/`

## Rules

- Logs never override product definition.
- Code never silently overrides approved specs.
- If current execution diverges from docs, create feedback and triage it.
- If a decision changes architecture or scope, record it in both plan and decision layers.
- If a file is stale, update it or mark it stale explicitly.
