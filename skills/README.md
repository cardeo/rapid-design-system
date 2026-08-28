# RDS Skills

RDS is a methodology/system that can contain composable agent skills. It is not itself a single skill and it is not tied to one agent harness.

This proof of concept includes four skills:

- `rds-orchestrator`: interpret natural-language RDS intent and route to available specialist skills.
- `rds-readiness-audit`: run the Component Readiness Audit and produce a structured outcome.
- `rds-component-classifier`: classify a design-system concern using the RDS component classification model.
- `rds-token-theme-advisor`: evaluate token, semantic token, and theme-governance decisions.

The canonical RDS methodology remains in [`../rapid-design-system.md`](../rapid-design-system.md) and [`../sections`](../sections). Skills should reference that material instead of copying the whole methodology into parallel instructions.

For now, RDS stops at design-system decisions and implementation direction. Coding in React, Vue, MUI, Radix, CSS, or another framework remains the responsibility of the surrounding agent environment.
