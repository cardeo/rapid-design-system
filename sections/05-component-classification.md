# Component Classification

Classify components before governing them.

Classification keeps effort proportional to value. It prevents teams from putting the same process around a layout primitive, a modal, a product workflow, and a low-level utility.

Different kinds of components deserve different levels of governance.

## Design Components

Design Components are product-facing components that introduce visible design decisions.

They may need design-tool support, runtime support, design review, state documentation, accessibility review, and product workflow validation.

Examples include dialogs, alerts, cards, navigation components, data tables, complex forms, and workflow indicators.

These components can influence how users understand the product. They deserve more design attention.

## Layout Components

Layout Components are structural primitives used to arrange content.

They should usually remain code-first, lightly governed, token-aligned, and minimally customized.

Examples include stack, grid, container, box, and responsive layout primitives.

Layout components usually need strong usage guidance, not custom design-tool modeling.

## Utility Components

Utility Components support behavior but are not usually visual design primitives.

They should usually remain native to the framework, code-first, lightly documented, and validated through examples.

Examples include click-away behavior, portal behavior, responsive helpers, transitions, and low-level autosizing utilities.

Only include utilities in the design system when they reduce developer confusion or clarify approved usage. Do not document utilities just to inflate component count.

## Infrastructure Components

Infrastructure Components are foundation-level components that enable other components.

They should remain lightweight, theme-driven, native to the framework, and minimally abstracted.

Examples include baseline styles, modal infrastructure, popover infrastructure, portal infrastructure, and positioning utilities.

Infrastructure should not become product architecture.

## Theme Overrides

Theme Overrides are pure theme-level customization.

This is the preferred implementation model.

Use theme overrides for color alignment, typography alignment, radius, density, state colors, elevation tuning, and default props.

Theme overrides are usually cheaper than wrappers and easier to keep aligned with the underlying framework.

## Thin Wrappers

Thin Wrappers are small convenience wrappers around existing primitives.

Use them rarely.

A thin wrapper is justified when it reduces repeated setup, prevents common mistakes, encodes a stable product convention, or improves ergonomics without hiding the underlying primitive.

Avoid wrappers that rename every prop, block framework capabilities, invent new behavior, create a parallel API, or make upgrades harder.

## Composition Patterns

Composition Patterns are reusable arrangements built from primitives.

These often belong in documentation and examples before they become components.

Examples include filter toolbar, settings section, empty state layout, card list, form section, and command menu composition.

Govern the pattern first. Abstract it later only if repeated use proves the value.

## Product Components

Product Components are application-specific UI tied to a particular workflow.

They should usually remain outside the core design system.

Examples include billing summary panels, case timelines, account setup wizards, project-specific navigation, and custom analytics dashboards.

Product components may use the design system, but they should not automatically become part of it.

## Why This Matters

Classification prevents overwork and underwork.

A high-visibility workflow component may deserve design-tool modeling, runtime documentation, accessibility review, product validation, and lock-in. A responsive helper may only need a runtime example and a short note. A product-specific dashboard may need to stay inside the product until it proves reusable across contexts.

The classification should happen before implementation. Otherwise the team may create a component first and invent the governance story after the fact.
