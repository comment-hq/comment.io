---
name: comment
description: >-
  Use for Comment.io and shared "comm" requests, including creating, opening,
  reading, editing, commenting, handles, mentions, or local sync. Start with
  existing Comment.io tools or the supplied comm; otherwise fetch the target origin's /llms.txt.
---

<!-- comment.io-skill -->

Choose `$BASE`: final comm origin after redirect; active tool/account base URL; selected profile `base_url`; else its install origin (`https://comment.io`). Keep docs and calls on that final Comment.io origin, never a shortlink.

Use existing tools first. Hosted MCP accepts a slug, token-free doc URL, or clean CMNT/configured link only in `url_or_slug`; rejects raw `?token=` URLs. Call `open_comm`, then `read_comm`; use `create_comm` only when requested, never for setup verification. HTTPS REST: resolve a clean shortlink with `Accept: text/html, application/json;q=0`, no auth or redirects; accept only its Comment.io `/d/:slug?token=...` Location; send `X-Comment-Share-Ingress: 1` on the first `?docs` GET then use `your_token`; or use its browser UI. URL fetch only: Use any supplied URL with `mode=agent` and read it directly. For a bare slug or token-free URL, first try `$BASE/d/{slug}?mode=agent`. Ask for **Share → Copy for agent** only on `markdown: null` or no readable state. Read-only. Read first.

If no route works, fetch `$BASE/llms.txt` and follow one matching guide. Skills add knowledge, not access. Create comm means a Comment.io doc, not a local file.