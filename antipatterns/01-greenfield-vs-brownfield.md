# Not adapting your spec for greenfield vs brownfield projects

## Example

You're adding a new payment flow to an existing platform. You try to document the entire system before describing the change: how the auth works, how the database is structured, how the notification system behaves. Three hours later you have a 60-page doc, the AI's context window is half gone, and you haven't even started describing what you actually want to build. As [InfoQ](https://www.infoq.com/articles/enterprise-spec-driven-development/) points out, trying to produce one all-covering spec is impractical to review, and that's before the AI even enters the picture.

## Why it's a problem

Greenfield and brownfield projects need completely different spec strategies. With greenfield, you describe everything from scratch. With brownfield, you can't, and you shouldn't try. The existing system is too large to fully document, and even if you got there, you'd burn your context window before the AI writes a single line of useful code.

The other trap is writing too little. If you give no context about the existing system, the AI makes assumptions, touches things it shouldn't, or duplicates logic that already exists.

## How to fix it

For brownfield projects, use two levels of detail:

**Overall description** is a high-level summary of the existing application. Just enough for the AI to understand the shape of the system: what it does, how it's structured, what the main components are. Keep this short and generalistic.

**Detailed description of the affected area** is a precise breakdown of the specific part being changed. Current behavior, data it touches, components involved, edge cases that matter.

This mirrors how practitioners describe brownfield SDD. [Augment Code](https://www.augmentcode.com/guides/what-is-spec-driven-development) recommends you "spec the area of change, not the whole system," and InfoQ puts it plainly: "the spec needs to be most granular near the area of change."

Everything else, the parts of the system that aren't relevant to this change, leave out entirely. Being decisive about what to exclude is just as important as knowing what to include.

This approach also has a compounding benefit: each time you work on a new area of the system, you add a detailed description of it. Over time, your spec becomes a growing map of the parts of your system that have actually been touched, built organically, not all at once.
