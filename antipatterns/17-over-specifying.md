# Over-specifying: writing a heavy spec for work that doesn't need one

## Example

A one-line bug fix gets pushed through the full pipeline and comes out as four user stories with sixteen acceptance criteria spread across a dozen markdown files.

## Why it's a problem

SDD has real overhead, and it doesn't always pay for itself. Birgitta Böckeler describes Kiro blowing a tiny bug up into exactly that pile of user stories, a "sledgehammer to crack a nut", and says she'd rather review code than a stack of markdown files (via [Florian Gahn](https://florian-gahn.de/blog/spec-driven-development-claude-code)). When the review effort exceeds the code you saved, the spec is making things worse. Exploratory work and throwaway prototypes suffer the same way: a spec there just creates the impression of clarity without the substance.

## How to fix it

Match the spec weight to the work. [Augment Code](https://www.augmentcode.com/guides/what-is-spec-driven-development) offers a clean test: if you'd be annoyed to have the agent interpret the requirement differently than you meant, write a spec; if you could fix the output in a quick follow-up prompt, skip it and just prompt. Write full specs for work that ships to production, spans multiple sessions, or is expensive to get wrong. Skip them for small, mechanical, or exploratory changes.
