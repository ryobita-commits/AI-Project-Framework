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
12. `tasks/todo.md`
13. `tasks/lessons.md`
14. the agent's own role file
15. the target spec, task, and relevant decisions

Before implementing any non-trivial work, create or refresh the plan in `tasks/todo.md`.

## Project Bootstrap

For a new project:

1. Ask what is being created
2. Route to the correct question file under `bootstrap/questions/`
3. Record answers in `bootstrap/initial-answers.md`
4. Use `bootstrap/session-bootstrap_template.md` to fill `PROJECT.md` and startup files
5. Use `_sample` files as concrete references, not as the live source of truth
6. Hold the first planning meeting and save it under `plans/meeting-notes/`
7. Create initial `tasks/todo.md` and `tasks/lessons.md`

## Planning Default

Enter a planning step first for any task that has three or more steps, architectural impact, or unclear scope.

1. Write a checkable plan in `tasks/todo.md`
2. Verify the repo state and latest priorities before implementation
3. Re-plan immediately if new findings change the approach
4. Write specs before implementation when ambiguity is high

## Design Before Code

Adopt the `superpowers` rule that implementation follows an explicit design step.

1. Explore the current repo state before proposing changes
2. Ask clarifying questions when intent, constraints, or success criteria are unclear
3. Present options and tradeoffs before committing to an approach
4. Write or update a design spec before implementation for any non-trivial change
5. Do not treat "simple" tasks as exempt from design; the design may be brief, but it must be explicit

## Task Management

Use `tasks/todo.md` as the live execution tracker.

1. Write the plan before implementation
2. Mark items complete as work progresses
3. Record verification steps before declaring done
4. Add a short review section with tests run, remaining risks, and follow-up actions

Use `tasks/lessons.md` to capture project-specific rules after corrections or preventable mistakes.

For implementation-heavy work, also create a dedicated plan document under `docs/plans/` using `templates/implementation-plan.md`.

## Standard Delivery Flow

1. Clarify the target in `PROJECT.md` or `specs/`
2. Record current priority in `CURRENT_STATE.md`
3. Create or refresh the design or spec document
4. Create or refresh `tasks/todo.md`
5. Write or update the implementation plan under `docs/plans/` when the task is non-trivial
6. Execute only within the role contract
7. Write findings to `feedback/` when issues or improvement opportunities are found
8. Route triage to PM AI
9. Update plans before implementation when change approval is required
10. Add implementation and verification logs to `worklog/`

## TDD Default

Adopt `test-driven-development` as the default for new behavior and bug fixes when practical.

1. Write the failing test first
2. Run it and confirm it fails for the expected reason
3. Write the minimal implementation to pass
4. Re-run the focused test and then broader relevant checks
5. Refactor only after green

If TDD is not practical, record why in `tasks/todo.md`.

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
7. Capture preventive rules in `tasks/lessons.md` when the issue exposed a reusable lesson
8. Move the record to the appropriate `feedback/` state

## Verification Before Done

Never mark work complete without evidence.

1. Run applicable tests, checks, or reproductions
2. Review the diff against the stated plan
3. Record the verification result in `tasks/todo.md` and `worklog/`
4. Ask whether the change would meet senior review standards

For behavior changes, verification should include:

1. The focused test that failed before the fix
2. The focused test passing after the fix
3. Broader regression checks or rationale for why they were not run

## Subagent And Parallel Work

When the runtime supports subagents, use them to keep the main context focused.

1. Offload bounded research or verification tasks
2. Use one owner per subtask
3. Prefer spec-compliance review before code-quality review
4. Prefer parallel analysis for independent questions
5. Do not use delegation to avoid thinking through the main plan

## Autonomous Bug Fixing

For accepted bug work:

1. Reproduce the issue or inspect failing tests and logs first
2. Gather evidence and trace the root cause before proposing fixes
3. Compare against working references or prior behavior when available
4. Fix the root cause, not only the symptom
5. Minimize context switching and avoid asking for hand-holding when the repository already contains enough evidence
6. Add or update regression coverage when practical

## Human Approval Rule

Human approval is required for:

- major scope changes
- core experience or business model changes
- pricing, policy, or stakeholder commitment changes
- state or data model changes
- release-risking changes
- changes above the authority threshold
