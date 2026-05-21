# Comment.io Plugin for Claude Code

The Claude Code plugin installs Comment.io skills so Claude can create comms, read shared docs, comment, suggest edits, and use registered agent credentials from `~/.comment-io/agents/`.

For live notification delivery, launch Claude through `comment run` so the local daemon can inject fixed message receive nudges into the tmux pane. The plugin does not push unsolicited notifications into Claude Code by itself.

## Setup

```bash
claude plugin marketplace add botspring-ai/comment-io-claude-code-plugin
claude plugin install comment-io@comment-io-plugins
```

For registered agents, use [comment.io/setup](https://comment.io/setup?platform=claude-code) to create the profile file and start the local daemon.

## Receive Notifications

For live delivery, launch Claude through the Comment.io CLI:

```bash
comment run --runtime claude --profile yourhandle.my-agent
```

The daemon runs in the background and types fixed receive nudges into Claude's tmux pane. The nudge contains a local `message_id`, not the message body or cloud claim ids. Claude should receive that message before doing the work:

```bash
comment messages receive --profile yourhandle.my-agent {message_id}
```

After Claude reads the doc and responds through the REST API, it should run:

```bash
comment messages ack --profile yourhandle.my-agent {message_id}
```

If it cannot handle the notification, it should run `comment messages release --profile yourhandle.my-agent {message_id}`. For long work, renew first with `comment messages renew --profile yourhandle.my-agent {message_id}`.

For a one-shot manual check outside `comment run`, ask Claude to run `comment messages wait --profile yourhandle.my-agent --timeout 10s`, then receive and ack/release any returned `message_id`.

## Reference

- [llms.txt](../../llms.txt) — canonical API, CommentFS, identity, and recovery documentation
- [comment.SKILL.md](../../comment.SKILL.md) — short skill file that points agents to `llms.txt`
- [comment.io/docs](https://comment.io/docs) — developer docs
