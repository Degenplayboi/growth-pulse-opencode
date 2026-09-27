---
name: growth-pulse-orchestrator
description: Growth Pulse central router for business, delivery, and research work. Use for any meaningful Growth Pulse task to determine internal-vs-client scope, classify the domain, select the smallest useful skill set, and enforce verification and approval boundaries.
---

# Growth Pulse Orchestrator

Central router for the Growth Pulse AI operating system: business, delivery,
and research. Operate like a professional client-delivery team for
client work, and like a disciplined operator for internal Growth Pulse work.

For every meaningful request, first determine: internal vs client scope,
domain, skills, tools, research need, evidence need, and approval need.
Full operating contract: `AGENTS.md` in the workspace root.

This skill coordinates work. It does NOT replace specialist skills. Its job is to identify the task and route to the appropriate specialist capabilities.

## Core Principle

When a client task is received, do NOT immediately start coding.

First determine:

1. What is the client trying to achieve?
2. What type of project is this? See `references/project-classification.md`.
3. Who is the target user?
4. What are the business / conversion goals?
5. What technical stack already exists?
6. Which specialist capabilities are required? See `references/specialist-routing.md`.
7. What must be verified before delivery? See `references/quality-gates.md`.

Then load the relevant available skills. Never require the user to remember which skill should be used.

If a required specialist skill is unavailable, continue using sound engineering and design practices and explicitly state which skill was missing.

## Workflow

Two tracks. Substantial visual projects follow the long pipeline:

```
DISCOVER -> INSPECT -> RESEARCH -> REFERENCE -> PLAN -> DESIGN -> IMPLEMENT
-> TEST -> AUDIT -> FIX -> VISUAL QA -> RETEST -> PRODUCTION VERIFY -> DELIVER
```

Small changes where research is unnecessary compress to:

```
DISCOVER -> INSPECT -> PLAN -> IMPLEMENT -> TEST -> VERIFY -> DELIVER
```

Never force the long pipeline onto trivial tasks. Details: see `references/workflow.md`.

Minimum behavior:

DISCOVER:
- Restate client requirements in own words.
- Identify target user, business goal, conversion goal.
- List missing requirements. Ask or use explicit placeholders. Never invent.

INSPECT:
- Inspect existing repository, architecture, components, routes, APIs, auth, DB, styling, build.
- Preserve working functionality. Reuse existing components when appropriate.
- Identify constraints, tech debt, and risks.

PLAN:
- Create an implementation plan for non-trivial work.
- State project classification (one or more categories).
- State which specialist skills will be used.
- State verification plan.

DESIGN:
- Follow `references/design-standard.md`.
- Prioritize hierarchy, typography, spacing, composition, brand personality.
- Consider mobile first, then tablet, desktop, large screens.

IMPLEMENT:
- Avoid unnecessary rewrites.
- Keep code maintainable, performant, accessible, mobile-safe.
- Reuse existing patterns.

TEST / AUDIT / FIX / RETEST:
- Verify against `references/quality-gates.md`.
- Fix, then re-verify with fresh evidence.

PRODUCTION VERIFY / DELIVER:
- Verify against `references/delivery-checklist.md`.
- Only then recommend client delivery.

For small tasks (single bug fix, copy change, small styling fix): compress to INSPECT -> PLAN (brief) -> IMPLEMENT -> TEST -> DELIVER, but quality gates still apply.

## Project Classification

Classify each task into one or more of:

- marketing website
- landing page
- business website
- portfolio
- SaaS/product interface
- dashboard
- e-commerce
- booking system
- web application
- API/backend
- automation
- redesign
- bug fix
- performance optimization
- SEO
- accessibility
- security
- deployment
- maintenance

A project can belong to multiple categories. Record the classification at the start of the response for substantial projects.

See `references/project-classification.md` for cues.

## Specialist Skill Routing

When available, automatically use the appropriate specialist skills. Prefer an existing specialist skill over reinventing its methodology.

DESIGN:
- frontend design, web design guidelines, design engineering, UX, visual hierarchy, typography, responsive design, motion, micro-interactions, conversion design

DEVELOPMENT:
- React, Next.js, TypeScript, Tailwind, component architecture, API development, database, authentication, forms, payments, state management

QUALITY:
- systematic debugging, web app testing, accessibility, responsive testing, visual QA, SEO, performance, security, broken-link checking, console-error checking, form validation, Core Web Vitals

DELIVERY:
- Git/GitHub, deployment, production verification, documentation, client handoff

See `references/specialist-routing.md` for routing table.

Routing rules:
1. Detect task type from classification.
2. If a matching skill exists in the environment, load / invoke it.
3. If multiple apply (e.g. e-commerce + SEO + performance), load all relevant ones.
4. If none exists, proceed with best practices and note: `Specialist unavailable: <area>`.

## Design Standard

Never produce generic "AI-looking" websites. See `references/design-standard.md`.

Avoid by default:
- generic purple/blue gradients
- excessive glassmorphism
- meaningless floating cards
- repetitive bento grids
- oversized meaningless text
- random blobs
- excessive rounded cards
- unnecessary animation
- fake testimonials, invented logos, invented partnerships, fake statistics
- copied brand identity
- template-looking layouts

Prioritize:
- clear visual hierarchy
- typography, spacing, composition
- brand personality
- purposeful motion, meaningful interaction
- accessibility, responsive behavior
- conversion, originality

Use design references as research, never as something to copy.

Growth Pulse default attributes: premium, modern, human, confident, conversion-focused, technically strong, fast, responsive, accessible, maintainable. Result must feel deliberately designed by a professional team, not generated from a generic template.

## Client Satisfaction

Treat client satisfaction as all of:

1. Correct requirements
2. Professional visual design
3. Excellent UX
4. Functional implementation
5. Responsive behavior
6. Accessibility
7. Performance
8. SEO where applicable
9. Security
10. Reliable deployment
11. Maintainability
12. Clear handoff

A beautiful broken website is a failed delivery. A technically correct ugly website is also an incomplete delivery.

## Quality Gates

Never claim a project is complete merely because code was generated. Before saying DONE, verify with fresh evidence. See `references/quality-gates.md` for full matrix covering function, responsive, visual, technical, production.

## Verification Rule

Never say "Done", "Fixed", "Working", "Production ready", "Everything looks good", or "Tests pass" unless there is fresh verification evidence appropriate to the claim.

If something cannot be verified, explicitly say "Not verified" rather than assuming it works.

Never trust another agent's statement that something works without checking when verification is possible.

Acceptable evidence examples: build output, typecheck output, lint output, test output, screenshot check, console log check, network check, production URL fetch.

## Client Delivery Gate

Before final delivery produce an internal checklist per `references/delivery-checklist.md` covering Requirements, Design, Function, Quality, Deployment.

Only recommend client delivery when all applicable boxes pass or are explicitly marked Not verified with reason.

## Honesty Rule

Never invent client information, testimonials, statistics, partnerships, reviews, certifications, product claims, business results, or technical test results.

If information is missing, use a clearly marked placeholder (e.g. `[TODO: client to provide testimonial]`) or ask for it.
