# Component Readiness Audit

Run a Component Readiness Audit before adding meaningful design-system surface area.

The audit exists to prevent teams from treating every component as equal. Some components need deep governance. Others only need a theme, an example, and a note.

Use the audit when a component may require a design-tool component, a custom wrapper, a new abstraction, a new API, new tokens, new state treatment, or product-specific workflow behavior.

## Audit Questions

The audit should answer:

- What product problem does this component solve?
- Is this a primitive, composition, pattern, or product feature?
- Do existing primitives already solve the behavior?
- Are required tokens already available?
- Are spacing and density rules already governed?
- Are semantic colors sufficient?
- Are states already covered by existing patterns?
- Does the component introduce overlay, focus, keyboard, or layout complexity?
- Does it require design-tool modeling?
- Can runtime documentation provide enough guidance?
- Will a wrapper reduce repeated work or create unnecessary abstraction?
- Is the component stable enough to govern now?

These questions should be answered in plain language. The audit does not need to become a ceremony. It needs to slow the team down just enough to avoid expensive surface area.

## Possible Outcomes

Recommended decision outcomes:

- theme override
- code-only primitive
- composition pattern
- runtime example
- design-tool component
- thin wrapper
- custom component
- defer

A theme override is appropriate when the primitive behavior is right and the work is mostly visual alignment.

A code-only primitive is appropriate when the concern is implementation-facing and has little new design meaning.

A composition pattern is appropriate when existing primitives solve the need but the arrangement should be repeated consistently.

A runtime example is appropriate when guidance is enough and the behavior is better understood in code than in a design tool.

A design-tool component is appropriate when the component introduces visible anatomy, workflow meaning, or state decisions that designers need to use directly.

A thin wrapper is appropriate when repeated setup is stable and error-prone enough to justify a small convenience API.

A custom component is appropriate when existing primitives cannot meet a clear product requirement.

Deferral is appropriate when usage is unclear, requirements are unstable, or the abstraction would freeze assumptions too early.

## AI Assistance

AI can assist the audit by identifying existing primitives, similar implementations, likely token dependencies, accessibility risks, composition opportunities, abstraction risks, and missing states or edge cases.

This can make the audit faster, especially for small teams.

The audit decision remains a human governance decision.

## A Light SWARM Pass

When the decision is unclear, use a short SWARM loop.

Spot: identify the product need and existing primitive.

Weigh: evaluate token, theme, composition, wrapper, and custom-component options.

Arrange: select the lightest responsible governance path.

Refine: validate through runtime and product testing.

Make: implement or defer.

The point is not to add process. The point is to keep the decision proportionate.
