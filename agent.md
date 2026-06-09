# Agent Operating Manual

This file explains how an AI coding or design agent should apply Rapid Design System.

It is not a prompt pack. It is an operating manual for AI tools working on a design system, UI framework, product frontend, documentation environment, or component library.

An agent using RDS should help the team make proportionate governance decisions. The goal is not to generate the most system surface area. The goal is to reduce UI drift while protecting product velocity.

## Core Rules

Theme existing primitives first.

Customize only when necessary.

Prefer tokens before components.

Prefer composition before abstraction.

Run a Component Readiness Audit before adding meaningful system surface area.

Classify the component before governing it.

Preserve framework behavior unless there is a clear product reason to diverge.

Use runtime validation before locking decisions.

Treat AI output as input, not policy.

Custom components require explicit human approval.

An AI agent may recommend a custom component but should not create one automatically.

Do not treat every requested component as a design-system component. Some concerns should be tokens. Some should be theme overrides. Some should be runtime examples. Some should stay product-specific. Some should be deferred.

## Default Agent Workflow

1. Read [README.md](README.md).
2. Read the relevant section files.
3. Run a Component Readiness Audit.
4. Classify the component or system concern.
5. Recommend the lightest responsible governance path.
6. Implement only after the path is clear.
7. Document the decision.

This workflow keeps the agent from jumping directly from request to abstraction.

## Decision Loop

RDS is the operating methodology.

SWARM is a thinking loop that can be used inside the methodology.

Use it when the system decision is uncertain, when several implementation paths seem plausible, or when the agent needs to explain why a lighter path is enough.

### Spot

Identify the real product need.

Identify existing primitives.

Identify governance signals.

Look for the source of friction:

- visual inconsistency
- repeated setup
- unclear usage
- missing tokens
- unstable product requirements
- accessibility risk
- product-specific workflow behavior

### Weigh

Evaluate token, theme, composition, wrapper, and custom-component tradeoffs.

Ask whether the need can be solved by:

- a token
- a theme override
- existing framework behavior
- a documented composition
- a runtime example
- a thin wrapper
- a design-tool component
- deferring until usage is clearer

Custom components should only be considered after all other options have been exhausted and should require explicit human approval.

Prefer the lowest-cost path that still governs the decision responsibly.

### Arrange

Select the lightest responsible governance path.

Route the work through:

- theme
- code-only primitive
- documentation
- composition pattern
- design-tool support
- thin wrapper
- defer

If none of these paths are sufficient, escalate for human review rather than creating a custom component automatically.

### Refine

Validate against runtime behavior, accessibility, product needs, and maintenance cost.

Check:

- states
- density
- long labels
- real content
- focus behavior
- keyboard behavior
- responsiveness
- token usage
- framework parity

### Make

Implement, document, or intentionally defer.

If implementation happens, keep it close to the framework.

If documentation happens, make it practical.

If deferral is the right decision, record why.

If a custom component appears necessary, escalate for human review rather than implementing it automatically.

## How to Behave Around Frameworks

The UI framework owns structure.

The design system owns governance.

An agent should usually preserve:

- framework APIs
- component anatomy
- overlay behavior
- focus management
- ARIA patterns
- keyboard interaction
- slot behavior
- runtime semantics

Override appearance through theme configuration first.

Use composition before abstraction.

Add wrappers only when they prevent repeated mistakes or encode a stable convention.

Do not create custom components without explicit human approval.

When framework limitations appear to justify a custom component, present the tradeoffs and request a governance decision rather than implementing it automatically.

Do not hide framework capability behind an invented API unless the product need justifies the cost.

## What to Produce

An RDS-aware agent may produce:

- token recommendations
- theme overrides
- readiness audits
- classification notes
- runtime examples
- Storybook examples
- documentation examples
- accessibility checks
- usage guidance
- composition patterns
- thin wrappers when justified
- custom component recommendations for human review
- decision records

An RDS-aware agent should avoid producing:

- speculative component APIs
- prompt-pack style instructions
- exhaustive token taxonomies before usage exists
- design-tool components for every primitive
- wrappers that rename the framework
- product-specific components inside the core system
- documentation that does not guide real work
- unapproved custom components

## Decision Records

When an agent adds or changes system surface area, it should document the decision in plain language:

- the product need
- the classification
- the governance path
- why lighter options were or were not enough
- runtime validation performed
- accessibility considerations
- what remains intentionally outside the system

If a custom component is recommended, the decision record should clearly explain:

- why primitives were insufficient
- why composition was insufficient
- why wrappers were insufficient
- what maintenance burden the component introduces
- why human review is required

The record does not need to be ceremonial.

It should help the next designer, engineer, or agent understand the decision quickly.