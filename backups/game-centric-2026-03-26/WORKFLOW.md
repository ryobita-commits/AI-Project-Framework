# WORKFLOW

## Goal

Run project development through explicit repository state, not conversational memory.

## Session Bootstrap

Every AI should read the following before acting:

1. `README.md`
2. `PROJECT.md`
3. `CURRENT_STATE.md`
4. `STATUS.md`
5. `governance/source-of-truth.md`
6. `config/agents.yaml`
7. `config/authority.yaml`
8. `config/workflows.yaml`
9. `agents/AGENTS_INDEX.md`
10. `agents/shared/conventions.md`
11. `agents/shared/definition-of-done.md`
12. the agent's own role file
13. the target spec, task, and relevant decisions

## Project Bootstrap

For a new project:

1. Ask what is being created
2. Route to the correct question file under `bootstrap/questions/`
3. Record answers in `bootstrap/initial-answers.md`
4. Use `bootstrap/session-bootstrap_template.md` to fill `PROJECT.md` and startup files
5. Use `_sample` files as concrete references, not as the live source of truth
6. Hold the first planning meeting and save it under `plans/meeting-notes/`

## Standard Delivery Flow

1. Clarify the target in `PROJECT.md` or `specs/`
2. Record current priority in `CURRENT_STATE.md`
3. Execute only within the role contract
4. Write findings to `feedback/` when issues or improvement opportunities are found
5. Route triage to PM AI
6. Update plans before implementation when change approval is required
7. Add implementation and verification logs to `worklog/`

## Planning Meeting Flow

Use the PM council when discussing product direction, scope, prioritization, or major tradeoffs.

1. PM moderator frames the decision question and success criteria
2. PM analyst summarizes facts and options
3. PM advocate argues for upside and practical momentum
4. PM critic searches for failure modes, assumptions, and hidden costs
5. Human participants add intent, constraints, and preferences
6. PM moderator captures the final decision and follow-up actions

Meeting outputs must be recorded under `plans/meeting-notes/`.

## Improvement Loop

1. Any role can detect a problem, gap, or improvement
2. Record it under `feedback/inbox/`
3. PM triage classifies severity and approval path
4. If accepted, update plan files and assign an owner
5. Execute the fix or improvement
6. Verify and log the result
7. Move the record to the appropriate `feedback/` state

## Human Approval Rule

Human approval is required for:

- major scope changes
- core loop changes
- progression or economy changes
- save data changes
- release-risking changes
- changes above the authority threshold
