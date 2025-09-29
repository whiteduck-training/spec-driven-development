# 1 — Intro to GitHub Spec Kit

This section gets you from zero to a working **spec‑driven repo** using the open‑source **Spec Kit**.

## Prerequisites
- **git** installed and authenticated (GitHub recommended).
- **uv** (fast Python tool manager) available on your PATH.
- An AI coding agent (pick one): **GitHub Copilot in VS Code (Agent/Chat)** or **Claude Code**, **Cursor**, **Gemini CLI**, etc.

> Tip: If you’re on corporate networks, ensure outbound access to GitHub and your agent’s endpoints.

## Install uv (one‑time)
**macOS / Linux**
```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```
**Windows (PowerShell)**
```powershell
powershell -ExecutionPolicy Bypass -c "irm https://astral.sh/uv/install.ps1 | iex"
```

Verify:
```bash
uv --version
```

## Install the Specify CLI (Spec Kit)
Install persistently so it’s always on your PATH:
```bash
uv tool install specify-cli --from git+https://github.com/github/spec-kit.git
```

Or run ad‑hoc without installing:
```bash
uvx --from git+https://github.com/github/spec-kit.git specify init my-spec-project
```

## Bootstrap a project
```bash
# Create a new folder with Spec Kit templates
specify init workshop-sandbox --ai copilot

# Or initialize in the current directory
specify init --here --ai copilot

# Sanity check — lists detected tools (git, copilot/claude/cursor, etc.)
specify check
```

Open the folder in your agent (e.g., VS Code with Copilot Chat) and verify that slash‑commands are available: `/constitution`, `/specify`, `/clarify`, `/plan`, `/tasks`, `/implement`.

## First run (happy path)
1. In agent chat, run:
    ```
    /constitution Emphasize testing, accessibility, and performance budgets. Enforce TypeScript strict mode and 95% unit test coverage on core domain.
    ```
    or
    ```
    /constitution Create principles focused on code quality, testing standards, user experience consistency, and performance requirements
    ```
    or
    ```
    /constitution Create principles focused on code quality, testing standards, user experience consistency, and performance requirements. Use "uv init --package -p 3.12" for initializing a project, "uv add" to add packages, "uv run" to execute stuff.
    After every task and unit of work commit it and push it.
    ```

2. Then create your first spec:
    ```
    /specify Build a minimal web app that stores timeboxed notes. Each note has a title, tags, and 1-minute timer. Offline-first, local data.
    ```
3. Ask for clarifications:
    ```
    /clarify Identify ambiguities and propose defaults (storage, syncing, PWA constraints).
    ```
4. Produce a plan:
    ```
    /plan Tech: Remix + TypeScript + SQLite (libsql) + Vitest + Playwright. PWA. Edge‑friendly.
    ```
5. Break down into tasks and implement:
    ```
    /tasks
    /implement
    ```

## Troubleshooting
- **Slash‑commands not appearing** in chat: confirm you opened the **workspace root**; run `specify check`; ensure your agent extension is enabled.
- **Auth issues on Linux**: Install Git Credential Manager and set it as the helper.
- **CLI not found** after install: ensure your shell init loads uv’s tool shims; try a new terminal; run `uv tool list`.

See `5_resources.md` for links to upstream docs and videos.

---

## What did Spec Kit scaffold?
- `constitution.md` — your project principles.
- `spec.md` — functional requirements and user stories.
- `plan.md` — technology and architecture choices.
- `tasks.md` — dependency‑ordered work plan.
- Helper scripts for your chosen agent/editor.

You now have a **repeatable loop** to drive agents from a durable spec.
