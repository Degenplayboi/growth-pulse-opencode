# Design reference catalog

Sources are research inputs for pattern recognition and art direction.
Never scrape, copy visual identity, or reproduce templates. Sources are NOT
equally suitable — use the right one per problem. Access dates matter;
re-verify availability before citing (gallery rotations, paywalls).

## Galleries (visual direction + composition)

- **Godly** — visual direction, unusual composition, contemporary web design,
  art direction. Best when a project risks looking ordinary; worst for
  conventional conversion flows (its picks skew avant-garde).
- **Land-book** — websites, landing pages, sections, layouts,
  conversion-oriented references. Best for landing-page structure and section
  patterns; weak on product/app UX.
- **SiteInspire** — typography, composition, agency/editorial work, visual
  systems. Best for editorial and type-led direction; filter by style.
- **Awwwards** — interaction, motion, experimental web, advanced visual
  references. Best for motion/interaction ambition; almost never directly
  buildable on a trade-business budget — extract principles, not techniques.

## Product UX (flows, not pages)

- **Mobbin** — product UX, mobile flows, SaaS/product interfaces, onboarding,
  application patterns. Best for dashboards, onboarding, settings, mobile app
  flows. Not a marketing-site source.

## Icons (MIT-or-verified only; check per icon set)

- **iconoir.com** — open-source SVG icon library. Best for interface icons in
  any stack; self-host the SVGs, never hotlink. Verify the license of the
  version pulled before shipping.
- **animatedicons.co** — animated icon sets. Motion counts against the
  one-effect-per-page discipline; verify license per set before use.

## Systems + starting material (transform, never copy)

- **Figma Community** — design systems, UI kits, templates, wireframes,
  editable resources. Research + starting geometry only; every adoption must
  pass the transformation test (what changed, why it fits, what is original).
- **Figma Templates** (official/featured) — same rules as Community, usually
  higher baseline quality; still never ship unmodified.
- **shadcn/ui ecosystem** — implementation-oriented UI patterns,
  React/Next.js/Tailwind structures. A construction reference: pairs with
  `growth-pulse-design-system`, never a source of visual identity.
- **Aceternity UI** — component/interaction patterns with heavy motion.
  Useful for studying interaction feel; high slop risk if pasted wholesale —
  one effect per page maximum, purposeful only.
- **uiverse.io** — community-built UI elements and components. Starting
  geometry only; restyle to project tokens, pass the transformation test,
  verify license per element.
- **21st.dev** — component registry / starting material. Same transform
  rules; verify license per component before use.
- **designvault.io** — pattern vault for flows and sections. Research input,
  not shippable code; verify per item.
- **balsa-ui.com** — verify before use: confirm what it offers, its license,
  and its suitability before citing or pulling anything.
- **springs.studio** — verify before use (offer, license, suitability).
- **craftwork.design** — verify before use (offer, license, suitability).
- **designspells.com** — verify before use (offer, license, suitability).

## Effects / motion tools (one effect per page maximum, purposeful only)

- **useanimations.com** — animated micro-interaction icons. Verify license
  per use; reduced-motion safe or it doesn't ship.

## Verify-before-use flags (never cite as established until checked)

- **gkurt.com/tegaki**, **meshfont.com** — unverified sources. Confirm each
  site exists, what it offers, its license, and its suitability before
  referencing it in any brief. Never record either as used without that check.

## Skill catalogs (expertise on demand)

- **UI Skills ecosystem** — agent skills for design engineering, frontend
  design, accessibility, interaction, mobile, implementation. On-demand via
  `npx ui-skills categories | list | get`. Routing by task:
  - Landing page → frontend-design + landing-page design + visual/interface critique
  - Dashboard → interface design + design system + accessibility
  - Animation → motion/animation + interaction + accessibility
  - Mobile → responsive/mobile + interaction + accessibility
  Max 2–3 per task. Nothing pre-installed; nothing wrapped.

## Code-adjacent sources

- **Relevant GitHub design/frontend repos** — framework examples, official
  starters, reputable UI libraries. Evaluate per repo: maintenance,
  license, fit. Prefer official examples over awesome-lists.

## Per-reference record (required when references are used)

Source + URL + date; what is useful; composition/typography/interaction
principles observed; what is rejected and why; how the final direction
differs (the originality receipt).
