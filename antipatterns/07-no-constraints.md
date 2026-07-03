# Not mentioning constraints and assumptions

## Example

A spec assumes the user always has a stable internet connection, that the app only runs on modern browsers, and that data is always in English, but none of this is written down anywhere.

## Why it's a problem

Developers make decisions based on unstated assumptions, and an AI agent does the same, filling every gap with a statistically likely guess. When those assumptions are wrong, things break in unexpected ways at the worst possible time, and the longer they stay hidden, the more expensive they are to fix. [Augment Code](https://www.augmentcode.com/guides/what-is-spec-driven-development) draws the line clearly: "If it affects implementation choices and isn't obvious from the codebase alone, it belongs in the spec."

## How to fix it

Add a "Constraints & Assumptions" section to your spec. List what you're taking for granted: technical environment, user behavior, data shape, scale, language, third-party API limits, performance requirements. Don't forget the services you depend on: connections to connected systems (payment providers, auth, external APIs) are constraints too, and their limits and failure modes belong here. If you're not sure what your assumptions are, try asking "what would break this?" The answers are usually your hidden assumptions.
