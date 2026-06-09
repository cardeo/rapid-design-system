# Risks

RDS is designed to avoid two common failures: no governance and overbuilt governance.

Most design-system problems come from drifting too far in one direction. Either every team makes decisions from scratch, or the system becomes heavy enough that product teams route around it.

The risks below are the failure modes RDS tries to make visible early.

## No Governance

Without governance, teams make the same decisions repeatedly.

Symptoms include inconsistent spacing, inconsistent states, duplicated components, hard-to-maintain screens, design review focused on basics, and engineering re-solving visual decisions.

The fix is not necessarily a large component library. Start with tokens, theme configuration, runtime examples, contribution rules, and a readiness audit.

## Overbuilt Governance

Too much governance slows product work.

Symptoms include every change requiring design-system work, custom wrappers hiding framework capabilities, documentation becoming ceremonial, product teams bypassing the system, and component APIs becoming harder than the primitives they wrap.

The fix is to route work through the lightest responsible path.

## Primitive Misclassification

Teams often mistake utilities, layout primitives, or infrastructure for product-facing components.

This leads to unnecessary design work and unnecessary abstractions.

Classify components before governing them.

## Composition Collapse

Repeated compositions sometimes get collapsed into components too early.

This can freeze product assumptions before the workflow is understood.

Govern the pattern first. Abstract later only when repeated use proves the value.

## Framework Drift

When a design system diverges too far from the underlying UI framework, upgrades become expensive.

Stay close to native structure unless the product need justifies the divergence.

Preserve framework behavior unless there is a clear product reason to replace it.

## Token Pollution

Creating too many tokens makes the system harder to use.

Add tokens when they clarify repeated decisions. Do not add tokens for every local adjustment.

A token should make consistency easier, not create a naming burden.

## Product-Pattern Creep

Product-specific workflows can accidentally enter the core design system.

Keep product patterns separate until they prove reusable across contexts.

A product component can use the design system without becoming part of the design system.

## Design-Tool Drift

Design-tool components can become disconnected from runtime implementation.

Validate important decisions in both places. Use the design tool where design judgment matters and runtime documentation where behavior must be proven in code.

## Documentation Bloat

Documentation that does not guide real work becomes noise.

Prefer concise examples, clear rules, and useful constraints.

If documentation does not help someone build correctly, it is probably too abstract.

## Local Optimization

A shortcut that helps one screen can hurt the system.

Optimize for reusable decisions and long-term portability.

## AI Output Drift

AI-generated design, code, or documentation can drift from the system if it is not checked against tokens, component classification, runtime behavior, accessibility expectations, approved patterns, and product needs.

AI output should be reviewed like any other contribution.

## Risk Check

When a decision feels unclear, ask:

- Is this reducing repeated decisions or creating new ones?
- Is this preserving framework behavior?
- Is this product-specific?
- Is the abstraction stable enough?
- Can a token, theme override, or runtime example solve it?
- Has the decision been validated in product context?
