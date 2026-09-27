---
name: growth-pulse-design-system
description: Design-system implementation specialist. Use when building reusable Tailwind/shadcn component systems, tokens, responsive shells, and accessible SaaS UI patterns.
---

# Growth Pulse Design System

Curated from: Tailwind CSS practices, shadcn/ui composition methodology, accessible SaaS UI patterns. Growth Pulse original wording.

Boundary: `growth-pulse-frontend-design` decides WHAT the interface should look and feel like (direction, hierarchy, taste). This skill decides HOW it is consistently constructed (tokens, primitives, composition, states). Never duplicate visual-direction guidance here — reference frontend-design instead. Never duplicate React perf patterns — those remain with `growth-pulse-react-next`.

## When to use

- Reusable component system being built or extended
- Tailwind present, or shadcn present (`components.json` found)
- SaaS / dashboard / web-app UI development
- Project explicitly needs tokens, variants, or shared states (loading/empty/error/skeleton/toast)

Do NOT turn every project into a shadcn project. If shadcn is absent and requirements do not justify it, use Tailwind + local primitives only.

## 1. Inspect first (never invent)

- Detect Tailwind version: v4 (`@theme` / CSS-first config) vs v3 (`tailwind.config.js`). Never assume.
- Detect shadcn: read `components.json` + `shadcn info --json` equivalent (framework, aliases, `tailwindVersion`, `tailwindCssFile`, `base` radix/base, `iconLibrary`, `resolvedPaths`, installed components). Respect existing aliases, paths, base, icons, and preset. Never invent aliases or config.
- Inventory existing `ui/` primitives vs `blocks/` compositions vs feature components before creating anything. Reuse first.

## 2. Tokens (semantic, not raw)

- Colors: semantic roles (`background`, `foreground`, `primary`, `muted`, `muted-foreground`, `border`, `destructive`) — never raw `bg-blue-500` in components. Dark mode via tokens, never manual `dark:` color overrides per instance.
- Typography: 1–2 families with roles + scale + line-length discipline (from frontend-design direction). Spacing: consistent scale + `flex gap-*` (never `space-x-*`/`space-y-*`). Radius/shadow consistent.
- `cn()` (clsx + tailwind-merge) for all conditional classes. `size-*` when square. `truncate` shorthand. No manual z-index on overlay primitives.

## 3. Composition (shadcn-aware)

- Compose before inventing: check installed components / registry (`search`/`view`/`docs`) before custom markup. Settings = Tabs + Card + form controls; dashboard = Sidebar + Card + Chart + Table.
- Structural rules: items inside Groups (`SelectItem`→`SelectGroup`); `asChild` (radix) / `render` (base) per detected base; Dialog/Sheet/Drawer always include Title (sr-only if hidden); full Card composition (Header/Title/Description/Content/Footer); `TabsTrigger` inside `TabsList`; `Avatar` with `AvatarFallback`.
- Variants via `cva` before custom styles (`variant="outline"`, `size="sm"`). Keep `ui/` pure — wrap/extend in feature layer, never fork primitives silently.
- Button has no built-in loading prop — compose `Spinner` + `disabled` + `data-icon`.

## 4. Accessible SaaS patterns

- Forms: label + hint + error (`aria-describedby`), validation states, async-submit pending/disabled, failed-submit announcement. Prefer schema-validated patterns where project already uses them.
- Overlays: focus trap + return focus + Esc; destructive confirm via AlertDialog.
- Data display: Table with header scope, sortable/filter/paginate states, empty state (not blank table), loading skeleton (not custom pulse divs), error + retry.
- Feedback: `sonner` `toast()` for transient; `Alert` for callouts; `Empty` for empty states; `Skeleton` for loading; `Separator` (never `hr`/`div` lines); `Badge` (never custom spans); `Spinner` for pending.
- Navigation: Sidebar + Breadcrumb + Tabs + Pagination + Command palette composition; icon sizing via `data-icon`, icons from project `iconLibrary` only.

## 5. Responsive + states

- Mobile-first Tailwind; app shell (sidebar → hamburger/drawer) at 360/768/1280/1600; tables/cards stack; tap targets ≥44px (coordinate with quality-audit gate, do not redefine gate here).
- Every async surface defines loading / empty / error / populated states. Reduced-motion respected.

## Rules

- Never invent Tailwind version, aliases, shadcn config, existing components, or conventions — inspect first.
- Never `add` shadcn components without checking installed list; preview updates with dry-run/diff thinking; fix third-party import paths to project aliases.
- Verify: typecheck clean + visual spot-check via web-testing screenshot; gates via quality-audit; claims via verification.

## Output

- Detection summary (Tailwind version, shadcn config or absent) + reuse inventory + tokens/components added with paths + composition notes + states covered + verification note + Not verified items.
