---
name: growth-pulse-research
description: Evidence-graded research for Growth Pulse. Use when current/external facts matter: market, competitor, technical, product, pricing, tooling, or design-reference research.
---

# Growth Pulse Research

Research BEFORE deciding whenever facts are current, external, or uncertain.
This skill FINDS and LABELS; it does not implement. Implementation stays with
delivery skills; claim rules stay with `growth-pulse-verification`.

## When to use

- Market, competitor, offer, advertising, or pricing research
- Technical facts: APIs, docs, library behavior, version changes, tooling
- Product, design-reference, or community-experience questions
- Any claim that would otherwise be a guess

Small stable questions (local files, known APIs already inspected) skip this.

## Source selection

- Technical facts → primary/official first (docs, GitHub, changelogs).
- Real-world experience → community (YouTube, X, Reddit, blogs, forums).
- Design direction → galleries + product references (extract principles,
  never clone identity).
- Capability search → GitHub, UI Skills, n8n/OpenCode/MCP ecosystems,
  automation and design communities. Curate; never install everything found.

## Method

1. State the question and what decision it serves.
2. Search broadly (not one source), inspect primary sources directly.
3. Record: source, URL, date, what it says — and what it does NOT say.
4. Synthesize smallest useful answer; competing evidence noted, not hidden.

## Claim labels (every important claim gets one)

- VERIFIED — inspected/measured this session (file:line, command output).
- REPORTED — source says so (cite source + date; may be stale or wrong).
- INFERRED — reasoned from evidence (mark as such, show reasoning).
- PROPOSED — recommendation (not a fact).
- UNKNOWN — cannot verify (say so; never fill the gap with invention).

## Rules

- Never present guesses as facts. Never invent APIs, URLs, credentials,
  behavior, results, statistics, or testimonials.
- Never claim an action was performed that was not performed.
- Distinguish lab vs field, docs vs behavior, single report vs consensus.
- Persist durable findings to `docs/research/` with source + date.

## Output

- Question + sources (URL + date) + findings each labelled + gaps marked
  UNKNOWN + PROPOSED next step. No unlabeled important claims.
