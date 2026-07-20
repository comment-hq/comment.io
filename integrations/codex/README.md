# Comment.io for Codex

Set `$BASE` to the final Comment.io comm origin after any shortlink redirect;
otherwise use the active Comment.io tool/account origin or an explicitly selected
profile's `base_url`. With no target context, use `https://comment.io`. Once
selected, keep every guide, setup action, and API call on `$BASE`.

Use the first Comment.io route already available in the current Codex session:

1. If Comment.io tools are present, use them immediately. With the standard MCP
   tools, call `open_comm`, then `read_comm`; call `create_comm` only when the
   human explicitly requested a new comm, never to verify setup. Other
   Comment.io tools follow their own open/read workflow and `next_actions`.
2. If the human supplied a comm, use that supplied locator immediately through
   the first available route that accepts it; do not ask for a replacement
   handoff first. Give a hosted MCP tool only the slug or token-free comm
   URL—never the token-bearing invite. A local MCP tool may receive the full
   invite only when its description explicitly accepts share URLs;
   authenticated HTTPS, URL fetch, and browser-control routes can use the exact
   supplied locator. With authenticated HTTPS, resolve a clean shortlink once
   without Authorization or automatic redirects, accept only an exact
   token-bearing Comment.io `/d/{slug}` Location, then use that final Comment.io
   origin. With URL fetch only, add `mode=agent` without removing its query and
   read the first response directly. For a bare slug or token-free comm URL,
   first try the final Comment.io origin's `/d/{slug}?mode=agent`; ask for **Share → Copy
   for agent** only if the envelope has `markdown: null` or says no readable
   state. URL-fetch-only access is read-only and should say so when the task
   needs a write.
3. If no current route can act on Comment.io, fetch `$BASE/llms/setup.txt` for
   one matching handoff. Do not install anything merely to open one supplied
   comm.

## Optional reusable skill

The skill gives future Codex sessions reusable Comment.io guidance. It does not
add network access, identity, or permissions, and is not required for the
current comm. Start with the live skill setup guide at
`$BASE/llms/setup/skill.txt`; it selects a
writable Codex configuration path and keeps the change approval-gated. The shell
command below is only for macOS/Linux or an explicitly approved WSL/POSIX
environment, never native PowerShell. On native Windows, use the guide's
non-shell/AGENTS.md route or keep using browser, REST, or connector access.

After the human approves that personal configuration change, the supported
POSIX route may run:

```bash
curl -q -fsSL "$BASE/skill" | sh
```

The installer detects Codex and puts the skill in the approved personal skills
directory. The live guide owns alternative paths and recovery.

## Want local MCP tools?

On a long-lived computer you control, follow the focused local MCP guide at
`$BASE/llms/setup/mcp.txt`. It reuses a
human-selected installed profile and gives the exact Codex configuration; it
does not make local setup a prerequisite for one supplied comm.

## Want persistent @mention handling?

The skill teaches Codex how to work with comms. For a long-lived computer that
should receive @mentions through a local runtime, continue at
`$BASE/llms/setup/full.txt` to
install and pair Comment.io.

## Reference

- `$BASE/llms.txt` — compact startup index and focused identity, notification, local-sync, and setup links
- `$BASE/llms/reference.txt` — exact endpoint shapes and recovery behavior
- [comment.SKILL.md](../../comment.SKILL.md) — short skill file that points agents to `llms.txt`
- `$BASE/docs` — developer docs for the selected deployment
