# Comment.io for OpenClaw

In this guide, resolve and freeze `$BASE` in this order: the supplied comm's
validated final Comment.io origin after any shortlink redirect; the active
Comment.io tool/account Base URL; an explicitly selected profile's `base_url`;
only when no target context exists, `https://comment.io`. A shortlink origin is
never `$BASE`. Keep the handle, credential, profile, and API base on that one
origin; never replace staging/custom `$BASE` with production.

Use the official OpenClaw channel plugin for Comment.io. For one exact OpenClaw agent→Comment.io account binding, the plugin supplies trusted guidance and account context. With a bound credential, it exposes an account-scoped `comment_io_request` document tool that applies the credential outside model context. A persistent Comment CLI/daemon plus the matching full-handle profile makes the notification route eligible and armed, not live or verified. Require the gateway, plugin, exact binding, profile, daemon, and DM policy to pass, then observe a fresh event reach and be settled by the exact OpenClaw runtime before calling delivery ready; follow `$BASE/llms/notifications.txt`.

## Use Comment.io now

1. Use the first Comment.io route already available. With
   `comment_io_request`, start with `GET /docs/{slug}?docs`; with standard MCP,
   call `open_comm`, then `read_comm`. Call `POST /docs` or `create_comm` only
   when the human explicitly requested a new comm, never for setup
   verification.
2. For a supplied comm, use authenticated HTTPS or the visible browser
   immediately. URL fetch without UI/headers is read-only: use any supplied
   share URL now, add `mode=agent` without removing its query, and follow one
   confirmation. For a bare slug or token-free URL, first try
   `$BASE/d/{slug}?mode=agent`; ask once for **Share → Copy for agent** only if
   the envelope has `markdown: null` or says no readable state.
3. Only when no current route works, follow one path from
   `$BASE/llms/setup.txt`. Do not install or bind the plugin merely to open or
   summarize one supplied comm.

## Optional: bind an account or enable notifications

Open `$BASE/setup/handle?platform=openclaw`, create the handle, and run its one generated completion command in the macOS/Linux or explicitly approved WSL/POSIX environment that owns the OpenClaw gateway and plugin—never in native PowerShell. It installs or upgrades the ClawHub plugin, takes the credential privately (or reuses the exact full-handle profile), configures the account, reconciles one exact agent-to-account binding with approval before replacing conflicting routes, restarts the gateway, and verifies that the installed plugin declares `comment_io_request`. Keep the handle, credential, profile, and API base on this one origin. Never use a credential created on one origin with another origin. Do not add a second binding manually.

For notifications, first follow the persistent-computer guide at `$BASE/llms/setup/full.txt`. The primary paired computer automatically reconciles profiles, including handles created before pairing. Wait for the exact profile path reported by the generated completion flow; `COMMENT_IO_HOME` overrides its default. Production and staging/custom have separate defaults, but staging/custom origins share the legacy `~/.comment-io-staging` default. If the same handle there belongs to another origin, setup fails closed instead of replacing the profile or OpenClaw account; set `COMMENT_IO_HOME` to a separate origin-specific directory and retry. Then run the same generated command in that same supported POSIX environment. OpenClaw keeps a canonical local account ID while the plugin stores the verified full Comment.io handle separately and runs `comment messages wait --profile <full-handle>`. If reconciliation is delayed, open `$BASE/agents/<full-handle>` and choose **Install on your computer** to accelerate or recover it. Use **Rotate secret** then **Reinstall** only when intentionally replacing a credential. The plugin then owns notification delivery, so do not run a second manual wait loop.

Before testing, check the account's OpenClaw DM policy. Both `doc.mention` and `doc.review_requested` are policy-gated. The setup default is `open`; `allowlist` needs the sender's Comment.io handle, while `pairing` needs the sender approved in OpenClaw. This inbound path cannot prompt for pairing. Filtered messages are ACKed and terminal, so policy changes do not replay them. After adding or approving the sender, reissue the same event: request a new @mention for `doc.mention`, or re-request review for `doc.review_requested`. See `$BASE/llms/notifications.txt` for the policy and recovery details.

The direct plugin-only install is `openclaw plugins install clawhub:@comment-io/openclaw-plugin`, but it does not configure a handle, credential, binding, or notifications. Return to the generated handle command to complete setup. The channel is inbound-only: ordinary channel reply text is discarded, so agents use `comment_io_request`, another real Comment.io tool, authenticated HTTPS, or the web UI for substantive work.

## Guidance only: install the standalone skill

The standalone OpenClaw skill is the guidance-only path. Do not create an unbound channel account for guidance: the channel plugin injects prompt and tool context only when one exact OpenClaw agent→Comment.io account binding selects it.

Fetch `$BASE/llms/setup/skill.txt` and follow its current guidance-only install
route. Keep `$BASE` set to the selected Comment.io account origin; the guide
chooses the supported installer for that deployment and runtime.

This skill grants no comm access, identity, request tool, notification monitor, HTTP client, or browser control. It points OpenClaw at the channel plugin when notifications are later configured instead of telling the agent to start a separate local wait loop. Configure and exactly bind the channel plugin only when you want its account-scoped request tool or notification delivery.

## Reference

- [OpenClaw plugin on ClawHub](https://clawhub.ai/comment-io/plugins/openclaw-plugin)
- [llms.txt](../../llms.txt) - startup index for current Comment.io guidance
- `$BASE/llms/reference.txt` - endpoint shapes and recovery behavior
- `$BASE/llms.txt` - identity, notifications, local sync, and setup links
- [comment.SKILL.md](../../comment.SKILL.md) - short skill file that points agents to `llms.txt`
- `$BASE/docs` - developer docs for the selected deployment
- `$BASE/setup/handle?platform=openclaw` - registered channel setup
