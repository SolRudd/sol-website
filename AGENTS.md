# AGENTS.md — sol-website

## Scope
These instructions apply to the entire repository.

## Project baseline
- Framework: Astro 6
- Styling: Tailwind CSS v4
- Adapter: @astrojs/vercel
- Package manager: npm (use lockfile)
- Node: >=22.12.0

## Working principles
- Make small, reversible, targeted changes.
- Do not refactor or restructure unrelated code.
- Reuse existing layout/components/patterns before introducing new abstractions.
- Preserve route structure and existing design direction unless explicitly asked.
- Never invent testimonials, analytics claims, metrics, or integration claims.

## Protected areas (require explicit user permission)
- `astro.config.*` (deployment/runtime behavior)
- `package.json` dependency or script changes
- Any environment or secret handling (`.env*`, CI/deploy config)
- Brand identity assets in `public/` (logo/favicon/etc.)
- Global metadata and navigation/footer identity links in `src/layouts/Layout.astro`

## Allowed default edit zones
- `src/pages/**` and `src/layouts/**` for requested UI/copy/content changes
- `src/styles/**` for scoped visual adjustments aligned with existing style system

## Commands
- Install: `npm ci`
- Dev: `npm run dev`
- Check/typecheck: `npm run astro -- check`
- Build: `npm run build`
- Preview build: `npm run preview`

## Validation policy
Run the narrowest relevant check first, then full build when appropriate:
1) `npm run astro -- check`
2) `npm run build`
3) `npm run preview` (if user asks for runtime smoke-check)

## Change safety
- Do not touch billing/auth/deploy/provider settings unless explicitly requested.
- If a requested change might alter deployment behavior, call it out before editing.
- If uncertain about factual copy, ask for source text or leave unchanged.

## PR/summary expectations
- Summarize exactly what changed, what commands were run, and remaining risks.
- Highlight any assumptions made.
