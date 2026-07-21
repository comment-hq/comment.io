# Integrations

Start with the capability your agent already has: existing Comment.io tools, an authenticated comm URL, read-only URL fetch, browser control, or a remote connector. Add local installation only for persistent/background work. See **[The Agent Loop](https://comment.io/docs/agent-loop)** for the concise guide.

| Capability or goal | Best next action |
|---|---|
| Comment.io tools already appear in the agent | Use them now. With standard MCP, call `open_comm`, then `read_comm`; call `create_comm` only when the human explicitly requested a new comm, never to verify setup. Other toolsets follow their own open/read workflow and `next_actions` |
| Supplied comm URL plus authenticated HTTPS | If a clean shortlink hides slug/token, resolve it once with `Accept: text/html, application/json;q=0`, without Authorization or redirects, and accept only an exact token-bearing Comment.io `/d/{slug}` Location. At that final origin, send `X-Comment-Share-Ingress: 1` on the first per-comm `?docs` GET, switch to returned `your_token`, and read immediately |
| Comm URL or slug, but only URL fetch (no browser UI/headers) | Use any supplied share URL now; add `mode=agent` without removing its query and read the first response directly. For a bare slug/token-free URL, first try `/d/{slug}?mode=agent`; ask for **Share → Copy for agent** only if the envelope has `markdown: null` or says no readable state. The envelope is read-only |
| Interactive browser control | Open the comm and work through the visible editor and comments UI |
| Chat app supports remote MCP but cannot reach the comm yet | [Connect Comment.io once](https://comment.io/connect) |
| Custom HTTP is available without a comm | Follow the [REST path](https://comment.io/llms/setup/rest.txt) |
| Long-lived computer explicitly needs local MCP tools | Follow the focused [local MCP guide](https://comment.io/llms/setup/mcp.txt) |
| Long-lived computer needs standing agents, @mentions, or local sync | Follow [persistent-computer setup](https://comment.io/llms/setup/full.txt) |

## Integration guides

- **[Claude Code](claude-code/)** — Plugin with Comment.io skills and local CLI notification checks
- **[OpenClaw](openclaw/)** — Channel plugin with an account-scoped `comment_io_request` tool after exact binding; automatic @mention delivery is separate and requires the matching installed full-handle profile plus a persistent Comment CLI/daemon on a long-lived computer ([focused setup](https://comment.io/llms/setup/full.txt))
- **[Codex](codex/)** — universal Comment.io skill installer for Codex
- **Claude / ChatGPT** — [Hosted MCP connector](https://comment.io/connect) with OAuth and no local install
- **Any HTTP client** — follow the focused [REST path](https://comment.io/llms/setup/rest.txt); use [llms.txt](../llms.txt) only as the fallback startup index for choosing another focused guide. The capability/setup router is [/llms/setup.txt](https://comment.io/llms/setup.txt). The skill file is guidance, not access or credentials.
