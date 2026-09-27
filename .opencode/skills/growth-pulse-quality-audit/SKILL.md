---
name: growth-pulse-quality-audit
description: Responsive, visual, accessibility, performance, and security audit. Use before DONE to check mobile/tablet/desktop, WCAG, Core Web Vitals, broken links, console errors, and visual consistency.
---

# Growth Pulse Quality Audit

Curated from: `vercel-labs/agent-skills` web-design-guidelines + `vercel-labs/web-interface-guidelines` (fetch-live pattern), Apple HIG / Material 3 / WCAG 2.2 rules (Platform Design Skills), Cloudflare Web Perf CWV ideas. Growth Pulse original checklist.

## When to use
- Mandatory before DONE/Fixed/Ready per orchestrator quality-gates
- After any UI, responsive, a11y, perf, or security-relevant change

## 1. Responsive (360-390, 768, 1280-1440, 1600+)
- No horizontal overflow, no clipped CTA, nav works (hamburger if needed), tap targets >=44px, readable type, tables/cards stack, images scale.

## 2. Visual
- Type scale, spacing rhythm, alignment grid, consistent radius/shadow, images load with dimensions, no layout shift, dark/light if applicable, motion purposeful + reduced-motion respected. Where a design-research asset manifest exists: every manifest entry is present at each breakpoint, traced by name to its manifest entry — not a placeholder, gradient, or generic substitute standing in for it.

## 3. Accessibility (WCAG 2.2 AA target)
- Semantic landmarks (main/nav/header/footer), one h1, logical h2/h3, labels for all inputs, error tied via aria-describedby, focus visible + logical order, keyboard operable + Esc closes, contrast AA, alt text meaningful (decorative empty), no keyboard trap.

## 4. Technical
- Build passes, typecheck/lint clean, no console errors, no failed network, no broken imports/links (crawl nav+footer+CTA), form validation messages correct.
- Performance: check unoptimized images (missing width/height, no lazy below fold, no WebP/AVIF), render-blocking scripts, font-display swap, bundle bloat. Note LCP/INP/CLS risks even without lab run.
- Security: no secrets in client, auth checked server-side, validation server-side, secure headers noted, HTTPS-only, no dangerouslySetInnerHTML without sanitize.

## Output format
Use terse `file:line` findings grouped FUNCTION / RESPONSIVE / VISUAL / TECHNICAL, each Verified (evidence) or Not verified (reason). Never claim pass without fresh run.
