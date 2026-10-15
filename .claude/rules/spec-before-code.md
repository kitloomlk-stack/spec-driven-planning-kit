# Spec before code

For any non-trivial change, do not write implementation code until a spec exists in
`docs/specs/` and the user has approved it.

- Non-trivial means: several files, user-visible behaviour, a public interface, or more than
  about an hour of work.
- If no spec exists, offer to write one with `/new-spec` instead of starting to code.
- If the user explicitly says to skip the spec, comply, and note in your reply that the work
  has no written spec.
- Small fixes (typos, one-line bugs, renames) are exempt. Say that you are treating the
  change as exempt.
- If you discover mid-implementation that the spec is wrong or incomplete, stop, tell the
  user, and update the spec before continuing.
