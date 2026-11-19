# Working on Code

- When a pinned dependency lacks required functionality, discuss an upgrade
  before building a custom workaround.
- Agree before expanding implementation beyond the requested scope.
- Fix every finding when running Ruff, including pre-existing findings. Do not
  leave Ruff failing merely because the current task did not introduce them.
- In step-by-step project work, Philip reviews and commits each phase. Implement
  and verify the requested phase, then leave the changes unstaged for him.
  A request to split the work into commits or start a phase defines its scope;
  it does not authorize staging or committing. Report the result and the next
  phase, then wait for Philip to tell you to continue.

Keep project-specific constraints in their project context. Do not generalize a
single task's restrictions on tests, runtime, or operations into global rules.
