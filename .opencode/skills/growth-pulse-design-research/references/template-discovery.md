# Template discovery workflow

Templates accelerate; they also homogenize. Default answer: no template.
Adopt one only when it genuinely accelerates AND passes transformation.

## Sources (in order of preference for client work)

1. Official framework examples (Next.js examples, shadcn blocks) — maintained,
   licensed clearly, construction-grade.
2. shadcn templates / reputable UI libraries — implementation speed for
   dashboards and SaaS shells; visual identity still custom.
3. Framer templates — landing-page structure and section ideas; rebuild in
   the project stack, never ship the Framer export as the site.
4. Figma Community (UI kits, wireframes, design systems) — geometry and
   systems thinking; restyle fully.
5. GitHub starters — audit maintenance + license before touching.

## Adoption test (all four required)

1. What is useful (name the parts: grid, auth flow, table patterns…).
2. What must change (identity, type, color, composition deltas).
3. Why it fits THIS project (constraint it removes: time, complexity…).
4. What makes the result original (logo-swap test: would it still read as
   this product? If yes, transform further).

## Rules

- Never introduce a template merely because it exists.
- Never ship a template unmodified to a client.
- Never copy a template's visual identity (type, palette, illustration style).
- Record the decision + the four answers in the design brief or
  `docs/design/`; the receipt is part of delivery evidence.
- If no template passes, build custom — say so in one line and move on.
