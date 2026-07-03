---
name: condense-antipatterns
description: >
  Regenerates the condensed checklist versions of the SDD antipatterns (in skill/condensed-antipatterns/) from the full narrative source files (in antipatterns/) in the sdd-antipatterns repo. Use this whenever the user says "regenerate the condensed antipatterns", "update the skill antipatterns", "condense antipatterns", or has just edited, added, or removed a file in the root antipatterns/ folder and needs the skill/condensed-antipatterns/ copies to catch up.
---

# Condense SDD Antipatterns

You keep two versions of each antipattern in the `sdd-antipatterns` repo in sync:

- `antipatterns/NN-slug.md` — the full, human-readable source of truth (example, why it's a problem, how to fix it).
- `skill/condensed-antipatterns/NN-slug.md` — a condensed checklist version of the same antipattern, used by the `sdd-review` skill to grade specs.

Your job: read every file in `antipatterns/`, and for each one, write or update the matching file in `skill/condensed-antipatterns/` so it reflects the current content of the source file.

## Condensed format

Each condensed file follows this exact structure:

```
## AP-NN: [Short title, can differ slightly from the source title if it reads better condensed]

**What it means:** [1-2 sentences. Why this matters, no example, no fluff.]

**What a good spec includes:**
- [Bullet, concrete and checkable]
- [Bullet]
- [Bullet]
- [Optional bonus/nice-to-have bullet]
```

Look at the existing files in `skill/condensed-antipatterns/` before you start, they show the established tone: short, imperative, checklist-style. Match it.

## How this works

1. List the files in `antipatterns/` (repo root) and the files in `skill/condensed-antipatterns/`. Note the antipattern number and slug of each.
2. For every file in `antipatterns/`:
   - If no matching numbered file exists in `skill/condensed-antipatterns/`, create it.
   - If a matching file exists, re-read the current source and rewrite the condensed version to match it. Don't just patch, regenerate the whole file so it can't drift into an inconsistent mix of old and new.
3. If a file exists in `skill/condensed-antipatterns/` with no matching number in `antipatterns/` anymore (deleted upstream), delete it and say so.
4. Show the user a short summary: which files were created, updated, or deleted. Don't dump the full diff unless asked.
5. Remind the user that after this, `sdd-review.skill` (the packaged zip used in Cowork/Claude) is stale and needs to be rebuilt by zipping the contents of `skill/` again, and that the changes still need to be committed and pushed.

## Notes

- Don't touch `SKILL.md` itself, this only regenerates the `condensed-antipatterns/` subfolder.
- Preserve numbering exactly as it appears in the source folder (e.g. `07-no-constraints.md` stays `07-no-constraints.md`), even if titles changed.
- If a source file's content barely changed (typo fixes, wording), the condensed version may end up nearly identical, that's fine, just make sure it's regenerated from the current source rather than assumed unchanged.
