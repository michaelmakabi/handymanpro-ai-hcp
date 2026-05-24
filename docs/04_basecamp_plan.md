# Basecamp Project Plan — HandyMan Pro × Loren AI HCP

> **Note:** This Cowork session does not currently have a Basecamp MCP connector. This document is **paste-ready** — your co-worker can create the Basecamp project and paste each to-do list below as-is. Tasks intentionally **unassigned**; team assignment happens in-product.

**Project name in Basecamp:** `HandyMan Pro × Loren AI HCP — Launch`

---

## Milestones (4)

| # | Milestone | Target |
|---|---|---|
| 1 | Foundation locked | T+3 days |
| 2 | AI + automation live | T+10 days |
| 3 | Site live on custom domain | T+14 days |
| 4 | First 100 production dials | T+21 days |

---

## To-do list 1 — Brand & strategy

- [x] Brand strategy document drafted (`docs/01_brand_strategy.md`)
- [x] Brand guide drafted (`branding/brand_guide.md`)
- [x] Hero offer stack defined ($4,999 tub/shower, $7,999 guest bath)
- [ ] Moses-approval on positioning + offer stack
- [ ] Lock final brand color palette (review against logo)
- [ ] Approve "Powered by LOREN AI" footer placement

## To-do list 2 — Site redesign (Lovable)

- [x] Site audit completed (`docs/06_site_audit.md`)
- [x] 21st.dev-curated single-file HTML written (`frontend/index.html`)
- [ ] Import new HTML into Lovable project
- [ ] Verify mobile responsive across iPhone + Android
- [ ] Verify form posts to GHL webhook
- [ ] Add real before/after photo gallery (8–12 pairs from Instagram)
- [ ] Replace generic OG image with custom 1200×630
- [ ] Inject `LocalBusiness` + `Service` + `Review` + `FAQPage` JSON-LD
- [ ] Install GA4, Meta pixel, Microsoft Clarity, GHL form pixel

## To-do list 3 — Subdomain + custom domain

- [x] GoDaddy A record created (`handymanpro.ai-loren.com → 185.158.133.1`)
- [ ] Add custom domain in Lovable project settings
- [ ] Complete TXT verification if Lovable requests
- [ ] Confirm SSL provisioned and live
- [ ] Hide Lovable badge

## To-do list 4 — GoHighLevel CRM

- [ ] Provision GHL sub-account `HandyMan Pro LLC`
- [ ] Create pipeline `Remodel — Inbound` with stages: New Lead → Qualified → Estimate Scheduled → Quote Sent → Signed → Job Active → Complete → Review Requested → Won/Lost
- [ ] Create pipeline `Commercial / PM — Outbound`
- [ ] Build tag taxonomy (see `docs/05_automation_map.md`)
- [ ] Build custom fields: service_category, property_type, urgency, budget_posture, lead_source
- [ ] Create calendar `estimate_visit` (Moses availability)
- [ ] Create calendar `emergency_callback`

## To-do list 5 — Automations & workflows

- [ ] Build workflow: New Lead → SMS + email confirmation + assign to pipeline
- [ ] Build workflow: Missed-call → text-back within 60s
- [ ] Build workflow: Estimate booked → 24h reminder + day-of reminder
- [ ] Build workflow: Quote sent → 1d / 3d / 7d / 14d follow-up cadence
- [ ] Build workflow: Job complete → review request automation (Google + Facebook)
- [ ] Build workflow: 180-day dormant lead → reactivation SMS
- [ ] Build workflow: Emergency intent → page Moses (SMS + call)

## To-do list 6 — AI voice receptionist (Retell)

- [x] Agent spec written (`docs/03_ai_agent_spec.md`)
- [x] System prompt written (`prompts/nepq_voice_agent.md`)
- [x] Retell config JSON drafted (`agents/retell_handymanpro_receptionist.json`)
- [ ] Select + clone ElevenLabs voice (warm female, EN + ES)
- [ ] Plug Retell webhook into GHL contact-create + appointment-book endpoints
- [ ] Port (754) 247-6766 or assign forwarding into Retell
- [ ] QA: 20 mock calls covering 7 intents
- [ ] Stage rollout: AI handles first ring → human fallback after 4 rings

## To-do list 7 — Chat widget

- [ ] Enable GHL native chat
- [ ] Train chat with FAQ + offer stack
- [ ] Embed widget snippet into `frontend/index.html` footer

## To-do list 8 — Payments & deposits (Stripe)

- [ ] Create Stripe product: "Tub or Shower Remodel — $4,999"
- [ ] Create Stripe product: "Guest Bathroom Package — $7,999"
- [ ] Create Stripe payment link for each (deposit % TBD with Moses)
- [ ] Wire deposit link into post-signed-contract workflow

## To-do list 9 — Content & assets

- [ ] Shoot Moses founder video (sub-90s, single take, daylight)
- [ ] Collect 8–12 before/after pairs from completed jobs
- [ ] Write 10 FAQ entries (permits, timelines, warranty, change orders, financing, cleanup, areas, emergencies, languages, commercial)
- [ ] Generate 9 service × 3 city SEO landing pages (27 total)
- [ ] Custom OG image (Canva or Figma)

## To-do list 10 — Outbound (secondary ICP — property managers)

- [ ] Build list of 200 South Florida PM companies
- [ ] Enrich with phone, email, property count
- [ ] Load into GHL Smart Lists
- [ ] Configure outbound Retell agent (separate from inbound Maya)
- [ ] Run first 100 dials with NEPQ outbound script

## To-do list 11 — QA & launch

- [ ] Full mobile + desktop site walkthrough
- [ ] Lead form → GHL contact created ✓
- [ ] AI call → GHL contact created + calendar booked ✓
- [ ] Missed-call text-back fires within 60s ✓
- [ ] Review automation pulls live Google reviews ✓
- [ ] Stripe deposit link works on test card ✓
- [ ] All footers show "Powered by LOREN AI"
- [ ] Lovable badge hidden
- [ ] All env variables set in production
- [ ] Run final "fresh-eyes" audit (Mike + Moses + Loren)

## To-do list 12 — Documentation & handoff

- [x] README written
- [x] All 8 strategy docs written
- [x] Lovable deploy SOP written
- [ ] Record Loom walkthrough of GHL automations (for Sanjeev/Shalu)
- [ ] Record Loom walkthrough of Retell agent (for ops team)
- [ ] Save final state to Makabi Memory under `project-handymanpro-hcp`

---

## Hill chart targets

- **Figured out:** Brand, positioning, offer stack, AI agent design, automation map, site redesign.
- **Making it happen (this sprint):** Lovable custom domain, GHL provisioning, Retell deploy, content shoot.
- **Done after this sprint:** First 100 production dials + first 10 booked estimates from AI inbound.
