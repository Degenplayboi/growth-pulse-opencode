---
name: growth-pulse-verification
description: Verification gate before DONE claims. Use before claiming complete, fixed, passing, production-ready, or opening PR/commit. Requires fresh command evidence, never trust-and-claim.
---

# Growth Pulse Verification

Curated from: `obra/superpowers` verification-before-completion (inspected 2026-09-21). Matches orchestrator Verification Rule. Wording adapted.

## Iron law
NO COMPLETION CLAIMS WITHOUT FRESH VERIFICATION EVIDENCE. If you did not run the command in this session, you cannot claim it passes.

## Gate
1. IDENTIFY what command proves claim (test, build, typecheck, lint, screenshot, URL fetch).
2. RUN full command fresh, complete output.
3. READ exit code, count failures, inspect logs.
4. VERIFY output confirms claim. If no, state actual status with evidence. If yes, state claim WITH evidence.
5. ONLY THEN claim.

## Claim table
- Tests pass -> test output 0 failures (not prior run, not should pass)
- Linter clean -> 0 errors (not partial)
- Build succeeds -> exit 0 (linter != build)
- Bug fixed -> original symptom test passes now
- Regression covered -> red-green cycle verified (fail then pass)
- Agent done -> VCS diff shows changes (not agent report)
- Requirements met -> line-by-line checklist verified

## Red flags = STOP
should/probably/seems, premature Great!/Perfect!/Done!, commit/PR without verify, trusting agent report, partial check, tired exception, reworded success to dodge gate.

## Output
- Command + exit code + key lines + Verified / Not verified (reason). Never imply success without it.
