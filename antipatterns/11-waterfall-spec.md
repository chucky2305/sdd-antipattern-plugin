# Building the whole thing at once instead of in small, validated slices

## Example

You spend three weeks writing a 40-page spec, then hand it over and find out half of it is technically impossible, wildly expensive, or based on a misunderstanding of how the system works. The same trap shows up at build time: you give the AI the full spec, say "build it", and it generates the entire feature in one pass. When something's wrong, you can't tell which part caused it, and fixing one thing quietly breaks another.

## Why it's a problem

Specs that don't touch reality stay theoretical. The longer you wait to test your assumptions against actual implementation, the more expensive mistakes become. A spec is a hypothesis, and treating it as a blueprint before validating it is how you waste months.

The same is true once the AI starts building. Asking for too much in one shot is one of the most common AI failure modes: the agent loses the thread, drifts from the spec, and produces a big blob that's hard to review or verify. Small, bounded units let you catch problems early, and independent ones can even run in parallel.

## How to fix it

Work in slices, both when writing the spec and when building from it.

While writing: draft a section, test it against a quick prototype or a dev spike, adjust, then continue. Start by speccing only the login flow. Hand just that over and ask, "Does this make sense? What questions do you have?" The answers surface assumptions you didn't know you were making. Fix those, then move to the next piece. By the time you've covered the whole product, you've already validated most of it.

While building: break the spec into discrete, ordered tasks grouped into phases (setup, then core features, then extras), where each task is something you can verify as done on its own. Aim for "implement the data repository", not "write a function". Then have the AI work one phase at a time: complete tasks 1 to 2, mark them done, stop. Review, run tests, then continue. [JetBrains](https://blog.jetbrains.com/junie/2025/10/how-to-use-a-spec-driven-approach-for-coding-with-ai/) and [Augment Code](https://www.augmentcode.com/guides/what-is-spec-driven-development) both make this task breakdown a first-class part of the workflow.
