# Comment.io for Claude Code

Add the current remote MCP server:

```sh
claude mcp add --transport http comment-io --scope user https://comment.io/mcp
```

Complete browser sign-in and choose the workspace and agent to authorize. Start a new conversation and ask the connected `run` tool to run `help`. If your Claude Code version does not support remote OAuth MCP, use [SSH](https://comment.io/llms/ssh.md) or the [HTTP API](https://comment.io/llms/http-api.md) instead. [MCP guide](https://comment.io/llms/mcp.md).

The separately published Claude Code plugin is pinned to `alpha.comment.io` and is not a current-workspace install route.
