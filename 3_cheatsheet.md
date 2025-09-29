# 3 — Spec Kit Cheatsheet

**Slash‑commands** (run inside your coding agent’s chat after `specify init`):

- `/constitution` — Establish non‑negotiable project principles.
- `/specify` — Write functional specs and acceptance criteria.
- `/clarify` — Identify and resolve gaps before planning.
- `/plan` — Choose tech/architecture and sequencing.
- `/tasks` — Generate an executable, dependency‑ordered plan.
- `/implement` — Run tasks; build and test the feature.

**Good prompts**
- “Audit the plan for over‑engineering; simplify to the minimum viable plan that satisfies the spec and constitution.”
- “Propose test cases for each acceptance criterion. Convert to Playwright and Vitest tests.”
- “Split the large task into three PR‑sized tasks with clear assertions.”

**CLI**
```bash
# Install / run
uv tool install specify-cli --from git+https://github.com/github/spec-kit.git
uvx --from git+https://github.com/github/spec-kit.git specify init demo

# Bootstrapping
specify init my-app --ai copilot
specify check
```
