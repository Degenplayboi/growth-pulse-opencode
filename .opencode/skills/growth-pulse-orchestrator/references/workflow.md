# Workflow

Substantial visual projects: DISCOVER -> INSPECT -> RESEARCH -> REFERENCE -> PLAN -> DESIGN -> IMPLEMENT -> TEST -> AUDIT -> FIX -> VISUAL QA -> RETEST -> PRODUCTION VERIFY -> DELIVER.

Other substantial projects: DISCOVER -> INSPECT -> PLAN -> DESIGN -> IMPLEMENT -> TEST -> AUDIT -> FIX -> RETEST -> PRODUCTION VERIFY -> DELIVER.

Small changes (copy fix, single-bug fix, spacing tweak): DISCOVER -> INSPECT -> PLAN -> IMPLEMENT -> TEST -> VERIFY -> DELIVER. Never force the long pipeline onto trivial tasks.

## DISCOVER
- Restate goal, target user, conversion goal.
- Outputs: classification, success criteria, missing-info list.
- Do not code yet.

## INSPECT
- Read repo structure, package.json / build config, routing, components, styles, API routes, auth, DB, env.
- Note reuse candidates and constraints.
- Preserve working functionality.

## RESEARCH (visual track; `growth-pulse-design-research`)
- Reason about type, industry, audience, brand, conversion, hierarchy,
  character, type, composition, imagery, interaction, motion, responsive,
  accessibility, constraints. Unknowns stay UNKNOWN.
- Decide in one line whether references would materially help; if no, skip
  to PLAN.

## REFERENCE (only if RESEARCH said yes)
- Gather 3–7 references per `references` catalog rules in design-research;
  record patterns observed + rejected. Template discovery only if build speed
  demands it, with the four-answer transformation receipt.

## PLAN
- Small plan for small tasks; written plan for substantial work.
- Include: classification, specialist skills to load, file-change list, data model / API changes, verification plan.
- Visual track: attach the design brief + visual thesis + Figma decision
  (full Figma phase, lightweight direction, or direct to code).

## DISCOVER
- Restate goal, target user, conversion goal.
- Outputs: classification, success criteria, missing-info list.
- Do not code yet.

## INSPECT
- Read repo structure, package.json / build config, routing, components, styles, API routes, auth, DB, env.
- Note reuse candidates and constraints.
- Preserve working functionality.

## PLAN
- Small plan for small tasks; written plan for substantial work.
- Include: classification, specialist skills to load, file-change list, data model / API changes, verification plan.

## DESIGN
- Define hierarchy, type scale, spacing, breakpoints, states (loading / error / empty), motion intent.
- Mobile-first. No generic AI-template patterns.

## IMPLEMENT
- Reuse existing components.
- Maintainable, accessible, responsive code.
- No invented content; placeholders where client input missing.

## TEST
- Build, typecheck, lint, unit / e2e where available.
- Manual: buttons, forms, navigation, links, APIs, auth, error / loading / empty states.

## AUDIT
- Responsive (mobile / tablet / desktop / large), visual (type / spacing / alignment / consistency), technical (console, network, a11y, SEO, performance, security).

## FIX -> RETEST
- Fix findings, then re-run failed checks with fresh evidence.

## PRODUCTION VERIFY
- Deployment succeeds, production URL works, critical flows work in production, no regression.

## DELIVER
- Run `references/delivery-checklist.md`. Only then recommend handoff.
