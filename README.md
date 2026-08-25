# Agent Memory

This private repository is the shared, durable memory for agents working with the user across local and Agent Box sessions.

## Rules

- Read `INDEX.md` first, then only the files relevant to the current task.
- Store durable facts, decisions, project status, and recurring-work checkpoints in the smallest relevant file.
- Keep entries concise and date information when its age matters.
- Do not store credentials, tokens, passwords, private keys, or unnecessary sensitive personal information.
- Record personal information only when the user explicitly provides or confirms it as durable memory.
- Agents manage this repository: after meaningful updates, stage, commit, and push the changes.

## Layout

- `INDEX.md`: active projects, workflows, and the memory map.
- `profile.md`: explicitly provided user facts and preferences.
- `projects/`: durable context for each project.
- `workflows/`: state for recurring work and deduplication.
- `sessions/`: concise cross-project summaries and handoffs.

## Locations

- Local Mac: `/Users/pheltweg/development/projects/agent-memory`
- Agent Box: `/home/agent/workspaces/agent-memory`
