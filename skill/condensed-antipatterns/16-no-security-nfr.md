## AP-16: Leaving out non-functional requirements, especially security

**What it means:** AI-generated code is measurably insecure by default. If the spec doesn't encode security and other non-functional rules, the model fills the gap with whatever is statistically common, which is often vulnerable. A code issue is usually a spec gap that keeps coming back on regeneration.

**What a good spec includes:**
- Non-functional requirements as first-class items: security constraints, performance budgets, compliance rules, data handling
- Specific and testable ("payment endpoint requires an idempotency key", "no localStorage for session tokens", "rate limit all endpoints")
- Security addressed early, not bolted on at the end
