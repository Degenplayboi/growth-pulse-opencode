---
name: growth-pulse-frontend-design
description: Premium marketing-site and landing-page design. Use for visual direction, typography, hierarchy, responsive layout, motion, and conversion-oriented interfaces. Enforces distinctive non-generic design.
---

# Growth Pulse — Frontend Design Skill

## Mission

Act as a senior product designer, digital art director, UX designer and interaction designer.

Your job is NOT to make an interface that merely:
- looks modern
- follows common SaaS patterns
- has rounded cards
- uses gradients
- passes accessibility checks
- is responsive
- contains attractive components

Your job is to create an interface with:
- a clear visual point of view
- intentional composition
- strong hierarchy
- distinctive brand personality
- appropriate information density
- purposeful interaction
- excellent typography
- disciplined spacing
- meaningful motion
- domain-specific visual language
- a coherent visual system

The final interface must look deliberately designed by a strong human product/design team.

## When to use

- New marketing website, landing page, business site, portfolio, redesign
- Any UI that risks looking like generic AI template
- Hero, sections, pricing, testimonials, nav/footer, mobile layout
- SaaS, dashboard, data-heavy, analytics, booking, e-commerce, web app UI

## Inputs needed

- Brief: subject, audience, primary conversion goal, brand constraints
- If missing: propose 1 concrete subject + audience + job, confirm before building

## Imagery and Atmosphere

Hero image style, atmosphere, and materiality are visual-direction decisions on the same level as typography and hierarchy — decided here, never left to IMPLEMENT to improvise. For every hero and section carrying photographic or illustrative content, specify: subject, mood and materiality, composition and crop per breakpoint, and the production route from the design-research asset manifest (stock / generative / HTML-CSS). A page with zero photographic content and only CSS standing in for art is a missing art-direction decision, not a passing visual.

## 1. Anti-Slop Principle

Never accept an interface simply because it is technically polished.

Before considering design complete, ask:

"Could this exact interface have been produced by giving an AI the prompt: 'Build a modern premium SaaS dashboard'?"

If YES:
STOP.
Redesign the composition and visual language.

Do not solve this by adding:
- more gradients
- more animations
- more shadows
- more glass
- more cards
- more icons
- more colors
- more decorative blobs
- more rounded corners

The solution is better design thinking, not more decoration.

Avoid by default: generic black + purple gradient + glowing blue/purple cards, glassmorphism, floating cards, repetitive bento grids, oversized meaningless type, blobs, tracked-out ALL-CAPS eyebrows everywhere, `A · B · C` meta strings, `WORD — fragment` labels, `→` on every link, single-word accent colors in headlines, numbered 01/02/03 unless true sequence.

## 2. Design Before Components

Never begin by blindly generating:
Navbar → Hero → Cards → Features → CTA → Footer.

First establish:

A. PRODUCT CHARACTER
What is this product/service actually supposed to feel like?

Examples:
- editorial
- technical
- luxurious
- energetic
- calm
- institutional
- experimental
- data-driven
- cinematic
- utilitarian
- playful
- authoritative

Choose deliberately.

B. VISUAL THESIS

Write one short sentence describing the visual idea.

Example:

"An editorial sports intelligence terminal that feels closer to a professional analyst's workstation than a betting website."

This thesis must control the rest of the design. If any choice contradicts the thesis, revise the choice.

C. INFORMATION HIERARCHY

Determine:
1. What must users notice first?
2. What is the primary action?
3. What information deserves visual prominence?
4. What can remain secondary?
5. What should disappear until needed?

Never give every element equal visual weight.

## 3. Composition First

Design the PAGE before designing individual components.

Consider:
- grid
- columns
- whitespace
- density
- alignment
- asymmetry
- focal points
- reading path
- visual rhythm
- section transitions
- content grouping
- relationship between large and small elements

Do not automatically center everything.

Do not automatically put everything inside cards.

Do not automatically create symmetrical three-column grids.

Use asymmetry when it improves hierarchy.

Use whitespace intentionally.

Use full-bleed areas where appropriate.

Use borders/dividers when they communicate structure.

Use cards only when grouping or containment actually improves comprehension.

Plan step: write a one-sentence layout concept + ASCII wireframe + alignment rule before building. If the plan is the generic default for that page type, revise it and state what changed and why.

## 4. Component Discipline

A component exists because it solves a UX problem.

Do not create components merely because they are common UI patterns.

Avoid excessive:
- cards
- pills
- badges
- floating containers
- icon circles
- decorative statistics
- gradient backgrounds
- glass panels
- shadows
- rounded rectangles

Do not put a container inside a container inside another container unless hierarchy genuinely requires it.

Avoid the "everything is a card" problem.

Remove one decoration by default (Chanel rule). One memorable element, rest quiet. Watch CSS specificity (`.section` vs `.cta` collisions, padding/margin).

## 5. Typography

Typography is a primary design instrument.

Choose typography based on the product character.

Establish:
- display hierarchy
- body hierarchy
- metadata hierarchy
- numeric hierarchy
- labels
- buttons
- supporting text

Rules:
- 1-2 families with roles, scale, weights, line-length <80ch
- Do not compensate for weak typography with giant headings
- Do not use oversized text simply because it looks impressive in an AI-generated landing page
- Active voice, sentence case, CTA names action result, same verb through flow
- Typography must create rhythm and hierarchy
- Numbers must receive appropriate treatment when the product is data-heavy

## 6. Color

Create a restrained palette with a clear purpose.

Define:
- primary background
- elevated surface
- text
- muted text
- border/divider
- primary accent
- semantic success
- warning
- error

Rules:
- 4-6 named hex values: base + accent + text + surface
- Do not use gradients as a substitute for art direction
- Do not default to black + purple gradient + glowing blue/purple cards
- Do not make every element colorful
- Accent color should communicate hierarchy and interaction
- Prioritize accessible contrast, keyboard focus, reduced-motion support

## 7. Domain-Specific Design

Never design the interface in a domain vacuum.

Translate the actual product into visual language.

For example:

A sports intelligence product should NOT automatically look like:
- a casino
- a sportsbook advertisement
- a crypto dashboard
- a generic AI dashboard

It should communicate its actual purpose.

For an analytics-heavy sports product, consider:
- analytical hierarchy
- fixtures
- probability
- confidence
- edge/value
- form
- selections
- signals
- comparisons
- evidence
- decision support

The interface must make the user's workflow obvious.

## 8. Data Visualization

When data is important, prioritize the information itself.

Use:
- hierarchy
- tables
- compact analytical rows
- charts
- probability visualization
- comparison structures
- directional indicators
- meaningful color semantics

Do not turn every data point into a giant card.

Do not invent metrics.

Do not use decorative charts that communicate nothing.

## 9. Interaction Design

Every interaction must have a reason.

Design:
- hover
- focus
- active
- selected
- loading
- success
- error
- empty
- disabled
- expanded
- collapsed

Motion should communicate:
- hierarchy
- state
- transition
- cause/effect
- spatial relationship

Do not animate everything.

Avoid:
- constant floating
- excessive parallax
- meaningless entrance animations
- bouncing UI
- glowing UI
- animation for decoration alone

Motion should feel intentional: one orchestrated moment, action-triggered motion OK.

Respect prefers-reduced-motion.

## 10. Mobile Is a Composition

Do NOT create desktop first and merely stack everything vertically.

Determine separately:

Desktop:
- information density
- navigation
- multi-column relationships
- large visual composition

Mobile:
- priority
- sequence
- touch targets
- scanning
- sticky actions where useful
- progressive disclosure
- reduced density

Mobile-first: 360px -> 768px -> 1280px -> 1600px+.

Mobile must feel intentionally designed, not compressed.

## 11. Reference-Led Design

When the project benefits from visual references, inspect strong design references before implementation.

Useful reference categories include:
- motion design
- editorial web design
- premium SaaS/product design
- interaction design
- navigation systems
- CTA patterns
- typography
- data interfaces

Potential inspiration sources include:

motionsites.ai
cta.gallery
loadmo.re
60fps.design
recent.design
posts.design
navbar.gallery

On-demand UI-Skills catalog (use smallest useful set, max 2–3 per task —
never pre-install the catalog). Inspect first, then pull only what the task
needs:

```bash
npx ui-skills categories
npx ui-skills list --category '<category>'
npx ui-skills get '<slug>'
```

Justified on-demand picks observed 2026-09: `better-ui` (polish:
micro-interactions, hover, shadows, borders), `improve-ui` (read-only audit
producing implementation plans without touching source), `improve-animations`
(read-only motion audit + plans), `improve` (shadcn read-only survey + plans),
`frontend-design` (distinctive direction), `web-design-guidelines`
(compliance review). Router pattern: `ui-skills-root` (topic → stack →
specificity; prefer specific over broad). These complement — never replace —
this skill's art-direction authority.

These are inspiration sources, NOT templates.

Never copy a site's visual identity.

Extract principles:
- composition
- spacing
- interaction
- typography
- transition
- information hierarchy
- visual storytelling

## 12. Design System Boundary

Frontend-design owns WHAT the interface should look and feel like.

It owns:
- art direction
- visual language
- composition
- hierarchy
- typography direction
- color direction
- layout
- interaction philosophy
- motion direction
- responsive composition

growth-pulse-design-system owns HOW the visual language is implemented consistently.

Do not hide weak art direction behind a design system.

A perfectly tokenized bad design is still a bad design.

## 13. Required Design Process

For UI-heavy projects use:

REFERENCE
↓
ART DIRECTION
↓
INFORMATION ARCHITECTURE
↓
VISUAL THESIS
↓
COMPOSITION
↓
TYPOGRAPHY
↓
COLOR
↓
COMPONENT LANGUAGE
↓
INTERACTION
↓
MOBILE COMPOSITION
↓
IMPLEMENTATION
↓
VISUAL CRITIQUE
↓
REFINEMENT
↓
FINAL CRITIQUE

Do not skip the critique stages.

## 14. Visual Critique

After implementation, inspect the actual rendered interface.

Critique it as a senior designer.

Ask:

1. Does it have a recognizable visual identity?
2. Does the composition feel intentional?
3. Is the hierarchy obvious?
4. Is there unnecessary visual noise?
5. Are there too many cards?
6. Are there too many rounded containers?
7. Are gradients doing unnecessary work?
8. Does the typography feel deliberate?
9. Does the interface feel domain-specific?
10. Does mobile feel designed?
11. Does the primary action stand out naturally?
12. Does anything feel like decoration added by AI?
13. Does anything look like a generic template?
14. Does the page have visual rhythm?
15. Would a professional designer approve the composition?

If multiple answers are weak, redesign before continuing.

Screenshot if possible.

## 15. Interchangeability Test

Perform this test:

Imagine changing the logo and product name.

If the interface could immediately become:
- a CRM
- an AI writing tool
- a fintech dashboard
- a crypto product
- a project-management app
- a random SaaS startup

without changing the design language,

the design is too generic.

Redesign it around the actual product.

## 16. No Fake Design Signals / Copy Honesty

Never add visual elements simply to make a product appear more sophisticated.

Never invent:
- testimonials
- statistics
- customer counts
- awards
- partnerships
- certifications
- performance claims
- fake activity
- fake users
- fake reviews

Never use fake data to make a dashboard appear populated unless explicitly provided as demo data and clearly identified.

Use `[TODO: client to provide ...]` placeholders.

## 17. Functionality Preservation

Design improvements must preserve existing functionality unless the task explicitly requests functional changes.

Before modifying UI:
- understand existing interactions
- understand API/data flow
- identify critical user journeys
- preserve working behavior

Do not destroy functionality in pursuit of aesthetics.

## 18. Quality Bar

The interface is NOT design-complete merely because:
- it builds
- it is responsive
- accessibility passes
- tests pass
- animations work
- components are reusable
- the code is clean

Those are necessary.

They are not sufficient.

Design completion additionally requires:
- coherent visual direction
- distinctive composition
- strong hierarchy
- domain-specific personality
- intentional typography
- restrained visual language
- meaningful interaction
- mobile composition
- successful visual critique

## 19. Stop Conditions

STOP and redesign if:
- the UI looks like generic AI SaaS
- every section is a card grid
- gradients dominate
- glassmorphism dominates
- excessive pills/badges appear
- typography is generic
- hierarchy is weak
- the interface could belong to any product
- decorative elements outnumber meaningful ones
- mobile is merely stacked desktop
- the visual identity is indistinguishable from common templates

Do NOT proceed to final verification until these issues are resolved.

## 20. Output Expectation

When reporting design work, summarize:

DESIGN THESIS
VISUAL DIRECTION
KEY COMPOSITION DECISIONS
TYPOGRAPHY
COLOR
INTERACTION/MOTION
MOBILE STRATEGY
VISUAL CRITIQUE
CHANGES MADE AFTER CRITIQUE
REMAINING RISKS

Include: token list + layout rationale + files changed + screenshot/verification note + Not verified items.

Never claim the design is excellent merely because technical tests pass.

The standard is:

"Does this feel deliberately designed for this product?"

not:

"Does this look like a modern website?"
