# Quality Gates

Verify with fresh evidence before claiming DONE. Check all applicable groups.

## FUNCTION
- buttons, forms, navigation, links
- APIs, authentication, error states, loading states, empty states
- form validation messages, failed-submit behavior

## RESPONSIVE
- mobile (360-390px), tablet (~768px), desktop (~1280-1440px), large (>1600px)
- no horizontal overflow, tap targets >= 44px, readable type, working nav

## VISUAL
- typography, spacing, hierarchy, alignment, consistency
- animations purposeful, images / assets load, dark / light modes when applicable

## TECHNICAL
- build passes, no type errors, no lint errors
- no console errors, no failed network requests
- no broken imports, no broken links
- accessibility (keyboard, focus, contrast, semantics)
- SEO (title, meta, headings, sitemap / robots where applicable)
- performance (Core Web Vitals: LCP / INP / CLS), security headers / validation

## VISUAL QA (client-facing visual work; human judgment, never automated-only)
- Visual thesis holds (logo-swap test: still reads as THIS product)
- No default AI patterns unless justified (gradients, glass, blobs, bento
  overload, card grids, decorative motion, stock sameness)
- Hierarchy, rhythm, composition deliberate at every breakpoint
- Motion purposeful; reduced-motion respected; works with JS disabled
  where applicable

## CONTENT / CLAIM HYGIENE
- No fake testimonials, statistics, logos, reviews, results, partnerships
- Every claim traced to client input or labelled placeholder
- Fictional/demo labeling where applicable

## PRODUCTION
- deployment succeeds, production URL works
- major user flows work in production, no obvious regression

Record each claim as Verified (with evidence) or Not verified (with reason).
