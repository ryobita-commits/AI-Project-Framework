# Shared Conventions

## General

- Work from repository state, not memory.
- Make assumptions explicit.
- Default to planning before non-trivial execution.
- Do not write outside your role's allowed area.
- Record findings instead of silently working around them.
- Prefer the simplest change that solves the real problem.
- Challenge your own approach before presenting it as done.

## Documentation

- Use Markdown.
- Keep one topic per file where practical.
- Add dates in `YYYY-MM-DD` format.
- Keep `tasks/todo.md` current during execution.
- Record reusable correction rules in `tasks/lessons.md`.

## Planning

- Scope changes require PM review.
- Major changes require a meeting note or change request.
- Meeting notes must capture dissent, not just conclusions.
- Any task with 3 or more meaningful steps should start with a written plan.
- If assumptions break, stop and re-plan instead of pushing through stale steps.
- For implementation work, create a design/spec step before code.
- Use exact file paths and explicit verification steps in implementation plans.

## Execution

- One task, one clearly scoped output.
- Use parallel or delegated work only when ownership and scope are clear.
- Add or update tests when fixing defects.
- Update state files when work changes priorities or status.
- Start bug fixing from logs, reproductions, or failing tests whenever available.
- Use TDD by default for behavior changes when practical.
- Review spec compliance before code quality when a task has formal requirements.

## Logging

- Add a session report for significant work.
- Record meaningful findings in `feedback/`.
- Record accepted improvements in `worklog/improvements/`.
- Do not call work complete without verification evidence.
