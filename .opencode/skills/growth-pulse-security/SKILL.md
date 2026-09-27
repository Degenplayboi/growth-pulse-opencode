---
name: growth-pulse-security
description: Web and application security specialist with tiered review. Use for headers/secrets/validation on all sites, auth/API/database hardening on apps, and AI-agent boundaries only when agents exist.
---

# Growth Pulse Security

Curated from: OWASP ASVS and relevant OWASP guidance (LLM / Agentic where applicable), secure-headers/CSP practices, server-side authorization patterns. Growth Pulse original wording.

This skill OWNS security review depth. `growth-pulse-quality-audit` keeps only its pass/fail pointer — do not duplicate this checklist there. Evidence claims follow `growth-pulse-verification`. Debugging fixes follow `growth-pulse-debugging`.

## When to use (tiered — do not apply all tiers to all projects)

- LEVEL 1 — every production website (marketing / static / business / landing / portfolio)
- LEVEL 2 — additionally for any auth / API / database / file-upload / webhook / payment / application project (SaaS, dashboard, booking, e-commerce, web app)
- LEVEL 3 — additionally ONLY when the project actually contains AI/agents/toolscalling. Never force AI threat modeling onto ordinary websites.

## Iron rules

- Never claim "secure" from a checklist pass. Report findings + residual risks + `Not verified` items.
- Never invent penetration-test results. Static review + header/fetch evidence only; state method per finding.
- Secrets: never commit, never log, never expose to client. Env names only in handoff docs.

## LEVEL 1 — all production websites

- HTTPS-only, HSTS where applicable, no mixed content
- Security headers noted (CSP where appropriate, frame-ancestors, content-type nosniff, referrer-policy); report actual response headers or `Not verified`
- XSS: no unsanitized `dangerouslySetInnerHTML` / `innerHTML`, no reflected input without encoding
- Injection: encode/validate at boundaries; no string-concatenated queries/commands
- Secrets exposure: no keys/tokens in client bundle, repo, or logs; `NEXT_PUBLIC_` reviewed
- Dependencies: note known-risky/outdated packages where evidence exists (lockfile inspection, not invented CVEs)
- Forms/inputs: server-side validation (client validation is UX only), error messages without stack/sensitive leakage
- External links: `rel="noopener noreferrer"` on `target="_blank"`, no open-redirect via `?next=`/`?url=` without allowlist
- Abuse basics: note spam/scraping exposure on public forms/endpoints; rate-limit suggestion where appropriate

## LEVEL 2 — web applications (in addition to Level 1)

- Authentication: session handling, cookie flags (HttpOnly/Secure/SameSite), expiry, logout invalidation; never trust client-side auth gates alone
- Authorization: server-side checks on every route/action; BOLA/IDOR review (object IDs scoped to owner/tenant, not just `authenticated` role)
- CSRF: state-changing routes protected (same-site + token/origin check per framework)
- API: authZ per endpoint, input schema validation, idempotency where retried, error codes without data leakage
- Database/storage: least-privilege access, RLS/ownership predicates reviewed where present, direct-object references scoped, file-upload type/size/quarantine checks
- Webhooks: raw-body signature verification (`constructEvent`-style), timestamp tolerance, idempotent handling, 200-only-on-success discipline
- Rate limiting: login/webhook/AI-invoking endpoints noted; suggest throttling/quotas where missing
- Sensitive data: PII minimization, no sensitive data in URLs/logs, masked logging

## LEVEL 3 — AI/agentic applications only (in addition to Levels 1–2)

- Prompt injection: untrusted content (tool output, docs, memory, uploads) treated as data, never as instructions; boundaries documented
- Excessive agency: least-privilege tool manifests, no open-ended shell/URL tools where scoped tools suffice, per-tool permission review
- Exfiltration: private-data + untrusted-content + external-egress combination flagged (lethal-trifecta check); restrict egress, redact secrets from tool context
- Human approval: high-impact/sensitive/irreversible actions require explicit approval; define which actions qualify
- Trust boundaries: model vs tools vs memory vs user — state what each may/may not do; session/tenant isolation for multi-user agents

## Output

- Tier applied (L1 / L1+L2 / L1+L2+L3) + why. Findings as `file:line` with severity + tier + fix. Headers evidence (fetch output) or `Not verified: <reason>`. Residual risks + explicitly non-claimed areas. Never write "secure" — write "no blocking findings in scope checked" with scope stated.
