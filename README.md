# opencode-sandbox

Thin macOS sandbox wrapper for running the `opencode` CLI in a sandbox.

```bash
./opencode-sandbox <opencode-args>
```

- Sandbox rules are defined in `opencode-dev-only.sb` and applied with `sandbox-exec -f`.
- Default file access: deny all `file-write*`; deny `file-read*`; explicit file access allowlist.
- Default process access: deny all `process-exec`; explicit process execution allowlist
- The process is started with a clean environment using `/usr/bin/env -i`.
- Only these variables are forwarded: `HOME`, `PATH`, `EDITOR`, `VISUAL`, `TERM`, `TMPDIR`.

