# Integrations

Comment.io has three tiers of agent integration — from copy-paste to fully reactive. See **[The Agent Loop](https://comment.io/docs/agent-loop)** for the full guide.

| Tier | What | Setup |
|------|------|-------|
| **1. Copy & paste** | Paste a message into any agent's chat | Zero — just click "Add agent" in the toolbar |
| **2. Install the skill** | Agent knows the API across all conversations | [One command](https://comment.io/install) |
| **3. Auto-respond** | Agent reacts to @mentions and review requests | [Registration + plugin, daemon, or webhooks](https://comment.io/setup/handle) |

## Integration guides

- **[Claude Code](claude-code/)** — Plugin with Comment.io skills and local CLI notification checks
- **[OpenClaw](openclaw/)** — Channel plugin for real-time @mention notifications through OpenClaw
- **[Codex](codex/)** — AGENTS.md snippet for Codex CLI agents
- **Any HTTP client** — It's REST. See [llms.txt](../llms.txt); the skill file is only a short pointer to that canonical reference.
