# Cook onboarding vision: shopfront first, paperwork last

Status: proposed, not yet agreed. Written 11 November 2026.
Related: [`brief.md`](brief.md) (product brief, rewritten around this vision), [`CONTEXT.md`](../CONTEXT.md) (research and sources), Linear I-11 "Onboarding Experience", P-PRO-42, PRO-591.

## Why this exists

Cook onboarding today is run by CS. Of the 41 steps in the process, the Cook owns 4. The current prototype (sign-up, Home checklist, Settings steps, publish gate, launch) moves that work to the Cook, but it keeps the same shape: fill in settings until Cookaborough lets the business sell.

This document proposes a different shape. The Cook sees their business live on Cookaborough within minutes, shapes it, then makes it official. Value comes before admin, and the Cook never has to visit Settings during onboarding.

The current concept is not thrown away. Its checklist becomes the backbone and fallback (see Phasing).

## Principles

**Start with what they already have.** Most Cooks have a website, an Instagram account or at least a photo of a dish. Begin there, not with a form.

**Show the shopfront before asking for anything else.** The first real screen is the Cook's own business on Cookaborough. Everything after that changes something visible.

**Work happens on the shopfront, not in Settings.** Dishes, About copy, photos and trading dates are edited where customers will see them. Settings stays the place for later refinement.

**Ask only what changes the outcome.** A short conversation sets defaults and decides the path. If an answer doesn't change the preview, the defaults or the path, the question waits.

**One gate, stated plainly.** "Open for orders" is visible from the start. Pressing it shows only what stands between the Cook and real customers.

**Drafts never make claims.** Anything Cookaborough drafts (dishes, descriptions, About copy) is clearly a draft. Allergen, dietary, nutrition and certification claims come only from the Cook's recipe data and compliance records.

**A person, when it helps.** CS is a named contact alongside the flow, not a step in it.

## What the data says

Pulled from Metabase (`cook_profiles`) on 11 November 2026.

### Web presence by Cook status

| Status | Website | Instagram, no website | Facebook only | Nothing |
|---|---|---|---|---|
| Live (146) | 107 (73%) | 27 (18%) | 2 (1%) | 10 (7%) |
| Onboarding (113) | 50 (44%) | 13 (12%) | 2 (2%) | 48 (42%) |
| New (194) | 72 (37%) | 20 (10%) | 5 (3%) | 97 (50%) |

Website values that were really Instagram, Facebook or Linktree links were moved into the right group. Archived (301) and Junk (21) are excluded.

Read with care. These fields are filled in during setup, so "Nothing" for New and Onboarding Cooks partly means "not entered yet". Live Cooks are also the ones who made it through, which may overstate how many Cooks have a website.

### What the websites look like

Of 232 websites across Live, Onboarding and New Cooks, 229 use a custom domain, so the address doesn't reveal the platform. A random sample of 20 Live Cooks' sites was checked by hand.

| Platform | Sites |
|---|---|
| WordPress | 8 |
| Shopify | 4 |
| Squarespace | 2 |
| Wix | 1 |
| Webflow | 1 |
| Square Online | 1 |
| Dead or unreachable | 3 |

Four findings shape the design:

1. **The website is usually a brand front and Cookaborough does the selling.** 11 of the 17 working sites link to the Cook's Cookaborough shopfront for ordering. Brand (logo, colours, photos, About copy, tone) is reliably there. Dishes often are not. Only 7 sites showed prices on the home page.
2. **About 1 in 4 stored links are broken or out of date.** 3 sites are dead and 2 have moved. Import must fail gracefully.
3. **Some Cooks already sell elsewhere.** 4 Shopify stores, a Wix shop, a Square Online store and one Cook using Mr Yum. These are the strongest import cases because their products are structured.
4. **WordPress is the most common and hardest case.** Each site uses a different theme or page builder, so reading the page with AI is more realistic than parsing its structure.

Assumption to test: New Cooks haven't yet built Cookaborough into their sites, so their sites may carry more of their own menu than Live Cooks' sites do.

## The flow

### 1. Start with what they have

The first screen asks for one thing: a website, an Instagram handle, or a sentence about the business and a dish photo. All 3 sit on the same screen as equal options, with website first because it's the most common.

Before anything is generated, the Cook gives an email address and confirms it through a magic link. No password, ABN or business details yet. This keeps the first minute fast while cutting abuse, stopping people previewing businesses they don't own, and giving CS someone to follow up if the Cook stalls.

Before anything is read, the Cook confirms they own the website or account, or have permission to use its content.

If the import fails (dead site, moved site, nothing useful found), the Cook drops straight into the sentence and photo path. The message describes what happened without implying the Cook did anything wrong.

### 2. Here's [business] on Cookaborough

In about a minute the Cook sees a draft shopfront: logo, colours, heading font, hero image and an About page drafted in their tone. The heading font is matched to the nearest available font Cookaborough is licensed to use, since the site's own font may not be reusable. Every suggestion can be swapped or replaced with an upload. Dishes detected on their site appear as drafts when they exist. When they don't, the menu area is a clear, unfinished space ready for step 4.

The draft is private and not indexed until the Cook opens for orders. Saving it creates the account.

The promise of this step is a branded shopfront. Detected dishes are a bonus, because the data shows most sites don't carry a menu.

### 3. A short conversation

4 or 5 questions, 1 per screen, each changing the preview or the defaults:

- Weekly rotating menu or always-on menu
- Delivery, pickup or both, and roughly where
- Whether the Cook serves Support at Home (SaH) or NDIS customers
- Business size

Answers set defaults (menu model, fulfilment starting point, which compliance items apply) and decide whether to offer assisted setup. The SaH and NDIS answer may open its own branch (see Paths).

### 4. Shape the first menu on the shopfront

The Cook works directly on the preview:

- Turn detected dishes into recipes (AI Ingredient Importer) or simple items
- Add photos (Plate Up later)
- Set trading dates
- Edit the About draft

"Preview as a customer" shows the shopfront exactly as a customer will see it. It replaces the customer demo from the CS kick-off call.

### 5. Open for orders

The button is visible from step 2. Pressing it lists only what stands between the Cook and real customers:

- ABN
- Food business documents
- Stripe
- Delivery days and order cutoff, confirmed
- Bank details, for SaH and NDIS Cooks

Delivery days and cutoff are a gate item because a wrong default costs a real customer. The Cook confirms them on the shopfront, with a summary of what the conversation set, rather than in Settings. Zones, windows and the full schedule builder stay in Settings for later.

CS reviews compliance in the background.

**Nearly open.** Council food business registration can take weeks. A Cook who has finished their shopfront but is waiting on paperwork sees a "nearly open" state: progress on each outstanding item, their CS contact, and a menu they can keep editing. A pre-launch interest list is tempting here but needs a compliance check first, because promoting a food business before it's registered may not be allowed.

### 6. A person, when it helps

CS appears as a named contact throughout. CS is alerted when a Cook stalls and when a Cook is ready to open. The showcase call becomes an optional launch review rather than a required step.

### 7. Launch as a moment

Opening for orders comes with a share kit: the shopfront link, a QR code, a social post drafted in the Cook's tone, and an invitation to import existing customers.

### 8. After launch, Home becomes a coach

Home shows the next best action and milestones (first order, first 10 orders), then the Optimisation tier: Automations, a Find a Cook listing, better photos.

## Paths

**Website (about 3 in 4 Live Cooks).** The lead path. Brand import is reliable. Dish detection is a bonus.

**Existing online shop (Shopify, Wix, Square Online and similar).** The strongest import case: products usually come across cleanly. These Cooks are also most likely to compare Cookaborough with what they already have, so the preview should make the difference obvious (scheduling, fulfilment, SaH and NDIS).

**Instagram only (about 1 in 5 Live Cooks).** Import of profile, photos and captions depends on what Instagram allows Cookaborough to read. Treat it as best effort, with the sentence and photo path as the immediate fallback.

**Nothing (a small share of Live Cooks, possibly more among new sign-ups).** A sentence and a dish photo produce a simpler draft: business name, a generated colour palette, the photo as hero, and an About draft from the sentence. This must still feel finished enough to be worth shaping.

**SaH and NDIS Cooks.** Pricing rules, bank details, extra compliance and how Care Managers find them all differ. Asking in step 3 is right. How far the path diverges after that is still open, and ties into the Care Managers work.

**Large businesses.** Multi-location businesses and Cooks with existing customer bases are offered assisted setup: the same shopfront, with CS driving.

**Broken or stale links.** Fail into the sentence and photo path without blame. Separately, stale profile links are worth fixing for existing Cooks.

## Decisions taken in this document

- Email and magic link before the preview, not after.
- The Cook confirms ownership or permission before any site or account is read.
- The draft shopfront is private and not indexed until opening for orders.
- Step 2 promises a branded shopfront. Detected dishes are a bonus.
- Delivery days and order cutoff are confirmed at the gate.
- No allergen, dietary, nutrition or certification tags on drafts.
- A "nearly open" state for Cooks waiting on paperwork.
- The current checklist stays as backbone and fallback.

## Phasing

**Phase 1: conversation, gate and coach.** Steps 3, 5, 6, 7 and 8, built on the PRO-591 checklist without import. Delivers the single gate, the nearly open state and a better post-launch Home.

**Phase 2: shopfront editing.** Step 4: shaping the menu, About and trading dates directly on the shopfront, with "Preview as a customer".

**Phase 3: import.** Steps 1 and 2. The riskiest and most expensive part, so it comes last in build. The prototype simulates it now so Cooks can react to it early.

## Measures

- Time from sign-up to first preview
- Time from sign-up to opening for orders
- Share of sign-ups open for orders within 14 days
- Time from opening to first order
- Share of Cooks needing assisted setup
- Import success rate, by path

Targets are TBC.

## Open questions

- **Gating rule.** What exactly blocks opening for orders, and does compliance need CS approval before a Cook can open?
- **Admin-first versus build-first.** Largely answered by this direction, but still worth testing with Cooks.
- **SaH and NDIS.** When to ask, and how far the path diverges.
- **Instagram.** What can Cookaborough legitimately read, and on what terms?
- **Pre-launch interest list.** Allowed before food business registration?
- **Declaration step.** In the MVP or not?
- **Checklist items as modals or pages** (PRO-591), for the fallback.
- **Time estimates.** Unvalidated.
- **Brief targets and owner.** Still TBC in `docs/brief.md`.
- **Where the brief lives in Linear.** P-PRO-42 or I-11.
- **CS involvement.** CS's role changes most. Walk CS through this document before the prototype hardens.

## Prototype plan

Build this as a second route in the existing prototype (`cam-cook/get-cooking`), alongside the current concept, so both can be tested with Cooks. Use realistic simulated imports for 3 example Cooks:

1. A Cook with a website (the common case)
2. An Instagram-only Cook
3. A Cook with nothing, set up as a small SaH Cook to test that branch

The current route stays untouched.

## Sources

- CS Notion docs: 41-step process, North Star, kick-off call guide
- 17 scored onboarding issues
- Staging review, October 2026
- Linear: I-11, P-PRO-42, PRO-591
- Precedents: Duolingo, Stripe, Shopify, Airbnb, Canva, Calendly, Notion, Headspace, Typeform
- Metabase `cook_profiles` queries and a 20-site sample of Live Cooks' websites, 11 November 2026
