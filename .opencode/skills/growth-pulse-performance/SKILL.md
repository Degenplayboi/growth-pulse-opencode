---
name: growth-pulse-performance
description: Measured web performance specialist. Use for Core Web Vitals, Lighthouse lab measurement, LCP/INP/CLS diagnosis, budgets, and pre-launch performance verification.
---

# Growth Pulse Performance

Curated from: Lighthouse / PageSpeed / CrUX measurement methodology, web performance trace-diagnosis patterns, `growth-pulse-react-next` as the implementation arm. Growth Pulse original wording.

This skill MEASURES and DIAGNOSES. It does not own React/Next implementation patterns — that remains with `growth-pulse-react-next`. It does not own pass/fail gating — that remains with `growth-pulse-quality-audit`. It does not own claim evidence rules — those remain with `growth-pulse-verification`.

## When to use

- Performance optimization request or pre-launch performance verification
- Marketing website, landing page, e-commerce, SaaS where performance is explicitly required
- Any LCP / INP / CLS / TTFB concern
- After adding heavy dependencies, images, fonts, or third-party scripts

Do NOT invoke for every project by default. Invoke when classified as performance-relevant or explicitly requested.

## Core principle

Lighthouse is evidence, not the goal. Never equate a score of 100 with a perfect user experience. Optimize for real users, mobile-first.

## Measurement statuses (use exactly these)

- `Measured` — fresh lab or field number from this session with tool + conditions stated
- `Estimated` — reasoned projection from code inspection, never presented as a number from a run
- `Not measurable` — no runnable URL/environment available
- `Not verified` — claim without fresh evidence, with reason

If no runnable URL/environment exists, report `Not measurable: <reason>` explicitly. Never invent Lighthouse scores, timings, or CrUX values.

## Method: measure → diagnose → fix → re-measure

1. **Baseline:** record conditions (URL, viewport, mobile vs desktop, throttling, tool version, build type). Run Lighthouse lab measurement where runnable. Note field data (CrUX/PageSpeed) separately when available — lab and field are different datasets, never conflated.
2. **Diagnose:** identify the dominant metric first (LCP vs INP vs CLS vs TTFB). Use trace/audit culprits where available: render-blocking resources, hero-image priority, font loading, JS long tasks, third-party impact, waterfall/serialization issues. Point to `file:line` causes.
3. **Fix (via implementation owner):** hand code changes to `growth-pulse-react-next` patterns (parallelize, split bundle, defer third-party, preload LCP element). This skill states WHAT to fix and WHY; react-next owns HOW in code.
4. **Re-measure:** repeat the same conditions, compare baseline vs optimized table. Improvement is proven only by re-measurement.

## What to check

- LCP: hero element identification, preload with `fetchpriority="high"`, modern formats, responsive sizes, no lazy on LCP image, server/TTFB contribution
- INP: long-task profiling, handler splitting, defer non-urgent work, third-party script cost, input debounce where appropriate
- CLS: explicit width/height or aspect-ratio, skeletons for async content, font swap discipline, no late-injected layout shifts
- TTFB: caching, SSR/SSG choice, redirect chains, server geography (note only; infra changes need client approval)
- Budgets: entry bundle size, image weight, font count, third-party count. Flag regressions against prior baseline.
- Mobile-first: diagnose on mobile conditions first; desktop second and separately.

## Rules

- Separate lab vs field always. Field p75 (LCP ≤2.5s / INP ≤200ms / CLS ≤0.1) is the user-truth standard; lab is the repeatable diagnostic.
- One dominant bottleneck at a time. Do not stack speculative fixes.
- Third-party scripts: measure cost before removal; never silently drop tracking/analytics without client confirmation.
- No invented numbers. No "should improve by Xms" without a measured basis — mark as `Estimated`.
- Verification claims go through `growth-pulse-verification` (command + exit code + key lines).

## Output

- Conditions + baseline table (Measured / Not measurable) + dominant metric + culprits with `file:line` + handed-off fix list (owner: react-next) + re-measure table + remaining `Not verified` items.
