# Site Audit — `preview--steelbuild-easy.lovable.app`

**Audit date:** 2026-05-24
**Auditor:** Loren AI HCP (Master Makabi build)
**Subject:** HandyMan Pro LLC marketing site (Lovable preview)
**Standard:** Loren AI HCP — premium, enterprise-grade, conversion-engineered.

---

## TL;DR

The baseline build covers the structural essentials — hero, services grid, dual lead forms, testimonials, service areas, TCPA opt-in. It's a competent **brochure site**. It is **not** an HCP.

To meet the Loren AI premium HCP standard, 17 conversion and brand levers must be added or rebuilt. Below is the full gap list, ordered by revenue impact.

---

## A. Conversion-blocking gaps (HIGH revenue impact)

### A1. No AI voice receptionist hook
- **Gap:** Site lists a phone number. No "talk to our AI 24/7" mechanism, no inline "call us now" widget, no SMS catch.
- **Why it matters:** Remodeling leads convert 7× higher when contacted within 60 seconds. The current site has a 1-business-day promise that loses leads.
- **Fix:** Embed Retell voice agent widget + GHL chat. Hero CTA becomes "Get an instant estimate — by AI."

### A2. No live chat widget
- **Gap:** Zero chat surface.
- **Fix:** GHL native chat or Loren chat with NEPQ qualification flow.

### A3. Empty project gallery
- **Gap:** "RECENT WORK" → "PROJECT GALLERY" → "VIEW ALL →" but no images.
- **Why it matters:** Before/afters are the #1 trust driver in remodeling. Empty gallery = abandoned page.
- **Fix:** Mandatory — 8–12 real before/after pairs from completed jobs. Pull from `@handymanprofl` Instagram.

### A4. No video / VSL
- **Gap:** No founder video, no walk-through video, no testimonial video.
- **Fix:** Sub-90-second Moses VSL — name his promise, show his face, walk through one finished kitchen.

### A5. Founder (Moses) is invisible
- **Gap:** Reviews mention "Moses and his team" — but Moses doesn't appear on the site. No "About" or "Meet the team" section.
- **Why it matters:** Personal trust is the only moat against the lowest-bidder spiral. Killing it costs 20%+ on close rate.
- **Fix:** Add "Meet Moses" section with photo, 2-sentence story, and one line about why he started the company.

### A6. No FAQ / objection-handling section
- **Gap:** Common remodeling fears unaddressed: permits, timelines, warranty, change orders, cleanup, financing.
- **Fix:** 10-question FAQ — see `docs/01_brand_strategy.md` § Emotional Buying Drivers.

### A7. No financing / payment plan
- **Gap:** High-ticket vertical with zero payment flexibility shown. $4,999 and $7,999 are "limited-time specials" with no easy yes.
- **Fix:** Stripe-linked "as low as $XX/month" badge on each offer. Hearth, Acorn Finance, or Wisetack integration.

### A8. No process timeline
- **Gap:** What happens after I submit the form? Silence.
- **Fix:** 4-step animated process: (1) Submit, (2) AI estimate call within 60s, (3) On-site walk-through, (4) Fixed-price quote.

### A9. No warranty/guarantee section
- **Gap:** Massive trust lever missing in a category dominated by "fly-by-night" fears.
- **Fix:** Dedicated band: "12-month workmanship warranty. Fixed price or we eat the difference."

---

## B. Brand & polish gaps (MEDIUM impact)

### B1. "Powered by LOREN AI" footer missing
- **Brand standard violation** (per CLAUDE.md). Must be in global footer.

### B2. Lovable badge still visible
- **Visual brand bleed.** Hide in Lovable project settings after custom domain verifies.

### B3. Testimonials hard-coded
- **Gap:** Three static quotes. No source link, no date, no photo, no Google star count.
- **Fix:** Google Places API live pull, with star count and review badge.

### B4. Generic OG image
- **Gap:** Default Lovable / GPT-engineer placeholder.
- **Fix:** Custom 1200×630 with Moses + tagline + brand color.

### B5. No mobile sticky call bar
- **Gap:** On mobile, the phone CTA disappears below the fold. Tap-to-call should be persistent.
- **Fix:** Sticky bottom bar: "📞 Call Now • 💬 Text Us • 📅 Book Free Estimate".

### B6. Commercial vertical buried
- **Gap:** "Residential & commercial" mentioned once in fine print at bottom CTA.
- **Fix:** Dedicated commercial CTA card for property managers — different lifecycle, different deal size.

### B7. No service-area landing pages for SEO
- **Gap:** Weston / Pembroke Pines / Davie listed as cards on home, but no `/weston-kitchen-remodel`, `/pembroke-pines-bathroom-remodel` deep pages for local SEO.
- **Fix:** Auto-generate 9 service × 3 city = 27 landing pages from a single template.

---

## C. Technical / hygiene gaps (LOW but cheap to fix)

### C1. URL still on preview subdomain
- **Status:** DNS now provisioned at `handymanpro.ai-loren.com`. Lovable custom domain TXT verify pending.

### C2. No schema.org markup
- **Gap:** No `LocalBusiness`, `Service`, `Review`, or `FAQPage` JSON-LD.
- **Fix:** Inject schema in `<head>` for Google rich results.

### C3. No analytics / conversion tracking
- **Gap:** No GA4, no GHL form tracking pixel, no Meta pixel visible.
- **Fix:** GA4 + Meta + GHL pixel + Microsoft Clarity heatmap.

---

## What stays

The baseline gets these right:
- TCPA opt-in language is correct
- Service taxonomy is complete and well-labeled
- Hero hierarchy (location → headline → subhead → dual CTA) is clean
- Two hero offers ($4,999 / $7,999) are prominent and concrete
- Service-area cards exist (just need SEO depth pages behind them)

---

## Redesigned site

A full premium rebuild lives at [`frontend/index.html`](../frontend/index.html). It uses 21st.dev / Magic UI / Aceternity-grade component patterns (bento, animated beam, marquee, sticky CTA, number ticker, hover cards) so it does not feel like AI slop. Dark luxury aesthetic, ready for Lovable import.

---

## Sources

- Live site DOM (Chrome-rendered, 2026-05-24): `https://preview--steelbuild-easy.lovable.app/`
- Existing brand site: `https://handymanprofl.com`
- Reviews intel: Angi, Thumbtack, Yelp, Houzz, Google Maps
