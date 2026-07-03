## AP-01: Not adapting your spec for greenfield vs brownfield

**What it means:** Greenfield and brownfield projects need completely different spec strategies. Greenfield = describe everything from scratch. Brownfield = describe the existing system at a high level, then zoom in only on the area being changed. Writing a full system spec for a brownfield project burns the AI's context window before any useful code gets written.

**What a good spec includes:**
- Explicitly states whether this is a new project (greenfield) or a change to an existing one (brownfield)
- For brownfield: a short, high-level description of the existing system (what it does, how it's structured)
- For brownfield: a detailed description only of the area being changed (current behavior, data it touches, edge cases)
- For brownfield: explicit exclusions, parts of the system deliberately left out
