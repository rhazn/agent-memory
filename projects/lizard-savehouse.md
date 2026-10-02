# Lizard Savehouse

Infrastructure repository at `/Users/pheltweg/development/projects/lizard-savehouse`.

## Pi configuration

- Pi's Git-managed source of truth is `agentic-coding/pi/` (lowercase, as requested). The user wants all Pi-specific configuration work there.
- `pi/scripts/restore` links settings, models, keybindings, instructions, extensions, prompts, themes, and Pi-only skills into the live agent directory, with backups for conflicts. Credentials and sessions remain local.
- Shared instructions and skills still use `agentic-coding/scripts/sync`; the Pi README documents restore and OpenCode parity recommendations.
- Pi preferences: light theme, medium thinking, hidden thinking blocks, and no Linear extension or local models.
- Pi 1.0.0 migration (2026-10-02): default `openai-codex/gpt-6.1-sol`; cycling matches OpenCode's six models (`gpt-5.6-terra`, `gpt-5.6-sol`, `gpt-5.6-luna`, `gpt-6-luna`, `gpt-6-astra`, `gpt-6.1-sol`). The user explicitly chose to keep the existing Codex login and use native MCP instead of the old adapter. `pi-web-access` is pinned to 0.35.0. All models are built in, so `models.json` stays empty. MCP servers/credentials stay local; none are declared by the repository. Restore tests and isolated Pi 1.0.0 model-resolution/native-MCP/web-extension loading checks passed without model requests.

## Hosts

- `agent-box` is a private NixOS development VM for OpenCode. It currently runs as an ARM VM on an Apple Silicon Mac. Its configuration is in `agent-box/`. When a request refers to the Agent Box, perform the work against this VM configuration, not the local macOS workspace.
- `selfhost-box` is a private NixOS self-hosting VM. It currently runs as a native ARM64 VM on an Apple Silicon Mac. Its configuration is in `selfhost-box/`. Its enrolled Tailscale hostname is `selfhost-box-1.tail3fb05a.ts.net`; the older `selfhost-box` device is offline.

## VM recovery (2026-09-30)

- Agent Box became unresponsive after host sleep with QEMU still running and no watchdog. SIGTERM did not stop QEMU; SIGKILL followed by `agent-box/scripts/vm start` restored it. Selfhost Box had already recovered through its existing watchdog.
- The user explicitly rejected persistent macOS LaunchAgents as too much and requested manual recovery only. Both LaunchAgents were unloaded and deleted, and all automatic watchdog code was removed. Do not reinstall automatic supervision without the user's request.
- Use `agent-box/scripts/vm restart` or `selfhost-box/scripts/vm restart`. Both give SSH shutdown 10 seconds, then force-stop QEMU from the host if contact fails. Successful guest shutdown gets 30 seconds; any surviving process gets SIGTERM and then SIGKILL after 10 seconds. Both wait for QEMU exit before booting again and use bounded boot/service restoration. `stop` uses the same fallback; `start` only boots the VM.
- Restart restores Agent Box's private OpenCode route, or Selfhost Box's existing Plane/Plane MCP stacks and Komodo/Plane/Plane MCP routes. Verified both forced-restart paths by suspending their real QEMU processes with SIGSTOP, then running the manual restart commands; both recovered and all three web endpoints returned HTTPS 200.
- Runtime logs and disks remain under `~/.local/state/<box>/`. Both boxes remain unavailable while the Mac sleeps or is powered off. Run manual restart after wake if access does not recover.
- Synced all 13 shared skills, agent instructions/documentation, and OpenCode configuration to Agent Box with `agentic-coding/scripts/sync --target agent-box`; checksum dry runs confirmed matching files. Agent Box, Komodo, and Plane returned HTTPS 200, and Plane MCP authenticated successfully.
