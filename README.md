# HandyMan Pro × Loren AI HCP

> **South Florida's full-service remodeling team — operated by an AI.**
> Complete Loren AI Hyper-Conversion Platform implementation for HandyMan Pro LLC.

[![Powered by LOREN AI](https://img.shields.io/badge/Powered%20by-LOREN%20AI-FF5E5B?style=for-the-badge)](https://ai-loren.com)
[![Live Site](https://img.shields.io/badge/site-handymanpro.ai--loren.com-0A84FF?style=for-the-badge)](https://handymanpro.ai-loren.com)
[![Status](https://img.shields.io/badge/status-pre--launch-yellow?style=for-the-badge)]()

---

## What is HandyMan Pro?

HandyMan Pro LLC is a South Florida remodeling firm serving Weston, Pembroke Pines, and Davie — led by Moses and a handpicked crew. Kitchens, bathrooms, flooring, drywall, painting, popcorn ceiling removal, water damage restoration, walk-in closets, and full-home renovations.

Hero offers: **$4,999 tub/shower remodels** and **$7,999 guest bathroom packages**.

This repository contains the **complete Loren AI HCP implementation** — marketing site, brand strategy, NEPQ sales script, AI voice agent spec, GoHighLevel automation map, Basecamp project plan, and system architecture.

---

## Repository Structure

```
handymanpro-ai-hcp/
├── README.md                    ← you are here
├── .env.example
├── .gitignore
│
├── frontend/                    ← Lovable site source
│   └── index.html               ← 21st.dev-curated single-file site → handymanpro.ai-loren.com
│
├── docs/                        ← strategy + implementation docs
│   ├── 00_INDEX.md
│   ├── 01_brand_strategy.md
│   ├── 02_sales_script_nepq.md
│   ├── 03_ai_agent_spec.md
│   ├── 04_basecamp_plan.md
│   ├── 05_automation_map.md
│   ├── 06_site_audit.md
│   ├── 08_system_architecture.md
│   └── 09_client_presentation.md
│
├── agents/                      ← AI agent configurations
│   └── retell_handymanpro_receptionist.json
│
├── prompts/                     ← prompt library
│   └── nepq_voice_agent.md
│
├── branding/
│   └── brand_guide.md
│
└── sops/
    └── lovable_subdomain_deploy.md
```

---

## Quick Links

- Marketing site: [handymanpro.ai-loren.com](https://handymanpro.ai-loren.com)
- Existing site: [handymanprofl.com](https://handymanprofl.com)
- Phone: **(754) 247-6766**
- Instagram: [@handymanprofl](https://instagram.com/handymanprofl)
- Strategy index: [docs/00_INDEX.md](./docs/00_INDEX.md)
- Site audit: [docs/06_site_audit.md](./docs/06_site_audit.md)
- NEPQ script: [docs/02_sales_script_nepq.md](./docs/02_sales_script_nepq.md)
- System architecture: [docs/08_system_architecture.md](./docs/08_system_architecture.md)

---

## The Unique Mechanism

**Same-day, single-crew, fixed-price remodeling — captured 24/7 by an AI receptionist that never sleeps.**

Three competitive moats fused into one:

1. **One crew, one project manager** — no subs, no finger-pointing, no schedule slip
2. **Fixed-price quotes** — no surprise change orders, no "scope creep" upcharges
3. **AI front desk** — phone, SMS, web chat, and missed-call text-back operate around the clock so no homeowner who's ready-to-buy ever hits voicemail

In a market where 73% of remodeling leads die from slow callback, HandyMan Pro responds in under 60 seconds — automated, branded, qualified, and booked.

---

## Tech Stack

| Layer | Tool |
|---|---|
| Existing site | handymanprofl.com |
| New marketing site | Lovable on `handymanpro.ai-loren.com` |
| CRM + automations | GoHighLevel (sub-account) |
| Voice AI receptionist | Retell AI |
| TTS voice | ElevenLabs |
| Chat widget | GoHighLevel native + Loren chat |
| LLM brain | Claude Sonnet 4.6 |
| Payments / deposits | Stripe |
| SMS / telephony | Twilio (via GHL) |
| Domain | GoDaddy → `ai-loren.com` subdomain |
| Component library | 21st.dev / Magic UI / Aceternity |

---

## Deployment Status

- [x] GitHub repo provisioned
- [x] GoDaddy A record `handymanpro.ai-loren.com → 185.158.133.1`
- [x] Brand strategy locked
- [x] NEPQ sales script v1
- [x] AI voice agent spec + Retell config
- [x] Site audit (gap analysis)
- [x] Curated 21st.dev redesign (single-file HTML)
- [x] Basecamp project plan (paste-ready)
- [x] GHL automation map
- [ ] Lovable custom domain TXT verification *(human action)*
- [ ] Lovable badge hidden *(human action)*
- [ ] GHL sub-account provisioned *(human action)*
- [ ] Retell agent deployed to production *(human action)*
- [ ] Stripe products for $4,999 / $7,999 offers *(human action)*
- [ ] First 100 dials live

---

## Quick Start — Internal

1. Read [`docs/01_brand_strategy.md`](./docs/01_brand_strategy.md) for positioning
2. Read [`docs/06_site_audit.md`](./docs/06_site_audit.md) for what's wrong with the Lovable site
3. Read [`docs/04_basecamp_plan.md`](./docs/04_basecamp_plan.md) for execution order
4. Read [`docs/08_system_architecture.md`](./docs/08_system_architecture.md) for the full stack
5. Provision env from [`.env.example`](./.env.example)
6. Follow [`sops/lovable_subdomain_deploy.md`](./sops/lovable_subdomain_deploy.md) to finish the deploy

---

## Team

| Role | Person |
|---|---|
| Project lead | Michael Makabi |
| HandyMan Pro principal | Moses |
| BRiX CEO | Julio Caceres |
| Loren AI ops | Sanjeev, Shalu |

---

**Powered by LOREN AI.**
