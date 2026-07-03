# Not stating what the software should AND should not be, including hard boundaries

## Example

A spec says: "Users can upload files." It doesn't say anything about which file types are allowed, what the size limit is, or whether executable files are blocked.

## Why it's a problem

Developers fill in the blanks themselves, and they all fill them in differently. You end up with inconsistent behavior, untested edge cases, and surprises in production that nobody planned for. It's worse with an AI agent, which expands scope by default. As [Augment Code](https://www.augmentcode.com/guides/what-is-spec-driven-development) puts it, "the out-of-scope list matters at least as much as the in-scope list. Agents expand scope if you don't close the door on it." Their example: "'OAuth is out of scope for this task' is not obvious to an agent that has learned that auth systems usually include OAuth."

## How to fix it

For every "should", ask: "what should it NOT do?" Add explicit exclusions. If there's a size limit, state it. If a file type is blocked, state it. If a feature is out of scope, write it down, not as a footnote, but as a first-class part of the spec. Hard "never" rules matter most: in a GitHub study of over 2,500 agent files, [Addy Osmani](https://addyosmani.com/blog/good-spec/) notes that "'Never commit secrets' was the single most common helpful constraint."
