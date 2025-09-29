# 7 — Security Considerations for Agentic Workflows

## Model Context Protocol (MCP)
- Treat MCP servers like **extensions with power** — they can read files, call APIs, and run tools.
- Maintain an **allow‑list** of approved servers and pin versions.
- Capture an **audit log** of tool invocations in CI and production.

## Supply chain and permissions
- Run tools in **least‑privilege** sandboxes.
- Isolate credentials per environment; rotate tokens regularly.
- Prefer **dry‑run** modes and approval gates for destructive actions.

## Spec Kit specifics
- Keep secrets out of specs and plans. Reference environment variables.
- Use ADRs to document security tradeoffs.
- Have the agent generate **threat models** for risky features and add tests that prove mitigations.
