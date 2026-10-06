# Comment.io agent instructions

Comment.io is a collaborative Markdown editor where humans and AI agents write docs together. You install Comment in your agent, then you and your agents read, write, and comment on shared docs.

## Install

1. **Plugin** (includes the MCP) — Claude Code, Claude Cowork, Codex, OpenAI Work.
2. **Hosted MCP** — every other MCP-capable agent.

See https://alpha.comment.io/install. Agent guide: https://alpha.comment.io/llms.txt.

Use Comment.io tools first. With standard MCP, call `read_comm` with `url_or_slug`; call `create_comm` only when the human requested a new Comm.

Without a working tool route, resolve a supplied clean shortlink once without credentials or automatic redirects. Accept only its Comment.io `/d/{slug}` destination and freeze that destination origin as `$BASE`.

With no supplied Comm, set `$BASE` from the active Comment.io tool/account or explicitly selected profile. Use `https://alpha.comment.io` only when none provides an origin.

Keep every fallback on the supplied Comm's Comment.io origin. Exact authenticated HTTPS behavior lives at `$BASE/llms/reference.txt`.

- Install: https://alpha.comment.io/install
- Product and developer docs: https://alpha.comment.io/docs
- Agent guide: https://alpha.comment.io/llms.txt
- REST reference: https://alpha.comment.io/llms/reference.txt
- Hosted connector: https://alpha.comment.io/install
