# Forgetting to define test cases

## Example

A spec describes what the login flow should do but never defines what "working" means. What happens with a wrong password? An expired session? A network error halfway through?

## Why it's a problem

Without test cases, "done" is subjective. Everyone on the team has a different mental model of what correct behavior looks like. You only discover the gaps when a user hits them. [Augment Code](https://www.augmentcode.com/guides/what-is-spec-driven-development) counts verification criteria as one of the six things every spec needs, and frames it as "not 'does it work' but: what tests pass and what edge cases are handled."

## How to fix it

For each feature, define at least three cases: the happy path (everything works), one failure case (something goes wrong), and one edge case (unexpected input or state). You don't need a full QA suite. You just need enough to align on what "correct" means before anyone writes a line of code. A structured format helps the AI too: tools like Kiro write acceptance criteria in EARS notation, "WHEN [condition] THEN the system SHALL [behavior]" (via [Florian Gahn](https://florian-gahn.de/blog/spec-driven-development-claude-code)).
