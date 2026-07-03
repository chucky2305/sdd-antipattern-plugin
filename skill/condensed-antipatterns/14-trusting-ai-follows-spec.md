## AP-14: Trusting the AI to follow the spec instead of verifying it did

**What it means:** A detailed spec is not a guarantee. LLMs are non-deterministic and will ignore parts of the spec (e.g., researching existing classes, then duplicating them anyway). Context does not replace verification.

**What a good spec includes:**
- Explicit, testable acceptance criteria so there is something concrete to check the output against
- A verification step in the process: review each criterion, or use a separate verifier/reviewer whose job is to find where the implementation diverged
- Not relying on the implementing agent to self-certify
