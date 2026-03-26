# AGENTS INDEX

## Purpose

This file lists all agent roles and the order in which they should be involved.

## Product And Planning

- `product_director`: owns product direction, priorities, and milestone framing
- `pm_triage`: classifies issues, assigns severity, and routes approval
- `pm_moderator`: runs planning meetings and produces decision-ready notes
- `pm_critic`: challenges assumptions and highlights risks
- `pm_advocate`: pushes constructive execution paths and upside
- `pm_analyst`: gathers evidence and compares options logically

## Design

- `game_designer`: owns gameplay design and feature intent
- `system_architect`: owns system decomposition and architectural decisions

## Engineering

- `client_dev`: implements client-facing functionality
- `server_dev`: implements backend and service logic

## Quality And Release

- `qa_planner`: defines test strategy and quality scope
- `test_automation`: implements and runs automated verification
- `release_manager`: manages release readiness and release records

## PM Council

Use the PM council for planning meetings when there is a non-trivial decision.

- Moderator: `pm_moderator`
- Advisors: `pm_critic`, `pm_advocate`, `pm_analyst`
- Human participants: expected for major product decisions

The moderator owns synthesis. Advisors provide perspective, not the final decision.
