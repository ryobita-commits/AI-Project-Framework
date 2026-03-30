# Superpowers Mapping

## Purpose

Map the `obra/superpowers` workflow into this framework so later AI sessions inherit the same operating model.

## Upstream References

- Repository: `https://github.com/obra/superpowers`
- Codex install guide: `https://raw.githubusercontent.com/obra/superpowers/refs/heads/main/.codex/INSTALL.md`

## Mapped Workflow

### 1. Brainstorming -> Design Approval

- Before implementation, define or refine the design in `docs/product/`, `docs/design/`, or a design spec file.
- Ask clarifying questions when the request is ambiguous.
- Present options and tradeoffs before selecting an approach.
- Do not implement until the design is explicit enough to plan.

Recommended output:
- `docs/design/<date>-<topic>-design.md`

Template:
- `templates/design-spec.md`

### 2. Writing Plans -> Implementation Plan

- After design approval, write a task-level implementation plan.
- Use exact file paths, clear ownership, and explicit verification steps.
- Prefer tasks that can be completed and reviewed independently.

Recommended output:
- `docs/plans/<date>-<topic>-implementation.md`

Template:
- `templates/implementation-plan.md`

### 3. Subagent-Driven Development -> Role-Based Execution

- Use the role routing in `config/agents.yaml`.
- When subagents are available, delegate bounded tasks with one owner per task.
- Review for spec compliance before code quality.

Primary framework files:
- `agents/`
- `config/agents.yaml`
- `tasks/todo.md`

### 4. Test-Driven Development -> Required For Behavior Changes

- For new behavior and bug fixes, write the failing test first when practical.
- Confirm the test fails for the expected reason.
- Implement the minimal change.
- Re-run the focused test, then broader verification.

Primary framework files:
- `tests/**`
- `tasks/todo.md`
- `templates/implementation-plan.md`

### 5. Requesting Code Review -> Review Gates

- Run review against spec and plan, not only style.
- Block completion if critical issues remain open.
- Record review findings and follow-up actions.

Recommended output:
- `docs/reviews/<date>-<topic>.md`

Template:
- `templates/code-review.md`

### 6. Verification Before Completion -> Done Gate

- No completion claim without fresh verification evidence.
- Verification must include the command or check actually run.
- Update `tasks/todo.md`, session report, and state files before closing work.

### 7. Systematic Debugging -> Root Cause First

- Bug fixing starts with reproduction, evidence gathering, and root-cause analysis.
- Do not bundle speculative fixes.
- Add or update regression coverage once the cause is understood.

Recommended output:
- `docs/debug/<date>-<topic>.md`

Template:
- `templates/debug-investigation.md`

## Framework Rules Added From Superpowers

- No implementation without explicit design or spec context.
- No non-trivial execution without a written plan.
- No production fix without root-cause investigation.
- No completion claim without fresh verification evidence.
- No large task without decomposition into smaller reviewable steps.
