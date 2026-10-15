---
name: decide
description: "Capture one architecture decision as a numbered ADR in docs/adr."
disable-model-invocation: true
---

# decide

When invoked, record one architecture decision (the argument describes the decision, or ask
the user what it is).

1. Look in `docs/adr/` for existing ADRs. Read any that touch the same area. Pick the next
   number in sequence; create the folder if it does not exist.
2. Ask the user for anything missing: the forces at play, at least two real options, and
   what they lean toward. Do not invent options that nobody would consider.
3. Write `docs/adr/NNNN-short-title.md` with: Status (Proposed), Date, Context, Options
   considered (each with pros and cons), Decision, Consequences (good and bad).
4. If the decision replaces an earlier ADR, mark the old one Superseded and link both ways.
   Never rewrite an accepted ADR.
5. Present the ADR to the user for approval. Change the status to Accepted only after they
   agree. Mention if the decision implies changes to a spec or plan.
