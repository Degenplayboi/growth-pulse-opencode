---
name: growth-pulse-automation
description: Automation architecture for Growth Pulse. Use for n8n workflow design, MCP selection, browser automation boundaries, Telegram approval flows, secrets handling, and cost-conscious tooling decisions.
---

# Growth Pulse Automation

OpenCode is the architect/operator; runtimes execute. This skill DESIGNS and
REVIEWS automation; it does not bypass auth, CAPTCHAs, rate limits, or
platform rules, and it never sends externally without approval.

## When to use

- n8n workflow design (schedules, leads, notifications, onboarding, reporting)
- MCP evaluation (purpose, permissions, security, overlap, business value)
- Browser automation or scraping decisions
- Telegram approval/control-center flows
- Secrets, tooling, or cost decisions for automation

## 1. n8n — workflow runtime, not the brain

- OpenCode designs, reviews, and debugs; n8n runs schedules, webhooks,
  integrations, and background jobs. No duplicated logic without reason.
- Official capability skills (`n8n-io/skills`) are the reference when building
  n8n work; entry meta-skill `using-n8n-skills-official` routes to the matching
  capability. No OpenCode plugin exists yet — connect via n8n MCP only when an
  instance exists; until then, design workflows as reviewed JSON/specs.
- Agent-capability pattern: sub-workflow-as-tool, typed inputs, human-review
  gates on destructive tools, anti-loop filtering on chat-triggered workflows
  (bot's own messages must not re-trigger).
- State this session's finding: no n8n instance connected here — workflows are
  designed and documented, not deployed, until credentials exist.
- Runtime knowledge base: `docs/automation/` (architecture, CE capability
  record, 7 workflow specs, credential map, approval mechanics, deploy
  procedure). Read the relevant file before designing n8n work; do not
  duplicate it here.

## 2. MCP — capability extensions, curated

Order: native capability → official MCP/API → maintained open source →
trusted community. For each candidate: purpose, permissions, security,
maintenance, overlap, actual business value. No collecting MCPs because they
exist. Current baseline: `context7` (docs) only — correct for now.

## 3. Browser automation — boundaries first

Navigation, forms, extraction, screenshots, and testing where supported.
Never bypass authentication, CAPTCHA, access controls, rate limits, or
platform restrictions. No spam systems. Prefer `growth-pulse-web-testing`
for verification flows.

## 4. Telegram — approval center (when connected)

No Telegram connection exists in this environment yet — this section activates
on connection. Pattern: agent prepares (leads/messages/drafts/deploys with
evidence) → Telegram presents APPROVE / REVIEW / REJECT → agent executes only
on approval. Rate-limited, truthful, platform-compliant sends. Bot loops
guarded (own-ID filter). Until connected: prepare artefacts, request approval
in chat.

## Rules

- Secrets: env vars / secret stores / runtime injection, least privilege.
  Never in source, logs, screenshots, public repos, or docs.
- Cost: free / open-source / existing / free-tier first. No paid infra without
  a clear reason; revenue and delivery beat infrastructure.
- No infrastructure obsession: if the current system solves it, use it.
- Model independence: instructions, reusable skills, verification,
  provider-neutral workflows, explicit docs.

## Output

- Design or review (topology, nodes/tools, triggers, gates) + security/secret
  notes + cost note + approval items + what stays manual until credentials
  exist. No deployed-or-connected claims without live evidence.
