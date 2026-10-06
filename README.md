# Comment.io

**The agent-native document editor.** Humans and AI agents collaborate in the same markdown document — with real-time editing, comments, suggestions, and full authorship tracking.

[Try Comment.io →](https://alpha.comment.io)  ·  [Install](https://alpha.comment.io/install)  ·  [Agent guide](https://alpha.comment.io/llms.txt)  ·  [REST reference](https://alpha.comment.io/llms/reference.txt)

---

You install Comment in your agent, then you and your agents read, write, and comment on shared docs.

## Install

- **Plugin** (includes the MCP) — Claude Code, Claude Cowork, Codex, OpenAI Work.
- **Hosted MCP** — every other MCP-capable agent (Claude Chat, ChatGPT, anything else).

See [comment.io/install](https://alpha.comment.io/install). Agent guide: [comment.io/llms.txt](https://alpha.comment.io/llms.txt).

For an existing Comm, use `read_comm` with a slug, token-free Comment.io URL, or exact clean CMNT/configured shortlink in `url_or_slug`. Never pass a raw `?token=` URL. Call `create_comm` only when the human requested a new Comm.

## Direct REST

When the user asks for a new Comm and no existing tool or browser route can
create it, follow the live [REST reference](https://alpha.comment.io/llms/reference.txt).
There is no SDK requirement; the protocol is plain HTTPS.

## What makes it different

|                       | Comment.io                                         | Google Docs                | Notion                    |
| --------------------- | -------------------------------------------------- | -------------------------- | ------------------------- |
| **Agent REST API**    | ✅ Full CRUD + comments + suggestions               | ❌ Batch import/export only | ❌ No document editing API |
| **Agent identity**    | ✅ Registered handles + doc-scoped tokens           | ❌                          | ❌                         |
| **Provenance**        | ✅ Per-edit attribution, human vs AI                | ❌                          | ❌                         |
| **Multi-agent**       | ✅ Multiple agents, real-time, with loop prevention | ❌                          | ❌                         |
| **@mention agents**   | ✅ Connector inbox or webhooks                       | ❌                          | ❌                         |
| **No login required** | ✅                                                  | ❌ Google account           | ❌ Account required        |
| **Suggestion mode**   | ✅ API + UI                                         | ✅ UI only                  | ❌                         |
| **Real-time sync**    | ✅ Yjs CRDTs + WebSocket                            | ✅ OT                       | ✅                         |

## Integrations

* **Claude Code** — [plugin](https://github.com/comment-hq/comment-io-plugins) (includes the MCP)
* **Codex** — [plugin](https://github.com/comment-hq/comment-io-plugins) (includes the MCP)
* **Claude Cowork / OpenAI Work** — plugin includes the MCP; connect at [comment.io/install](https://alpha.comment.io/install)
* **ChatGPT / Claude chat / other MCP-capable agents** — [Hosted MCP connector](https://alpha.comment.io/install)
* **OpenClaw** — [Channel plugin](integrations/openclaw/)
* **Any HTTP client** — It's REST. If you can `curl`, you can collaborate.

See the [integrations/](integrations/) directory for setup guides.

## Official channels

- **Install** — [comment.io/install](https://alpha.comment.io/install)
- **Agent guide** — [comment.io/llms.txt](https://alpha.comment.io/llms.txt) · [exact REST reference](https://alpha.comment.io/llms/reference.txt)
- **Engineering-workflow skills** — [comment-hq/skills](https://github.com/comment-hq/skills): `npx skills add comment-hq/skills` ([skills.sh](https://skills.sh/comment-hq/skills))
- **Claude Code and Codex plugins** — [comment-hq/comment-io-plugins](https://github.com/comment-hq/comment-io-plugins)
- **OpenClaw plugin** — [comment-hq/openclaw-plugin](https://github.com/comment-hq/openclaw-plugin)

## Documentation

|                                                                                      |                                           |
| ------------------------------------------------------------------------------------ | ----------------------------------------- |
| [**Install**](https://alpha.comment.io/install)                                            | Plugin and hosted MCP setup               |
| [**Agent guide**](https://alpha.comment.io/llms.txt)                                 | Machine-readable agent start              |
| [**API Reference**](https://alpha.comment.io/llms/reference.txt)                    | Exact REST endpoint behavior and recovery |
| [**OpenClaw skill**](integrations/openclaw/SKILL.md)                                 | OpenClaw-specific skill stub              |
| [**What is agent-native editing?**](https://alpha.comment.io/what-is-agent-native-editing) | The concept explained                     |

## Community

* 🐛 [Issues](https://github.com/comment-hq/comment.io/issues) — bug reports and feature requests
* 💬 [Discussions](https://github.com/comment-hq/comment.io/discussions) — questions, ideas, show & tell

## License

MIT — see [LICENSE](LICENSE).
