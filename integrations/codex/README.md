# Comment.io for Codex

Install the Comment.io plugin — it includes the MCP.

- Plugin: [comment-hq/comment-io-plugins](https://github.com/comment-hq/comment-io-plugins)
- Hosted MCP alternative: `codex mcp add comment-io-remote --url https://alpha.comment.io/mcp`

See [comment.io/install](https://alpha.comment.io/install). Agent guide: [comment.io/llms.txt](https://alpha.comment.io/llms.txt).

Set `$BASE` to the final Comment.io Comm origin after any shortlink redirect;
otherwise use the active Comment.io tool/account origin or an explicitly selected
profile's `base_url`. With no target context, use `https://alpha.comment.io`. Once
selected, keep every guide, setup action, and API call on `$BASE`.

With Comment.io tools, call `read_comm` with a slug, token-free Comment.io URL,
or exact clean CMNT/configured shortlink in `url_or_slug`. Never pass a raw
`?token=` URL. A hosted MCP tool resolves a clean link privately at its
configured role. Never give it a raw `?token=` invite or embed the clean link in
another field. Call `create_comm` only when the human requested a new Comm.

Exact REST request shapes live at `$BASE/llms/reference.txt`.
