# ClawTeam

> Team of AI agents with shared brain and sandboxed execution.

Built on [OpenClaw](https://github.com/openclaw/openclaw). MIT licensed.

## What is this?

ClawTeam turns OpenClaw into a multi-agent engineering team. Each agent has a role (CTO, CMO, COO), a workspace (brain), and access to shared tools. Agents track work in Linear, search knowledge via qmd, and execute code in sandboxed containers.

## What's added on top of OpenClaw

- **Team workspaces** — one brain per agent, synced to Obsidian via Syncthing
- **Linear integration** — issue tracking, kanban, status updates via `linear-cli`
- **Knowledge base** — search docs/specs/memory via `qmdr` (powered by [qmd](https://github.com/tobi/qmd))
- **Sandboxed execution** — code runs in isolated containers via [sandboxed.sh](https://sandboxed.sh)
- **Agent pipeline** — research → plan → approve → execute → PR → review

## Architecture

```
Human (CEO)
  ├── reviews in Linear + Obsidian
  └── approves plans, merges PRs

Agent workspaces (~/.openclaw/workspace/)
  ├── neo/    (COO — operations, coordination)
  ├── cto/    (CTO — engineering, code)
  └── cmo/    (CMO — content, research)

Tools
  ├── linear-cli  → Linear API (issues, status)
  ├── qmdr        → knowledge base search
  ├── gh           → GitHub CLI
  └── sandboxed.sh → isolated code execution
```

## Quick start

```bash
# Install OpenClaw first
curl -fsSL https://openclaw.ai/install.sh | bash

# Clone ClawTeam
git clone https://github.com/0xyaya/clawteam.git
cd clawteam

# Set up team workspace
./scripts/setup.sh
```

## Keeping up with OpenClaw

```bash
git fetch upstream
git merge upstream/main
git push origin main
```

## Links

- [OpenClaw docs](https://docs.openclaw.ai)
- [Linear](https://linear.app)
- [qmd](https://github.com/tobi/qmd)
- [sandboxed.sh](https://sandboxed.sh)

## License

MIT — same as OpenClaw.
