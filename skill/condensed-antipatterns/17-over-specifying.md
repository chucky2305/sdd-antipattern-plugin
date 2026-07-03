## AP-17: Over-specifying (a heavy spec for work that doesn't need one)

**What it means:** SDD has real overhead and doesn't always pay for itself. Pushing a tiny bug or a throwaway prototype through the full pipeline creates a pile of markdown that costs more to review than the code it saved.

**What a good spec includes (right-sizing signals):**
- Spec weight matched to the work: full specs for production, multi-session, or expensive-to-get-wrong work
- Small, mechanical, or exploratory changes handled with a quick prompt instead of a formal spec
- Test: if you'd be annoyed to have the agent interpret the requirement differently than you meant, write a spec; if you could fix the output in a quick follow-up, skip it
