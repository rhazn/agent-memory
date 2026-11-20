# Working on Code

- When a pinned dependency lacks required functionality, discuss an upgrade
  before building a custom workaround.
- Agree before expanding implementation beyond the requested scope.
- Fix every finding when running Ruff, including pre-existing findings. Do not
  leave Ruff failing merely because the current task did not introduce them.

Keep project-specific constraints in their project context. Do not generalize a
single task's restrictions on tests, runtime, or operations into global rules.
