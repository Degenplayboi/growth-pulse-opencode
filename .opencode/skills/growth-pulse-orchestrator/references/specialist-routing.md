# Specialist Routing

Prefer an available specialist skill over reinventing its methodology. Auto-load by classification.

## DESIGN — load for marketing website, landing page, business website, portfolio, redesign, SaaS/product, dashboard
- frontend design, web design guidelines, design engineering
- UX, visual hierarchy, typography, responsive design
- motion, micro-interactions, conversion design

## DEVELOPMENT — load by stack / feature
- React, Next.js, TypeScript, Tailwind, component architecture
- API development, database, authentication, forms, payments, state management
- e-commerce -> payments + forms + state; booking system -> forms + database + auth; dashboard / SaaS -> auth + database + state

## QUALITY — always consider; mandatory before DONE
- systematic debugging (bug fix), web app testing (flows)
- accessibility, responsive testing, visual QA
- SEO (marketing / landing / business), performance + Core Web Vitals
- security (auth / payments / API), broken-link checking, console-error checking, form validation

## BUSINESS — load for strategy, ops, PM, pipeline, client framing
- `growth-pulse-business`: planning, SOPs, milestones, sales pipeline, client
  requirements/scope/acceptance, internal-vs-client distinction.
  Internal work is NEVER auto-framed as a client service; services come only
  from `docs/business/services.md`.

## RESEARCH — load when current/external facts matter
- `growth-pulse-research`: market, competitor, technical, product research.
  Claims labelled VERIFIED / REPORTED / INFERRED / PROPOSED / UNKNOWN.

## GROWTH — load for leads, outreach prep, marketing, social, creative
- `growth-pulse-growth`: lead pipeline, outreach drafts (approval-gated),
  campaigns, social system, creative production. Prepares; never sends.

## DESIGN RESEARCH — load before designing any substantial interface
- `growth-pulse-design-research`: reason about type/audience/character/constraints,
  gather 3–7 references (catalog in its `references/design-sources.md`),
  template discovery (transformation test), UI Skills on-demand (max 2–3 via
  `npx ui-skills get`, never installed/wrapped), visual thesis. Output is a
  design brief handed to frontend-design. Skip with one line for trivial changes.

## CREATIVE — load for production of creative artifacts
- `growth-pulse-creative`: production METHOD (HTML/SVG first, Remotion for
  deterministic video, generative models only where fitting + license recorded).
  Pipeline/approvals stay with `growth-pulse-growth`; never duplicate them here.

## AUTOMATION — load for n8n, MCP, browser, Telegram approvals
- `growth-pulse-automation`: n8n as runtime (OpenCode designs), MCP curation,
  browser boundaries, Telegram approval pattern, secrets, cost control.

## DELIVERY — load for deployment / handoff
- Git/GitHub, deployment, production verification, documentation, client handoff

## PHASE 3 — conditional specialists (do NOT invoke every skill for every project)

- PERFORMANCE (`growth-pulse-performance`): performance optimization, pre-launch performance verification, marketing websites, landing pages, e-commerce, SaaS, any project where performance is explicitly required. Measures LCP/INP/CLS/TTFB; implementation stays with React/Next skill; gating stays with quality-audit.
- ACCESSIBILITY (`growth-pulse-accessibility`): accessibility classification, pre-DONE quality verification, forms-heavy interfaces, SaaS/dashboard, public-facing websites. Executes automated + manual checks; gating stays with quality-audit.
- SECURITY tiered (`growth-pulse-security`): Level 1 all production websites; Level 2 additionally auth/API/database/payment/application projects; Level 3 additionally AI/agentic applications only. Never force Level 3 onto ordinary websites.
- DESIGN SYSTEM (`growth-pulse-design-system`): reusable component systems, Tailwind present, shadcn present, SaaS/dashboard/web-app UI, explicit design-system need. Frontend-design owns WHAT it looks like; design-system owns HOW it is built.

Ownership: implementation guidance in implementation specialist; measurement in measurement specialist; pass/fail criteria in quality-audit; evidence/claim rules in verification; production orchestration in deploy.

## Routing procedure
1. Map classification -> specialist areas above.
2. Check environment for matching skill names.
3. Load all that apply.
4. If missing: continue with best practices and note `Specialist unavailable: <area>`.
5. Never ask the user which skill to use.
