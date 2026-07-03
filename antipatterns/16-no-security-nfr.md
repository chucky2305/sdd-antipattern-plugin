# Leaving out non-functional requirements, especially security

## Example

The spec covers what the feature does but says nothing about security, performance, or data handling. No mention that session tokens must not go in localStorage, that endpoints need rate limiting, or that the payment endpoint must be idempotent.

## Why it's a problem

AI-generated code is measurably insecure by default. Veracode tested over 100 models on 80 tasks and found insecure code in 45% of cases, with Java failure rates above 70% (via [JAVAPRO](https://javapro.io/de/spec-driven-development-warum-die-zukunft-der-ai-gestuetzten-softwareentwicklung-mit-der-spezifikation-beginnt/)). If the spec doesn't encode the security and non-functional rules, the model fills the gap with whatever is statistically common, which is often vulnerable. And a code issue is really a spec gap: regenerate from the same spec and the same hole comes back.

## How to fix it

Put non-functional requirements in the spec as first-class items: security constraints, performance budgets, compliance rules, data handling. Make them specific and testable ("payment endpoint requires an idempotency key", "no localStorage for session tokens"). Add security early, not as a final pass. Heeki Park's lesson from bolting OAuth on at the end: it forced a full redeploy of the stack.
