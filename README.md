# AI Project Development Framework

This repository is a starter layout for AI-assisted project development with explicit role ownership, model routing, discussion advisors, and feedback-driven improvement loops.

## Purpose

The framework is designed so each AI agent can rebuild shared context from repository files instead of relying on memory.

## Source Of Truth

When files disagree, resolve them in this order:

1. `PROJECT.md`
2. `CURRENT_STATE.md`
3. approved files under `plans/change-requests/`
4. files under `docs/decisions/`
5. role contracts under `agents/`
6. feature specs under `specs/features/`
7. session logs under `worklog/`

See `governance/source-of-truth.md` for the full policy.

## Key Files

- `PROJECT.md`: what the project is and is not
- `CURRENT_STATE.md`: current progress, priorities, blockers, active work
- `STATUS.md`: concise human-readable status dashboard
- `FRAMEWORK_STATUS.md`: framework-level readiness summary
- `WORKFLOW.md`: operating rules for planning, execution, feedback, and release
- `config/agents.yaml`: maps each role to a provider, model, reasoning level, and permissions
- `config/authority.yaml`: defines which issues can be auto-approved by PM AI and which require human approval
- `config/workflows.yaml`: defines the detect-to-fix feedback loop across planning, implementation, testing, and release
- `agents/AGENTS_INDEX.md`: role catalog including PM advisors for planning meetings
- `bootstrap/project-type-router.md`: selects the right initial question set for the project type
- `bootstrap/output-templates/`: recommended first live files for each project type
- `samples/`: concrete examples for project bootstrap
- `REPOSITORY_SETUP.md`: GitHub publishing checklist and local setup steps

## Operating Principle

Every agent should reconstruct context in this order before acting:

1. `README.md`
2. `PROJECT.md`
3. `CURRENT_STATE.md`
4. `STATUS.md`
5. `WORKFLOW.md`
6. `governance/source-of-truth.md`
7. `config/agents.yaml`
8. `config/authority.yaml`
9. `config/workflows.yaml`
10. `agents/AGENTS_INDEX.md`
11. `agents/shared/conventions.md`
12. `agents/shared/definition-of-done.md`
13. its own role contract under `agents/`

## Meeting Mode

Planning and product meetings can include:

- a PM AI that moderates, structures decisions, and owns the outcome
- advisor AIs with distinct personalities and analysis styles
- one or more human participants

The default advisor set is:

- `pm_critic`: critical and risk-seeking
- `pm_advocate`: opportunity-seeking and forward-driving
- `pm_analyst`: evidence-driven and integrative

See `agents/pm/` and `WORKFLOW.md` for the discussion protocol.

## Generic Bootstrap

This framework can be used for games, apps, planning workshops, sales planning, and general projects.

Start with:

1. `bootstrap/project-type-router.md`
2. the matching question file in `bootstrap/questions/`
3. `bootstrap/initial-answers.md`
4. `bootstrap/session-bootstrap_template.md`
5. `PROJECT.md`
6. a sample file under `samples/` if an example is useful

## Publishing

Before publishing to GitHub, review:

1. `FRAMEWORK_STATUS.md`
2. `REPOSITORY_SETUP.md`
3. `LICENSE`
