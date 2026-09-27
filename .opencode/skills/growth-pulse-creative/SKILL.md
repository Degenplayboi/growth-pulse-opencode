---
name: growth-pulse-creative
description: Creative production methods for Growth Pulse. Use when producing static ads, social/product graphics, site imagery, short-form video, variants, resizing, or captions. Chooses the correct production method: HTML/SVG, Remotion, or generative models.
---

# Growth Pulse Creative

Boundary: `growth-pulse-growth` owns the creative PIPELINE (brief → approval →
publish, claim hygiene, no fabrication). This skill owns PRODUCTION METHOD —
how each artifact is made. Never duplicate pipeline/approval guidance here.

## When to use

- Static ads, social graphics, product graphics, website imagery, promos
- Product demonstrations, short-form video, ad variants, platform adaptations
- Image editing, resizing, captions, image-to-video workflows

## Method selection (in order — first fit wins)

1. **HTML/CSS/SVG** — typography-heavy UI, deterministic graphics, diagrams,
   annotated mockups, anything with text that must render exactly. Most
   reliable; preferred default. (Proven in-repo: teardown campaign exhibit.)
2. **Remotion** — deterministic branded video, UI demonstrations, ad variants
   at scale (aspect ratios, hooks, captions from one composition). Code-reviewed
   like any other code; render outputs verified by viewing, never assumed.
3. **Generative image models** — imagery that genuinely benefits from
   generation (textures, scenes, conceptual visuals). NEVER for
   typography-heavy UI (HTML/SVG wins), never for logos, never for anything
   requiring exact text. Every output inspected; rejects re-rolled or rebuilt
   deterministically.

## Image-model discovery (no hardcoding — run per need)

Sources: Hugging Face Models/Spaces, Civitai, curated open-source/open-weight
directories, relevant GitHub repos. Distinguish per candidate, in writing:
open source vs open weights vs free-to-use vs free-to-try vs commercial
license vs non-commercial; local vs hosted/API. "Open model" NEVER implies
commercially unrestricted — check the license file, record it.
Choose per task on: image quality, text rendering, editing ability,
consistency, licensing, hardware, cost. Record the choice + license +
why in the task notes. No permanent default model.

## Rules

- Claim hygiene inherits from `growth-pulse-growth`: no fabricated clients,
  results, revenue, testimonials, statistics, partnerships, completed work.
  Fictional/demo labeling where applicable.
- Platform adaptations are deliberate (aspect, safe areas, caption length,
  hook in first seconds for video) — never mechanical resize-and-ship.
- Cost: free/open-source/existing first; generative calls metered and
  justified per asset. No paid API without a clear reason.
- Verify: view every render/image at full size before approval; gates via
  `growth-pulse-quality-audit`; claims via `growth-pulse-verification`.

## Output

- Method chosen + why + assets produced (paths) + license notes (if
  generative) + verification note + Not verified items.
