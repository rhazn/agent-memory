# Lizard Savehouse

Infrastructure repository at `/Users/pheltweg/development/projects/lizard-savehouse`.

## Hosts

- `agent-box` is a private NixOS development VM for OpenCode. It currently runs as an ARM VM on an Apple Silicon Mac. Its configuration is in `agent-box/`. When a request refers to the Agent Box, perform the work against this VM configuration, not the local macOS workspace.
- `selfhost-box` is a private NixOS self-hosting VM. It currently runs as an x86_64 VM on an Apple Silicon Mac. Its configuration is in `selfhost-box/`.
