# Bootstrap

This folder contains the routing logic and question sets used to initialize a new project.

## Flow

1. Ask what kind of project the user wants to run.
2. Select the matching question set.
3. Record the answers in `bootstrap/initial-answers.md`.
4. Use `bootstrap/bootstrap-checklist.md` and `bootstrap/session-bootstrap_template.md` to produce the first live files.
5. Use samples under `samples/` when concrete examples are helpful.

## Core Files

- `project-type-router.md`: classifies the project
- `questions/`: project-type-specific starting questions
- `initial-answers.md`: stores the first answer set
- `bootstrap-checklist.md`: defines the initialization sequence
- `session-bootstrap_template.md`: defines how answers become canonical files
- `session-bootstrap_sample.md`: concrete example of a successful bootstrap
- `output-templates/`: recommended first live files by project type
