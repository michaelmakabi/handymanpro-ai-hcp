# NEPQ Sales Script v1 — HandyMan Pro

Framework: Jeremy Miner NEPQ (Neuro-Emotional Persuasion Questioning). Tonality: neutral, slightly disinterested, never pitchy. The AI agent uses this script. Human follow-up uses it too.

---

## A. Inbound — homeowner called the AI line

### A1. Connection (first 5 seconds)
> "Hey, this is the HandyMan Pro virtual front desk — I help schedule estimates. Mind if I ask a couple quick questions so I can get you to the right person?"

(If they say "I want a quote" — don't bridge to price. Bridge to **situation**.)

### A2. Situation questions
- "Just so I understand — what's going on at the house that made you call today?"
- "Is this something that just came up recently, or has it been on your list for a while?"
- "And the property — is it your primary residence, a rental, or commercial?"

### A3. Problem-awareness questions
- "What have you tried so far to get this handled?"
- "What didn't work about that?"
- "If it stayed exactly the way it is for another six months — what would that look like for you?"

### A4. Solution-awareness questions
- "When you picture this finished — what does it look like?"
- "Have you had estimates before? What did you like or not like about how that went?"

### A5. Consequence questions (only if they're warm)
- "If you got past this, what changes for you and the family?"
- "And if you don't get to it this season — what's the cost of waiting?"

### A6. Qualifying / commitment
- "Sounds like it makes sense to have one of our project managers come measure and give you a fixed-price quote. We can do that this week — Tuesday or Thursday work better?"

### A7. Booking
- "Great. I've got Moses available Thursday at 10 AM or 2 PM. Which works?"
- Confirm name + address + phone + email + photos via SMS link.

### A8. Soft close
> "You'll get a text confirming. Moses will measure, walk through finishes, and you'll have a written fixed-price quote within 24 hours. No pressure, no obligation. Sound good?"

---

## B. Inbound — emergency water damage

Pattern interrupt: skip qualification, route to Moses cell immediately.
> "Got it — water situation, I'm patching you to Moses on the emergency line right now. Stay on. If we drop, call back this same number."

Trigger SMS to Moses: `EMERGENCY — [name] — [address] — [phone] — water damage`.

---

## C. Missed-call text-back (auto-triggered)

> "Hey — this is HandyMan Pro. Just saw your call. Quick question so I can route you right — kitchen, bath, flooring, or something else? Text me back and I'll get a project manager on you within the hour. — Moses"

---

## D. Outbound — property manager cold call

### D1. Pattern interrupt
> "Hey [Name], this is Moses with HandyMan Pro out of Weston. We never spoke before. I know this is a cold call. Want me to keep going or is this a bad spot?"

### D2. Reason for call
> "I'll be quick. The reason I called specifically — we work the [Pembroke Pines / Davie / Weston] area doing turnover and tenant-move-in remodels on a fixed-price basis. Last 90 days we did 14 units. Most PMs we work with hated juggling subs and getting ghosted."

### D3. NEPQ probe
- "Are you guys feeling that at all, or do you have your turnover crew dialed in?"
- (Wait. Let them talk.)
- "What's the bottleneck — is it speed, price, or the actual quality of the finish?"
- "When that happens, what does it cost you — vacancy days, owner complaints, both?"

### D4. Commitment to next step (never the sale)
> "Look, I'm not going to pitch you on a call. What I'd love is 15 minutes — I'll show you how our fixed-price turnover packet works and you can decide if it's worth pulling us in on the next unit. Thursday afternoon or Friday morning?"

---

## E. Follow-up cadence (post-estimate, no decision yet)

| Day | Channel | Message |
|---|---|---|
| Day 1 | SMS | "Hey [name], Moses here. Sent over your quote — let me know if any of it's unclear, happy to walk through line-by-line." |
| Day 3 | Email | Project gallery of 3 similar completed jobs + reviews from same neighborhood. |
| Day 7 | SMS | "Still thinking on the [kitchen / bath]? No rush — just wanted to make sure the price I quoted is held for you if you decide this week." |
| Day 14 | Voice | Moses personally calls. Soft tonality: "Just checking in — what's holding you back? What would have to be true for this to be a yes?" |
| Day 30 | Email | "Closing your file unless you say otherwise — let me know if timing changed." |
| Day 180 | SMS reactivation | "It's been six months since we talked about your [kitchen]. Still on your list? We have a [seasonal] opening coming up." |

---

## F. Objection-handling library (NEPQ-style — always a question, never a counter)

| Objection | NEPQ-style response |
|---|---|
| "Your price is too high." | "I hear that. Just so I understand — too high compared to what you were expecting, or too high compared to another quote you got? Mind if I see what the other quote covers — I want to make sure we're comparing apples to apples." |
| "I need to think about it." | "Totally fair. Help me understand — is it the scope, the timing, or the price you need to think through?" |
| "I need to talk to my spouse." | "Of course. What do you think they'll want to know? Want me to put a one-pager together you can both look at?" |
| "We're getting other quotes." | "Smart. How many are you collecting? And what's the criteria you're going to use to pick? Just curious — sometimes the cheapest isn't the savings people thought." |
| "Can you do it cheaper?" | "Maybe. What part of the scope would you want to cut to get the price down?" |

---

## G. Voicemail script (if AI fails to connect)

> "Hey — this is HandyMan Pro, sorry I missed you. Text this same number with the word ESTIMATE and your zip code — I'll send a project manager out this week. Or just call back, we're picking up till 9 PM."
