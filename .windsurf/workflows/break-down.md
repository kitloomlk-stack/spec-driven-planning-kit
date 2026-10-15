# break-down

Turn an approved spec into an ordered task list in docs/plans.

# break-down

When invoked, turn an approved spec into an ordered task list. The argument names the spec;
if it is missing, list the files in `docs/specs/` and ask which one.

1. Read the spec. If its status is not Approved, tell the user and ask whether to proceed
   anyway. Read related ADRs and the relevant code.
2. Create `docs/plans/<feature-name>.md`. For each task give: a checkbox title, the goal in
   one sentence, the requirement or acceptance IDs it serves, files likely touched, the
   acceptance check, and dependencies.
3. Order the tasks so the first is a thin end-to-end slice. Put risky unknowns early.
   Keep refactoring tasks separate from feature tasks. No task may be larger than one
   focused session.
4. Delegate to the `plan-auditor` sub-agent if available and fix any gaps it reports.
5. Summarize the plan for the user: task count, the first task, and the biggest risk.
   Do not start implementing; wait for the user to say which task to begin.
