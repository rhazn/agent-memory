# Lizard Savehouse

Infrastructure repository at `/Users/pheltweg/development/projects/lizard-savehouse`.

## Pi configuration

- Pi's Git-managed source of truth is `agentic-coding/pi/` (lowercase, as requested). The user wants all Pi-specific configuration work there.
- `pi/scripts/restore` links settings, models, keybindings, instructions, extensions, prompts, themes, and Pi-only skills into the live agent directory, with backups for conflicts. Credentials and sessions remain local.
- Shared instructions and skills still use `agentic-coding/scripts/sync`; the Pi README documents restore and OpenCode parity recommendations.
- Pi preferences: light theme, only `openai-codex/gpt-6-astra` for startup/model cycling, medium thinking, hidden thinking blocks, and no Linear extension. The user no longer needs the Linear integration; its extension was removed. The user no longer wants local models; custom provider definitions were removed.

## Hosts

- `agent-box` is a private NixOS development VM for OpenCode. It currently runs as an ARM VM on an Apple Silicon Mac. Its configuration is in `agent-box/`. When a request refers to the Agent Box, perform the work against this VM configuration, not the local macOS workspace.
- `selfhost-box` is a private NixOS self-hosting VM. It currently runs as a native ARM64 VM on an Apple Silicon Mac. Its configuration is in `selfhost-box/`. Its enrolled Tailscale hostname is `selfhost-box-1.tail3fb05a.ts.net`; the older `selfhost-box` device is offline.

## VM recovery (2026-09-30)

- Agent Box became unresponsive after host sleep with QEMU still running and no watchdog. SIGTERM did not stop QEMU; SIGKILL followed by `agent-box/scripts/vm start` restored it. Selfhost Box had already recovered through its existing watchdog.
- Both VM scripts now use repository-root `scripts/vm-watchdog.sh` to install persistent macOS LaunchAgents with KeepAlive and login startup. Labels are `org.lizard-savehouse.agent-box.watchdog` and `org.lizard-savehouse.selfhost-box.watchdog`. Watchdog crash recovery was tested for both.
- `vm start` ensures monitoring even for an already-running VM; `vm stop` removes its LaunchAgent. Watchdogs recover missing/unresponsive VMs on startup, bound SSH/health checks, and exclude check duration from sleep detection. Agent Box forcibly kills QEMU after its shutdown grace period. Selfhost Box checks Tailscale and restores Komodo, Plane, and Plane MCP routes.
- Runtime logs and disks remain under `~/.local/state/<box>/`. Keep the infrastructure checkout at its installed path. Both boxes remain unavailable while the Mac sleeps or is powered off; monitoring restores access after wake/login.
- Synced all 13 shared skills, agent instructions/documentation, and OpenCode configuration to Agent Box with `agentic-coding/scripts/sync --target agent-box`; checksum dry runs confirmed matching files. Agent Box, Komodo, and Plane returned HTTPS 200, and Plane MCP authenticated successfully.
