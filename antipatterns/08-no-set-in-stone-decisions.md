# Not mentioning decisions that are already "set in stone"

## Example

The team has already decided to use PostgreSQL and deploy on AWS. The spec doesn't mention this. A developer spends time evaluating database options and proposes MongoDB, creating unnecessary back-and-forth.

## Why it's a problem

It wastes time and creates friction. People explore options that were never actually on the table. With an AI agent it's worse: it won't just waste time, it will quietly pick for you. As [Augment Code](https://www.augmentcode.com/guides/what-is-spec-driven-development) puts it, "if you've chosen the database schema or the encryption library, say so. Agents that don't know a decision has been made will make their own." It also signals a lack of trust when decisions get made in the background and only surface later.

## How to fix it

Add a "Decisions already made" section. Include tech stack choices, vendors, architectural patterns, or any other decisions that are locked in and not up for debate. Be clear about why they're locked: budget, existing infrastructure, compliance, and so on. This lets the team, and the agent, focus their energy on decisions that are still open.
