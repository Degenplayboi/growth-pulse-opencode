---
name: growth-pulse-design-research
description: Research-led design intelligence for Growth Pulse. Use before designing any substantial interface to reason about project type, audience, character, and constraints, gather references, run template discovery, and produce a specific visual thesis. Never generates generic design.
---

# Growth Pulse Design Research

This skill RESEARCHES the design problem. It does not implement
(`growth-pulse-frontend-design` owns visual direction,
`growth-pulse-design-system` / `growth-pulse-react-next` own construction).
Its output is a design brief with a specific visual thesis — never code,
never "modern premium SaaS".

## When to use

- Any substantial interface: landing page, marketing site, product UI,
  dashboard, e-commerce, booking flow, redesign.
- Skip for trivial changes (copy fix, single-bug fix, spacing tweak) —
  say so in one line and proceed.

## Method: reason → reference → thesis

### 1. Reason (always; from the brief + repo, no invention)

Determine: project type, industry, audience, brand position, conversion
objective, information hierarchy, visual character, typography needs,
composition needs, imagery needs, interaction needs, motion needs,
responsive behavior, accessibility obligations, technical constraints
(stack, budget, timeline). Missing items are UNKNOWN or `[TODO: client]` —
never filled with guesses. Client work additionally needs the brief items
in `growth-pulse-business` (offer, proof assets, reviewer).

### 2. Decide if references would materially help

References pay off when: the domain has strong conventions to learn or break
(product UX, editorial, e-commerce), the project risks genericism (SaaS,
dashboard, agency site), or motion/interaction carries the experience.
Skip when: the direction is already set by an approved system, the surface
is trivial, or the budget forbids it. Record the decision in one line.

### 3. Reference (if yes — see `references/design-sources.md`)

Gather 3–7 references. Extract per reference: what is useful, composition /
typography / interaction principles observed, what is rejected and why.
Never scrape, copy identity, or reproduce templates. Figma Community /
template ecosystems are starting material only — see template discovery.

### 4. Template discovery (if build speed matters — see `references/template-discovery.md`)

Search Figma Community, Framer/shadcn templates, GitHub, official framework
examples. Adopt a template ONLY when it genuinely accelerates AND survives
transformation (see thesis). Record: what is useful, what must change, why
it fits, what makes the result original. Default: no template.

### 5. UI Skills routing (on-demand, smallest set)

The UI Skills catalog is searched, never installed. Identify the problem
(e.g. landing page, dashboard, animation, mobile), pull at most 2–3 skills
via `npx ui-skills get '<slug>'`, use them, drop them. Routing examples live
in `references/design-sources.md`. Never wrap external skills in Growth Pulse
clones unless routing genuinely requires it (it doesn't today).

## Output: the design brief

- Project type, audience, visual objective (one line each)
- References used (3–7 or "none — <reason>")
- Patterns observed + patterns intentionally rejected
- Typography / composition / interaction / motion direction
- **Asset Manifest (required for any interface with photographic or illustrative content — hero + every section):** one entry per asset — subject, composition/crop per breakpoint (360 / 768 / 1280+), production route (stock / generative / HTML-CSS, per `growth-pulse-creative` method selection). No entry may be "TBD" at handoff; unavailable assets are `[TODO: client]` with an explicit fallback route.
- Responsive strategy
- **Visual thesis: one concrete sentence tied to THIS project.**
  Reject "modern premium SaaS", "clean and professional", "minimal and
  elegant" — if the thesis fits any product, it fits none. Rewrite until
  a logo-swap would break it.
- Figma decision: full Figma phase, lightweight direction-to-code, or
  direction-to-code direct (see `docs/design/figma.md`).

Hand the brief — including the Asset Manifest — to BOTH `growth-pulse-frontend-design` (visual direction) and `growth-pulse-creative` (production method + license per asset). Design quality is then
gated by its critique + `growth-pulse-quality-audit`; claims by
`growth-pulse-verification`.
