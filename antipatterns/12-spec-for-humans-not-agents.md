# Writing the spec for a human reader instead of an AI agent

## Example

A spec reads like a classic PRD. It leans on shared context ("handle auth the usual way", "follow our normal error format") and assumes the reader knows the team, the codebase, and past decisions. A human teammate fills those gaps fine. An AI agent fills them too, but with generic guesses.

## Why it's a problem

The whole point of an SDD spec is that an agentic process picks it up and builds from it, not a person who can ask around or lean on tribal knowledge. As [Augment Code](https://www.augmentcode.com/guides/what-is-spec-driven-development) puts it, a PRD gets its ambiguity resolved through "conversation, tribal knowledge", while an SDD spec is resolved through "explicit constraints". Anything you leave implicit, the agent answers for you, and usually not the way you wanted. It has learned that auth systems "usually" include OAuth, so it adds OAuth you never asked for.

## How to fix it

Write for the agent, not for a colleague. Spell out what a human would infer on their own. Drop the "as usual" and the unstated conventions. If a decision lives only in someone's head or an old chat thread, put it in the spec. A good test: could someone with zero knowledge of your team build the right thing from this document alone? If not, the agent can't either.
