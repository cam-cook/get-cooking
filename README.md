# Get cooking: Cook onboarding prototype

A clickable prototype of the refined Cook onboarding flow for Cookaborough, from sign-up to the first live menu. Greyscale wireframe style, so testing focuses on the flow rather than visuals.

## Run it

It's a single file with no build step. Open `index.html` in a browser.

To share it with Cooks for testing, turn on GitHub Pages: **Settings › Pages › Deploy from a branch › main / root**. The prototype is then live at `https://cam-cook.github.io/get-cooking/`.

Progress saves in the browser. Use **Reset to new Cook** in the yellow bar to start again.

## What's in the flow

1. **Sign up.** ABN, business name, business address, "Meals are prepared at this address", and a Support at Home / NDIS question.
2. **Welcome.** What happens next, roughly how long it takes, and when Customer Success gets involved.
3. **Home checklist.** Required steps and Get cooking, with the next step highlighted.
4. **General details**, prefilled from sign-up.
5. **Compliance.** Upload, In review, Approved and Returned states, plus the declaration. The care declaration appears for SaH and NDIS Cooks only.
6. **Stripe payments.** A simulated round trip to Stripe, including the "left before finishing" state. Bank details appear for SaH and NDIS Cooks only.
7. **Brand kit.** Logo, square logo created from the logo, colours suggested from the logo, and an email preview.
8. **Government programs.** Toggle on or off. Its steps don't block standard menus.
9. **First recipe, delivery or pickup, About page.** The recipe and zone builders are placeholders, since they're separate projects.
10. **Menu.** A draft banner listing what's still needed, a publish-blocked dialog with direct links, then a shopfront preview.
11. **Launch.** Shopfront link, QR code and invite customers.

## Prototype controls (yellow bar)

| Control | Use |
|---|---|
| Order | Switch between **Admin first** and **Build first** to compare the 2 checklist orders |
| CS approves documents | Moves every submitted document from In review to Approved |
| CS returns a document | Returns 1 document, to test the rejected state |
| Skip required steps | Completes the admin steps, to jump straight to menu building |
| Reset to new Cook | Clears all progress |

## Test scenarios

1. **Admin first.** Sign up and get a first menu live. Where does the participant slow down or hesitate?
2. **Build first.** The same task with Order set to Build first. Compare time and confidence.
3. **Blocked publish.** Skip to building a menu, then try to publish. Can the participant fix every blocker from the dialog?
4. **Returned document.** Upload documents, then use CS returns a document. Does the participant notice and fix it?
5. **Stripe interrupted.** Leave Stripe before finishing. Does the participant know how to resume?

## Assumptions to validate

- Menus can be built at any time. Publishing waits for the 4 required steps, an About page, a recipe and a delivery or pickup option.
- Uploaded compliance documents count as "submitted" for the checklist, but must be **approved** by Customer Success before publishing.
- Government programs steps gate SaH and NDIS orders only, not standard menus.
- Customer Success is notified automatically when all 4 required steps are complete.
- Time estimates (about 20 minutes, 5–10 minutes for compliance) are unvalidated.
