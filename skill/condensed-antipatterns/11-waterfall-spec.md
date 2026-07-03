## AP-11: Building the whole thing at once instead of in small, validated slices

**What it means:** Specs that don't touch reality stay theoretical, and asking the AI to build everything in one pass is a top failure mode. A spec is a hypothesis; both the writing and the building should happen in small, verifiable slices.

**What a good spec includes (or implies):**
- Evidence of iterative development: the spec covers a scoped piece, or is explicitly a draft to validate before full build
- A breakdown into discrete, ordered tasks or phases, each verifiable on its own
- Tasks sized like "implement the data repository", not "write a function" and not "build the whole feature"
