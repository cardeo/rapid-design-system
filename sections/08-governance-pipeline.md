# Governance Pipeline

Use a pipeline that matches risk.

The full pipeline is:

> Readiness Audit -> Design Tool -> QA -> Framework Parity -> Code -> Runtime Docs -> Product Validation -> Lock

AI assistance may be applied at any stage of the pipeline, but it should not replace governance checkpoints, runtime validation, QA, or product validation.

Not every component needs every step.

## Full Pipeline

Use the full pipeline for high-visibility components, workflow-heavy components, reusable product patterns, components with complex states, and components that introduce new visual language.

The full pipeline is appropriate when the component changes how users understand or complete work in the product.

In these cases, the team should audit the need, model the design where useful, check quality, preserve framework parity, implement carefully, document runtime behavior, validate in realistic product contexts, and then lock the decision.

Locking does not mean the component can never change. It means the system has decided this is the approved path until new evidence appears.

## Shorter Pipeline

Use a shorter pipeline for low-level primitives:

> Readiness Audit -> Theme -> Code -> Runtime Docs -> QA

This path works when the framework already provides most behavior and the design-system work is mostly governance and alignment.

It is common for layout primitives, utilities, infrastructure, and theme overrides.

## Documentation-Only Pipeline

Use documentation-only governance when the framework already handles the component well:

> Readiness Audit -> Usage Guidance -> Example -> QA

This path works when the behavior is native to the framework, does not need a wrapper, only needs usage guidance, and is better shown through examples than modeled as a component.

Documentation-only is still a real governance decision. It tells the team that the approved path is to use the primitive directly with clear guidance.

## Defer

Deferring is a valid governance decision.

Use defer when product usage is unclear, requirements are unstable, the abstraction would be speculative, or the component might encode product architecture too early.

Deferral should be documented briefly. The point is not to avoid work forever. The point is to wait until the system has enough evidence.

## A SWARM Pass for Routing

Spot the product need, existing primitive, risk level, and governance signals.

Weigh the available paths: theme, code-only, documentation-only, design-tool plus code, wrapper, custom component, or defer.

Arrange the lightest responsible pipeline.

Refine through QA, framework parity, runtime validation, product validation, and maintenance review.

Make the decision visible in documentation or a decision record.

The pipeline exists to reduce drift, not to create ceremony.
