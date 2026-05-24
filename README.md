# HandyMan Pro × Loren AI HCP

> **LIVE at [handymanpro.ai-loren.com](https://handymanpro.ai-loren.com)** — South Florida's full-service remodeling team, operated by an AI front desk.

[![Powered by LOREN AI](https://img.shields.io/badge/Powered%20by-LOREN%20AI-FF5E5B?style=for-the-badge)](https://ai-loren.com)
[![Production](https://img.shields.io/badge/PROD-handymanpro.ai--loren.com-3FB68C?style=for-the-badge)](https://handymanpro.ai-loren.com)
[![SSL](https://img.shields.io/badge/SSL-Enforce%20HTTPS-E8B257?style=for-the-badge)]()

---

## Live URLs

| URL | Status |
|---|---|
| **`https://handymanpro.ai-loren.com/`** | **PRODUCTION** — HTTP 200, SSL active, Enforce HTTPS ON |
| `https://michaelmakabi.github.io/handymanpro-ai-hcp/` | 301 redirects to custom domain |
| `https://handymanprofl.com/` | Legacy brand site (existing) |

**Hosting:** GitHub Pages (auto-deploys on push to `main`). DNS A record `185.199.108.153`.

---

## What is HandyMan Pro?

HandyMan Pro LLC — South Florida remodeling firm (Weston, Pembroke Pines, Davie) led by Moses. Kitchens, bathrooms, flooring, drywall, paint, popcorn ceiling, water damage, closets, full-home renovations.

Hero offers: **$4,999 tub/shower** · **$7,999 guest bath turn-key**. Phone: **(754) 247-6766**.

---

## Repository structure

```
handymanpro-ai-hcp/
├── README.md
├── index.html                   ← LIVE site (served by GitHub Pages at handymanpro.ai-loren.com)
├── CNAME                        ← handymanpro.ai-loren.com
├── .nojekyll
├── .github/workflows/
│   └── deploy-pages.yml         ← auto-deploy on push
├── .env.example
├── .gitignore
├── frontend/index.html          ← legacy stub, meta-refresh → /index.html
├── docs/                        ← strategy + implementation
│   ├── 00_INDEX.md
│   ├── 01_brand_strategy.md
│   ├── 02_sales_script_nepq.md
│   ├── 03_ai_agent_spec.md
│   ├── 04_basecamp_plan.md
│   ├── 05_automation_map.md
│   ├── 06_site_audit.md
│   ├── 08_system_architecture.md
│   └── 09_client_presentation.md
├── agents/
│   └── retell_handymanpro_receptionist.json  ← agent_id pinned, voice pinned
├── prompts/
│   └── nepq_voice_agent.md
├── branding/brand_guide.md
└── sops/lovable_subdomain_deploy.md
```

---

## Maya — voice receptionist

- **Agent created:** `agent_cb542686e718d0b43f489be30f` in Retell workspace `mtip`
- **Voice:** `11labs-Andrea` (ElevenLabs, Mexican accent, female, middle-aged) — preview: [.mp3](https://retell-utils-public.s3.us-west-2.amazonaws.com/11labs-Andrea.mp3)
- **LLM (current):** `llm_99cb6f0514d3ef9e950842791ccb` (borrowed from Loren Seller AI)
- **LLM swap pending:** create dedicated LLM in Retell dashboard with `prompts/nepq_voice_agent.md`, then point this agent at it. NOT production-ready until that swap.

---

## Responsive design (verified)

| Viewport | What you see |
|---|---|
| **Mobile** (< 600px) | Single column, sticky bottom nav (📞 Call · 💬 Text · 📅 Book), safe-area inset for iPhone notch, 16px form inputs (no iOS zoom) |
| **Tablet** (768–1023px) | Hero stacks, 2-col services bento, 2-col process steps, AI card max-width 520px centered |
| **Desktop** (1024px+) | 2-col hero (text + AI card), 3-col services bento, 4-col process timeline, full inline nav |

44px+ touch targets, `aria-label`s, autocomplete attributes, `prefers-reduced-motion` respected.

---

## Deployment status

- [x] GitHub repo provisioned
- [x] Premium single-file site (mobile/tablet/desktop responsive)
- [x] Brand strategy, NEPQ script, AI agent spec, GHL automation map, system architecture
- [x] Basecamp plan (paste-ready)
- [x] GitHub Pages auto-deploy workflow
- [x] DNS switched to GitHub Pages (`185.199.108.153`)
- [x] CNAME + Custom domain registered on GitHub Pages
- [x] **SSL active + Enforce HTTPS ON**
- [x] **PRODUCTION LIVE at `https://handymanpro.ai-loren.com/`**
- [x] Retell agent created with Andrea voice
- [ ] Retell LLM swap to Maya-dedicated LLM (one Retell dashboard task)
- [ ] Moses founder video + before/after photos for gallery (content shoot, not deployable)
- [ ] GHL provisioning (handled by co-worker per prior session)

---

## Quick start — operators

1. [`docs/01_brand_strategy.md`](./docs/01_brand_strategy.md) — positioning
2. [`docs/06_site_audit.md`](./docs/06_site_audit.md) — what was broken on the original Lovable build
3. [`docs/04_basecamp_plan.md`](./docs/04_basecamp_plan.md) — execution order
4. [`docs/08_system_architecture.md`](./docs/08_system_architecture.md) — full stack
5. [`.env.example`](./.env.example) — env inventory

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
