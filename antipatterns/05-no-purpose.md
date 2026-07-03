# Not explaining why the software exists, what problem it solves, and what success looks like

## Example

A spec jumps straight into features without ever saying: "People currently struggle with X. This software fixes it by doing Y. We'll know it worked when Z."

## Why it's a problem

Without a clear purpose, it's impossible to make good tradeoffs. Every decision, what to build, what to cut, what counts as done, requires knowing what you're trying to achieve. Without it, you optimize for the wrong things. This is why GitHub's Spec Kit separates the "what and the why" into its own first step and, per [Microsoft](https://developer.microsoft.com/blog/spec-driven-development-spec-kit), "explicitly excludes technical decision making" there, so you focus on motivation before mechanics.

## How to fix it

Add a problem statement at the top of your spec. Three things: what's broken today, how your software fixes it, and what success looks like in concrete terms. [Addy Osmani](https://addyosmani.com/blog/good-spec/) reduces a good spec to the same core questions: "What problem does it solve? What does success look like?" If you can't write this in a few sentences, you don't understand the problem well enough yet.
