# Rapid Design System

### Theme-First Governance for Fast-Moving Teams

Rapid Design System (RDS) is a theme-first methodology for building practical design systems in fast-moving product teams.

It is also becoming an executable design-system problem-solving framework: a set of reusable agent skills that help capable AI agents apply RDS to ambiguous design-system decisions.

Instead of asking a generic AI a design-system question, ask RDS.

A general-purpose model may know a lot about design systems. RDS gives that model a coherent, opinionated context for reasoning about them: explicit decision frameworks, bounded specialist procedures, and orchestration for deciding which RDS reasoning applies to the problem.

RDS does not replace human judgment. It helps people and agents reduce unnecessary design-system decisions without turning the system into a blocker.

## What RDS Solves

RDS helps teams decide what deserves design-system governance and what does not.

It is useful for questions like:

- Should this become a component?
- Is this actually a design-system concern or product-specific UI?
- Should this value become a token?
- Should this treatment live in the theme?
- Is this repeated pattern mature enough to move into the system?
- Should we wrap the framework primitive or keep using it directly?
- Are we abstracting too early?
- Should this visual state be governed globally or locally?
- Does this need a custom component?
- What belongs in the design system versus the product?

The basic idea is simple:

> Theme existing primitives first. Customize only when necessary.

A design system should reduce decisions, not create new ones.

## How RDS Thinks

RDS starts from the primitives, frameworks, and product realities a team already has. It favors tokens, theme configuration, runtime validation, and clear contribution boundaries before custom components or heavy process.

RDS is methodology-first, stack-agnostic, and AI-aware. It can be applied with Material UI, Radix, shadcn, Ant Design, Chakra, Mantine, custom component libraries, internal UI kits, and hybrid systems.

The default path is:

```text
Theme -> Compose -> Document -> Validate
```

The core boundary is:

```text
The UI framework owns structure.
The design system owns governance.
```

That means RDS usually asks whether an issue can be solved with tokens, semantic state treatment, theme overrides, composition, runtime examples, or documentation before recommending a wrapper or custom component.

## Ask RDS

Working on a UI decision? Give your agent the relevant context and say:

```text
RDS this. Should this pattern become part of the design system?
```

Users ask design-system questions. RDS determines which parts of the methodology need to answer them.

Example questions:

- "RDS this: should this repeated pattern become a component?"
- "Should this visual state be a token, theme override, or local treatment?"
- "We keep building this UI in different places. Is it mature enough for the design system?"
- "I need a date-range picker. How should RDS approach this before we build anything?"
- "Our framework component gets us 80% there. Should we customize it, wrap it, or build our own?"
- "Is this a design-system concern or product-specific UI?"
- "Should selected-row background be a semantic token?"
- "Audit this proposed component using RDS. Should it actually exist?"
- "Are we abstracting this too early?"
- "RDS this UI and tell me what belongs in the design system versus the product."

## Real Decisions

### Repeated Form Status

A product repeatedly communicates required, completed, and incomplete form-field states.

A generic response might jump toward creating a component.

RDS can reason through readiness, classification, and token/theme concerns and conclude that this is better represented as a governed **composition pattern with semantic state treatment**, while retaining the framework's existing form primitives.

### Selected Row Treatment

A team repeatedly uses a selected-row background treatment across data surfaces.

RDS can determine whether this represents a reusable semantic state that belongs in token/theme governance rather than creating a new component.

### One-Off Spacing

A screen happens to use `12px` spacing once.

RDS should be able to recommend that it remain local rather than creating another system token simply because a value exists.

## How The Skill Layer Works

RDS can be read and applied by humans. It can also be executed by capable agents through reusable skills.

```text
Your design-system question
        ↓
RDS
        ↓
Relevant methodology + decision procedures
        ↓
RDS-informed recommendation
```

The current layers are:

- **Methodology**: how RDS thinks about design systems.
- **Orchestrator**: determines which RDS reasoning applies to the problem.
- **Specialist skills**: execute bounded RDS decision processes.
- **AI runtime/model**: provides the general reasoning capability used to apply RDS.

The current skills are:

- [`rds-orchestrator`](skills/rds-orchestrator/SKILL.md): routes natural-language RDS questions.
- [`rds-readiness-audit`](skills/rds-readiness-audit/SKILL.md): runs the Component Readiness Audit.
- [`rds-component-classifier`](skills/rds-component-classifier/SKILL.md): classifies design-system concerns.
- [`rds-token-theme-advisor`](skills/rds-token-theme-advisor/SKILL.md): evaluates token, semantic token, and theme-governance decisions.

See [skills/README.md](skills/README.md) for the current skill-system overview.

## Using RDS With An AI Agent Today

RDS itself is not an AI model or standalone chat application. It needs to be available to a capable AI coding or agent runtime that can read this repository and follow the skill files.

What works today:

1. Clone or open this repository in an agent-capable environment.
2. Make sure the agent can read this repo, including [skills](skills).
3. Ask a natural-language design-system question and explicitly invoke RDS:

```text
Use RDS to evaluate this component.
```

```text
RDS this. Should this visual state live in the theme?
```

4. If the environment supports skills, use [`rds-orchestrator`](skills/rds-orchestrator/SKILL.md) as the entry point.
5. If the environment does not automatically discover repo-local skills, tell the agent to read and follow [`skills/rds-orchestrator/SKILL.md`](skills/rds-orchestrator/SKILL.md).
6. RDS returns a design-system recommendation, decision, question, or approval request.
7. The surrounding coding agent or harness may perform implementation separately if desired.

Current limitation: this repository includes standard `SKILL.md` files, but it does not yet provide one-command installation, automatic skill registration, package distribution, or universal agent-runtime adapters.

Where this could go:

- packaged skill installation for specific agent environments
- adapters for runtimes that use different skill formats
- optional tooling for validating skill outputs
- additional specialist skills added only when real RDS usage exposes a concrete gap

## What RDS Does Not Do

RDS does not try to put everything into the design system.

It does not automatically generate a component library.

It does not replace design review, accessibility judgment, product context, or human governance.

It does not require a specific framework, design tool, IDE, or agent harness.

It does not make AI output policy. AI output is input. The system and team still decide what belongs.

## Contents

1. [Why RDS](sections/01-why-rds.md)
2. [Theme First](sections/02-theme-first.md)
3. [Token vs Component](sections/03-token-vs-component.md)
4. [Component Readiness Audit](sections/04-component-readiness-audit.md)
5. [Component Classification](sections/05-component-classification.md)
6. [Runtime First](sections/06-runtime-first.md)
7. [Code-Only Governance](sections/07-code-only-governance.md)
8. [Governance Pipeline](sections/08-governance-pipeline.md)
9. [Composition Over Abstraction](sections/09-composition-over-abstraction.md)
10. [AI and Governance](sections/10-ai-and-governance.md)
11. [Risks](sections/11-risks.md)
12. [Starting a System](sections/12-starting-a-system.md)

For AI agent guidance, see [agent.md](agent.md).

The original long-form methodology document is preserved in [rapid-design-system.md](rapid-design-system.md).

## Using SWARM With RDS

RDS defines the governance and implementation model for design systems.

[SWARM](https://swarmloop.xyz/) is a decision-making loop that can be used within RDS when the next move is unclear. Teams may use Spot, Weigh, Arrange, Refine, and Make when navigating uncertainty, audits, tradeoffs, governance decisions, and implementation choices.

RDS = what to do.

SWARM = how to think while doing it.

SWARM is optional but complementary. RDS stands on its own without prior knowledge of SWARM.

## Author

Rapid Design System + SWARM are developed by Matt Lambert.

## Links

- [swarmloop.xyz](https://swarmloop.xyz) - SWARM online
- [Substack](https://cardeo.substack.com/) - ongoing writing and exploration
- [cardeo.ca](https://cardeo.ca) - broader creative and systems work
