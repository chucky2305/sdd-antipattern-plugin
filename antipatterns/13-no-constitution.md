# Not defining a project "constitution" of non-negotiable principles

## Example

Every feature spec starts from a blank slate. One feature adds rate limiting, the next forgets it. One keeps database access in the repository layer, another queries the database straight from a controller. Nothing says these rules apply everywhere, so they don't.

## Why it's a problem

Without a shared set of always-on rules, the AI makes its own architectural choices per feature, and the codebase drifts into inconsistency. GitHub Spec Kit added a dedicated `constitution.md` for exactly this: non-negotiable principles (testing approach, "CLI-first", coding standards, "no direct database access outside the repository layer") that get loaded into every step. As [Microsoft's write-up](https://developer.microsoft.com/blog/spec-driven-development-spec-kit) describes it, this is how an organization enforces an opinionated stack across every project.

This is different from the "decisions already made" section inside a single spec. Those are choices for one feature. A constitution spans the whole project and every feature you will ever add to it.

## How to fix it

Write a short constitution once, separate from any single spec. List the principles that must hold across the entire project: architecture rules, security baselines, testing requirements, naming and structure conventions. Keep it to hard rules, not preferences. Load it alongside every spec so the AI always works inside the same frame.
