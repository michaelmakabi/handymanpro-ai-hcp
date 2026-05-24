# GoHighLevel Automation Map

## Sub-account structure

**Sub-account name:** `HandyMan Pro LLC`
**Owner:** Master Makabi (Loren AI agency)
**Operator:** Moses
**Timezone:** America/New_York
**Default phone:** (754) 247-6766

---

## Pipelines

### Pipeline 1 — `Remodel — Inbound` (residential)

| Stage | Trigger to enter | Trigger to exit | SLA |
|---|---|---|---|
| 1. New Lead | Form submit OR AI call OR missed-call text-back | Maya/Moses qualifies | < 60 sec |
| 2. Qualified | NEPQ pass + intent confirmed | Estimate booked | < 2 hr |
| 3. Estimate Scheduled | Calendar event created | Visit completed | < 5 days |
| 4. Quote Sent | Moses sends written fixed-price quote | Signed OR lost | < 24 hr post-visit |
| 5. Signed | Contract signed + deposit paid | Job starts | < 48 hr |
| 6. Job Active | Crew on site | Job complete | per project |
| 7. Complete | Final walk-through done | Review requested | same day |
| 8. Review Requested | Review automation fired | Won (review received) | 7-day window |
| 9. Won | Review received OR 7 days elapsed | (closed) | — |
| 10. Lost | Explicit no OR 30-day silence | (closed) | — |

### Pipeline 2 — `Commercial / PM — Outbound`

| Stage |
|---|
| Cold List → Dialed → Discovery Booked → Proposal Sent → Negotiating → Signed → Active → Renewal |

---

## Tags (taxonomy)

**Service tags:**
`svc:kitchen` · `svc:bath` · `svc:flooring` · `svc:drywall` · `svc:paint` · `svc:popcorn` · `svc:water-damage` · `svc:closet` · `svc:full-home`

**Source tags:**
`src:ai-inbound` · `src:web-form` · `src:missed-call` · `src:chat` · `src:google-lsa` · `src:meta-ads` · `src:referral` · `src:outbound-pm` · `src:instagram`

**Geo tags:**
`geo:weston` · `geo:pembroke-pines` · `geo:davie` · `geo:other-sofla`

**Urgency tags:**
`urg:emergency` · `urg:this-week` · `urg:this-month` · `urg:this-quarter` · `urg:exploring`

**Budget tags:**
`bud:under-5k` · `bud:5-15k` · `bud:15-40k` · `bud:40k-plus` · `bud:unknown`

**Property type tags:**
`prop:primary` · `prop:rental` · `prop:commercial`

**Lifecycle tags:**
`life:past-customer` · `life:cold-reactivation` · `life:vip` · `life:do-not-contact`

---

## Custom fields

| Field | Type | Source |
|---|---|---|
| service_category | dropdown | Form + Maya |
| property_type | dropdown | Form + Maya |
| timeline_urgency | dropdown | Maya NEPQ |
| budget_posture | dropdown | Maya NEPQ |
| photos_received | boolean | SMS attachment |
| moses_warm_transfer | boolean | Retell escalation |
| estimate_visit_dt | datetime | GHL calendar |
| quote_sent_dt | datetime | Moses manual |
| signed_dt | datetime | Stripe webhook |
| review_link_sent | boolean | Review workflow |

---

## Workflows

### W1 — New Lead Welcome (any source)

**Trigger:** Contact created with any `src:*` tag.

1. Send SMS: "Hey [first name] — got your request. Maya from HandyMan Pro will reach out within the hour. Reply STOP to opt out."
2. Send email: brand-styled confirmation with offer reminder
3. Assign to `Remodel — Inbound` pipeline, stage `New Lead`
4. Notify Moses via internal SMS: `New lead: [name] / [service] / [city]`

### W2 — Missed-Call Text-Back

**Trigger:** Inbound call to (754) 247-6766 ends with no human answer (Retell handles first; this is the **Retell-down** fallback).

1. Within 60 seconds, send SMS: see `docs/02_sales_script_nepq.md` § C
2. Tag `src:missed-call`
3. Open contact, stage `New Lead`

### W3 — Estimate Reminders

**Trigger:** GHL calendar event created on `estimate_visit`.

- 24h before: SMS reminder with address + Moses photo
- 2h before: SMS reminder + "reply R to reschedule"
- T+15 min after end: SMS "How'd it go? Reply 1 = great / 2 = need follow-up / 3 = not for us"

### W4 — Quote Follow-up Cadence

**Trigger:** `quote_sent_dt` populated.

- Day 1 SMS: see `docs/02_sales_script_nepq.md` § E
- Day 3 email: gallery + neighborhood reviews
- Day 7 SMS
- Day 14 voice call task → Moses
- Day 30 email: "closing file unless..."
- Day 31: move to `Lost` if no response

### W5 — Review Automation

**Trigger:** Stage moves to `Complete`.

1. Wait 24h
2. SMS: "Wrapping up — would you mind sharing 60 seconds about how it went? [google review link]"
3. If 5★ → auto-thank
4. If <5★ → notify Moses, no public review link sent, internal callback task

### W6 — 180-Day Reactivation

**Trigger:** Contact in `Lost` for 180 days.

1. SMS: see `docs/02_sales_script_nepq.md` § E (Day 180)
2. If reply → re-open as new lead

### W7 — Emergency Page-Moses

**Trigger:** Retell webhook with intent `emergency`.

1. Warm transfer in Retell (handled at agent layer)
2. Simultaneously SMS Moses + auto-dial Moses cell
3. Create contact with tag `urg:emergency` + `svc:water-damage`
4. Open contact in `New Lead` with red flag

### W8 — Stripe Deposit Follow-up

**Trigger:** Contract signed but deposit not paid within 24h.

1. SMS: "Got the signed contract — deposit link to lock the crew in: [stripe link]"
2. If unpaid at 48h → Moses call task

---

## Notifications (internal)

| Event | Who | Channel |
|---|---|---|
| New lead | Moses + Mike | SMS |
| Emergency intent | Moses | SMS + call |
| Quote signed | Moses + Mike | SMS |
| Negative review threat (<5★) | Moses + Mike | SMS |
| AI agent down / Retell failure | Mike + Sanjeev | Email |

---

## Daily metrics report (auto-email at 8 AM ET)

To: Moses, Mike

- Calls answered (last 24h) — AI / human split
- Leads created (last 24h) — by source
- Estimates booked (last 24h)
- Quotes sent (last 24h)
- Contracts signed (last 24h)
- Reviews received (last 24h)
- Pipeline value (open) — total $
- Conversion rate snapshot (Lead → Estimate → Quote → Signed)
