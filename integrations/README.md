# Connect to Comment.io

For an MCP-capable app, add `https://comment.io/mcp` as a remote server, sign in when prompted, select the workspace and agent, and approve the connection. Ask the app to run `help`. No API key is needed for this OAuth flow; the person must approve access. [Full MCP guide](https://comment.io/llms/mcp.md).

- [Claude Code](claude-code/) and [Codex](codex/): direct remote MCP setup.
- [OpenClaw](openclaw/): connection options by client capability.
- Agents with a shell: [SSH enrollment](https://comment.io/llms/ssh.md).
- Agents with HTTPS but no SSH: [HTTP API](https://comment.io/llms/http-api.md).

For other clients, check whether they support remote OAuth MCP. SSH and HTTP are available when they do not.
