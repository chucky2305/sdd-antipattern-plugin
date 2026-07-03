# Spec-Driven-Development (SDD) Antipatterns

If you write specs for AI agents (or for a team) to build from, you've probably shipped a spec with a hole in it. Not because you wrote it badly, but because you forgot to answer a question you didn't know you needed to answer. The AI then fills that gap with a guess, and the guess is usually wrong.

This repo is a checklist of the 17 most common holes, plus a Claude skill that checks your spec against all of them in one pass and tells you exactly what's missing before you hand it off.

## Get the skill

The skill is called `sdd-review`. Paste it your spec and say "review this spec", it grades the spec against all 17 antipatterns and gives you a pass/warn/fail table plus a list of concrete fixes.

**Using Claude Code?** Install it as a plugin, updates whenever this repo changes:

```
/plugin marketplace add chucky2305/sdd-antipattern-plugin
/plugin install sdd-review@sdd-antipatterns
```

**Using Claude Desktop or Cowork?** Download [`sdd-review.skill`](./sdd-review.skill) and drop it in, no CLI needed.

## The list

Each antipattern lives in its own file in [`antipatterns/`](./antipatterns/):

1. [Not adapting your spec for greenfield vs brownfield projects](./antipatterns/01-greenfield-vs-brownfield.md)
2. [Not stating what the software should AND should not be, including hard boundaries](./antipatterns/02-no-boundaries.md)
3. [Not defining your target audience](./antipatterns/03-no-target-audience.md)
4. [Not connecting your features into a user story](./antipatterns/04-no-user-experience.md)
5. [Not explaining why the software exists, what problem it solves, and what success looks like](./antipatterns/05-no-purpose.md)
6. [Not defining the stage: MVP or first full version?](./antipatterns/06-no-stage-definition.md)
7. [Not mentioning constraints and assumptions](./antipatterns/07-no-constraints.md)
8. [Not mentioning decisions that are already "set in stone"](./antipatterns/08-no-set-in-stone-decisions.md)
9. [Forgetting to define test cases](./antipatterns/09-no-test-cases.md)
10. [Not owning the "what" in your spec](./antipatterns/10-not-owning-the-what.md)
11. [Building the whole thing at once instead of in small, validated slices](./antipatterns/11-waterfall-spec.md)
12. [Writing the spec for a human reader instead of an AI agent](./antipatterns/12-spec-for-humans-not-agents.md)
13. [Not defining a project "constitution" of non-negotiable principles](./antipatterns/13-no-constitution.md)
14. [Trusting the AI to follow the spec instead of verifying it did](./antipatterns/14-trusting-ai-follows-spec.md)
15. [Writing the spec once and letting it go stale](./antipatterns/15-spec-goes-stale.md)
16. [Leaving out non-functional requirements, especially security](./antipatterns/16-no-security-nfr.md)
17. [Over-specifying: writing a heavy spec for work that doesn't need one](./antipatterns/17-over-specifying.md)

## Links

**[Kiro](https://kiro.dev/)** is an agentic IDE by AWS built around spec-driven development. You write a prompt, Kiro turns it into structured requirements, a system design, and a task list, then implements it with AI agents. Relevant here because it shows what a tool looks like when specs are a first-class part of the workflow, not an afterthought.

**[GitHub Spec Kit](https://github.com/github/spec-kit)** is a lightweight toolkit from GitHub to help teams get started with spec-driven development. Contains templates, examples, and guidance for writing specs before writing code.

**[Tessl](https://docs.tessl.io)** is a platform that treats AI context (rules, skills, instructions) like software: versioned, evaluated, and distributed. Useful for teams that want to package and share how they work with AI agents across projects and tools.

## How the skill is built

The `sdd-review` skill's source lives in `skill/`:

- `skill/SKILL.md` is the skill definition.
- `skill/condensed-antipatterns/` holds a condensed checklist version of each antipattern, one file per antipattern (`01-...` through `17-...`), mirroring the top-level `antipatterns/` folder. This is what the skill actually reads at review time.

The files in `antipatterns/` are the full, human-readable source of truth. The files in `skill/condensed-antipatterns/` are condensed copies of them. They are not linked automatically, so if you edit, add, or remove an antipattern, update the matching file in `skill/condensed-antipatterns/`, then rebuild `sdd-review.skill` by zipping the contents of `skill/` (SKILL.md and the condensed-antipatterns folder). Or use the `condense-antipatterns` tool skill in `tools/` to regenerate them automatically.

This repo also doubles as a Claude plugin marketplace (see `.claude-plugin/marketplace.json`). The plugin's source is `skill/` directly, so any commit pushed here is picked up automatically by plugin installs, no separate rebuild step needed for that path.

## Contributing

Found an antipattern that's missing? Open a PR or file an issue.
