---
name: growth-pulse-seo-conversion
description: Technical SEO and landing-page conversion. Use for meta, headings, schema, sitemap/robots, internal links, page speed signals, and honest persuasive copy that converts.
---

# Growth Pulse SEO Conversion

Curated from: `seo-skills/seo-audit-skill` (SEOmator 251-rule taxonomy inspected), `whawkinsiv/solo-founder-superpowers` seo-audit workflow, `agenticskills.io` Page CRO / Pricing / Programmatic SEO / Schema Markup ideas. Lightweight code-first version — no CLI dependency.

## When to use
- Marketing site, landing page, business site pre-launch or traffic drop
- New route, framework migration (SSR/SSG), i18n addition

## Audit steps (codebase-first)
1. **Scope:** framework (Next/HTML/etc.), SSR vs client-only critical content, routes to check.
2. **Technical:** title 50-60 unique keyword-frontloaded, meta description 120-155 + CTA, canonical self-referencing, robots meta correct, OG (title/desc/image/url) + twitter:card, favicon, sitemap.xml generation, robots.txt, clean slugs (lowercase-hyphen, no query for content), redirects no chains, hreflang if i18n, pagination indexability.
3. **Content structure:** exactly one h1, h1>h2>h3 no skip, semantic article/nav/main/section, descriptive alt, anchor text meaningful (no click here), adequate length for type, FAQ/question headings for AI-answer visibility, TL;DR summary box, inverted-pyramid answer first.
4. **Schema:** JSON-LD Organization + WebSite minimum; add Article/BlogPosting, FAQPage, BreadcrumbList, Product/SoftwareApplication/HowTo where fitting. Validate @type + required fields. Confirm rendered DOM (not just raw HTML) for client-injected schema.
5. **Speed signals:** image width/height + lazy + modern format, no render-blocking, font-display swap, CWV LCP/INP/CLS risk notes.
6. **Conversion:** one primary CTA above fold, same verb through flow, social proof only if real (else TODO placeholder), pricing clarity, form friction minimal, trust pages reachable (about/contact/privacy), internal links pillar<->spoke, no orphans.

## Reject
- Keyword stuffing, fake stats/testimonials, cloaking, thin programmatic pages.

## Output
- Save `seo-audit.md` in project root when substantial: scored table + prioritized P0/P1/P2 fixes with file:line + exact snippet to change. Mark each Verified / Not verified.
