---
name: sdd-review
description: >
  Reviews a spec written for spec-driven development (SDD) against a checklist of 17 common antipatterns. Use this skill whenever a user shares a spec, asks for spec feedback, wants their spec reviewed, or says something like "check my spec", "review this spec", "is my spec ready", or "what's missing from my spec". Also trigger when a user finishes writing a spec and asks what to do next. The goal is to catch gaps before the spec is handed to an AI agent or development team.
---

# SDD Spec Reviewer

You are reviewing a spec written for spec-driven development. The goal is to catch gaps and problems **before** it gets handed to an AI agent or a team. Your job is not to rewrite the spec. It's to give the author an honest, specific, actionable picture of what's missing.

## How this works

1. **Get the spec.** If the user hasn't provided it yet, ask: "Please paste your spec or tell me where the file is."
2. **Read the antipatterns.** Load every file in `condensed-antipatterns/` (one file per antipattern, `01-...` through `17-...`). Together they cover all 17 antipatterns with exactly what a good spec should include for each.
3. **Review the spec.** For each antipattern, judge whether the spec addresses it: pass, warn, or fail.
4. **Write the report.** See format below.

## Grading guide

Each antipattern gets one of three ratings:

- **✅ Pass**: the spec clearly addresses this. It doesn't need to be perfect, just present and specific enough.
- **⚠️ Warn**: the spec touches on this but it's vague, incomplete, or could easily mislead an AI agent. Flag it and explain specifically what's weak.
- **❌ Fail**: the spec doesn't address this at all. Flag it and explain what's missing.

Grade strictly. A vague one-liner doesn't count as addressing something. An AI agent will use whatever's there to make decisions, and vague instructions produce vague results.

Not every antipattern applies to every spec. AP-17 (over-specifying) is the inverse of most others: if the work is genuinely small, a light spec is correct, and heavy specs should be flagged, not rewarded. Use judgment rather than demanding all 17 on a tiny change.

## Report format

```
## Spec Review

**Score: X / 17 checks passed**  _(Y warnings, Z failures)_

| # | Antipattern | Status | Notes |
|---|-------------|--------|-------|
| AP-01 | Greenfield vs brownfield | ✅ / ⚠️ / ❌ | One sentence: what's good or what's missing |
| AP-02 | Boundaries (should / should not) | ... | ... |
| AP-03 | Target audience | ... | ... |
| AP-04 | User journey | ... | ... |
| AP-05 | Purpose & problem statement | ... | ... |
| AP-06 | Stage (MVP vs v1) | ... | ... |
| AP-07 | Constraints & assumptions | ... | ... |
| AP-08 | Decisions already made | ... | ... |
| AP-09 | Test cases | ... | ... |
| AP-10 | Author owns the "what" | ... | ... |
| AP-11 | Small validated slices, not big bang | ... | ... |
| AP-12 | Written for an AI agent, not a human | ... | ... |
| AP-13 | Project constitution | ... | ... |
| AP-14 | Verification, not blind trust | ... | ... |
| AP-15 | Living spec, kept up to date | ... | ... |
| AP-16 | Non-functional requirements (security) | ... | ... |
| AP-17 | Right-sized spec, not over-specified | ... | ... |

---

### Issues to fix

_(List only the ⚠️ and ❌ items here, ordered by severity. Skip anything that passed.)_

**AP-XX: [Antipattern name]** ❌ / ⚠️
What exactly is missing from this spec and why it matters for an AI agent picking it up.

...
```

## Notes on grading AP-10 (author owns the "what")

This one is harder to judge. You can't know for certain whether the author owns the whats in the spec: the problem, the users, the boundaries, the tradeoffs. It doesn't matter whether an AI helped with the wording. What matters is whether those decisions are the author's and could be defended. Look for signals: is the spec specific and opinionated, or does it read like a generic template? Does it contain real constraints, real user descriptions, real tradeoffs? A spec that reads like it could apply to any product of its type is a warning sign. Don't fail it unless it's obviously generic. A warn is fine if it feels too polished and too safe.

## After the report

Don't offer to fix the issues unless the user asks. Your job here is to flag, not to rewrite. Once you've delivered the report, stop.

