# Token vs Component

Tokens are flexible.

Components are expensive.

Tokens can be remapped, themed, extended, and reused across many contexts without changing product architecture. Components carry heavier costs: API design, accessibility expectations, documentation, maintenance, testing, versioning, design-tool parity, migration risk, and product-specific assumptions.

RDS treats custom components as a governance decision, not a default output.

Before creating a custom component, ask:

- Can this be solved with tokens?
- Can this be solved with theme overrides?
- Can this be solved by composing existing primitives?
- Can this be documented as a pattern instead of abstracted?
- Will this reduce product complexity or add system complexity?
- Is the product need stable enough to encode?

If the answer is unclear, do not create the component yet.

## Tokens as the Lowest-Cost Governance Layer

Tokens are the design system's lowest-cost governance layer.

Start with a small set:

- color
- typography
- spacing
- radius
- elevation
- icon sizing
- state treatment
- breakpoints

Keep token sets practical. Avoid creating tokens for every local decision.

Good tokens are reusable, named by purpose, easy to apply, stable across product areas, and understandable to design and engineering.

Weak tokens are too specific, named after one component, created before repeated usage exists, disconnected from runtime implementation, or hard to explain.

Tokens should make consistency easier. They should not become a naming exercise detached from product reality.

## Color Governance

Color should be governed semantically.

Avoid treating raw color ramps as direct product decisions. A practical system should define brand or primary color, neutral scale, semantic feedback colors, text colors, surface colors, border and divider colors, state colors, and optional data visualization colors.

Semantic colors should be used for meaning: success, warning, error, information, disabled, selected, focus, and hover.

Data visualization colors should be kept separate. Do not use chart colors as status colors. Do not use semantic status colors as arbitrary decoration.

## Typography Governance

Typography should create hierarchy, readability, and rhythm.

For most product teams, the goal is not a custom type system. The goal is consistent usage: headings, body text, captions, labels, buttons, dense UI text, and data-table text.

Prefer the typography model of the underlying UI framework unless there is a strong reason to change it.

Govern font family, weights, sizes, line heights, label usage, heading hierarchy, and dense interface text.

Avoid custom typography wrappers, excessive display styles, one-off text sizes, decorative type choices, and hierarchy created only through color.

## Density Governance

Density is one of the most important design-system decisions for product teams.

A product can look polished but still fail if the density does not match the work.

Govern control heights, table row heights, list row heights, input heights, toolbar density, card padding, modal padding, spacing between groups, and mobile adjustments.

Do not solve density one component at a time. Define density as a system behavior. Then apply it consistently through theme overrides, examples, and product validation.

## Overlay Governance

Overlays often cause design-system drift.

Treat overlay weight carefully. Not every overlay is a modal.

Common overlay categories include tooltip, menu, select menu, popover, dropdown, command surface, dialog, drawer, and modal infrastructure.

Govern elevation, border radius, surface color, spacing, backdrop behavior, focus management expectations, dismissal behavior, and stacking discipline.

Avoid turning lightweight menus into modal systems, adding backdrops where the framework does not expect them, inventing overlay infrastructure too early, or creating product-specific overlay managers without clear need.

Preserve the intended interaction weight of each primitive.

## Decision Test

Use the lightest responsible layer:

- Use a token when the decision should apply broadly.
- Use a theme override when the framework primitive is right but its defaults need alignment.
- Use a pattern when primitives compose well but usage needs guidance.
- Use a component when repeated, stable product usage deserves governed surface area.
- Defer when the product need is still unclear.
