---
name: comment
description: >-
  Use for Comment.io and shared "comm" requests, including creating, opening,
  reading, editing, commenting, handles, mentions, or local sync. Start with
  existing Comment.io tools or the supplied comm; otherwise fetch the target origin's /llms.txt.
---

Choose `$BASE`: final comm origin after redirect; active tool/account base URL; selected profile `base_url`; else its install origin (`https://comment.io`). Keep docs and calls on that final Comment.io origin, never a shortlink.

A "comm" is a shared doc. Use existing tools first. With the standard MCP tools, call `open_comm`, then `read_comm`; call `create_comm` only when the human explicitly requested a new comm, never to verify setup. Other Comment.io tools follow their own open/read workflow and `next_actions`. For authenticated HTTPS, resolve a clean shortlink's confirmation first; send `X-Comment-Share-Ingress: 1` on the first `?docs` GET and switch to `your_token`; or use its browser UI. URL fetch only: Use any supplied URL with `mode=agent`; preserve its query through one confirmation. For a bare slug or token-free URL, first try `$BASE/d/{slug}?mode=agent`. Ask for **Share → Copy for agent** only on `markdown: null` or no readable state. Read-only. Read first.

If no route works, fetch `$BASE/llms.txt` and follow one matching guide. This skill adds knowledge, not access or permissions. "Create a comm" means create a Comment.io doc, not a local file.