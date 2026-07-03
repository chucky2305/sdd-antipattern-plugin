## AP-12: Writing the spec for a human reader instead of an AI agent

**What it means:** An SDD spec is consumed by an agentic process, not a colleague who can ask around or lean on tribal knowledge. Anything left implicit ("handle auth the usual way") gets filled with generic guesses.

**What a good spec includes:**
- Everything a human would otherwise infer, spelled out: no "as usual", no unstated conventions
- Decisions that would normally live in someone's head or an old chat thread, written down
- Passes the test: someone with zero knowledge of the team could build the right thing from the document alone
