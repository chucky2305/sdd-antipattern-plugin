## AP-13: Not defining a project "constitution" of non-negotiable principles

**What it means:** Without a shared set of always-on rules, the AI makes its own architectural choices per feature and the codebase drifts into inconsistency. This is broader than "decisions already made" for one spec: it spans the whole project.

**What a good spec (or its project) includes:**
- A short, separate constitution of hard rules that hold across every feature: architecture rules, security baselines, testing requirements, naming and structure conventions
- Hard rules, not preferences
- Loaded alongside every spec so the AI works inside the same frame each time
