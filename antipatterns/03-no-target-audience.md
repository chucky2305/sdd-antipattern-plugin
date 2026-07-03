# Not defining your target audience

## Example

A spec says: "This app helps people manage their tasks." Who exactly? A solo freelancer? A team of 50? A non-technical 60-year-old, or a developer who lives in the terminal?

## Why it's a problem

Every design and implementation decision is implicitly about who's using the software. Without a defined audience, everyone on the team makes different assumptions, and so does the AI. You end up building for a person who doesn't exist. [Addy Osmani](https://addyosmani.com/blog/good-spec/) frames a good agent spec around exactly these questions: "Who will use this? What problem does it solve? How will they interact with it?"

## How to fix it

Write a one-paragraph description of your primary user. Include their context, technical level, and what they're actually trying to accomplish. If there are multiple user types, rank them, don't treat them as equal. This is what GitHub's Spec Kit puts first: its opening phase is about "user journeys, experiences, and what success looks like," not the tech.
