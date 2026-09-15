# Lizard Savehouse

Infrastructure repository at `/Users/pheltweg/development/projects/lizard-savehouse`.

## Pi configuration

- Pi's Git-managed source of truth is `agentic-coding/pi/` (lowercase, as requested). The user wants all Pi-specific configuration work there.
- `pi/scripts/restore` links settings, models, keybindings, instructions, extensions, prompts, themes, and Pi-only skills into the live agent directory, with backups for conflicts. Credentials and sessions remain local.
- Shared instructions and skills still use `agentic-coding/scripts/sync`; the Pi README documents restore and OpenCode parity recommendations.
- Pi preferences: light theme, only `openai-codex/gpt-6-astra` for startup/model cycling, medium thinking, hidden thinking blocks, and the existing Linear extension. The user no longer wants local models; custom provider definitions were removed.

## Hosts

- `agent-box` is a private NixOS development VM for OpenCode. It currently runs as an ARM VM on an Apple Silicon Mac. Its configuration is in `agent-box/`. When a request refers to the Agent Box, perform the work against this VM configuration, not the local macOS workspace.
- `selfhost-box` is a private NixOS self-hosting VM. It currently runs as an x86_64 VM on an Apple Silicon Mac. Its configuration is in `selfhost-box/`.
