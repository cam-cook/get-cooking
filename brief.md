# Brief: Onboarding Experience

**Linear:** Initiative I-11 "Onboarding Experience" (Proposed, tagged Needs Brief) and project P-PRO-42 "Onboarding Checklist" (Backlog).
**Status:** Draft for review. Rewritten 11 November 2026 around the shopfront-first direction in [`vision.md`](vision.md), which is proposed but not yet agreed. Items marked [TBC] need a decision or a number.
**Owner:** [TBC] · **Lead team:** Squid (initiative), Product Team (project)

**Summary:** A new Cook sees their business live on Cookaborough within minutes, shapes it on the shopfront itself, then makes it official through a single "Open for orders" gate. Setup starts from what the Cook already has (a website, an Instagram account, or a sentence and a dish photo), and CS moves from doing the setup to coaching alongside it.

---

## 🧠 Problem / Opportunity

Onboarding a new Cook is almost entirely manual. Of the 41 steps in CS's onboarding process, the Cook owns 4: creating Stripe and entering bank details, providing recipe information, connecting Xero, and launching the menu. CS does the other 37, many of them only possible in Super Admin.

The platform doesn't support self-setup yet:

- **No starting point.** A new Cook lands on a Home with empty menu, meal and sales panels and nothing saying what to do first. The Home setup checklist is designed (PRO-592) but not built (PRO-591, DESIGN-160, DESIGN-165).
- **Admin before value.** Every version of the flow so far starts with paperwork: business details, compliance documents, Stripe. These are the least rewarding and most stall-prone tasks, and the Cook doesn't see anything of their business until the end.
- **Hidden requirements.** A menu won't publish without an About page, and nothing says why. Customer emails fail without a square logo, which was Super Admin only.
- **Fragmented settings.** There's no single view of "what's needed to open" outside Settings, and SaH and NDIS content appears even for Cooks who don't serve those programs.
- **Branding and content start from scratch.** CS applies each Cook's branding by hand before the kick-off call, from their G-Drive, website or socials. Cooks then write the About page, FAQs and menu descriptions themselves, often in a voice that doesn't match the rest of their brand.
- **The customer view comes late.** CS shows Cooks the customer experience in the kick-off call. Without CS, a Cook has no way to see their shopfront as a customer would before they launch.

The cost falls on CS time, on how fast Cooks reach their first sale, and on growth. Onboarding larger businesses is a bottleneck on CS and lead developers (2026 Rock "Improved onboarding for Large Cooks").

The opportunity: much of what self-setup needs now exists on staging (Required and Completed statuses in Settings, compliance document states, ABN lookup, the AI Ingredient Importer, the customer importer, the AI writing assistant's tone of voice). Most Cooks also already have a brand: 73% of Live Cooks have a website and a further 18% have Instagram without one. What's missing is a path that starts from that brand and ties the rest together.

Evidence: Notion "Cook Onboarding" and "Cook Onboarding Issues" (CS), FigJam "Onboarding Issues" (scored issues), the Discovery Phase rock (Q1, Done), a staging review in October 2026, and Metabase data and a website sample from November 2026. Detail in [`CONTEXT.md`](../CONTEXT.md) and [`vision.md`](vision.md).

---

## 🎯 Goal

What does success look like when this project is done?

* A new Cook sees a branded draft of their shopfront within minutes of signing up.
* A new Cook can go from sign-up to opening for orders without CS entering any of their setup information, and without visiting Settings.
* The Cook always knows what stands between them and real customers, and nothing else is presented as a blocker.
* Everything Cookaborough drafts (About page, menu descriptions, FAQs, social post) sounds like the Cook's business, and never makes a food claim the Cook's own data doesn't support.
* CS moves from data entry to coaching: menu review, recipe compliance, fulfilment and marketplace positioning (the CS North Star), with a launch review replacing the required showcase call.

---

## ✅ Success Criteria

How will we know this worked?

- [ ] **Time to first preview:** median time from sign-up to a draft shopfront of [TBC] minutes.
- [ ] **Time to open for orders:** median days from sign-up, down from a baseline taken from the CS Trello board to [TBC].
- [ ] **Open within 14 days:** [TBC]% of new standard Cooks open for orders within 14 days of sign-up.
- [ ] **Time to first order:** median days from opening for orders to first order, [TBC].
- [ ] **Self-serve rate:** [TBC]% of new standard Cooks open for orders without CS entering data for them.
- [ ] **Assisted setup:** share of Cooks taking assisted setup is tracked; target [TBC].
- [ ] **Import success:** [TBC]% of website imports produce a usable draft, measured separately for websites, existing online shops and Instagram.
- [ ] **Drafts accepted:** [TBC]% of AI drafts (About page, menu descriptions) are kept with light or no edits.
- [ ] **Drop-off by step:** measured for every step, with no single step losing more than [TBC]% of the Cooks who start it.
- [ ] **CS time per new Cook:** down from [TBC] hours to [TBC].
- [ ] **No Super Admin-only steps** for a standard Cook's setup.
- [ ] **No unsupported food claims:** zero allergen, dietary, nutrition or certification claims in drafts that aren't in the Cook's recipe data or compliance records.
- [ ] **Usability validated:** 4 or 5 new or prospective Cooks complete the prototype from sign-up to open for orders, with task success of [TBC]%, and both prototype routes are compared.

---

## 📦 Scope

The flow is described step by step in [`vision.md`](vision.md). It's delivered in 3 phases. The PRO-591 Home setup checklist stays as the backbone and the fallback for any Cook who leaves the main flow.

### In Scope

**Phase 1: conversation, gate and coach** (built on the PRO-591 checklist, no import)

* **Sign-up:** email address confirmed by magic link. No password, ABN or business details at this point.
* **Short conversation:** 4 or 5 questions, 1 per screen: menu model (weekly rotating or always-on), delivery, pickup or both and roughly where, SaH or NDIS customers, and business size. Answers set defaults and decide the path.
* **"Open for orders" gate:** visible from the start. Lists only ABN (with lookup), food business documents, Stripe, delivery days and order cutoff confirmed, and bank details for SaH and NDIS Cooks. Each item links to where it's fixed. CS reviews compliance in the background.
* **Nearly open state:** for Cooks waiting on documents such as council registration. Shows progress on each item, the CS contact, and a menu that can still be edited.
* **Conditional SaH and NDIS:** Invoice payments, care declaration, SaH and NDIS Shopfront pages, approval emails and fees, shown only when the Cook serves those programs.
* **CS alongside:** a named CS contact throughout; CS alerted when a Cook stalls and when a Cook is ready to open; the showcase call becomes an optional launch review.
* **Assisted setup offer:** for large or multi-location businesses, decided by the conversation. The Cook uses the same flow with CS driving.
* **Launch share kit:** shopfront link, QR code, a social post drafted in the Cook's tone, and an invitation to import existing customers (customer importer).
* **Home as coach after launch:** next best action and milestones (first order, first 10 orders), linking to the Optimisation tier.
* **Silent failures removed:** the About page dependency, square logo and other blockers explained where they occur.
* **Tracking:** step start, completion and time for every step, to measure the success criteria.

**Phase 2: shopfront editing**

* **Work on the shopfront itself:** add dishes as recipes (AI Ingredient Importer) or simple items, set trading dates, and edit the About draft directly on the preview.
* **Preview as a customer:** the shopfront exactly as a customer sees it, replacing the customer demo from the kick-off call (builds on PRO-594).
* **Brand kit from the shopfront:** square logo created from the main logo and validated, image dimension guidance, email header moved out of Super Admin.

**Phase 3: import**

* **Start with what they have:** a website, an Instagram handle, or a sentence and a dish photo, offered as equal options on the first screen, website first.
* **Ownership confirmation:** the Cook confirms they own the site or have permission to use its content before anything is read.
* **Draft shopfront in about a minute:** logo (main and square), brand colours, heading font (nearest available, licensed font), hero image, and an About page drafted in the Cook's tone. Detected dishes appear as drafts when the site has them.
* **Tone of voice profile:** a short, editable profile written from the site's language and saved to Settings › AI, used for every AI draft.
* **Existing online shops:** Shopify, Wix, Square Online and similar stores import products as structured drafts where the platform allows.
* **Graceful failure:** a dead, moved or thin site drops straight into the sentence and photo path without blame.
* **Private drafts:** the draft shopfront isn't public or indexed until the Cook opens for orders.

### Out of Scope

* **Bulk data import for large Cooks:** CS or Sales pre-filling accounts and importing data in bulk. Covered by the "Improved onboarding for Large Cooks" rock. The assisted setup offer above is in scope.
* **Care Provider onboarding:** the Cook to Care Provider onboarding pack and requests. A separate flow with the same name (Gov projects, SQU-27).
* **Builder rebuilds:** the recipe builder, menu builder (Menus – React Rebuild) and delivery zone builder. Onboarding links into them as they are. Zones, windows and the full schedule builder stay in Settings.
* **Optimisation tier features themselves:** photo tools, Find a Cook listing improvements, Automations, SEO and marketing guidance. The post-launch coach links to them; it doesn't build them.
* **Items / Products and Plate Up:** separate features. The flow adopts them once released.
* **A pre-launch interest list:** until compliance confirms it's allowed before food business registration.
* **Renaming "onboarding"** in product or internal language (decided November 2026: keep it).

---

## 🧩 Deliverables

- [ ] **Agree the direction:** review [`vision.md`](vision.md) with Product, CS and the CTO, and confirm or change it.
- [ ] **Decisions:** the open decisions in [`CONTEXT.md`](../CONTEXT.md) section 9, starting with the gating rule.
- [ ] **CS walkthrough:** walk CS through the vision before the prototype hardens, since CS's role changes most.
- [ ] **Prototype:** a second route in the existing prototype, alongside the current one, with simulated imports for 3 example Cooks (website, Instagram only, nothing and SaH).
- [ ] **Prototype testing:** sessions with 4 or 5 Cooks comparing both routes.
- [ ] **Design, phase 1:** sign-up, conversation screens, Open for orders gate, nearly open state, launch share kit, post-launch Home.
- [ ] **Build the Home setup checklist** (PRO-591) as backbone and fallback.
- [ ] **Design and build, phase 2:** shopfront editing, Preview as a customer, Brand kit changes.
- [ ] **Design and build, phase 3:** import for websites, online shops and Instagram; tone of voice profile; failure paths.
- [ ] **AI guardrails:** rules and tests so drafts never make unsupported food claims.
- [ ] **Conditional SaH and NDIS:** hide pages, emails, fees and steps for Cooks who don't serve those programs.
- [ ] **Fees in 1 place** and the copy fixes from the staging review.
- [ ] **CS process:** handover and stall alerts, a CS view of each Cook's progress to replace the Trello board, and an updated kick-off and launch review guide.
- [ ] **Event tracking** for the success criteria.
- [ ] **Stale profile links:** fix or flag existing Cooks' broken website links (about 1 in 4 in the sample).

---

## 🧪 Dependencies / Risks

* **The direction isn't agreed.** The vision is a proposal. Until it's confirmed, phase 1 should stay compatible with the PRO-591 checklist.
* **The gating rule isn't decided.** At least 6 versions exist across the design work, and the live system differs again (About page blocks publishing). The vision proposes one gate at "Open for orders"; it still needs agreement.
* **Compliance review timing.** If CS must approve documents before a Cook can open, review speed becomes the Cook's bottleneck. Needs an agreed turnaround.
* **Council registration takes weeks.** Cooks can finish their shopfront long before they can legally open. The nearly open state has to keep them engaged.
* **Import quality.** Most Cooks' websites are a brand front with ordering on Cookaborough, so dishes often aren't there to detect. Half the sample runs on WordPress with different themes, so reading the page with AI is more realistic than parsing it. About 1 in 4 stored links are broken or out of date.
* **Logos, colours and fonts.** Logos may be low resolution or embedded in images; colours may come from photos rather than the brand; fonts may be unavailable or unlicensed for reuse. Every suggestion needs review and a manual fallback.
* **Instagram.** What Cookaborough can read depends on Instagram's terms. Treat it as best effort.
* **Privacy and abuse.** A preview built from someone else's site is a risk. Email before the preview, ownership confirmation and private drafts reduce it; rate limits are still needed.
* **AI accuracy and compliance.** Drafts must not state allergen, dietary, nutrition or certification claims that aren't in the Cook's data. This is a compliance risk, especially for SaH and NDIS customers.
* **Fulfilment defaults.** A wrong delivery day or cutoff costs a real customer. Confirming them at the gate reduces this; zones and windows still need setting properly in Settings.
* **Menus – React Rebuild** is in progress. Shopfront editing and the gate need to land in the new builder, not the old one.
* **Stripe** is an external round trip; Cooks who leave part way need a clear way back.
* **CS process change.** The kick-off call, fortnightly Cook review and Trello board all assume CS-led setup. CS needs to own the new handover.
* **Scope.** This is much bigger than PRO-591. Phasing keeps the checklist useful while the rest is built.
* **Terminology.** "Onboarding" also means Care Provider onboarding in SaH and NDIS. Screens showing both need to make clear which is meant.
* **Priority and ownership.** The initiative has no owner and both it and the project are Low priority, while the 2026 Rocks show "Onboarding checklist" as Done although PRO-591 isn't built. The project name "Onboarding Checklist" also no longer describes the scope.
* **Staging.** Home renders blank on platform.staging, so the starting point can't be tested in the product until PRO-591 ships.

---

## Release details

Add a link under each heading when ready.

### Feature Flag:

[TBC] Suggest releasing each phase to new accounts only behind a flag, then to existing incomplete accounts.

### CS Handover:

[TBC] Updated kick-off and launch review guide reflecting self-setup; when and how CS is alerted on stalls and on readiness to open.

### User Guide:

[TBC] Help articles for each gate item, plus intro videos. Include how import and the tone of voice profile work, and how to edit them.

### Internal Guide:

[TBC] What each status means, how to see a Cook's progress, how to approve or return documents, and how to run assisted setup.

### EDM:

[TBC] Welcome email, nearly open updates, and reminder emails for Cooks who stall part way.

### Announcements:

[TBC]

---

## References

| What | Where |
|---|---|
| Vision | [`vision.md`](vision.md) |
| Full context | [`CONTEXT.md`](../CONTEXT.md) |
| Linear | Initiative I-11, project P-PRO-42, PRO-591, PRO-592, PRO-637, DESIGN-160, DESIGN-165, SQU-49 (canceled), PRO-343, PRO-594 |
| Approved checklist design | Figma "Home" `tHGL0riAr0USLXguECSjnA`, node `2145-6516` |
| CS process and issues | Notion "Cook Onboarding", "Cook Onboarding Issues", "Kick-Off Call Meeting Guide" |
| Strategy | Notion 2026 Rocks: Discovery Phase (Done), Onboarding checklist (Done), Improved onboarding for Large Cooks (Not started) |
| Design boards | FigJam "Onboarding – Shopfront – Branding", "Onboarding Issues", "New Cook starting point" |
| Data | Metabase `cook_profiles` (web presence by status), November 2026; 20-site sample of Live Cooks' websites |
| Prototype | get-cooking-b9px.vercel.app, repo cam-cook/get-cooking |
