# Spec-Driven Planning Kit

This kit makes the agent plan before it codes. For any change that is not trivial, the agent
first clarifies the intent, writes a short spec, records the architecture decisions that
matter, and breaks the work into small tasks. Only then does it implement, one thin slice at
a time. The output of planning is plain Markdown in the repository, so a human can read,
edit and approve it, and a later session can pick it up cold.

## Working agreement

- Do not start implementing a non-trivial change until a spec exists in `docs/specs/` and the
  user has said it is approved. "Non-trivial" means: touches more than one file, changes
  behaviour users can see, changes a public interface, or takes more than about an hour.
- Typo fixes, one-line bugs and pure renames do not need a spec. Say so and proceed.
- If the request is vague, ask questions first. One question at a time, most important
  first. Stop asking when you could write the acceptance criteria without guessing.
- Never invent requirements. If something is unknown, write it under "Open questions" in
  the spec instead of choosing silently.
- Keep planning documents short. A spec that nobody finishes reading is a failed spec.
  Prefer a page over five.
- When the plan and the code disagree, say so and update the plan; do not let it rot.

## Where things live

Use these paths unless the project already has its own convention, in which case follow it.

- `docs/specs/<feature>.md` — one spec per feature or change.
- `docs/adr/NNNN-short-title.md` — one numbered architecture decision record each.
- `docs/plans/<feature>.md` — the ordered task list for a spec.

Create the folders when they are first needed. Do not scatter planning notes elsewhere.

## The workflow

1. **Clarify.** Use the idea and interview skills until the problem, the user and the
   success measure are stated in your own words and the user confirms them.
2. **Specify.** Write the spec with: problem, goals, non-goals, users, requirements,
   acceptance criteria (each one testable), constraints, risks, open questions.
3. **Decide.** For every choice that is hard to reverse (data model, framework, public API,
   auth approach, build or hosting), write an ADR with the options considered and why one won.
   Cheap, reversible choices stay in the spec.
4. **Break down.** Convert the spec into tasks no larger than one focused session. Each task
   has a goal, files likely touched, acceptance check, and what it depends on.
5. **Implement.** Take one task at a time, in order. Finish it, check it against its
   acceptance check, then stop and report before starting the next.
6. **Close the loop.** Tick off tasks, record any deviation from the spec, and write down
   decisions that were made along the way.

## Spec quality checks

Before presenting a spec, confirm each of these:

- Every requirement can be answered with yes or no by someone who did not write it.
- Non-goals are listed, so scope cannot creep in unnoticed.
- Terms are used consistently; a glossary entry exists for anything project-specific.
- Open questions have an owner or a proposed default.
- Nothing in the spec describes how to code it; that belongs in the plan.

## Task quality checks

- A task is done when its acceptance check passes, not when the code is written.
- Order tasks so that the first one produces something runnable end to end, even if crude.
  Prefer thin vertical slices to horizontal layers.
- If a task needs more than one sentence to explain its goal, split it.
- Mark dependencies explicitly. Do not hide blocking relationships in prose.

## Before you finish

- The spec, ADRs and plan agree with what was built.
- Open questions are either resolved or still listed.
- You have told the user what was done, what was not, and what is next.
- No planning file contains secrets, tokens or personal data.

## Skills in this kit

- grill-with-docs — stress-test a plan by interview and record ADRs and a glossary as you go.
- idea-refine — shape a vague idea into a concrete concept before specifying.
- interview-me — extract the real intent when a request is underspecified.
- spec-driven-development — write the PRD or spec before coding starts.
- to-spec — convert an existing conversation into a written spec.
- architecture-decision-records — write a durable ADR for a significant technical choice.
- planning-and-task-breakdown — order and size tasks from an approved spec.
- to-tickets — produce thin tickets with explicit blocking edges.
- wayfinder — plan work too big for one session as a map of decision tickets.
- incremental-implementation — implement the next task as a small, verifiable slice.

If a skill talks about publishing to an issue tracker and the project has none configured,
write the output as Markdown files under `docs/` instead and tell the user.

## Commands

- `/new-spec` — interview the user and write a spec to `docs/specs/`.
- `/decide` — record one architecture decision as a numbered ADR.
- `/break-down` — turn an approved spec into an ordered task list.

## Sub-agents

- `spec-reviewer` — read-only critique of a draft spec. Delegate after writing a spec.
- `plan-auditor` — read-only check that a task list covers its spec. Delegate before starting
  implementation.

## Rules in this kit

- `spec-before-code` — always on; blocks implementation without an approved spec.
- `planning-docs` — conventions for files under `docs/specs`, `docs/adr` and `docs/plans`.
- `task-sizing` — how to size and order tasks in plan files.

## Boundaries

Ask before pushing, deploying, publishing to a tracker, or changing anything outside the
planning documents. Planning never requires running remote scripts or installing tools.

## Scoped rules

Agents that support scoped rules load these automatically. If yours does not, read the matching file before editing files it covers:

- `.agents/rules/spec-before-code.md` — always: Always on: no implementation work starts until a written spec and task list exist for non-trivial changes.
- `.agents/rules/planning-docs.md` — for `docs/specs/**/*.md`, `docs/adr/**/*.md`, `docs/plans/**/*.md`: Conventions for files under docs/specs, docs/adr and docs/plans.
- `.agents/rules/task-sizing.md` — for `docs/plans/**/*.md`, `**/tasks.md`: How to size, order and write tasks in plan and task-list files.
