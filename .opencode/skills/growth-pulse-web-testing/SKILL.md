---
name: growth-pulse-web-testing
description: Functional browser testing with Playwright. Use to verify local web apps, debug UI behavior, capture screenshots, check console errors, test forms, links, and navigation.
---

# Growth Pulse Web Testing

Curated from: `anthropics/skills` webapp-testing (official Anthropic, inspected 2026-09-21). Node-first Playwright via `playwright-core` + system browser channel (Edge/Chromium), headless. Python is NOT required; it remains optional only for specialized tooling. This file is Growth Pulse wording.

## When to use
- Any clickable flow must be proven: buttons, forms, nav, links, auth, error/loading/empty states
- Visual check via screenshot, console/network failure hunt
- Before claiming fixed/working/done

## Method: reconnaissance-then-action
1. Static HTML? Read file directly for selectors. Else dynamic:
2. Server running? If no, start it first (ask for command/port, e.g. `npm run dev` :5173). Keep server management separate from test logic.
3. Navigate + `wait_for_load_state('networkidle')` BEFORE DOM inspect (critical for JS apps).
4. Recon: screenshot `<temp>/inspect-<viewport>.png` full_page where useful, dump `page.content()`, list `button/link/input` locators.
5. Act with discovered selectors (`text=`, `role=`, CSS, ID). Add explicit waits (`wait_for_selector`), never arbitrary sleeps unless condition-based.

## Script pattern (Node — primary; verified 2026-09-23 with playwright-core 1.63 + Edge channel, no Python, no browser download)
```js
const { chromium } = require('playwright-core');
(async () => {
  const browser = await chromium.launch({ headless: true, channel: 'msedge' });
  const page = await browser.newPage({ viewport: { width: 1280, height: 800 } });
  const errors = [];
  page.on('pageerror', e => errors.push('pageerror: ' + e.message));
  page.on('console', m => { if (m.type() === 'error') errors.push('console: ' + m.text()); });
  await page.goto('http://localhost:5173'); // or file:///… for static pages
  await page.waitForLoadState('networkidle');
  // ... actions + asserts (overflow check: document.documentElement.scrollWidth
  //      minus clientWidth must be 0; screenshot per viewport)
  await browser.close();
})().catch(e => { console.error(e.message); process.exit(1); });
```
Setup lives OUTSIDE the repo (temp dir): `npm init -y; npm i playwright-core`
then `channel: 'msedge'` (or `'chrome'`) to use the installed system browser —
no `ms-playwright` browser download needed. Python remains optional for
specialized tooling only, never a prerequisite for testing or verification.

## Must capture
- Screenshot proof for key states
- Console errors + failed requests (log them, fail on unexpected)
- Form matrix: valid, invalid, empty, failed-submit message, focus/error association

## Rules
- Headless chromium always for automation.
- Close browser when done.
- Do not read large helper scripts into context; run `--help` first, use as black box.
- One behavior per script; descriptive names.

## Output
- Script path + command + pass/fail + screenshots + console/network log + selectors used.
