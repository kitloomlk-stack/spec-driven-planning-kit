# Spec-Driven Planning Kit

Planning-first workflow for coding agents: turn a rough idea into a spec, record architecture decisions, and break the work into small verifiable tasks before any code is written.

A setup for AI coding agents, made by [Kitloom](https://kitloom.site). One source, generated for every major agent: Claude Code, OpenAI Codex, Cursor, Google Antigravity, Gemini CLI, GitHub Copilot, Windsurf (Devin), opencode and Aider.

## Install

1. Download this repository as a ZIP, or use the **Check and download** button on its Kitloom page, which checks it first.
2. Read the files. Nothing here runs on its own: the kit has no hooks and no install scripts.
3. Copy the folders and files you want into the root of your project. `AGENTS.md` is the shared instructions file; edit it to fit your project.

## What is inside

### Skills

- `grill-with-docs` — Stress-test a vague plan with a relentless interview that also records ADRs and a glossary as you go.
- `idea-refine` — The idea is still fuzzy; diverge and converge on a sharp concept before writing a spec.
- `interview-me` — The request is underspecified and the real intent has to be extracted one question at a time.
- `spec-driven-development` — Write the PRD or spec (objectives, scope, acceptance criteria) before any implementation starts.
- `to-spec` — Synthesize an already-discussed conversation into a written spec without another interview.
- `architecture-decision-records` — A significant technical choice needs a durable, well-structured ADR with alternatives and consequences.
- `planning-and-task-breakdown` — Split an approved spec into ordered, estimable tasks with clear acceptance criteria.
- `to-tickets` — Turn a spec into thin tracer-bullet tickets that declare what blocks what.
- `wayfinder` — The work is too large for one session; map it as decision tickets and resolve them one at a time.
- `incremental-implementation` — Pick up the next task from the plan and deliver it as a thin, verifiable slice.

### Commands

Invoke by name (for example `/new-spec`).

- `new-spec` — Interview the user and write a spec to docs/specs/<name>.md.
- `decide` — Capture one architecture decision as a numbered ADR in docs/adr.
- `break-down` — Turn an approved spec into an ordered task list in docs/plans.

### Sub-agents

- `spec-reviewer` — Delegate to critique a draft spec for ambiguity, missing acceptance criteria and untestable claims.
- `plan-auditor` — Delegate to check that a task list fully covers its spec, is ordered correctly and has no oversized tasks.

### Scoped rules

- `spec-before-code` — Always on: no implementation work starts until a written spec and task list exist for non-trivial changes.
- `planning-docs` — Conventions for files under docs/specs, docs/adr and docs/plans.
- `task-sizing` — How to size, order and write tasks in plan and task-list files.

## Where each agent finds it

| Agent | Instructions | Skills and commands | Rules | Sub-agents |
|---|---|---|---|---|
| Claude Code | `CLAUDE.md` (imports `AGENTS.md`) | `.claude/skills/` | `.claude/rules/` | `.claude/agents/` |
| OpenAI Codex | `AGENTS.md` | `.agents/skills/` | listed in `AGENTS.md` | `.codex/agents/` |
| Cursor | `AGENTS.md` | `.agents/skills/`, `.claude/skills/` | `.cursor/rules/` | `.claude/agents/` |
| Google Antigravity | `AGENTS.md` | `.agents/skills/` | `.agents/rules/` | `.agents/agents/` |
| Gemini CLI | `AGENTS.md` via `.gemini/settings.json` | `.agents/skills/`, `.gemini/commands/` | listed in `AGENTS.md` | `.gemini/agents/` |
| GitHub Copilot | `AGENTS.md` | `.agents/skills/`, `.github/prompts/` | `.github/instructions/` | `.claude/agents/` |
| Windsurf (Devin) | `AGENTS.md` | `.agents/skills/`, `.windsurf/workflows/` | `.windsurf/rules/` | — |
| opencode | `AGENTS.md` | `.agents/skills/`, `.opencode/commands/` | listed in `AGENTS.md` | `.opencode/agents/` |
| Aider | `AGENTS.md` via `.aider.conf.yml` | — | — | — |

Skills are stored twice (`.agents/skills/` and `.claude/skills/`) because Claude Code reads only its own folder. Agents that read both may list a skill twice; delete the copy you do not need.

## Credits

The skills come from these open-source repositories, each under its own licence. Their licence and a notice are kept beside every copied skill.

| Skill | Source | Licence |
|---|---|---|
| `grill-with-docs` | [mattpocock/skills](https://github.com/mattpocock/skills) at `49dd158` | MIT |
| `idea-refine` | [addyosmani/agent-skills](https://github.com/addyosmani/agent-skills) at `aeac41d` | MIT |
| `interview-me` | [addyosmani/agent-skills](https://github.com/addyosmani/agent-skills) at `aeac41d` | MIT |
| `spec-driven-development` | [addyosmani/agent-skills](https://github.com/addyosmani/agent-skills) at `aeac41d` | MIT |
| `to-spec` | [mattpocock/skills](https://github.com/mattpocock/skills) at `49dd158` | MIT |
| `architecture-decision-records` | [wshobson/agents](https://github.com/wshobson/agents) at `46891e7` | MIT |
| `planning-and-task-breakdown` | [addyosmani/agent-skills](https://github.com/addyosmani/agent-skills) at `aeac41d` | MIT |
| `to-tickets` | [mattpocock/skills](https://github.com/mattpocock/skills) at `49dd158` | MIT |
| `wayfinder` | [mattpocock/skills](https://github.com/mattpocock/skills) at `49dd158` | MIT |
| `incremental-implementation` | [addyosmani/agent-skills](https://github.com/addyosmani/agent-skills) at `aeac41d` | MIT |

Everything else in this repository (instructions, rules, commands, sub-agents) is by Kitloom under the MIT licence.

## Use at your own risk

Read every file before you use it. Agent instructions can make an agent run commands on your machine. This kit was checked with Kitloom's pre-download check, which looks for warning signs but cannot prove anything is safe.
