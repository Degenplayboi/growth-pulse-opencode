---
name: growth-pulse-debugging
description: Systematic debugging with root-cause analysis. Use for any bug, test failure, build failure, or unexpected behavior before proposing fixes. Enforces reproduce, trace, single hypothesis, failing test.
---

# Growth Pulse Debugging

Curated from: `obra/superpowers` systematic-debugging + test-driven-development (inspected 2026-09-21, S-rank 286K). Growth Pulse wording; process preserved.

## Iron law
NO FIXES WITHOUT ROOT CAUSE INVESTIGATION FIRST.

## Phase 1 — Root cause
1. Read full error/stack, line numbers, codes. Don't skip warnings.
2. Reproduce reliably: exact steps, every-time? If not reproducible gather more data, don't guess.
3. Check recent changes: git diff, commits, deps, config, env differences.
4. Multi-component (CI->build->deploy, API->service->DB): add diagnostic logs at each boundary (in/out + env/config), run once, identify failing layer first.
5. Trace data flow backward: where bad value originates, who called with it, fix at source not symptom.

## Phase 2 — Pattern
Find working similar code in repo. If implementing pattern, read reference completely. List every difference. Check deps/config/assumptions.

## Phase 3 — Hypothesis
Single specific hypothesis: "X root cause because Y". Smallest single-variable test. If fails, new hypothesis. Don't stack fixes.

## Phase 4 — Implement
1. Failing test first (RED: watch it fail for right reason). No production code without it; delete pre-written code and start over.
2. Single minimal fix (GREEN). No drive-by refactoring.
3. Verify: test passes, suite still green (run full project test command, not just one file), symptom gone. Use growth-pulse-verification before claiming.
4. If >=3 fixes failed: STOP, question architecture with human. Pattern of new symptoms per fix = wrong pattern, not wrong fix.

## Stop signals
"Quick fix for now", "try X and see", "multiple changes at once", "skip test, manual verify", "probably X". All mean return to Phase 1.

## Output
- Root cause statement + evidence + failing test path + fix diff + verification output + regression risk.
