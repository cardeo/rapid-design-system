---
name: rds-readiness-audit
description: Run the Rapid Design System Component Readiness Audit for a proposed component, UI pattern, primitive, wrapper, token/theme change, or design-system surface-area decision. Use before adding meaningful system surface area or when deciding whether to theme, compose, document, wrap, customize, or defer.
---

# RDS Readiness Audit

Use this skill to turn a design-system request into a readiness outcome another RDS skill or agent can consume.

Preserve the existing RDS Component Readiness Audit. Do not invent a new readiness framework.

Canonical sources:

- `../../sections/04-component-readiness-audit.md`
- `../../sections/03-token-vs-component.md`
- `../../sections/02-theme-first.md`
- `../../rapid-design-system.md`

## Procedure

1. Identify the product problem the requested system surface would solve.
2. Identify known existing primitives, framework behavior, tokens, patterns, or product implementations.
3. Evaluate whether the concern adds meaningful design-system surface area.
4. Answer the audit questions that can be answered from available context.
5. Mark unknowns that affect the decision.
6. Select the lightest responsible readiness outcome.
7. State whether component classification should run next.

## Audit Questions

Answer these in concise, practical language:

- What product problem does this solve?
- Is this likely a primitive, composition, pattern, or product feature?
- Do existing primitives already solve the behavior?
- Are required tokens already available?
- Are spacing and density rules already governed?
- Are semantic colors sufficient?
- Are states already covered by existing patterns?
- Does it introduce overlay, focus, keyboard, or layout complexity?
- Does it require design-tool modeling?
- Can runtime documentation provide enough guidance?
- Will a wrapper reduce repeated work or create unnecessary abstraction?
- Is the concern stable enough to govern now?

Do not force certainty. If evidence is missing, say what is unknown and whether the decision can still proceed.

## Readiness Outcomes

Choose one primary outcome:

- theme override
- code-only primitive
- composition pattern
- runtime example
- design-tool component
- thin wrapper
- custom component recommendation for human review
- defer

Use `custom component recommendation for human review` instead of directly approving custom component creation. RDS can recommend that a custom component may be justified, but implementation requires explicit human approval.

## Classification Trigger

Recommend `rds-component-classifier` next when:

- the request names or implies a component
- the concern may be a primitive, layout component, utility, infrastructure, theme override, thin wrapper, composition pattern, or product component
- the product-vs-system boundary is unclear
- governance weight depends on component type

Classification may be unnecessary when the answer is a simple token/theme decision or when missing information blocks the audit.

## Output Shape

Return:

```text
Readiness Audit
- Product need:
- Existing primitive/pattern:
- Decision signals:
- Missing information:
- Readiness outcome:
- Classification recommended: yes/no
- Reason:
- Recommended next direction:
```

Keep the output short enough for an orchestrator to route from it.
