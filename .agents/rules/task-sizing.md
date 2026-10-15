---
trigger: glob
globs: "docs/plans/**/*.md,**/tasks.md"
description: "How to size, order and write tasks in plan and task-list files."
---

# Task sizing and ordering

Applies to plan files and task lists.

- A task fits in one focused session. If you cannot name its acceptance check in one
  sentence, it is too big; split it.
- Every task has: a title, the goal in one sentence, files likely touched, an acceptance
  check, and its dependencies (or "none").
- The first task must produce something that runs end to end, even if crude. Build vertical
  slices, not layers (not "all models, then all APIs, then all UI").
- Put risky or unknown work early so surprises show up while the plan is still cheap to change.
- Do not combine refactoring with feature work in one task. Give each its own task.
- Use checkboxes (`- [ ]`) for status. Tick one only after its acceptance check passed.
- Estimates, if given, are rough ranges (small, medium, large), not precise hours.
- When a task turns out bigger than planned, stop and split it in the plan before continuing.
