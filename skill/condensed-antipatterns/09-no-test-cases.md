## AP-09: Not defining test cases

**What it means:** Without test cases, "done" is subjective. Everyone has a different mental model of what correct behavior looks like.

**What a good spec includes:**
- For each feature: at least three cases, the happy path, one failure case, one edge case
- Enough to align on what "correct" means before anyone writes code
- Bonus: acceptance criteria in a structured form (e.g., EARS, "WHEN [condition] THEN the system SHALL [behavior]")
