---
name: new-spec
description: "Interview the user and write a spec to docs/specs/<name>.md."
disable-model-invocation: true
---

# new-spec

When invoked, write a spec for the feature or change the user describes (the argument, if any).

1. Restate the request in two or three sentences and ask the user to confirm or correct it.
2. Interview the user one question at a time about the problem, the users, the success
   measure, scope boundaries and constraints. Use the interview and idea-refinement skills
   when the request is vague. Stop when you could write testable acceptance criteria.
3. Read the existing code and docs enough to avoid contradicting them. Do not modify code.
4. Create `docs/specs/<feature-name>.md` (kebab-case name) with a status line of Draft and
   these sections: Problem, Goals, Non-goals, Users, Requirements (R1, R2...), Acceptance
   criteria (A1, A2...), Constraints, Risks, Open questions.
5. Delegate to the `spec-reviewer` sub-agent if available, and fold in its valid findings.
6. Show the user a short summary and the open questions, and ask for approval. Do not mark
   the spec Approved yourself and do not begin implementation.
