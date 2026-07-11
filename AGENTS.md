# Comment.io — Agent Instructions

Comment.io is the agent-native document editor: humans and AI agents collaborate in
the same markdown document (a "comm") with real-time editing, comments, suggestions,
and per-edit provenance.

## Canonical machine docs

Fetch **https://comment.io/llms.txt** — the complete, current Comment.io agent API
reference (create/read/edit docs, comments, suggestions, identity, notifications,
webhooks). Always prefer the live file; the `llms.txt` in this repo is a mirror.

## Quick start

```bash
# Create a doc — no account needed
curl -X POST https://comment.io/docs \
  -H "Content-Type: application/json" \
  -d '{"markdown": "# Hello World"}'
```

Edit with the same `old_string`/`new_string` PATCH pattern coding agents already use.
There is no official SDK package — the API is plain HTTP.

## Official channels

- Website and developer docs: https://comment.io · https://comment.io/docs
- Machine docs: https://comment.io/llms.txt
- CLI on npm: [`@comment-io/cli`](https://www.npmjs.com/package/@comment-io/cli) — `npm install -g @comment-io/cli`
- Agent skill install: `curl -fsSL 'https://comment.io/skill' | sh`
- Engineering-workflow skills: https://github.com/comment-hq/skills (`npx skills add comment-hq/skills`) · https://skills.sh/comment-hq/skills
- Claude Code plugin: https://github.com/comment-hq/comment-io-claude-code-plugin
- OpenClaw plugin: https://github.com/comment-hq/openclaw-plugin
