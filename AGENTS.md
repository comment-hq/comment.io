# Comment.io — Agent Instructions

Comment.io is the agent-native document editor: humans and AI agents collaborate in
the same markdown document (a "comm") with real-time editing, comments, suggestions,
and per-edit provenance.

## Canonical machine docs

First use any Comment.io tools or comm access already available in your runtime.
For standard MCP and an existing comm, call `open_comm`, then `read_comm`; call
`create_comm` only when the human requested a new comm, never as setup
verification. For every other capability or setup route, fetch
`$BASE/llms/setup.txt` and follow the first matching typed handoff; it contains
the canonical share-ingress, browser, URL-fetch, handle, skill, connector, and
persistent-computer choices. Use `$BASE/llms/setup/rest.txt` only for focused
authenticated-HTTPS detail. Do not recreate those instructions here.

Keep every fallback on the same Comment.io deployment. For a supplied clean
shortlink, resolve it without credentials or automatic redirects and accept its
token-bearing `/d/{slug}` destination only after its origin and slug match the
live handoff's `api_reference_url` and `slug`. Set and freeze `$BASE` to that
validated final comm origin; a shortlink origin is never `$BASE`. With no supplied comm, use the
origin of the active Comment.io tool/account or the explicitly selected
profile. Use `https://comment.io` only when none of those provides an origin.

Only when the current tool or supplied-comm handoff does not cover the task,
fetch **`$BASE/llms.txt`** for the compact startup index. Exact direct-REST
behavior and recovery live at **`$BASE/llms/reference.txt`**. Always prefer the live files; the
`llms.txt` in this repo is a mirror of the startup index.

## Direct REST fallback for a requested new comm

Use REST only when the user asked for a new comm and no existing Comment.io
tool or interactive browser route can create it. Follow the live
**`$BASE/llms/setup/rest.txt`** path; it owns identity, anonymous fallback,
per-doc tokens, and the safe first request. Exact endpoint shapes and recovery
behavior live only in **`$BASE/llms/reference.txt`**. Do not copy an API recipe
from this repository mirror.

## Official channels

- Website and developer docs: https://comment.io · https://comment.io/docs
- Machine-doc startup index: https://comment.io/llms.txt
- Exact REST reference: https://comment.io/llms/reference.txt
- Hosted MCP connector for chat apps: https://comment.io/connect
- CLI on npm: [`@comment-io/cli`](https://www.npmjs.com/package/@comment-io/cli) — `npm install -g @comment-io/cli`
- Agent skill install: `curl -q -fsSL 'https://comment.io/skill' | sh`
- Engineering-workflow skills: https://github.com/comment-hq/skills (`npx skills add comment-hq/skills`) · https://skills.sh/comment-hq/skills
- Claude Code plugin: https://github.com/comment-hq/comment-io-claude-code-plugin
- OpenClaw plugin: https://github.com/comment-hq/openclaw-plugin
