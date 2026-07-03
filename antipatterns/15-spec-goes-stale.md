# Writing the spec once and letting it go stale

## Example

The spec kicks off the project, then everyone moves into the code. Three weeks later the code has changed a dozen times and the spec still describes a product that no longer exists.

## Why it's a problem

A spec that isn't maintained quietly becomes a lie. AWS's Heeki Park calls this ["spec-once" development](https://heeki.medium.com/using-spec-driven-development-with-claude-code-4a1ebe5d9f29): the spec launches the project and is then forgotten. It's worse with AI in the loop, because the spec is supposed to be the source of truth the agent builds from. When code and spec diverge, the next AI change is grounded in a stale description, and the drift compounds with every iteration.

## How to fix it

Treat the spec as a living document. When you change direction mid-build, update the spec before or alongside the code, not "later". [Florian Gahn](https://florian-gahn.de/blog/spec-driven-development-claude-code) frames the maturity levels: spec-first (write once, then abandon) is the weak version; spec-anchored (the spec lives with the feature and is updated on every change) is what you actually want. Updating the spec should feel as routine as refactoring.
