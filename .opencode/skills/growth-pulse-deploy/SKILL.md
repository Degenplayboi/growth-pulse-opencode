---
name: growth-pulse-deploy
description: Git, Vercel deployment, production verification, and client handoff. Use for commit hygiene, preview/production deploys, post-deploy checks, docs, and maintenance handover.
---

# Growth Pulse Deploy

Curated from: `vercel-labs/agent-skills` deploy-to-vercel v3.0.0 (inspected 2026-09-21) + GitHub gh CLI patterns + orchestrator delivery-checklist. Growth Pulse wording.

## When to use
- Deploy request, pre-launch, production verify, handoff docs, maintenance note

## Git hygiene
- Status/diff/log check before commit, stage only intended files, never commit secrets, concise message matching repo style. No force-push, no empty commits, no config changes unless asked. Fix hook rejections with new commit, never amend failed.

## Deploy (Vercel-first)
- Default: preview deployment, not production, unless user explicitly says production.
- Linked (.vercel/ exists): `vercel deploy`. Not linked + authenticated: link then deploy. Not linked + unauthenticated: install/auth/link/deploy. Static HTML auto-handled, node_modules/.git excluded, 40+ frameworks auto-detected.
- Record preview URL + commit SHA. For claimable flows record claim URL.

## Production verify (mandatory before handoff)
1. Deploy succeeds, production URL 200, no build warnings ignored.
2. Critical flows pass in production (use growth-pulse-web-testing recon against prod URL where safe, read-only first).
3. No regression: nav, forms, auth, payments (test mode), links, console clean, headers/HTTPS OK.
4. Rollback note: prior SHA / revert path.

## Handoff
- README update: run instructions, env vars (names only, no values), deploy target, rollback, content TODOs (testimonials/stats placeholders), maintenance owner.
- Delivery checklist: Requirements / Design / Function / Quality / Deployment each pass or Not verified with reason. Only then recommend client delivery.

## Output
- Commit SHA + preview/prod URLs + verification evidence + handoff file paths + Not verified items.
