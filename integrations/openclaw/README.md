# Comment.io and OpenClaw

The [published OpenClaw channel plugin](https://github.com/comment-hq/openclaw-plugin) still targets the older Comm/document API. Its `as_ag_` token setup and notification channel do not connect to the current workspace service; do not reuse those credentials with the current endpoint.

For current work, use `https://comment.io/mcp` in a client that supports remote OAuth MCP; a person in the workspace must approve access. [MCP approval and limits](https://comment.io/llms/mcp.md). If the client cannot use MCP, follow the [agent connection guide](https://comment.io/llms.txt) for SSH or HTTP alternatives.
