# Code-Only Governance

Not every component needs design-tool modeling.

Some components are implementation primitives rather than design primitives. They introduce little new anatomy, little new visual language, little new token demand, and little new governance learning.

They primarily consume existing tokens, existing state treatments, existing composition rules, and native framework behavior.

For these components, consider:

> Theme -> Code -> Runtime Docs -> QA

without requiring a dedicated design-tool component.

## When Code-Only Is Enough

Code-only governance is often enough when the component:

- is a layout primitive
- is a utility
- is infrastructure
- has little new anatomy
- is already well-covered by the UI framework
- primarily consumes existing tokens
- can be explained clearly in runtime documentation

This path is especially useful for stacks with strong primitives. If the framework already handles structure, accessibility, focus behavior, keyboard interaction, or overlay mechanics, the design system may only need to govern usage and theme alignment.

## What Code-Only Still Requires

Code-only does not mean ungoverned.

A code-only primitive should still have clear token usage, theme alignment, examples, constraints, accessibility expectations where relevant, and QA.

It should still be classified. It should still pass the readiness audit if it adds meaningful system surface area. It should still be validated in runtime.

The difference is that the design tool is not forced to model something that does not need visual decision-making.

## Benefits

Code-only governance reduces duplicate work, maintenance burden, design-tool drift, delayed implementation, and false complexity.

It keeps the design tool focused on decisions that benefit from visual modeling and keeps implementation-facing concerns close to the implementation.

The goal is not to skip design quality. The goal is to apply design effort where it creates real leverage.

## Watchouts

Code-only governance can fail if teams use it to avoid decisions that do need shared design language.

Do not use code-only governance for components that introduce meaningful visible anatomy, carry workflow meaning, require design review, have complex states that designers need to reason about, or are likely to be reused across product areas in visually important ways.

When in doubt, classify the component and ask what kind of decision it represents.

A utility can stay code-only. A modal pattern probably cannot. A product-specific workflow component may need product design, but still may not belong in the core system.
