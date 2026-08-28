---
name: rds-token-theme-advisor
description: Evaluate Rapid Design System token and theme decisions. Use when deciding whether a concern should be a token, semantic token, theme override, framework theme setting, local product treatment, composition pattern, or component avoidance path; for color, typography, density, spacing, radius, elevation, overlay, state treatment, dark mode, and token-vs-component questions.
---

# RDS Token Theme Advisor

Use this skill to make RDS-informed token and theme governance recommendations.

Preserve the existing RDS methodology. Do not invent a new token system, naming taxonomy, or framework-specific implementation pattern.

Canonical sources:

- `../../sections/02-theme-first.md`
- `../../sections/03-token-vs-component.md`
- `../../sections/09-composition-over-abstraction.md`
- `../../sections/11-risks.md`
- `../../rapid-design-system.md`

## Boundary

Make design-system decisions and recommendations.

Do not implement framework code. Do not write React, Vue, CSS, MUI theme code, Radix code, or other implementation unless RDS later adds that responsibility.

Recommend implementation direction only, such as:

- use an existing framework theme capability
- introduce or reuse a semantic token
- use a theme override
- keep the treatment local to product code
- use composition rather than a component
- avoid creating a token because the value is too contextual or one-off
- route back to readiness or classification if the concern is structural rather than token/theme-related

## Procedure

1. Identify the visual or semantic concern being evaluated.
2. Identify whether the concern is repeated, stable, semantic, and useful across product contexts.
3. Determine whether existing tokens, semantic colors, typography, spacing, density, radius, elevation, overlay, or state treatment can govern it.
4. Determine whether the framework theme should own the implementation mechanics.
5. Decide whether the concern belongs in system token/theme governance or should remain local product treatment.
6. Prefer token/theme governance before component abstraction when the primitive behavior is already sufficient.
7. Recommend the lightest responsible next direction.

## Decision Rules

Use or introduce a semantic token when the decision represents reusable product meaning across contexts.

Use a theme override when the framework primitive is right but its defaults need alignment.

Use framework theme capabilities when the concern maps cleanly to existing theme slots, palette roles, typography variants, density controls, radius, elevation, breakpoints, overlay behavior, or state treatment.

Keep a treatment local when it is one-off, screen-specific, experimental, or tied to a product workflow that has not proven reuse.

Avoid creating tokens for every local adjustment. Token pollution makes the system harder to use.

Avoid creating a component when tokens, theme overrides, or composition can govern the decision.

Escalate back to `rds-readiness-audit` or `rds-component-classifier` when the concern is actually structural, behavioral, product-specific, or component-surface related.

## Common Concerns

For color, prefer semantic meaning over raw ramps. Keep status colors, state colors, text colors, surface colors, borders, and data visualization colors distinct.

For typography, prefer the underlying framework model unless there is a strong reason to change it. Govern hierarchy, readability, labels, dense UI text, and data text.

For density and spacing, distinguish primitive anatomy from composition spacing. Do not create a token for a one-off spacing value.

For radius and elevation, prefer system-level consistency and framework theme slots before local exceptions.

For overlays, preserve the intended interaction weight of each primitive. Do not turn lightweight menus into modal systems through theme decisions.

For dark mode, treat it as system-level theme architecture, not a one-off set of color swaps. Recommend semantic token coverage before implementation.

## Output Shape

Return:

```text
Token/Theme Recommendation
- Concern:
- Semantic/design intent:
- Token/theme governance appropriate: yes/no/partial
- Recommended governance level:
- Token/theme recommendation:
- Framework ownership:
- Product-vs-system boundary:
- Recommended next direction:
- Unresolved questions:
```

Keep the output structured enough for `rds-orchestrator` to combine it into a final RDS recommendation.
