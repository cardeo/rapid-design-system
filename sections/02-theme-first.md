# Theme First

Theme First is the default posture of Rapid Design System.

Start by theming the UI framework or component library already in use. Do not begin by creating custom components.

Most teams already have access to primitives with accessibility behavior, keyboard interaction, focus management, ARIA patterns, layout behavior, overlay behavior, state APIs, and component composition models.

RDS assumes those primitives should remain the foundation unless there is a clear product reason to replace them.

## Theme-First Architecture

The default implementation path is:

> Theme -> Compose -> Document -> Validate

Only move beyond this path when the product need is clear.

The preferred order of operations:

1. Use the existing primitive.
2. Apply tokens through theme configuration.
3. Compose primitives for common patterns.
4. Document approved usage in the runtime environment.
5. Validate against real product screens.
6. Add a wrapper only when repeated product usage proves it is needed.
7. Create a custom component only when the primitive cannot meet the requirement.

Avoid starting with custom wrappers, new component APIs, custom slot systems, parallel interaction models, design-tool-only component systems, or speculative product abstractions.

The strongest design systems are often not the most custom. They are the ones where the team knows exactly when not to customize.

## Ownership Boundaries

The UI framework owns structure.

The design system owns governance.

The framework or component library should usually own:

- primitive structure
- keyboard interaction
- focus behavior
- accessibility contracts
- runtime behavior
- placement and overlay mechanics
- lower-level component APIs

The design system should usually own:

- color tokens
- typography tokens
- spacing tokens
- radius tokens
- elevation tokens
- density guidance
- semantic state treatment
- usage examples
- composition rules
- documentation standards
- quality gates

This separation keeps teams from accidentally rebuilding the UI framework inside the design system.

## Structural State Principle

Structure should remain stable. States should remain visual.

Interactive states should not cause layout changes. Across hover, focus, selected, active, disabled, loading, and pressed states, preserve dimensions, padding, border width, spacing, alignment, layout geometry, and grouped-control structure.

State changes should primarily affect background, foreground color, icon color, border color, opacity, emphasis, and shadow when appropriate.

Avoid hover padding changes, state-based border-width changes, layout shifts on selection, tricks to hide broken boundaries, moving labels or icons unless the primitive explicitly supports it, and changing component size between states.

This principle keeps UI stable, predictable, and easier to implement. It also makes theme overrides safer.

## Composition Spacing Principle

Primitive spacing and composition spacing are different concerns.

Do not solve every spacing issue at the primitive level.

For example, icon-to-label spacing is primitive spacing. Option-to-option spacing is composition spacing. Field-to-helper-text spacing is primitive spacing. Form-section-to-form-section spacing is composition spacing.

Preserve compact primitive pairings: checkbox and label, radio and label, icon and text, input and helper text, avatar and label.

Preserve larger composition rhythm: option groups, toolbar sections, form sections, card groups, page regions, modal content blocks.

A good design system distinguishes local anatomy from surrounding layout.
