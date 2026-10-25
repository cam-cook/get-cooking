# get-cooking

Clickable Cook onboarding prototype for Cookaborough. Plain HTML, CSS and JavaScript in single files. No build step. Deployed on Vercel from `main` (get-cooking-b9px.vercel.app).

## Files
- `index.html`: the whole prototype (Cookbook Pro styled). Screens, state and actions all live in this file.
- `README.md`: test scenarios and assumptions.

## Design system
- Cookbook Pro library: Figma file `3q43vMIfRF26jSITABVBzE`
- Reference implementation: Settings details, Figma file `NBftiAAPSarwjUwOVGrISE`, node `4002-4071`
- Tokens live as CSS custom properties at the top of `index.html`. Use them; don't hardcode new hex values.
- Inter, 14 px body. Page title 24/32 semibold. Card title 18/28 medium.
- Controls 32 px high. Cards: white, 12 px radius, 2xs shadow. Primary button teal `#00786F`.
- Icons: Lucide, 16 px, stroke 1.33.
- Card heading is the input label.

## Copy
- Sentence case, active voice, Australian spelling
- No "you" or "your" in interface copy, no exclamation marks
- Ampersands only in top-level titles
- Buttons start with a verb; an action keeps the same name through the flow
- Numerals, not words, for numbers

## Prototype rules
- The teal bar at the top is prototype controls, not product UI
- Recipe builder, delivery zone builder and Stripe are placeholders or simulations
- State saves to localStorage
