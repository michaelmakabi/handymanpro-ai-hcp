# System Architecture

## Stack overview

```
                  ┌────────────────────────────────────────┐
                  │       HOMEOWNER / PROPERTY MANAGER     │
                  └───┬───────────┬────────────┬───────────┘
                      │           │            │
              voice   │       web │        sms │
                      ▼           ▼            ▼
         ┌──────────────┐  ┌─────────────┐  ┌───────────────┐
         │  Retell AI   │  │ Lovable Site│  │ GHL SMS Inbox │
         │   (Maya)     │  │ handymanpro │  │ (754) 247-6766│
         │ +ElevenLabs  │  │ .ai-loren   │  │               │
         └──────┬───────┘  └──────┬──────┘  └───────┬───────┘
                │ webhook         │ form              │
                │                 │ submit            │
                ▼                 ▼                   ▼
         ┌──────────────────────────────────────────────────┐
         │           GoHighLevel — HandyMan Pro             │
         │  Pipelines · Tags · Custom Fields · Workflows    │
         └───┬────────────┬─────────────┬────────────┬──────┘
             │            │             │            │
             ▼            ▼             ▼            ▼
       ┌─────────┐  ┌─────────┐  ┌──────────┐  ┌──────────┐
       │ Twilio  │  │ Stripe  │  │ Google   │  │  Email   │
       │   SMS   │  │ Deposit │  │ Calendar │  │ (Mailgun)│
       └─────────┘  └─────────┘  └──────────┘  └──────────┘
                │
                ▼
         ┌──────────────┐
         │   Moses /    │
         │   Crew SMS   │
         │   alerts     │
         └──────────────┘
```

## Layer-by-layer

### 1. Capture layer

- **Lovable site** (handymanpro.ai-loren.com) — primary web capture. Form posts directly to GHL webhook.
- **Retell AI** (Maya) — voice capture. Spawned on inbound to (754) 247-6766. Webhooks fire on call-end with structured payload.
- **GHL inbound SMS** — direct SMS to brand number; routes through GHL inbox.
- **Chat widget** (GHL native, embedded on site) — text capture.

### 2. Brain layer

- **Anthropic Claude Sonnet 4.6** powers Maya's reasoning via Retell.
- Knowledge base loaded into Retell context: `docs/01_brand_strategy.md`, `docs/02_sales_script_nepq.md`, `docs/03_ai_agent_spec.md`, FAQ snippets, live calendar availability.

### 3. CRM layer

- **GoHighLevel sub-account** is the system of record for every contact, conversation, pipeline movement, tag, and custom field. Single source of truth.

### 4. Automation layer

- **GHL workflows** (W1–W8 in `docs/05_automation_map.md`) handle: lead welcome, missed-call text-back, estimate reminders, quote follow-up cadence, review automation, 180-day reactivation, emergency paging, deposit follow-up.

### 5. Transaction layer

- **Stripe** — products for hero offers ($4,999 / $7,999), payment links per quote, deposit collection.
- **GHL invoicing** — final invoices on completion.

### 6. Notification layer

- **Twilio** (via GHL) — outbound SMS to homeowners + internal alerts to Moses
- **Mailgun** (via GHL) — transactional emails
- **Moses cell** — warm transfer destination + emergency page

### 7. Observability layer

- **GA4** — site analytics
- **Meta Pixel** — paid attribution
- **Microsoft Clarity** — heatmaps + session replay
- **GHL native reports** — pipeline metrics
- **Retell dashboard** — call analytics
- **Internal 8 AM daily email** — see `docs/05_automation_map.md` § Daily metrics

## Data contracts

### Lovable form → GHL webhook payload

```json
{
  "first_name": "Maria",
  "last_name": "Sanchez",
  "phone": "+19545551234",
  "email": "maria@example.com",
  "service_category": "Bathroom Remodeling",
  "address": "1840 NW 142nd Ave, Pembroke Pines, FL 33028",
  "message": "Looking to redo the guest bath",
  "tcpa_consent": true,
  "source": "web-form",
  "page_url": "https://handymanpro.ai-loren.com/",
  "utm": { "source": "google-lsa", "medium": "cpc", "campaign": "guest-bath-package" }
}
```

### Retell call-end webhook → GHL

```json
{
  "call_id": "ret_abc123",
  "duration_sec": 258,
  "from_number": "+19545551234",
  "language_detected": "en",
  "intent": "estimate_request",
  "extracted": {
    "first_name": "Maria",
    "service": "Bathroom Remodeling",
    "address": "1840 NW 142nd Ave, Pembroke Pines, FL 33028",
    "timeline": "this_month",
    "budget_posture": "5-15k"
  },
  "appointment_booked": {
    "calendar": "estimate_visit",
    "datetime_iso": "2026-05-29T14:00:00-04:00"
  },
  "summary": "Maria wants guest bath remodel...",
  "tags_to_apply": ["svc:bath", "geo:pembroke-pines", "src:ai-inbound", "urg:this-month", "bud:5-15k", "prop:primary"]
}
```

## Failure modes & fallbacks

| Failure | Detection | Fallback |
|---|---|---|
| Retell offline | Health-check webhook | Twilio routes to Moses cell + auto SMS text-back |
| ElevenLabs latency spike | Latency metric > 1500ms | Switch to Retell native voice |
| GHL webhook reject | Workflow error log | Internal email alert + Zapier mirror |
| Site form fails | Cloudflare error page | Static fallback page with phone + SMS |
| Stripe down | Stripe status API | Email confirmation, deposit collected on-site |

## Env variable matrix

See `.env.example` at repo root.

## Deployment surfaces

| Component | Host | Domain |
|---|---|---|
| Marketing site | Lovable | handymanpro.ai-loren.com |
| CRM | GoHighLevel | (sub-account internal) |
| Voice agent | Retell | (754) 247-6766 |
| Existing brochure site | (current host) | handymanprofl.com — redirect to subdomain post-launch |
| GitHub source of truth | GitHub | github.com/michaelmakabi/handymanpro-ai-hcp |
