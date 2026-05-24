# HandyMan Pro × Loren AI HCP

> **South Florida's full-service remodeling team — operated by an AI.**
> Complete Loren AI Hyper-Conversion Platform implementation for HandyMan Pro LLC.

[![Powered by LOREN AI](https://img.shields.io/badge/Powered%20by-LOREN%20AI-FF5E5B?style=for-the-badge)](https://ai-loren.com)
[![Live preview](https://img.shields.io/badge/preview-github%20pages-0A84FF?style=for-the-badge)](https://michaelmakabi.github.io/handymanpro-ai-hcp/)
[![Custom domain](https://img.shields.io/badge/domain-handymanpro.ai--loren.com-E8B257?style=for-the-badge)](https://handymanpro.ai-loren.com)

---

## Live URLs

| URL | What it is | Status |
|---|---|---|
| `https://michaelmakabi.github.io/handymanpro-ai-hcp/` | GitHub Pages live preview — instantly viewable | Auto-deploys on push to `main` once Pages is enabled (one-time toggle: repo → Settings → Pages → Source: **GitHub Actions**) |
| `https://handymanpro.ai-loren.com/` | Production custom domain — DNS provisioned, currently points to Lovable edge | Awaiting Lovable custom-domain TXT verify, OR DNS switch to GitHub Pages |
| `https://handymanprofl.com/` | Legacy brand site | Live (existing) |
| `https://preview--steelbuild-easy.lovable.app/` | Original Lovable preview (auto-generated slug) | Live (existing, pre-redesign) |

---

## What is HandyMan Pro?

HandyMan Pro LLC is a South Florida remodeling firm serving Weston, Pembroke Pines, and Davie — led by Moses and a handpicked crew. Kitchens, bathrooms, flooring, drywall, painting, popcorn ceiling removal, water damage restoration, walk-in closets, and full-home renovations.

Hero offers: **$4,999 tub/shower remodels** and **$7,999 guest bathroom packages**.

---

## Repository structure

```
handymanpro-ai-hcp/
├── README.md
├── index.html                   ← CANONICAL site (served by GitHub Pages)
├── .nojekyll
├── .github/workflows/
│   └── deploy-pages.yml         ← auto-deploy site to GH Pages on push
├── .env.example
├── .gitignore
│
├── frontend/
│   └── index.html               ← meta-refresh stub → /index.html
│
├── docs/
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
├── agents/
│   └── retell_handymanpro_receptionist.json  ← voice pinned: 11labs-Andrea
│
├── prompts/
│   └── nepq_voice_agent.md
│
├── branding/
│   └── brand_guide.md
│
└── sops/
    └── lovable_subdomain_deploy.md
```

---

## Maya — voice receptionist

- **Voice pinned:** `11labs-Andrea` (ElevenLabs-backed, Mexican accent, female, middle-aged)
- **Rationale:** Mexican Spanish is the dominant accent in South Florida bilingual markets. Middle-aged conveys experience and trust — on brand for HandyMan Pro.
- **Preview:** https://retell-utils-public.s3.us-west-2.amazonaws.com/11labs-Andrea.mp3
- **Config:** [`agents/retell_handymanpro_receptionist.json`](./agents/retell_handymanpro_receptionist.json)
- **Status:** Voice + config ready. Agent creation in Retell needs a one-time manual step — create the LLM in the Retell dashboard (30 sec), grab its `llm_id`, then rerun `retell_create_agent` with that id.

---

## Responsive design

The site is built mobile-first and explicitly tested across:

| Viewport | Breakpoint | What changes |
|---|---|---|
| **Mobile** (< 600px) | base | 1-column everything, sticky bottom nav bar (Call / Text / Book), `safe-area-inset-bottom` for iPhone notch, 16px form inputs (no iOS zoom-on-focus) |
| **Mobile-large** (600–767px) | `@media (min-width: 600px)` | 2-col offers form, 3-col gallery, larger paddings |
| **Tablet portrait** (768–1023px) | `@media (min-width: 768px) and (max-width: 1023px)` | Explicit polish — hero stacks vertically, AI card centers + max-width, 2-col services bento and process steps |
| **Desktop** (1024px+) | `@media (min-width: 1024px)` | 2-col hero (text + AI card), 3-col services bento, 4-col process timeline, full inline nav links visible |

**Accessibility:** 44px+ touch targets everywhere, `aria-label`s on all interactive elements, `prefers-reduced-motion` respected, autocomplete attributes on every form field.

---

## Deployment status

- [x] GitHub repo provisioned
- [x] GoDaddy A record `handymanpro.ai-loren.com → 185.158.133.1`
- [x] Brand strategy locked
- [x] NEPQ sales script v1
- [x] AI voice agent spec + Retell config (voice pinned)
- [x] Site audit (17-point gap analysis)
- [x] Curated single-file site (root `/index.html`, responsive across mobile/tablet/desktop)
- [x] GitHub Pages auto-deploy workflow
- [x] Basecamp project plan (paste-ready)
- [x] GHL automation map (your co-worker handles GHL provisioning per prior session)
- [ ] **Enable GitHub Pages** — repo Settings → Pages → Source: **GitHub Actions** *(one-time, 10 sec)*
- [ ] **Choose hosting** — keep `handymanpro.ai-loren.com` on Lovable (import `/index.html` into the Lovable project) **OR** switch DNS to point at GitHub Pages
- [ ] Create the Retell LLM in the dashboard + rerun `retell_create_agent`
- [ ] Shoot Moses founder video + collect 8–12 before/after photo pairs from `@handymanprofl`

---

## Quick start — operators

1. Read [`docs/01_brand_strategy.md`](./docs/01_brand_strategy.md) for positioning
2. Read [`docs/06_site_audit.md`](./docs/06_site_audit.md) for what was broken on the original Lovable build
3. Read [`docs/04_basecamp_plan.md`](./docs/04_basecamp_plan.md) for execution order
4. Read [`docs/08_system_architecture.md`](./docs/08_system_architecture.md) for the full stack
5. Provision env from [`.env.example`](./.env.example)

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
