## AP-15: Writing the spec once and letting it go stale

**What it means:** A spec that isn't maintained becomes a lie ("spec-once" development). With AI in the loop it's worse, because the spec is supposed to be the source of truth the agent builds from, and drift compounds every iteration.

**What a good spec includes:**
- Signs it is a living document, updated when direction changes, not frozen at kickoff
- Spec and code kept in sync (spec-anchored), updating the spec treated as routine as refactoring
