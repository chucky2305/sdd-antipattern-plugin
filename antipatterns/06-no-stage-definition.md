# Not defining the stage: MVP or first full version?

## Example

A spec reads like a full product vision, polished UI, edge case handling, multiple user roles, but it's meant to be built in two weeks by one developer to test an idea.

## Why it's a problem

An MVP spec and a v1 spec are completely different documents with different tradeoffs. Conflating them causes over-engineering early (building too much before validating) or under-delivering later (shipping something too rough when users already expect quality). Getting this wrong is a known SDD failure mode: the ThoughtWorks Technology Radar warns that spec-driven development carries "a bias toward heavy up-front specification and big-bang releases," which is exactly what an MVP shouldn't do (via [Augment Code](https://www.augmentcode.com/guides/what-is-spec-driven-development)).

## How to fix it

State the stage explicitly at the top of your spec. Either: "This is an MVP. We're trying to validate [specific assumption]. We're okay with rough edges." Or: "We've validated the market. This is v1. Quality and completeness matter." Everything else in the spec flows from this. And if it's a throwaway prototype, consider skipping the heavy spec altogether: Augment Code lists "prototype is meant to be thrown away" as a case to skip the spec and just prompt.
