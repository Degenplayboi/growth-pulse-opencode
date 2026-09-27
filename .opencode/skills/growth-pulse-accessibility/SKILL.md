---
name: growth-pulse-accessibility
description: Accessibility execution specialist. Use for WCAG 2.2 AA audits, axe-core automation where runnable, keyboard/focus/semantics/contrast checks, and remediation evidence.
---

# Growth Pulse Accessibility

Curated from: WCAG 2.2 AA / axe-core automated-testing methodology, Lighthouse accessibility signals, platform HIG semantics. Growth Pulse original wording.

This skill EXECUTES accessibility checks and remediation. Pass/fail gating remains with `growth-pulse-quality-audit`. Claim evidence rules remain with `growth-pulse-verification`. Browser execution patterns compose with `growth-pulse-web-testing` (do not duplicate its recon/script method here).

## When to use

- Classification `accessibility`, or pre-DONE quality verification
- Forms-heavy interfaces, SaaS/dashboard, public-facing websites
- Any change touching forms, dialogs, menus, tables, navigation, focus, or color

Do NOT invoke for every trivial change, but DO invoke before DONE on any user-facing flow.

## Iron rule

Automated testing NEVER proves full WCAG conformance. axe-core / Lighthouse catch a subset. Always report automated and manual results separately. Never claim "WCAG compliant" from a tool score alone.

VPAT/ACR is NOT default. Only plan or perform VPAT-related work when the client/project explicitly requires it.

## 1. Automated checks (where runnable)

- Run axe-core (or equivalent where already present) against runnable routes, including one representative of each template plus keyboard-critical flows. Prefer existing project tooling; do not install packages into the client project.
- Optionally note Lighthouse accessibility signals as supporting evidence, not proof.
- Record: tool + version + URL + viewport + auth state. Group findings by rule with `file:line` and WCAG success criterion (e.g. 1.4.3, 2.4.7, 3.3.1).
- If no runnable environment exists, report `Not measurable: <reason>` — never invent violations or passes.

## 2. Manual checks (always applicable via code inspection)

- Keyboard: full flow operable, visible focus, logical order, no trap, Esc closes dialogs/menus, skip link where appropriate
- Names/roles: every control has an accessible name (icon-only buttons labelled), `aria-label` matches visible text where both exist
- Semantics: landmarks (header/nav/main/footer), exactly one h1, no skipped heading levels, lists/tables marked up as such
- Forms/errors: labels for all inputs, errors tied via `aria-describedby`, failed-submit announced, required/invalid states exposed
- Contrast: text AA (4.5:1, 3:1 large), UI components/focus indicators perceivable; flag gold-on-white and slate-400/500-on-light patterns
- Motion/media: `prefers-reduced-motion` respected, no autoplay surprises, alt text meaningful (decorative empty), captions/transcripts where video/audio present
- Dialogs/menus/tables: focus trap + return focus for modals, arrow-key patterns for menus/tabs where used, table headers scoped

## Remediation

- One fix per finding with exact snippet and `file:line`. Fix at source component (prefer shared primitive — one fix can clear many pages).
- Re-run the failing check with fresh evidence; new serious/critical violations block DONE via `growth-pulse-quality-audit`.

## Output

- Two sections: AUTOMATED (tool + results or Not measurable) / MANUAL (pass/fail per area with `file:line`). Each finding: severity + WCAG criterion + fix snippet. End with Verified / Not verified list. Never imply conformance beyond what was checked.
