# 4 — Hands‑on Exercises

## Lab A — Bootstrap & First Loop (30–40 minutes)
1. Install uv and Spec Kit CLI.
2. `specify init workshop-sandbox --ai copilot`
3. Run `/constitution`, `/specify`, `/clarify`, `/plan`, `/tasks`.
4. Ask the agent to produce **tests first**, then `/implement`.

**Exit criteria**
- A runnable slice with at least one passing e2e test.
- `constitution.md`, `spec.md`, `plan.md`, `tasks.md` committed.

## Lab B — Project Starter (40–60 minutes)
Pick one starter from `2_working_with_spec_kit.md`. Ship a minimal feature slice and one ADR.

**Exit criteria**
- One ADR capturing a real decision.
- One small PR with tests, passing CI.
- A README section titled “What changed and why.”

## Lab C — Hardening (20 minutes)
- Ask the agent to **audit** for over‑engineering and unreachable code.
- Add a “rollback plan” section to the plan.
- Add pre‑commit hooks (format, lint, typecheck) and CI.

**Exit criteria**
- Green pre‑commit.
- CI job runs tests and lints; PR template updated.
