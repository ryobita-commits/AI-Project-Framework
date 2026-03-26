# Session Bootstrap Template

Use this file to convert the initial answers into the first live project package.

## Inputs

- `bootstrap/project-type-router.md`
- matching file under `bootstrap/questions/`
- matching file under `bootstrap/output-templates/`
- `bootstrap/initial-answers.md`
- `PROJECT_sample.md`
- files under `samples/`

## Outputs

- `PROJECT.md`
- `CURRENT_STATE.md`
- `STATUS.md`
- `plans/meeting-notes/<date>-kickoff.md`
- `issues/backlog.md`
- first live spec under `specs/features/` or equivalent project work package

## Transformation Rules

- `_sample` files are examples only and must not become the canonical source of truth
- prefer concise, project-specific wording over generic placeholders
- unresolved choices must be copied into `Open Questions` in `PROJECT.md`
- if the project type is not `game`, adapt feature terminology to the domain
- select the active role set from `config/agents.yaml#project_type_profiles`

## Required Extraction

- project type
- title
- pitch
- primary goal
- main deliverable
- first milestone
- top risks
- top open decisions
- initial role selection

## Kickoff Meeting Minimum Content

- decision question
- shared goal
- options considered
- advisor positions
- human input
- decision
- next actions
