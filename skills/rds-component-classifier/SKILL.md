---
name: rds-component-classifier
description: Classify a design-system concern using the Rapid Design System component classification model. Use when deciding whether something is a Design Component, Layout Component, Utility Component, Infrastructure Component, Theme Override, Thin Wrapper, Composition Pattern, or Product Component, and when determining governance weight or product-vs-system boundaries.
---

# RDS Component Classifier

Use this skill to classify a component or design-system concern before governing it.

Preserve the existing RDS classification categories. Do not invent new categories unless the canonical methodology changes.

Canonical sources:

- `../../sections/05-component-classification.md`
- `../../sections/09-composition-over-abstraction.md`
- `../../sections/07-code-only-governance.md`
- `../../rapid-design-system.md`

## Classification Categories

Classify the concern as one primary category:

- Design Component
- Layout Component
- Utility Component
- Infrastructure Component
- Theme Override
- Thin Wrapper
- Composition Pattern
- Product Component

If more than one category seems plausible, name the strongest classification and note the secondary possibility.

## Procedure

1. Identify what the concern is trying to govern.
2. Determine whether it introduces visible product meaning, layout structure, utility behavior, infrastructure, theme-level styling, wrapper ergonomics, repeated composition, or product-specific workflow behavior.
3. Classify it using the RDS categories.
4. Explain the reasoning in practical terms.
5. State the governance weight.
6. State whether it belongs in the core design system, product code, documentation, theme configuration, or human review.
7. Recommend the next direction.

## Governance Weight

Use one of these weights:

- light: native primitive, utility, infrastructure, theme override, or documentation-only concern
- medium: repeated composition, thin wrapper, or visible component with limited workflow meaning
- heavy: product-facing design component, complex states, workflow meaning, design-tool support, accessibility risk, or broad reuse
- product-only: application-specific workflow that should usually remain outside the core design system
- human-review: custom component appears necessary or system impact is high enough to require explicit approval

## Product-vs-System Boundary

Keep product components out of the core design system until reuse is proven across contexts.

A product component can use the design system without becoming part of the design system.

A repeated composition can be documented before it becomes an abstraction.

A thin wrapper is justified only when it reduces repeated setup, prevents common mistakes, or encodes a stable product convention without hiding the underlying primitive.

## Output Shape

Return:

```text
Component Classification
- Classification:
- Secondary classification, if any:
- Reasoning:
- Governance weight:
- Product-vs-system boundary:
- Recommended next direction:
- Unresolved questions:
```

Keep the output structured enough for `rds-orchestrator` to combine it into a final RDS recommendation.
