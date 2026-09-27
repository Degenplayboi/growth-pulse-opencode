---
name: growth-pulse-react-next
description: Production React and Next.js development. Use when writing, reviewing, or refactoring React components, Next.js pages, data fetching, bundle size, or rendering performance.
---

# Growth Pulse React Next

Curated from: `vercel-labs/agent-skills` react-best-practices v1.0.0 MIT (inspected 2026-09-21, 70 rules across 8 categories). This file is Growth Pulse summary wording; read upstream rule files for full examples.

## When to use
- New React component, Next.js page/layout/route, server/client component decision
- Data fetching, caching, waterfalls, bundle, re-render, hydration issues
- Code review for performance

## Priority order
1. Eliminating waterfalls (CRITICAL): parallelize with Promise.all, defer await to branch, Suspense streaming, start promises early in API routes
2. Bundle size (CRITICAL): direct imports not barrels, next/dynamic for heavy, defer third-party past hydration, conditional load, preload on hover/focus, statically analyzable paths
3. Server performance (HIGH): React.cache per-request dedup, LRU cross-request, avoid module mutable request state, hoist static IO, minimize RSC-to-client serialization, parallelize fetches incl. nested Promise.all, after() for non-blocking, auth server actions like API routes
4. Client fetching (MEDIUM-HIGH): SWR dedup, dedup global listeners, passive scroll listeners, versioned minimal localStorage
5. Re-render (MEDIUM): don't subscribe state only used in callbacks, memoize expensive subtrees, primitive effect deps, derive during render not in effect, functional setState, lazy useState init, no inline component defs, startTransition for non-urgent, useDeferredValue for input responsiveness
6. Rendering (MEDIUM): animate wrapper div not SVG, content-visibility for long lists, hoist static JSX, reduce SVG precision, ternary not && for conditionals, resource hints for preload, defer/async scripts
7. JS micro (LOW-MEDIUM): batch DOM CSS via classes, Map/Set lookups, cache property/function/storage reads, combine filter/map passes, early exit, hoist RegExp, toSorted for immutability

## Rules
- Server vs client: minimize 'use client' boundary, push client leaves down.
- No barrel re-export chains in hot paths.
- Verify: build + typecheck + lint clean before DONE. No claim without fresh output.

## Default stack policy

For NEW client-facing production websites, the default architecture is
Next.js + React + TypeScript + Tailwind + Motion — applied without being told,
with shadcn where it is genuinely the better call (never wholesale, never
forced for its own sake). Override deliberately with a documented reason: an
existing healthy architecture (Astro docs site, Shopify storefront,
automation-only request, single-page static test) is inspected first and never
forced onto the default stack.

## Output
- Files changed + pattern applied (e.g. async-parallel, bundle-dynamic-imports) + build/typecheck evidence + remaining risks.
