---
name: rds-orchestrator
description: Interpret natural-language Rapid Design System requests and route them through the available RDS specialist skills. Use when a user asks for RDS guidance, wants to add or evaluate a design-system component, asks whether something belongs in a design system, asks how to govern a UI pattern, or gives a design-system task without naming a specific RDS skill.
---

# RDS Orchestrator

Use this skill as the entry point for general Rapid Design System work.

RDS is the methodology/system. This orchestrator coordinates RDS capabilities; it does not replace the canonical methodology or duplicate every specialist procedure.

Canonical sources:

- `../../README.md`
- `../../agent.md`
- `../../rapid-design-system.md`
- `../../sections/04-component-readiness-audit.md`
- `../../sections/05-component-classification.md`
- `../../sections/03-token-vs-component.md`
- `../../sections/02-theme-first.md`
- `../../sections/08-governance-pipeline.md`

## Operating Principles

Preserve the RDS philosophy:

- Theme existing primitives first.
- Customize only when necessary.
- Prefer tokens before components.
- Prefer composition before abstraction.
- Run a Component Readiness Audit before adding meaningful system surface area.
- Classify the component before governing it.
- Preserve framework behavior unless there is a clear product reason to diverge.
- Treat AI output as input, not policy.
- Do not create custom components without explicit human approval.

## Recognize User Intent

Route natural-language requests into the proof-of-concept workflow when the user asks to:

- add, create, introduce, or evaluate a design-system component
- decide whether a pattern belongs in the system
- decide whether something should be a component, token, theme override, wrapper, composition, runtime example, or product-only concern
- decide whether a visual treatment should live in tokens, semantic tokens, theme configuration, framework theme settings, or local product code
- introduce or evaluate color, typography, spacing, density, radius, elevation, overlay, state treatment, or dark-mode governance
- review a component contribution
- evaluate repeated UI work for possible system governance
- create a custom component
- clarify product-vs-system boundaries

This proof of concept only supports routing to:

- `rds-readiness-audit`
- `rds-component-classifier`
- `rds-token-theme-advisor`

If the request clearly needs a future skill that does not exist yet, say so and provide the best RDS-informed direction using the canonical methodology.

## Routing Procedure

1. Read enough of the user request and available project context to identify the design-system concern.
2. If the concern is primarily a token, semantic token, visual state, theme override, framework theme, dark mode, spacing, density, color, typography, radius, elevation, or overlay question, route to `rds-token-theme-advisor`.
3. If the concern would add meaningful system surface area, route first to `rds-readiness-audit`.
4. Use the readiness outcome to decide whether classification or token/theme guidance is useful.
5. Route to `rds-component-classifier` when the concern is a component, primitive, wrapper, composition, product component, theme override, or unclear system boundary.
6. After classification, route to `rds-token-theme-advisor` when the classification or recommended next direction calls for semantic state guidance, token decisions, theme overrides, framework theme usage, or avoiding component abstraction through token/theme governance.
7. Combine the specialist outputs into a concise RDS decision or recommendation.
8. Stop when RDS has produced useful design-system direction.

Do not continue into framework implementation. RDS may recommend implementation direction, but the surrounding coding agent or harness owns actual code changes.

## Ask or Infer

Infer when the request provides enough context to identify the product need, likely primitive, repeated pattern, or system concern.

Ask for missing information when a responsible RDS decision depends on information that is not present, especially:

- the actual product problem is unclear
- no framework or primitive context is available and the decision depends on it
- reuse is claimed but not evidenced
- the request implies a custom component
- the system/product boundary is ambiguous
- accessibility, overlay, focus, keyboard, or workflow behavior may be affected

Ask the fewest questions needed to continue.

## Handoff Convention

When routing to a specialist skill, provide the specialist with:

- user request
- product need, if known
- existing framework or primitive, if known
- evidence of reuse or instability, if known
- suspected risks
- question the specialist should answer
- prior specialist output, when routing from one skill to another

## Consume Specialist Output

Expect `rds-readiness-audit` to return:

- audit summary
- decision signals
- readiness outcome
- whether classification is recommended
- missing information

Expect `rds-component-classifier` to return:

- classification
- reasoning
- governance weight
- product-vs-system boundary
- recommended next direction
- unresolved questions

Expect `rds-token-theme-advisor` to return:

- concern
- semantic/design intent
- whether token/theme governance is appropriate
- recommended governance level
- token/theme recommendation
- framework ownership
- product-vs-system boundary
- recommended next direction
- unresolved questions

## Stop Conditions

Return control to the user when:

- a clear RDS recommendation is available
- the responsible answer is defer
- the next step requires human approval
- the next step is framework implementation
- a future, unimplemented RDS skill would be required
- missing information blocks a responsible decision

For custom components, stop and request explicit human approval before implementation.

## Output Shape

Prefer a concise Markdown response with:

- RDS decision
- skill path used
- why this path fits
- recommended next direction
- questions or approval needed, if any
