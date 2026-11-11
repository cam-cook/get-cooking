# get-cooking

Clickable Cook onboarding prototype for Cookaborough. Plain HTML, CSS and JavaScript in single files. No build step. Deployed on Vercel from `main` (get-cooking-b9px.vercel.app).

## Files
- `index.html`: the current route, the checklist concept (Cookbook Pro styled). Screens, state and actions all live in this file.
- `README.md`: test scenarios and assumptions.

## Docs (read before planning)
- `docs/vision.md`: the shopfront-first direction for the second route. Proposed, not agreed. The source of truth for what the second route does.
- `docs/brief.md`: the product brief, rewritten around the vision. Scope, phases, success criteria and risks.
- `CONTEXT.md`: research, sources, staging findings, data and open decisions behind both.
- `HANDOFF.md`: the build brief for the current route, if present.

Where they disagree, `docs/vision.md` wins for the second route and `HANDOFF.md` wins for the current route.

## Two routes
- The current route (`index.html`) stays as it is, so both can be tested with Cooks. Don't change its screens, copy or behaviour.
- The second route follows `docs/vision.md`. Propose where it lives (for example its own file) in the plan before building.
- A switch between routes may be added to the prototype controls bar only.
- Imports in the second route are simulated. Use realistic data for 3 example Cooks: a Cook with a website, an Instagram-only Cook, and a Cook with nothing set up as a small SaH Cook. Invent the businesses; don't use real Cooks' names or content.
- Drafted dishes never show allergen, dietary, nutrition or certification tags.

## Design system
- Cookbook Pro library: Figma file `3q43vMIfRF26jSITABVBzE`
- Reference implementation: Settings details, Figma file `NBftiAAPSarwjUwOVGrISE`, node `4002-4071`
- Tokens live as CSS custom properties at the top of `index.html`. Use them; don't hardcode new hex values.
- Inter, 14 px body. Page title 24/32 semibold. Card title 18/28 medium.
- Controls 32 px high. Cards: white, 12 px radius, 2xs shadow. Primary button teal `#00786F`.
- Icons: Lucide, 16 px, stroke 1.33.
- Card heading is the input label.
- Single-column forms. No sheets.
- Card descriptions describe the section, not its status.
- The second route uses the same tokens and components as `index.html`.

## Copy
- Sentence case, active voice, Australian spelling
- No "you" or "your" in interface copy, no exclamation marks
- Ampersands only in top-level titles
- Buttons start with a verb; an action keeps the same name through the flow
- Numerals, not words, for numbers

## Prototype rules
- The teal bar at the top is prototype controls, not product UI
- Recipe builder, delivery zone builder and Stripe are placeholders or simulations
- State saves to localStorage. Keep each route's state under its own keys.
