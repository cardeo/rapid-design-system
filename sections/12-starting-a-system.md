# Starting a System

For a team starting from scratch, begin by governing the primitives you already have.

Do not begin by designing every component in a design tool.

Do not begin by creating a package of custom wrappers.

Do not begin by building a complete design-system universe.

Start with the minimum useful system that reduces UI drift without slowing delivery.

## Recommended Starting Sequence

1. Choose the UI framework or component library.
2. Define foundational tokens.
3. Apply a theme.
4. Set up a runtime documentation environment.
5. Document foundations.
6. Audit core primitives.
7. Add theme overrides where needed.
8. Document approved component usage.
9. Validate components in real product screens.
10. Create wrappers only after repeated usage proves the need.

This sequence keeps the system close to product reality. It also keeps the team from spending early energy on speculative abstractions.

## Minimum Useful System

A useful first version should include:

- color tokens
- typography tokens
- spacing tokens
- radius tokens
- elevation guidance
- icon sizing
- state treatment
- core component theme overrides
- runtime examples
- documentation for common primitives
- a Component Readiness Audit
- contribution rules
- anti-patterns

This is enough for many teams to reduce UI drift without slowing engineering.

The system can grow later when usage proves the need.

## What Not to Build First

Avoid starting with:

- full component rewrites
- custom form systems
- custom overlay managers
- custom navigation frameworks
- custom animation systems
- complete design-tool parity
- exhaustive token taxonomies
- product-specific workflow components
- design-system packages before usage stabilizes

These may become useful later. They should not be the starting point.

## Operating Checklist

Use this checklist before adding to the design system.

Is there a real product need? If no, defer.

Does the UI framework already solve this? If yes, theme or document it first.

Is the component visually meaningful? If yes, consider design-tool support. If no, runtime documentation may be enough.

Does it introduce new tokens? If yes, confirm the tokens are reusable beyond this component.

Does it introduce new behavior? If yes, validate accessibility, keyboard interaction, focus, and states.

Is this a primitive, composition, or product feature? Classify it before implementing it.

Can an example solve the problem? If yes, avoid abstraction.

Will a wrapper reduce or increase complexity? Only wrap when it clearly reduces repeated work or prevents mistakes.

## Success Formula

Theme existing primitives first.

Customize only when necessary.

Govern usage before inventing infrastructure.

Use tokens before custom components.

Prefer composition before abstraction.

Validate in runtime before locking decisions.

Classify components before governing them.

Keep utilities lightweight.

Keep infrastructure native.

Use design-tool effort where design meaning exists.

Avoid wrappers unless they reduce real complexity.

AI assists the work. Governance owns the decisions.

Protect product velocity.

Optimize for portability.

Build enough system to reduce drift, not enough to slow delivery.
