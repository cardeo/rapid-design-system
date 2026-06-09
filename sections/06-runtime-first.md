# Runtime First

The runtime environment is where component behavior becomes real.

Use a documentation environment such as Storybook, Ladle, Histoire, local examples, or a product sandbox to validate actual rendered components, theme application, interaction behavior, focus states, responsive behavior, density, accessibility behavior, composition patterns, and edge cases.

The design tool remains valuable, but it is not the runtime.

## What Runtime Validation Does Better

Runtime validation reveals behavior that static design artifacts cannot fully prove:

- keyboard interaction
- focus order
- overlay placement
- responsive behavior
- loading and disabled states
- long labels
- dense data
- scroll behavior
- real theme application
- actual implementation constraints

A design-system decision is not complete because a component looks good in isolation. Important components should be validated in real or realistic product contexts.

Validate against dense screens, empty states, error states, loading states, mobile layouts, long labels, real data, permission differences, workflow edge cases, and accessibility expectations.

## The Design Tool Role

The design tool is useful for visual exploration, anatomy, layout direction, interaction notes, handoff references, product workflow modeling, and high-value reusable components.

The design tool should not become a second runtime, a behavioral simulation platform, a parallel engineering environment, or the only source of truth for interactive behavior.

Avoid using the design tool to recreate native keyboard behavior, focus mechanics, portal behavior, transition internals, responsive code behavior, or every low-level utility.

Design-tool components should focus where design judgment matters. Runtime documentation should handle behavior that is better validated in code.

## Documentation Environment Role

The documentation environment is the bridge between design-system intent and implementation reality.

It should help contributors answer:

- What should I use?
- When should I use it?
- What variants are approved?
- What states exist?
- What should I avoid?
- What can I compose?
- What should not be abstracted?

It should include foundations, tokens, component examples, state examples, density examples, layout examples, usage notes, known constraints, and product-like examples.

Documentation should be practical. If it does not help someone build correctly, it is probably too abstract.

## Product Validation

Product validation should not mutate primitives into product-specific components.

It should reveal spacing issues, density issues, missing states, unclear usage guidance, weak composition rules, overbuilt abstractions, and places where the framework primitive is enough.

Use product validation before locking important decisions. A component that works in a clean demo but fails in a dense workflow is not ready.

## AI in Runtime Documentation

AI can help generate runtime examples, state coverage, edge cases, realistic content variations, responsive scenarios, and long-label or dense-data examples.

Generated examples should be reviewed against governance rules, token usage, accessibility expectations, and real product needs.

AI-generated scenarios are prompts for validation. They are not validation themselves.
