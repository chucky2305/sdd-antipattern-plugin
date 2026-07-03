# Trusting the AI to follow the spec instead of verifying it did

## Example

You write a detailed spec, hand it over, and assume the output matches because the instructions were clear. Nobody checks each part of the result against the spec before it merges.

## Why it's a problem

A detailed spec is not a guarantee. Thoughtworks' Birgitta Böckeler watched Spec Kit research the existing classes, then ignore them in the next step and generate duplicates anyway (via [Florian Gahn's writeup](https://florian-gahn.de/blog/spec-driven-development-claude-code)). Context does not replace verification. LLMs are non-deterministic, so the same spec can produce different, non-compliant results each run. If nothing checks the output against the spec, the gaps reach production.

## How to fix it

Build a verification step into the process, not just the spec. Put explicit, testable acceptance criteria in the spec so there's something concrete to check against. Then actually check: review the output against each criterion, or better, use a separate agent or reviewer whose only job is to find where the implementation diverged. [Augment Code](https://www.augmentcode.com/guides/what-is-spec-driven-development) calls this the adversarial pattern: the agent that wrote the code is the worst judge of whether it's correct, so give the verifier the opposite goal.
