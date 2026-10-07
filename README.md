# Comment.io

Comment.io is a shared workspace of Markdown documents for people and their agents. People review, comment, suggest changes and edit in the browser; agents read and contribute over MCP, SSH or HTTP. Keep the decisions and corrections in the workspace so the next agent can pick up the work.

[Get started](https://comment.io/llms.txt) · [Use cases](https://comment.io/use-cases.md) · [FAQ](https://comment.io/faq.md) · [Support](mailto:support@comment.io)

## Connect an agent

Access to a workspace requires a person in that workspace to approve the agent. Start with MCP if your client supports remote OAuth MCP:

1. **MCP (default):** Add `https://comment.io/mcp` as a remote server. A person signs in and approves the app and its agent. The server offers a `run` tool for workspace commands. [MCP setup and limitations](https://comment.io/llms/mcp.md). The separate `/mcp/tools` endpoint provides one tool per command for clients that need it.
2. **Shell alternative:** [Connect over SSH](https://comment.io/llms/ssh.md). The agent generates an SSH key and a human approves its enrollment; the guide covers key pinning and verification.
3. **HTTPS alternative:** [Use the HTTP API](https://comment.io/llms/http-api.md). A person creates an agent API token on the workspace's Team page; the agent sends commands to `POST https://comment.io/api/run`.

Start with `help` after connecting. [The command guide](https://comment.io/llms/commands.md) covers reading, writing, searching, comments, suggestions, files, and typed records. Agents can [propose a new workspace](https://comment.io/llms/propose-a-workspace.md) or [prepare a person's invitation](https://comment.io/llms/invite-a-person.md) for human approval.

For future sessions, install the [using-commentio skill](https://comment.io/skills/using-commentio/SKILL.md) in your agent's supported skills directory and record the working connection without storing secrets in the skill. The [live agent guide](https://comment.io/llms.txt) is the authoritative onboarding and capability reference.

## Client setup

See the [integration guides](integrations/) for direct MCP configuration in Codex and Claude Code. For another client, check that it supports remote OAuth MCP and follow the [MCP guide](https://comment.io/llms/mcp.md). ChatGPT has not been verified as an MCP client.

## Community

[Issues](https://github.com/comment-hq/comment.io/issues) · [Discussions](https://github.com/comment-hq/comment.io/discussions) · [support@comment.io](mailto:support@comment.io)

MIT — see [LICENSE](LICENSE).
