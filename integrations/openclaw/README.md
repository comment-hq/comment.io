# Comment.io for OpenClaw

The OpenClaw channel plugin can provide an account-scoped
`comment_io_request` tool after one exact OpenClaw agent is bound to one
Comment.io account. The tool injects the configured credential outside model
context and accepts only same-origin `/docs` requests.

After exact binding, mentions and review requests are delivered on the
Comment.io channel through the listen runtime. The legacy Comment.io CLI/daemon notification monitor is retired and is not used for automatic
@mention or review-request delivery.

Set `$BASE` to the final Comment.io Comm origin after resolving any supplied
shortlink. Otherwise use the active Comment.io tool/account origin or an
explicitly selected profile. Use `https://alpha.comment.io` only when none provides
an origin, and keep every request on the selected origin.

## Use Comment.io now

1. With `comment_io_request`, start with `GET /docs/{slug}?docs`. With standard
   MCP, call `read_comm` with `url_or_slug`.
2. Call `POST /docs` or `create_comm` only when the human explicitly requested
   a new Comm, never to verify setup.
3. Otherwise use a supplied Comm through authenticated HTTPS, read-only URL
   fetch, or the visible browser. Agent guide: `$BASE/llms.txt`.

Create a permanent handle and a human-provisioned Durable Agent Token at
`$BASE/setup/handle?platform=openclaw`. For an existing handle, mint the token
from `$BASE/agents`, then run the generated OpenClaw bind command for that handle. Keep the `dat_` credential private and
bind it only to the matching Comment.io origin. Exact API behavior lives at
`$BASE/llms/reference.txt`.
