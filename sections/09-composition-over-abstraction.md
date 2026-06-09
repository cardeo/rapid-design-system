# Composition Over Abstraction

Composition is often enough.

Before creating a new abstraction, ask whether an example composition would solve the problem.

A composition is a reusable arrangement built from primitives. It can be documented, demonstrated, copied, adapted, and validated before becoming an API.

An abstraction is a stronger decision. It creates a component surface, maintenance expectations, documentation requirements, and migration cost.

Composition keeps product teams flexible. Abstraction should be earned.

## Prefer Composition When

Prefer composition when primitives already exist, layout is the main concern, product usage is still evolving, behavior is native to the framework, or the pattern is easy to document.

Examples include filter toolbars, settings sections, empty state layouts, card lists, form sections, and command menu compositions.

These patterns can often be governed through runtime examples and usage guidance before they become components.

That is usually healthier than freezing the first version into a reusable API.

## Prefer Abstraction When

Prefer abstraction when usage is repeated, setup is error-prone, a stable product convention exists, accessibility would otherwise be missed, or the abstraction reduces meaningful complexity.

A good abstraction should make the product easier to build and the system easier to maintain.

A weak abstraction hides the framework, renames familiar APIs, blocks legitimate use cases, or encodes assumptions from one screen too early.

## Thin Wrappers

Thin wrappers are one possible abstraction, but they should stay thin.

Use a wrapper when it reduces repeated setup, prevents common mistakes, encodes a stable product convention, or improves ergonomics without hiding the underlying primitive.

Avoid wrappers that rename every prop, block framework capabilities, invent behavior, create a parallel API, or make upgrades harder.

The best wrapper feels like a small guardrail. It should not become a private framework.

## Product Components

Composition also helps keep product components out of the core design system until they prove reusable.

A billing summary panel, case timeline, setup wizard, project-specific navigation, or analytics dashboard may use design-system primitives. That does not automatically make it part of the design system.

Keep product patterns separate until they prove reusable across contexts.

## Decision Test

Before abstracting, ask:

- Is the setup repeated across product areas?
- Are teams making the same mistakes?
- Is the behavior stable?
- Does the abstraction preserve framework behavior?
- Will this reduce product complexity more than it adds system complexity?
- Can a runtime example solve the problem for now?

If an example solves the problem, avoid abstraction.

If repeated use proves the value, abstract deliberately.
