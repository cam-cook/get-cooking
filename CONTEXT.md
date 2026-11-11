# Context: Cook onboarding

Everything gathered so far on Cook onboarding at Cookaborough: sources, evidence, analysis, staging findings and open decisions. `HANDOFF.md` is the build brief for the current prototype route, [`docs/vision.md`](docs/vision.md) describes the proposed shopfront-first direction, and [`docs/brief.md`](docs/brief.md) is the product brief, rewritten around the vision. This file is the background behind all three. Notion pages are marked unverified, so confirm anything important with their owners.

## 1. The project in brief

Cookaborough is moving Cook onboarding from a process Customer Success (CS) runs by hand to one Cooks complete themselves. Today the Cook owns 4 of the 41 onboarding steps, and CS does the other 37, many of them in Super Admin.

The aim is to capture what's legally and technically required at sign-up and in a Home checklist, guide the Cook into running their business, and let CS shift from data entry to coaching.

**Update, November 2026.** The checklist concept wasn't ambitious enough. The proposed direction is now "shopfront first, paperwork last": the Cook sees a branded draft of their shopfront within minutes, shapes it, then opens for orders through a single gate. The checklist stays as backbone and fallback. See [`docs/vision.md`](docs/vision.md); the data behind it is in section 14.

## 2. Sources

### FigJam and Figma

| Source | What it is | Status |
|---|---|---|
| FigJam `9X2vQPRzBx28JcUbaVMYAm` "Onboarding – Shopfront – Branding" | Current direction: 3 tiers (Required, Get started, Optimisation), MVP objective, co-designs with Nick, Abood and Steph, 2 concepts, setup checklist card, video strategy, Shopfront and Branding simplification | 11 pages. Branding page empty. Some pages are reference screenshots only |
| FigJam `HbbcI2qJzsL8YjQX2Y11jg` "Onboarding – Get started" | 2023 thinking, duplicated as the "Get started 2023" page of the board above | Superseded; archive |
| FigJam `GuFnonNmAx7hv7aXRxliY5` "Onboarding Issues" | 17 CS issues with MoSCoW priority and effort tags | The scored version of the Notion issues page |
| FigJam `eAMdRrZgMqB7yF2fFNxGxc` "New Cook starting point" | Current-state diagram from staging, plus 6 editable greyscale wireframes | Made in this work |
| Figma `tHGL0riAr0USLXguECSjnA` "Home", node `2145-6516` | High-fidelity setup checklist card (linked from PRO-591) | Approved design, not yet built |
| Figma `bEWZeXt5wwMDFqNq3qL67h` "Get started – Required", node `17-903` | Earlier first-time dashboard with a "Get started" modal (from SQU-49) | Older concept |
| Figma `3q43vMIfRF26jSITABVBzE` "New Cookbook" | Cookbook Pro library | Current |
| Figma `NBftiAAPSarwjUwOVGrISE` "Settings details", node `4002-4071` | Cookbook reference implementation (General details) | Current |
| claude.ai canvas "Cook onboarding — wireframes concept 1" | The same 6 wireframes as HTML artboards | Made in this work |

### Notion (Customer Success Hub and Strategy Hub)

| Page | Key content |
|---|---|
| Cook Onboarding | The as-is process: 5 phases (Handover & Kickoff, Account Setup, Showcase, Go Live, Activation), 41 steps with owners, the North Star workflow. Links the CS Trello board `trello.com/b/bx2Q1c5E/cook-onboarding`. CS reviews Cooks in onboarding at a fortnightly Cook Review Meeting. Last edited April |
| Cook Onboarding Issues | The same 17 issues as the FigJam board, plus overview and North Star. Last edited February |
| Kick-Off Call Meeting Guide | What CS covers in the first call (see section 6) |
| 2026 Rocks: Cook Onboarding – Discovery Phase | Q1, Design, **Done**. Goal: identify the platform blockers using Steph's CS documentation, rank them by importance and complexity, turn them into Linear tasks with Nick and Cam, then set a new rock for design and development |
| 2026 Rocks: Onboarding checklist | Q3, Product, **Done**, with sub-item "Onboarding – design" (Q2, Done). Pages are blank; detail lives in Linear |
| 2026 Rocks: Improved onboarding for Large Cooks | Q3, Sales, Not started. Onboarding large businesses is manual and bottlenecked on CS and lead developers handling data. 4 phases: review, propose, build and trial (including self-onboarding resources), document |
| 2026 Rocks: Cook onboarding and compliance pack | Q2, Product, Stalled. A different kind of onboarding (see the terminology note below) |

**Terminology clash.** In SaH and NDIS work, "onboarding" also means a **Cook being onboarded by a Care Provider**: the onboarding pack, onboarding requests, and the "not onboarded" status. This is a separate flow from a Cook joining Cookaborough. **Decision (Nov 2026): keep "onboarding" for this project for now.** "Setup" (product copy), "Cook launch" (internal) and "provider onboarding" (SaH) were considered and parked. Where both meanings could appear together, make clear which is meant. DESIGN-102 (Done) defined related SaH status terms.

### Linear

| Issue | Status | What it means for this work |
|---|---|---|
| **PRO-591** Onboarding – Setup checklist card (project "Onboarding Checklist") | Todo, unassigned | The build ticket for the Home checklist. Spec: card 896 px wide; welcome banner and other Home content are placeholders, not built; first checklist item uses a primary button, the rest ghost buttons; **clicking an item opens that Settings page as a modal**; **an SaH/NDIS modal appears when the Cook starts Compliance**, and its answer decides whether Government compliance shows. Out of scope: what happens after completion, any stepper flow. Design: Figma `tHGL0riAr0USLXguECSjnA`, node `2145-6516`. Related: OLDDEV-701 Compliance settings page |
| PRO-592 Design – Setup checklist card | Done (Erin) | Design for PRO-591 |
| PRO-637 Low fidelity – Setup checklist card | Done (Cecilia) | Earlier sketch, in "Ideas – Parking Lot" |
| DESIGN-165 Discovery – Welcome banner on Home | Todo | The welcome moment is still open |
| DESIGN-160 Low fidelity sketch – Home page | Todo (Cam), project "Settings – Uplift" | The new Home overall is still open, which explains the blank Home on staging |
| SQU-49 Onboarding / Settings / New Account Dependencies | Canceled (Aug) | Defined the Required, Operational and Optimisation tiers, linked the 2023 board and "Get started – Required" design, with a "Get started" modal concept. Superseded by the checklist approach |
| PRO-343 No warning when scheduling a menu with missing compliance/status | Done | A publish-time warning already exists in some form; check it against the blocked dialog design |
| PRO-594 Cooks to be able to preview draft menus regardless of status | Triage | Supports a "preview shopfront before publishing" step |
| AVO-189 Shopfront editor shows no preview menu | Done | Shopfront preview behaviour fixed |
| PRO-74, PRO-388 Customer importer (project "Onboarding – Customer Import Tool") | Done | Partly addresses the "invites and imports" issue |
| SQU-3 Make Find a Cook in Settings more compelling | Triage (Cam) | Find a Cook listing is a CS Showcase step |
| OLDDEV-816, DESIGN-231 Compliance alert on Government programs settings | Done | SaH compliance messaging exists |
| DESIGN-48 Show expired/expiring compliance documents on dashboard | Done | Source of the Expired state seen on staging |
| Menus – React Rebuild (AVO-69, AVO-194, AVO-387 and others) | In progress | The menu builder is being rebuilt, so the onboarding hand-off into it should follow the new builder |

## 3. The as-is process (Notion, 41 steps)

The Cook owns 4 steps: creating Stripe and entering bank details, providing recipe information, connecting Xero, and launching the menu. CS owns the other 37.

**Steps the design already moves to the Cook:** business details and ABN, compliance documents (today Sales collects these first), Stripe, and branding. CS applies branding before kickoff from the Cook's G-Drive, website or socials; the scraper idea in the MVP Branding step automates exactly that.

**Steps the design should take on:**
- Email and label logo, and email header. Marked critical in Notion: emails don't send without them; Super Admin only.
- Bank details before the Stripe CTA.
- Kitchen address. Lived under Compliance, which is why it was missed; now in General details on staging.
- Public contact details, which Settings once called "Shop details".

**Steps no design covers yet:** applying SaH and NDIS fees, delivery and pickup settings, default menu image and heading, menu badges, About, links, FAQs, customer reviews, Routific, Xero, the collateral pack and drafting the Find a Cook listing.

**Phases mapped to the design tiers:** Account Setup maps to Required; Showcase and Go Live map to Get started; Activation maps to Optimisation.

**North Star (CS):** Sales sends a link, the Cook signs up and goes straight into a wizard, and wizard completion is "a true demonstration of commitment". CS then runs facilitated onboarding: menu optimisation, recipe compliance, fulfilment and marketplace positioning.

## 4. The 17 issues (FigJam scores)

**Incomplete:** 14 of the 17 issues are listed below. The other 3 still need copying from the FigJam "Onboarding Issues" board.

| Issue | Priority | Effort |
|---|---|---|
| Signup form captures too little (ABN, addresses) | Must | S |
| 1:1 logo only in Super Admin; emails fail without it | Must | S |
| Menu won't publish without About Us, and no message says why | Must | S |
| Core settings fragmented, no "minimum to launch" view | Must | L |
| Image uploads inconsistent, no dimensions shown | Must and Should (2 tags) | XL |
| Bank details missed below the Stripe CTA | Should | S |
| Repetitive address entry, no "same as" option | Should | M |
| Email header only in Super Admin | Should | M |
| FAQs copied in manually | Should | M |
| Accounts only creatable via the signup link | Should | L |
| Compliance docs collected by Sales | Should | L |
| Menu heading has no preview | Could | L |
| Invites and imports not fit for purpose | Could | L |
| SaH/NDIS profile import | Won't | L |

Recipes, menus and fulfilment are marked "Already prioritised" as separate projects.

**Quick wins** (Must/S plus Should/S): expand signup fields, surface the 1:1 logo, add a message for the About Us dependency, put bank details first.

**Image sizes from CS:** About 16:9, hero 2:1, plus sizes for SEO, default menu and SaH images listed on the issues board.

## 5. Staging review (Oct 2026)

Reviewed on platform.staging with a set-up account (`cam+11`, Cam's Burgers) and an empty one (`cam+1`, Test Account). The empty account already had a logo, colours, 18 delivery zones and 2 unscheduled menus, so a real new Cook starts with less.

**Built and working:**
- The Settings index shows a live status on 4 tiles: General details, Brand kit, Compliance and Stripe payments show "Required" until done, then "Completed". This is the "minimum to launch" view CS asked for, but only inside Settings.
- Compliance documents each carry a status, including Expired.
- The kitchen address sits in General details with a "same as business address" toggle, ticked by default.
- ABN is an "Add ABN" action with an ABN register lookup and GST status.
- Bank details have their own page (Invoice payments), separate from Stripe.
- The square food label logo (512 × 512) is Cook-managed in Brand kit, and logo dimensions are shown.
- The menu heading and default menu image sit in the Shopfront Home editor with a desktop, tablet and mobile preview.
- SaH and NDIS fees are in Government programs.
- About, FAQs, customer reviews and the SaH and NDIS pages are in Shopfront.
- The welcome email has default copy and uses the Brand kit logo.
- The Closures & public holidays page lists state holidays.

**Problems:**
- Home renders blank on platform.staging for both accounts; app.staging still shows the old Home with empty Previous menus, Top meals and a $0 sales chart. There's no entry point for a new Cook. This matches PRO-591 and DESIGN-160 still being Todo.
- Brand kit counts as Completed without the food label logo, though emails reportedly fail without it. Confirm whether emails now fall back to the main logo.
- The email header wasn't found in Brand kit or Customer notifications; possibly still Super Admin only.
- SaH and NDIS content shows even when Government programs is off: Shopfront pages, approval emails marked "Always on", and fee options.
- Fees are split across 3 pages (Service fees, Catering, Government programs), and the Service fees card claims to cover Catering but doesn't.
- Invoice payments isn't Required, even when SaH or NDIS will be switched on.
- Workers compensation is Required for everyone, though sole operators are exempt elsewhere in the copy.
- Shopfront uploads (About, hero) show file types and size limits but not dimensions.
- FAQs aren't preloaded.
- Pickup locations are added by hand; there's no "use kitchen address" shortcut.

**Copy bugs:** Xero and QuickBooks cards say "Not connected" next to "Sales and payment data are syncing"; there are 2 Routific integrations ("Routific" and "Routific – Old"); the Stripe card says "Connect a bank account via Stripe", which confuses the separate bank details page; the AI page uses "your business" and "you'd like".

**Product names to adopt everywhere:** General details, Brand kit, Compliance, Stripe payments, Invoice payments, Government programs, Find a Cook (FAC), Closures & public holidays (feature work has used "Public holidays and breaks"; align on one).

## 6. What CS covers in the kick-off call

From the Kick-Off Call Meeting Guide. The self-serve flow has to carry this or hand it to CS deliberately:

1. Confirm the Sales handover: business type, menu style, delivery areas, target customers, interest in government programs.
2. Walk through the customer experience on the website.
3. Explain the 2 customer segments: "Hungry Households" (working professionals and families, a few weeknight meals per week) and Government program customers (larger baskets of mains, soups, salads, snacks and desserts, often comparing against Lite n' Easy, very loyal).
4. Show marketplace discovery by suburb or postcode.
5. Review a Find a Cook listing: cover, food imagery, story, testimonials, menu preview. "The first impression customers have."
6. Show menu models: **weekly rotating** (changes weekly or fortnightly, orders for a delivery window) and **always-on** (fixed range, order any time).
7. Show ordering: cart, minimum order and free delivery thresholds, delivery or pickup, checkout.
8. Move to the dashboard and explain setup: Stripe and bank details; recipe import (documented recipes, a website or a menu to reference); delivery and pickup (suburbs, days, pickup location and hours).
9. Explain the next milestone: the **menu showcase call**, where CS reviews the menu and delivery settings and schedules launch.

Implications: the prototype doesn't yet ask which menu model the Cook runs, show the customer view early, or explain the 2 segments. Sign-up could ask the menu model (it changes how menus and fulfilment are set up), and the welcome could show the customer experience.

## 7. Analysis

**The gating rule is inconsistent.** At least 6 versions exist across the sources: required "before publishing a Menu"; required "before opening the Shopfront"; Shopfront blocked until Branding is done; steps "can't be skipped" (concept 1); the whole platform locked until done (concept 2); steps skippable (MVP and co-designs). The real system gate differs again: menus can't publish without an About page. The North Star's commitment test needs at least 1 hard gate, which rules out "everything skippable". Erin's task, "Determine what NEEDS to be filled out for a menu and cut the other mandatory requirements", is the work that settles it.

**Who owns Get started.** The boards make Recipes, Menus and fulfilment self-serve with videos; the North Star and kick-off guide have CS facilitating them. Decide whether videos replace or support CS sessions.

**Admin first or build first.** The design order puts compliance paperwork first, the least rewarding and most stall-prone task. Building first keeps the Cook motivated, with admin gating only the publish. This is the main thing to test.

**SaH question timing.** The prototype asks at sign-up; PRO-591 asks in a modal when Compliance starts. Sign-up is earlier and also controls Shopfront pages, emails and fees; the PRO-591 approach is lighter at sign-up. Pick 1.

**Checklist items: page or modal.** The prototype opens full Settings pages and returns to Home. PRO-591 opens each Settings page as a modal over Home. The modal approach keeps the Cook on the checklist; check it works for long pages like Compliance and Brand kit.

**Moments not yet designed:** the first minute after sign-up (DESIGN-165); ABN errors; Stripe errors on return; upload failures; recipe and menu hand-off into the rebuilt builder; a shopfront preview before publishing (PRO-594); the launch moment; reminder emails when a Cook stalls; Home on a return visit.

**The CS side:** a trigger to CS when Required is done; a CS view of each Cook's progress to replace the Trello board; where Sales' handover lands; and the large-Cook path (Large Cooks rock), where CS and developers import data in bulk.

**Measurement:** no baseline for time to launch yet. The CS Trello board likely holds dates per phase. Suggested measures: time from sign-up to first live menu, and drop-off at each step.

## 8. Earlier board review notes

**The 2023 board's ideas worth keeping:** "Setting up is not settings"; a separate kitchen address; the Stripe explainer copy (an existing Stripe account still needs a new connection; funds arrive less commission); a declaration step; "show added and waiting for approval" for documents; the open questions (can the list change after events, how to keep resources relevant, can items done elsewhere tick off).

**Business name and shop name.** The 2023 board used "Shop name", the newer board "Business name". The legal entity comes from the ABN lookup; the trading name is what customers see.

**Copy fixes on the boards:** HCP should be SaH (Home Care Packages were replaced by Support at Home in late 2025); the video strategy says intro videos aren't step-by-step, but Recipes and Menus intro copy says "step-by-step guide"; copy across boards uses you/your and exclamation marks. Typos include "scrapper" (scraper), "Serval" (several), "We compliance" (when), "Partically", "Setup S tripe", "chjanges", "ca't", "create and account", "traken", "Cookboook", "withint he", "curently", "onboaring", "seperate", "Lets", and US spellings (utilize, colors, summarizes, Fulfillment, ORGANIZED, optimization, Standardized).

## 9. Open decisions

1. The gating rule: what blocks publishing, and whether compliance needs CS approval first.
2. Admin first or build first.
3. Who owns Get started: self-serve or CS-led.
4. When to ask the SaH/NDIS question: sign-up or at Compliance (PRO-591).
5. Checklist items as modals (PRO-591) or full pages.
6. Whether the declaration step is in the MVP.
7. Whether sign-up asks the menu model (weekly rotating or always-on).
8. Time estimates, which are unvalidated.
9. Whether the direction in `docs/vision.md` is agreed.
10. What Cookaborough can legitimately read from Instagram, and on what terms.
11. Whether a pre-launch interest list is allowed before food business registration.
12. How far the SaH and NDIS path diverges after the Cook says they serve those programs.

Decision 2 (admin first or build first) is largely answered by the vision, which puts the shopfront first and admin at the gate. It's still worth testing. Decision 7 is folded into the vision's short conversation, which asks the menu model after the first preview.

**Taken in `docs/vision.md` (proposed):** email and magic link before the preview; ownership confirmation before any site is read; private, non-indexed drafts until opening for orders; a branded shopfront as the promise, with detected dishes as a bonus; delivery days and order cutoff confirmed at the gate; no food claims on drafts; a nearly open state for Cooks waiting on paperwork.

## 10. Suggested research

Test both prototype routes (the current checklist concept and the shopfront-first route from `docs/vision.md`) with 4 or 5 new or prospective Cooks, using the existing moderated session setup from Delivery schedules testing. Scenarios are in `README.md`; add scenarios for the second route when it's built.

## 11. Related Cookaborough work to build on

Capabilities that exist or are in design elsewhere, and how each could make setup more self-driven.

| Work | Status | Use in setup |
|---|---|---|
| **AI Ingredient Importer** (Linear project "AI Ingredient Importer – MVP Release"; AVO-267, PRO-291) | Released; "Recipes – AI Importer" project continues (PRO-250 kitchen instructions, PRO-143 design workshop) | The fastest route to a first recipe. CS currently imports recipes for Cooks; point the "Add the first recipe" step at the importer, with "paste or upload an existing recipe" as the first option |
| **Items / Products** (Recipes vs Pre-packaged, or Simple vs Complete) | In design; structure and names undecided; may ship behind a feature flag | Lets a Cook get a first menu live without full ingredient matching. Includes a planned import from 1 product image (ingredients, allergens, NIP, prep and storage). Get cooking should allow "first item", not only "first recipe", once this ships |
| **Plate Up** (Recipes) | Concept and prototype planning | Solves the food photo gap at launch; container photo plus a plated version, flagged as AI |
| **Customer importer** (PRO-74, PRO-388) | Done | The "Invite existing customers" launch step can use it |
| **Suburb import** for delivery zones | In design | Makes the delivery option in Get cooking much faster than adding zones by hand |
| **Fulfilment intro video** and **fulfilment simulator** | In progress | Ready-made content for the fulfilment step; the video pattern also suits the other Get cooking intro videos |
| **Menu status model** | Proposed: lifecycle (Draft → Scheduled → Published → Archived) and trading status (Open, Closed, Paused) as separate axes; Draft means "no trading dates set" | The setup flow's "draft menu" and "publish" should use these terms. The publish gate applies when a menu moves from Draft to Scheduled |
| **Automations** (triggered customer emails, triggers set by Cookaborough) | Design direction locked | The same trigger engine could send Cook-facing setup nudges, such as "signed up, no recipe after 3 days", and alert CS when a Cook stalls |
| **Find a Cook** redesign | In progress (FigJam "Find a Cook") | The listing is a CS Showcase step and the Cook's "first impression". The launch step could prompt the listing, with a preview |
| **Care Managers project** (why Care Managers choose Lite n' Easy; Trilogy as test lab) | In progress | For SaH and NDIS Cooks, real activation is being onboarded by Care Providers. Compliance documents uploaded at setup should feed the provider onboarding pack (rock stalled; SQU-27, SQU-60) |
| **Cooks Brain** (Cook verbatims store) | Artifact built | Source of verbatims to test setup copy and steps against, and the place to log findings from setup testing |
| **Cook personas** (FigJam "Cook personas – Needs work") | Draft | Basis for tailoring setup paths, for example a home cook, an established caterer, a large business |

## 12. Proposals for a self-driven experience

These proposals were developed into the shopfront-first direction in [`docs/vision.md`](docs/vision.md).

These are suggestions, not decisions, drawn from the evidence above.

**Personalise from sign-up.** 3 or 4 questions shape the path: menu model (weekly rotating or always-on), delivery, pickup or both, SaH and NDIS, and business size. Large businesses get an assisted path where CS or Sales pre-fills the account, which also covers the "accounts only via signup link" issue and the Large Cooks rock.

**Bring what you already have.** Offer imports before forms: a website or social link to suggest branding, colours and an About draft (the scraper idea); existing recipes through the AI importer; product photos through the image import; a customer list through the customer importer; a suburb list for delivery zones.

**Defaults over blank fields.** The kitchen as first pickup location, default FAQs, default email copy (already done for the welcome email), a default weekly schedule, and the square logo created from the main logo.

**Show the result as it grows.** A live shopfront preview that fills in as steps are completed gives the motivation the kick-off call currently provides. PRO-594 (preview draft menus) supports this.

**Explain at the point of need.** Dependency messages where the blocker is, not only at publish; short intro videos per step; "Book a call" in context rather than only in the header.

**Nudge and hand over.** Reminder emails when a Cook stalls, CS alerted on stalls and on completion, and a CS progress view to replace the Trello board.

**Mark milestones.** First recipe, first menu scheduled, first order. After launch, Home moves to the Optimisation tier: photos, Find a Cook listing, Automations, customer invites.

**Measure it.** Track each step's start, completion and time, so drop-off and time to first live menu can be compared before and after.

## 13. Precedents: exceptional onboarding elsewhere

Examples to refer to when making design calls. Details reflect these products as last known and may have changed; check current versions before quoting them.

| Product | What it does well | Lesson for Cook onboarding |
|---|---|---|
| **Duolingo** | A first lesson before creating an account; daily goal; streaks and quick positive feedback | Let Cooks build something real (a recipe, a draft menu) before asking for compliance documents. Supports the "build first" order |
| **Stripe** | Test mode works immediately; identity and business verification needed only to go live and receive payouts | The cleanest model for the gating rule: everything works in draft, and legal and payment details gate only when money and customers are involved |
| **Shopify** | A few sign-up questions, then a setup guide on Home; the store is a real, previewable site from day one, protected until launch | The closest analogue to the Home checklist plus a live shopfront preview |
| **Airbnb (hosting)** | Listing broken into small single-purpose screens with progress; save and return any time; new hosts can get one-to-one help from an experienced host | Small steps with visible progress, and human help as a safety net, not a requirement. Matches the CS North Star |
| **Canva** | Asks what it'll be used for, then shows relevant templates; first design in minutes | Personalise from 1 or 2 questions (such as menu model) and start from something pre-filled |
| **Calendly** | A shareable booking link within minutes, from default availability and an auto-created event type | Defaults over blank fields: kitchen as first pickup location, a default weekly schedule |
| **Notion** | A "Getting started" page that teaches the product using the product; templates | Onboarding content can be real, editable content, such as a sample menu or an About draft |
| **Headspace** | A few warm goal questions, a short first session straight away, a reminder for the next day | Reminders tied to the Cook's goal when they stall, not to the task list |
| **Typeform** | 1 question per screen, conversational wording, instant feedback | If sign-up questions grow, ask them 1 at a time |

**Common threads:** value before admin; personalise early; start from defaults and templates; make the result real and previewable from the start; gate only what must be gated, at the moment it matters; keep human help available but optional; use reminders that bring people back.

**To research:** Uber Eats and DoorDash merchant sign-up and menu creation. Some Cooks will compare Cookaborough against these, so review current versions rather than relying on memory.

## 14. Data: web presence and websites (November 2026)

Pulled from Metabase (`cook_profiles`) on 11 November 2026. Full findings and what they mean for the design are in [`docs/vision.md`](docs/vision.md).

### Web presence by Cook status

| Status | Website | Instagram, no website | Facebook only | Nothing |
|---|---|---|---|---|
| Live (146) | 107 (73%) | 27 (18%) | 2 (1%) | 10 (7%) |
| Onboarding (113) | 50 (44%) | 13 (12%) | 2 (2%) | 48 (42%) |
| New (194) | 72 (37%) | 20 (10%) | 5 (3%) | 97 (50%) |

Website values that were really Instagram, Facebook or Linktree links were moved into the right group. Archived (301) and Junk (21) are excluded. These fields are filled in during setup, so "Nothing" for New and Onboarding Cooks partly means "not entered yet", and Live Cooks may overstate how many Cooks have a website.

### Website sample

229 of 232 websites use a custom domain, so the platform isn't visible from the address. A random sample of 20 Live Cooks' sites, checked in a browser:

| Platform | Sites |
|---|---|
| WordPress | 8 |
| Shopify | 4 |
| Squarespace | 2 |
| Wix | 1 |
| Webflow | 1 |
| Square Online | 1 |
| Dead or unreachable | 3 |

- 11 of the 17 working sites link to the Cook's Cookaborough shopfront for ordering, so the site is usually a brand front and dishes often aren't there to detect.
- Only 7 showed prices on the home page (home pages only; menus may sit deeper or in PDFs).
- About 1 in 4 stored links are broken or out of date: 3 dead, 2 moved.
- 7 Cooks already sell through another tool (4 Shopify stores, a Wix shop, a Square Online store, 1 using Mr Yum).
- New Cooks' sites may carry more of their own menu, since they haven't built Cookaborough into them yet. Untested.
