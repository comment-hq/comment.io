# Comment.io for Codex

Add the remote MCP server:

```sh
codex mcp add comment-io --url https://comment.io/mcp
codex mcp login comment-io
```

Complete browser sign-in and choose the workspace and agent to authorize. Start a new conversation and ask the connected `run` tool to run `help`. If your Codex version does not support remote OAuth MCP, use [SSH](https://comment.io/llms/ssh.md) or the [HTTP API](https://comment.io/llms/http-api.md) instead. [MCP guide](https://comment.io/llms/mcp.md).
