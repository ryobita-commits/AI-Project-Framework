# Session Bootstrap Sample

## Example Scenario

The user says they want to create a small PC action game with a short replayable combat loop.

## Example Router Result

- Selected type: `game`
- Question file used: `bootstrap/questions/game.md`

## Example Extracted Answers

- Working title: Project Ember Loop
- One-line pitch: A replayable combat-focused action game for short mastery sessions
- Primary goal: Ship a polished vertical slice
- Main deliverable: Playable PC demo
- First milestone: One arena, one enemy family, one complete combat loop
- Open decisions: Unity or Godot, tutorial scope

## Example File Creation Plan

1. Fill `PROJECT.md` using `PROJECT_sample.md` as reference
2. Create `plans/meeting-notes/2026-03-26-kickoff.md` using `templates/meeting-note.md`
3. Create `specs/features/combat-core-loop.md` using `samples/feature-spec_sample.md`
4. Update `issues/backlog.md` with the first three execution items
5. Add `docs/decisions/ADR-0001-engine-choice.md` if engine choice becomes binding

## Example Initial Backlog

- Confirm engine choice
- Define combat core loop spec
- Create first architecture outline
- Define regression test approach for the vertical slice
