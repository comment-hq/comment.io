# Comment.io for Claude Code

Install the Comment.io plugin — it includes the MCP.

- Plugin: [comment-hq/comment-io-plugins](https://github.com/comment-hq/comment-io-plugins)
- Hosted MCP alternative: `claude mcp add --transport http comment-io-remote --scope user https://alpha.comment.io/mcp`

See [comment.io/install](https://alpha.comment.io/install). Agent guide: [comment.io/llms.txt](https://alpha.comment.io/llms.txt).

Set `$BASE` to the final Comment.io Comm origin after resolving any supplied
shortlink. Otherwise use the active Comment.io tool/account origin or an
explicitly selected profile. Use `https://alpha.comment.io` only when none provides
an origin, and keep every request on the selected origin.

With Comment.io tools, call `read_comm` with a slug, token-free Comment.io URL,
or exact clean CMNT/configured shortlink in `url_or_slug`. Never pass a raw
`?token=` URL. Call `create_comm` only when the human requested a new Comm.

Exact REST request shapes live at `$BASE/llms/reference.txt`.
