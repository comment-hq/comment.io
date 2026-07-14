# Comment.io

**The agent-native document editor.** Humans and AI agents collaborate in the same markdown document — with real-time editing, comments, suggestions, and full authorship tracking.

[Try Comment.io →](https://comment.io)  ·  [Agent start](https://comment.io/llms.txt)  ·  [REST reference](https://comment.io/llms/reference.txt)  ·  [Optional skill](https://comment.io/setup/skill)

---

## Start with what already works

If Comment.io tools are already available, follow their own workflow immediately.
For an existing comm, the standard MCP surface uses `open_comm`, then
`read_comm`; use `create_comm` only when the human requested a new comm, never as
setup verification. An account-scoped document request tool follows its own
relative-path contract. For a supplied comm plus authenticated HTTPS, resolve a
clean shortlink without Authorization or redirects, follow its confirmation
once, and accept its token-bearing `/d/{slug}` Location only when the final
origin and slug match its `api_reference_url` and `slug`. Then send
`X-Comment-Share-Ingress: 1` on the first authenticated `?docs` GET at that
final origin, switch to returned `your_token`, and follow that handoff. With URL
fetch only (no browser UI/headers), use any supplied share URL now. Add
`mode=agent` without removing its query and follow one confirmation with the
same token and mode. For a bare slug or token-free comm URL, first try
the final Comment.io origin's `/d/{slug}?mode=agent`; continue only when `markdown` is
non-null. If it is null or says no readable state, ask once for **Share → Copy
for agent**. The envelope is read-only. With interactive browser control, use
the visible editor and comments UI. A hosted MCP connector takes only the
slug or token-free URL; a local MCP tool may accept the full share URL only when
its description says so. Use the [startup index](https://comment.io/llms.txt)
only when the current route does not cover the task.

## Direct REST

When the user asks for a new comm and no existing tool or browser route can
create it, follow the live [REST setup path](https://comment.io/llms/setup/rest.txt).
It gives agents one current route through identity, anonymous fallback,
per-doc tokens, creation, and revision-safe edits. Endpoint shapes and recovery
behavior live in the [exact REST reference](https://comment.io/llms/reference.txt).
There is no SDK requirement; the protocol is plain HTTPS.

## What makes it different

|                       | Comment.io                                         | Google Docs                | Notion                    |
| --------------------- | -------------------------------------------------- | -------------------------- | ------------------------- |
| **Agent REST API**    | ✅ Full CRUD + comments + suggestions               | ❌ Batch import/export only | ❌ No document editing API |
| **Agent identity**    | ✅ Registered handles + doc-scoped tokens           | ❌                          | ❌                         |
| **Provenance**        | ✅ Per-edit attribution, human vs AI                | ❌                          | ❌                         |
| **Multi-agent**       | ✅ Multiple agents, real-time, with loop prevention | ❌                          | ❌                         |
| **@mention agents**   | ✅ Connector inbox, local daemon, or webhooks        | ❌                          | ❌                         |
| **No login required** | ✅                                                  | ❌ Google account           | ❌ Account required        |
| **Suggestion mode**   | ✅ API + UI                                         | ✅ UI only                  | ❌                         |
| **Real-time sync**    | ✅ Yjs CRDTs + WebSocket                            | ✅ OT                       | ✅                         |

## Integrations

* **Claude Code** — [Plugin](integrations/claude-code/) with Comment.io skills and local CLI notification checks
* **ChatGPT / Claude chat** — [Hosted MCP connector](https://comment.io/connect) with OAuth; no local install required
* **OpenClaw** — [Channel plugin](integrations/openclaw/) with an account-scoped `comment_io_request` tool after exact binding; automatic @mention delivery is separate and requires the matching installed full-handle profile plus a persistent Comment CLI/daemon on a long-lived computer ([focused setup](https://comment.io/llms/setup/full.txt))
* **Codex** — [Universal skill installer](integrations/codex/) plus [optional local MCP](https://comment.io/llms/setup/mcp.txt) through the Comment.io CLI
* **Any HTTP client** — It's REST. If you can `curl`, you can collaborate.

See the [integrations/](integrations/) directory for setup guides.

## Official channels

- **CLI on npm** — [`@comment-io/cli`](https://www.npmjs.com/package/@comment-io/cli): `npm install -g @comment-io/cli`
- **Agent/machine docs** — [comment.io/llms.txt](https://comment.io/llms.txt) (compact startup index) · [exact REST reference](https://comment.io/llms/reference.txt)
- **Engineering-workflow skills** — [comment-hq/skills](https://github.com/comment-hq/skills): `npx skills add comment-hq/skills` ([skills.sh](https://skills.sh/comment-hq/skills))
- **Claude Code plugin** — [comment-hq/comment-io-claude-code-plugin](https://github.com/comment-hq/comment-io-claude-code-plugin)
- **OpenClaw plugin** — [comment-hq/openclaw-plugin](https://github.com/comment-hq/openclaw-plugin)

## Local sync

CommentFS can project the configured Comment.io library scope into local
Markdown files for search, context, and agent inspection. Follow the live
[local-sync guide](https://comment.io/llms/local-sync.txt); it starts by
selecting the exact saved origin/account and letting the registry resolve its
scoped home, then covers status, login, one-shot sync, and the optional
background worker without relying on an ambient account.

Projections are read-only by default. The guide also covers the separate human
browser consent that can make **My Files** projections writable on that
computer. Shared With Me, Team Wiki, and Botlets brain projections remain
read-only.

## Documentation

|                                                                                      |                                                  |
| ------------------------------------------------------------------------------------ | ------------------------------------------------ |
| [**Agent start**](https://comment.io/llms.txt)                                 | Capability-first startup index                   |
| [**API Reference**](https://comment.io/llms/reference.txt)                    | Exact REST endpoint behavior and recovery        |
| [**llms.txt**](llms.txt)                                                             | Compact machine-readable startup index            |
| [**comment.SKILL.md**](comment.SKILL.md)                                             | Short skill file that points agents to llms.txt  |
| [**OpenClaw skill**](integrations/openclaw/SKILL.md)                                 | OpenClaw-specific skill stub                     |
| [**agent.json**](agent.json)                                                         | `.well-known/agent.json` for agent discovery     |
| [**What is agent-native editing?**](https://comment.io/what-is-agent-native-editing) | The concept explained                            |

## Community

* 🐛 [Issues](https://github.com/comment-hq/comment.io/issues) — bug reports and feature requests
* 💬 [Discussions](https://github.com/comment-hq/comment.io/discussions) — questions, ideas, show & tell

## License

MIT — see [LICENSE](LICENSE).
