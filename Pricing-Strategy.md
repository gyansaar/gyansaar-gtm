# GyanSaar — Pricing Strategy & Structure (v0.1)

**Owner:** Deepak Nagpal (with Nitigya, per PRD action A36) · **Draft date:** 28 October 2026 · **Status:** v0.1 for internal review with Ankit and Nitigya before the first paying contract is written.

> This is a starting framework, not a shipped price list. It uses PRD §15.2 cost
> figures as the floor. Numbers are mine; the floor is Ankit's. If any number
> here would land in a signed MSA, it needs the three of us to agree first.

---

## 0. TL;DR — recommended pricing

**Two SKUs, picked by GyanSaar (not the customer) based on institute size:**

| SKU | Fit | Headline price | Monthly floor |
|---|---|---|---|
| **Classroom** (per student) | Up to 150 active students | **₹200 / active student / month** | ₹5,000 (25 students) |
| **Centre** (per recorded hour + student allowance) | 150+ students or multi-batch coaching | **₹300 / recorded hour + ₹60 / active student / month** | ₹20,000 (40 hrs + 150 students) |

**Both include everything we have live today:** instructor app, transcription, lesson records, assignment drafts, submission grading, WhatsApp doubt bot, weekly parent digest, admin portal.

**One-time setup fee:** ₹10,000 (waived on annual plan).

**Annual plan:** pay for 10 months, get 12 — ~17% effective discount.

**Pilot:** first two customers get **4 weeks free**; from the third customer onwards, ₹5,000 flat pilot fee for 4 weeks.

**GST:** 18% added on top of every invoice (payable by customer; remitted by us once GyanSaar has a GSTIN, A20-ish).

**All numbers price on cost model A (Sarvam Saaras ₹35.40 / audio-hour)** — the ASR that runs today. If model B (self-hosted IndicWhisper) clears PRD §18.1 q11, cost drops ~90% on ASR and margins widen; prices do not need to drop with them (see §8).

---

## 1. Why these numbers

### 1.0 Market context (from the TeachFX India market analysis, Oct 2026)

Two external data points inform where we price:

- **TeachFX US pricing** (the closest comparable product): $10,000–$30,000 per district implementation = **~₹8.8L–₹26.4L/year per district**. US institutional WTP for diagnostic classroom AI is very high.
- **Indian K-12 "accessible utility" PSPM range** (per Razorpay / school-ERP benchmarks): **₹10–₹30 per student / month**. A 1,000-student school = ₹1.2L–₹3.6L / year. This is the band that ERPs like Teachmint and LEAD occupy — a floor for schools, not a ceiling.
- **Coaching institutes** (JEE/NEET prep: FIITJEE, Allen, PW) have "exceptionally high willingness to pay for a scalable quality-control SaaS" per the report, because star-teacher dependency and franchise-pedagogy consistency are their most expensive problems.

**What this tells us about the ₹200 / student headline:**

- 7× the K-12 "accessible utility" band — too high for schools (confirmed by the report; schools pricing is a separate exercise, see §12).
- A reasonable premium for **coaching institutes**, where WTP is higher and GyanSaar's feature set (WhatsApp bot + marked submissions + digest) is a superset of what TeachFX offers today.
- Well below any per-student-per-month equivalent of TeachFX's US district price (which, converted, implies ~₹100–₹300/student/month for a ~500-student institution — our range).

**Blue-ocean confirmation.** The report finds no competitor in India doing ambient classroom audio diagnostics for pedagogy. Teachmint, LEAD, MagicSchool, Chanakya and others are **adjacent** (ERPs, generative tools, student tutors) but none capture live classroom audio. **This means we price on value, not competition — nobody else sets the market rate.**

### 1.1 The cost reference, in one line

PRD §15.2:

> Monthly running cost ≈ H × (ASR + ₹1.50) + S × (Q × ₹0.40 + G × ₹1.50)
>
> At reference usage (Q = 25 questions, G = 4 graded submissions per student per month), each student costs **~₹16/month** irrespective of recorded hours. Each recorded hour costs **₹36.90** under Sarvam (₹35.40 ASR + ₹1.50 summarisation).

### 1.2 Four principles behind the design

1. **Price on model A (Sarvam).** It is what runs today. Model B is upside, not a plan.
2. **One SKU per customer, picked by us.** Letting the customer self-select between per-student and per-hour creates arbitrage where the cheaper SKU for them is always the loss-making one for us.
3. **Floors matter more than headline rates.** A small institute recording all day under per-student pricing turns negative without a minimum. A large institute under per-hour pricing bleeds on student doubts without a student allowance. Floors sit in both SKUs.
4. **The headline must sit inside the buyer's existing cost language.** Coaching owners count per-student (fee structure). Larger institutes count per-batch, which approximates per-recorded-hour. Price in their units, not ours.

### 1.3 Four principles behind the numbers themselves

- **~65–80% gross margin** at the usage targets. Cheap enough to be a quick yes; healthy enough to fund GTM, support, and the inevitable discount round.
- **Clears PRD assumption A3** (≥ ₹1,500/instructor/month) by a factor of two or more in every worked example — so if Ankit tightens A3, the margins absorb it.
- **Round numbers**, not price-engineered oddities (₹199.50 reads cheap and small; ₹200 reads like a real product). This is enterprise B2B, not a mobile app.
- **Headroom to discount** 15–25% in the first ten conversations without going underwater. Early pricing is as much research as it is revenue.

---

## 2. SKU 1 — "Classroom" (per active student)

**Who it fits:** institutes with **up to 150 active students** per implementation. Typical shape: a single-brand coaching centre, a boutique CA / finance academy, a single college department, a professional-skills bootcamp.

### 2.1 Terms

| Item | Value |
|---|---|
| **Price** | **₹200 per active student per month** |
| **Minimum** | 25 students (₹5,000/month floor) |
| **Fair-use recording** | 2 hours of recording per enrolled student per month, pooled across the implementation |
| **Overage** | ₹75 per recorded hour beyond the pooled allowance |
| **What "active student" means** | A student on the institute's roster who was in a batch during the month, whether or not they personally opened the app |
| **Setup fee** | ₹10,000 one-time (waived on annual plan) |

### 2.2 What's included (and the headline we lead with)

Every live product capability per PRD and STATE.md:

- Instructor app with one-tap record, approve, discard
- Transcription within minutes
- Approved lesson record per class
- First-draft assignments, with grading when students submit
- **24×7 doubt-clearing bot on WhatsApp, grounded in that class**
- **Weekly WhatsApp digest for parents**
- Admin portal and basic coverage data (institution-level only — never per-instructor rankings, per PRD §13.3)

### 2.3 Worked example — TWSS (BA B1 + MYSQL B1)

- 40 active students, 60 hours of recording per month
- Price: 40 × ₹200 = **₹8,000 / month**
- Cost (§15.2, model A): ₹2,850 / month
- Gross margin: **64 %**
- Per instructor (3 instructors): ₹2,667 — clears A3 (≥ ₹1,500) with margin
- Student allowance: 40 × 2 = 80 hours; 60 used; no overage
- Annual plan: ₹80,000 (₹8k × 10)

### 2.4 Pricing-conversation anchors (for Deepak, in a live meeting)

- "₹200 per student per month" ≈ 5–7 % of a typical coaching-centre monthly fee (₹3,000–₹4,000)
- One doubt-solving faculty session avoided per month ≈ ₹500, pays for ~2.5 students
- WhatsApp digest to parents is the single feature parents ask for most; included

---

## 3. SKU 2 — "Centre" (per recorded hour + student allowance)

**Who it fits:** institutes with **150+ active students**, or **multi-batch coaching** where a lecture serves 100+ students in one shot. Typical shape: Vidya Mandir, FIITJEE / Aakash centres, Narayana / Sri Chaitanya.

### 3.1 Terms

| Item | Value |
|---|---|
| **Price — recording** | **₹300 per recorded hour** |
| **Price — students** | **₹60 per active student per month** |
| **Minimum** | 40 hours recording + 150 students (₹20,000/month floor) |
| **What "recorded hour" means** | Hours actually captured and uploaded, not scheduled. A discarded recording still counts (we spent ASR on it, and discard rate is a KR not a punishment — PRD §9.3) |
| **Lectures over 2 hours** | Must be split before Sarvam (PRD §12, A13); customer billed on the raw duration. No surprise. |
| **Setup fee** | ₹10,000 one-time (waived on annual plan) |

### 3.2 What's included

Identical to Classroom. The split between the two SKUs is pricing shape, not feature access.

### 3.3 Worked examples

**Imarticus-shape** (200 students, 50 hours / month across multiple batches):
- Price: 50 × ₹300 + 200 × ₹60 = ₹15,000 + ₹12,000 = **₹27,000 / month**
- Cost: 50 × ₹36.90 + 200 × ₹16 = ₹1,845 + ₹3,200 = ₹5,045
- Gross margin: **81 %**
- Per instructor (~7 instructors): ₹3,857 — clears A3

**Vidya-Mandir-shape** (500 students, 80 hours / month across 4 big batches):
- Price: 80 × ₹300 + 500 × ₹60 = ₹24,000 + ₹30,000 = **₹54,000 / month**
- Cost: 80 × ₹36.90 + 500 × ₹16 = ₹2,952 + ₹8,000 = ₹10,952
- Gross margin: **80 %**
- Per instructor (~12 instructors): ₹4,500 — clears A3

**Mega-centre** (1,500 students, 120 hours / month):
- Price: 120 × ₹300 + 1,500 × ₹60 = ₹36,000 + ₹90,000 = **₹1,26,000 / month**
- Cost: 120 × ₹36.90 + 1,500 × ₹16 = ₹4,428 + ₹24,000 = ₹28,428
- Gross margin: **77 %**
- Per instructor (~25 instructors): ₹5,040

### 3.4 The volume ladder — before you offer it, think twice

| Students | Default per-student rate |
|---|---|
| 150–500 | ₹60 |
| 501–1,000 | ₹50 |
| 1,001–2,500 | ₹40 |
| 2,500+ | ₹30 — bespoke; Ankit must sign off because it lives on cost model B assumption |

**Rule:** do not offer the volume ladder in the first conversation. Lead with the flat rate. Only concede down the ladder if the deal needs it to close.

---

## 4. Pilot pricing

### 4.1 First two customers — free 4-week pilot

**TWSS and whoever closes next.** Four weeks of full product access at no cost. We eat the ~₹5,000 of Sarvam burn (PRD §15.1 pot covers it). What we get in return:

- A real cohort of recordings for A1, A2, A6 validation
- One written case study each
- Verbal commitment to convert to paid at full price (with 10 % loyalty discount for a year, optional)
- The right to name them publicly in subsequent GTM

**Why 4 weeks, not 12:** per PRD §9.3's discard rule and A22, we need to see sustained usage past the honeymoon. Four weeks is enough to see week 1 enthusiasm pass and week 3 reality land. More than four is us subsidising their indecision.

**Why free, not discounted:** at this stage, the data is worth more than the money. ₹5,000 either way is noise.

### 4.2 From the third customer — ₹5,000 flat pilot fee

Covers Sarvam burn and the setup cost without making a free pilot the default expectation. Pilot converts to full-price subscription at week 5 unless the customer opts out.

### 4.3 Pilot success criteria (we agree with the customer up-front)

Signed on the pilot agreement, not left verbal:

| KR | Threshold | What it measures |
|---|---|---|
| Instructor compliance | ≥ 60% of scheduled classes recorded | A2 |
| Approved-without-edit rate | ≥ 60% | PRD KR2 |
| Student engagement with doubt bot | ≥ 40% of students ask at least one question in week 4 | KR4 |
| Instructor NPS | ≥ 40 | A2 |

If three of four miss, we and the customer write a joint "what we learned" note, do not convert, and part on good terms. If two miss, we discount month 1 and 2 by 50 % and try again. If one or none miss, standard conversion at month 2.

---

## 5. One-time and recurring economics

### 5.1 Setup fee — ₹10,000 one-time

Covers:

- Consent docs tailored to the institute (PRD §13), handed to legal
- Instructor onboarding: 15 minutes per instructor, in person or video
- App installation and keystore trust
- First class dry-run with the Academic Head present
- First week of extra support hours

Waived on annual plan or on first-two-customer pilot.

### 5.2 Annual plan — pay 10, get 12

Standard SaaS carrot. Reduces churn risk and improves cash flow. Three details:

- Paid upfront on day 1 of the annual term
- 12-month commitment, 30-day written notice to cancel after year 1
- Setup fee is waived
- Student count and hour count are reviewed and reset at renewal; mid-year expansion is prorated

### 5.3 Monthly plan — no commitment

- Invoiced on the 1st, due by the 10th
- Razorpay card, UPI, or NEFT
- 7-day grace period before suspension; 30 days before data export and offboarding
- Cancellable anytime with 30 days notice; last month billed normally

### 5.4 Payment-processing and tax load

| Line | Rate | Who absorbs |
|---|---|---|
| GST | 18% | Customer, added to invoice |
| Razorpay card fee | ~2.0% | GyanSaar |
| Razorpay UPI fee | ~0.5% | GyanSaar |
| NEFT | ~₹0 | GyanSaar |
| Platform overhead (Vercel + Supabase Pro) | ₹4,300/month | GyanSaar, amortised across all paying customers |

**Prefer UPI/NEFT over card** in collection: 1.5 % margin recovered on every rupee.

---

## 6. Add-ons (not in base price; roadmap)

Not sold yet. Priced here so Deepak can **mention** them in a meeting ("roadmap, included in base when live") and so we have a reference once they are built.

| Add-on | When live | Price |
|---|---|---|
| Google Classroom / Drive auto-publish | PRD §9.6, A28 — spike only today | ₹20 / student / month |
| Custom app branding (logo + colours in instructor app) | Phase 2, needs mobile work | ₹10,000 / month flat |
| SSO / SAML | Phase 2, needs auth rework | ₹5,000 / month flat |
| Dedicated success manager | For enterprise, needs a hire | ₹25,000 / month flat |
| Multi-institute reporting (franchise view) | Phase 2, needs schema work | ₹15,000 / month flat |

**Rule:** do not quote any of these as "available now". If a prospect asks, "roadmap — included in base plan the quarter it ships" is the honest answer.

---

## 7. Margin and burn math at pilot volume

**At two live pilots** (TWSS Classroom + one Centre-shape pilot, say Vidya Mandir):

| Line | Monthly |
|---|---|
| Revenue — TWSS (40 students) | ₹8,000 |
| Revenue — Vidya Mandir shape (500 students, 80 hrs) | ₹54,000 |
| **Gross revenue** | **₹62,000** |
| Running cost (ASR + grading + bot) | ~₹13,800 |
| Platform overhead | ₹4,300 |
| **Gross profit** | **~₹43,900** |
| Gross margin | **71%** |

This covers Nitigya's social budget, one card payment-processing bill, and leaves room for Ankit's spike experiments on IndicWhisper. **It does not cover a founder salary.** That remains the thing GyanSaar is building toward, not something that gets paid out of month 3.

---

## 8. If cost model B lands (self-hosted IndicWhisper)

Per PRD §15.2, model B drops ASR from ₹35.40/hour to ~₹4/hour — a 90 % cut on the single largest cost line. **Prices do not need to come down.** The margin widens:

- TWSS gross margin: 64 % → ~**84 %**
- Vidya-Mandir shape: 80 % → ~**90 %**

**What to do with that windfall:**

1. Fund a second salesperson or a success hire (currently we have none)
2. Introduce a lower-priced "Essentials" SKU for schools (recording + transcript only, no bot or grading) at ₹100/student/month
3. Discount annual plans more aggressively to drive upfront cash

**What NOT to do:** cut headline prices on existing customers. They did not sign for cost-plus pricing; they signed for a value they are getting. Cutting price unprompted suggests we were overcharging.

---

## 9. Price objections and how to defend

### 9.1 "₹200 per student feels high — your competitor charges ₹100."

> "Our ₹200 includes the WhatsApp doubt-clearing bot, the parent digest, and marked submissions, which the competitor's ₹100 does not. If you want a feature-matched comparison I'll walk through what you're actually paying for in each. If the competitor is genuinely offering all three at ₹100, I'd like to understand how — I don't think it is possible at that price."

### 9.2 "We'd like a discount."

Standard SaaS answer: **do not negotiate on headline rate**, negotiate on **term** or **scope**.

> "The rate is the rate. What I can do is: lock you into the current rate for 24 months instead of 12, or waive the setup fee, or add two extra months free on the annual plan. Which of those three is most useful to you?"

Last resort — only if the deal is otherwise lost and the LTV justifies it: 10 % off headline, in exchange for a case study and a reference call.

### 9.3 "What happens if a student uses the bot a hundred times a month?"

> "The reference usage is 25 questions and 4 graded submissions per student per month. We will not meter you unless usage goes significantly beyond that — if a student uses the bot 100 times a month, that is a student we love and I will not come to you with an extra bill. If it is sustained across the whole cohort over a quarter, we have a conversation about moving you to the per-recorded-hour plan where usage is less of a factor."

### 9.4 "Why per-student if we're a 300-student institute?"

They should not be on per-student. If a prospect is 150+ students and the sales conversation drifted to per-student, that is a sales error on our side.

> "Thanks for raising that. For 300 students you're actually a better fit for our Centre plan, which is priced per recorded hour instead — it ends up cheaper for you at your scale. Let me redo the quote on that basis."

### 9.5 "Can we pay quarterly instead of monthly?"

Yes — quarterly billing available on Classroom and Centre, no discount. Annual is the only discounted term.

### 9.6 "Can we start free and pay when we see value?"

That is the pilot. See §4.

### 9.7 "What's your refund policy?"

- Monthly: no refunds; cancel for next cycle
- Annual: pro-rata refund on the remaining months **minus** a 10 % early-termination fee, if the exit is for cause (we failed to deliver per SLA). No refund if the exit is because they changed strategy.

### 9.8 "₹10 / student / month is what Teachmint charges — why are you 20×?"

> "Teachmint is an ERP — attendance, fees, timetabling, parent WhatsApp. We don't do any of those. GyanSaar captures the teaching itself: every lecture becomes a transcript, a draft assignment, graded submissions, and a 24×7 doubt bot grounded in your trainer's actual class. That's a different category of product, and nobody else in India does it. You will keep your ERP; we sit next to it, not instead of it."

**Why this answer works** (per the TeachFX India report): the market has no competitor doing ambient classroom audio diagnostics; comparing GyanSaar to Teachmint is a category error we should correct, not a benchmark we need to meet.

---

## 10. Open decisions, before we quote anyone a real number

Flagging explicitly so this doc does not quietly become policy. Each needs a resolution before an invoice carries any of its outcomes.

| # | Decision | Owner |
|---|---|---|
| P1 | GSTIN — register as proprietorship / LLP / Pvt Ltd before first paid invoice | Ankit |
| P2 | Approve the two SKU rates (₹200/student, ₹300/hour + ₹60/student) | Ankit + Deepak + Nitigya |
| P3 | Approve pilot pricing (first two free, then ₹5,000) | Deepak + Nitigya |
| P4 | Approve the volume ladder (§3.4) and the Ankit sign-off threshold | Ankit |
| P5 | A33 resolution (PRD §13.3): can we market trainer-time saved to owners? Current pricing conversation leans on this. If A33 lands negative, revisit §9.1 | Ankit |
| P6 | Pilot KRs (§4.3) — are those the right four thresholds? | Ankit |
| P7 | Add-on roadmap (§6) — commit a quarter to each, or leave as "future" | Ankit |
| P8 | A3 revisit — assumption says ≥ ₹1,500/instructor/month; our worked examples beat it by 2–3× but worth checking against the first three live conversations | Deepak |
| P9 | MSA template (master services agreement), with the §9 defences built in | Deepak + a lawyer |

---

## 11. Trojan-horse positioning for institutional sales

Three different buyers inside one institute, three different budget pools. **Lead with whichever is tightest for the person you're sitting across from.** (This logic is drawn from the TeachFX India report, which argues classroom AI only moves in India when positioned as compliance automation, not as pedagogical idealism.)

| Buyer | What they care about | What we pitch them |
|---|---|---|
| **Owner / Director** (coaching) | Revenue, retention, star-teacher risk | Trainer time saved, course marketing evidence, batch consistency (**current pitch**) |
| **Principal / HOD** (college, future) | NAAC Criterion II score (teaching-learning, 350 points), accreditation renewal | "Documented teaching for NAAC SSR" — moves spend from academic budget to compliance budget |
| **Principal** (K-12, future) | NEP 2020 CPD 50-hour tracking (CBSE affiliation renewal depends on it) | "Automated CPD generation and tracking" — bypasses pedagogy conversation entirely |
| **Academic Head** | Day-to-day quality, visibility across batches | Coverage data at institution level (never per-instructor rankings; PRD §13.3) |
| **Trainer / Faculty** | "Not another surveillance tool" | Private pedagogical mirror — teacher owns the tape, discards leave no trace |

**Rule:** the price does not change by buyer; the pitch does. All three decision-makers end up in the same conversation, and the contract gets signed from the budget pool that was easiest to unlock.

---

## 12. What's different when we price schools (future, do not use yet)

Schools are **not** priced like coaching. Flagging because the current SKUs will be misused if copied over.

| Dimension | Coaching (current) | Schools (future) |
|---|---|---|
| Headline PSPM | ₹200 | ₹30–₹60 (reference: TeachFX India report) |
| Primary wedge | Trainer time + marketing | NEP 2020 CPD 50-hour compliance |
| Budget pool | Operational / growth | Administrative / compliance / affiliation renewal |
| Setup fee | ₹10,000 | ₹25,000–₹50,000 (schools expect it, and the DPDP consent workflow is heavier) |
| Pilot shape | 4 weeks free | 1 full academic quarter free (longer validation cycle, slower buying) |
| Hard gate | Instructor consent (PRD §13) | Verifiable parental consent via DigiLocker (DPDP Act 2023) — this is a product build, not a pricing decision |

**Do not pitch schools before the DPDP + CPD compliance pack exists** (see GTM-Plan §1c and this file's P5). Pricing a school on current coaching numbers will produce a loss-making contract we can't exit.

---

## 13. Competitive positioning (not for the price sheet; for the sales conversation)

The TeachFX India report maps the field. Here's where we land versus the categories a prospect might name:

| Category | Example | What they do | How we're different |
|---|---|---|---|
| **US classroom-AI incumbent** | TeachFX | Talk-time, wait-time, questioning metrics for the teacher only | We go further: transcript + assignment + grading + student bot. Also India-native (Hinglish, Sarvam ASR, DPDP-compliant). |
| **India generative teacher-prep AI** | MagicSchool AI, Coschool Vin | Lesson plans, quizzes, drafting | They help the teacher **prepare**; we capture what the teacher **does**. Complementary, not competing. |
| **India student-facing AI tutors** | YoLearn.ai, Chanakya AI | Student-focused doubt-solving on a generic textbook | Our doubt bot is grounded in **the specific class the student attended** — not a textbook. Fundamentally different quality. |
| **India school ERP** | Teachmint, LEAD | Attendance, fees, parent comms, timetabling | ERPs; we're classroom AI. Sit alongside them. |
| **India AI voice training** | Project Tara | English pronunciation coaching for teachers | Training tool, not classroom analytics. |

**One-line summary for Deepak to use in a meeting:**

> "Nobody else in India captures ambient classroom audio to generate pedagogical artifacts and a doubt bot grounded in your own class. The closest thing is TeachFX in the US — and they only do analytics, we do the full loop."

---

## 14. What this doc is not

- **Not a public price list.** Keep it internal until P2–P4 are settled.
- **Not a per-feature price card.** Pricing per feature invites customers to opt out of the feature that makes GyanSaar work (the WhatsApp bot). All live features are in base, always.
- **Not a quote for any specific customer.** Every customer conversation starts with their shape (students, hours, batches) and the quote is derived; the doc is the formula, not the quote.
- **Not a competitive price position.** If a competitor materially undercuts us, the response is to improve the product, not to drop headline price. We will not win a race to the bottom in a market where the product is grounded in classroom audio — the moat is quality, not cheapness.

---

## Appendix A — the cost formula, inline

For quick lookup during a sales conversation. From PRD §15.2.

> **Monthly running cost ≈ H × (ASR + ₹1.50) + S × (Q × ₹0.40 + G × ₹1.50)**
>
> H = recorded hours per month
> S = active students
> Q = questions per student per month (reference: 25)
> G = graded submissions per student per month (reference: 4)
> ASR = ₹35.40 (model A, Sarvam) or ≈ ₹4 (model B, IndicWhisper — not built)
>
> At reference usage, per-student cost ≈ **₹16 / month**, independent of H.
> Per-recorded-hour cost ≈ **₹36.90**, independent of S.

Platform overhead ≈ ₹4,300 / month (Vercel Pro + Supabase Pro), shared across all paying customers.

---

## Change log

- **v0.1 · 28 October 2026** · Deepak · Initial pricing framework based on PRD §15.2 and §15.3. Two SKUs (Classroom, Centre), per-SKU fit logic, pilot pricing, defensive floors, open decisions P1–P9. Needs Ankit sign-off on rates before any customer quote.
- **v0.2 · 28 October 2026** · Deepak · Folded in the TeachFX India market analysis (Deepak's own report). Added §1.0 market context, §9.8 defence against Teachmint-style price comparisons, §11 Trojan-horse positioning (buyer × budget pool), §12 "what's different for schools" so coaching pricing isn't reused there, §13 competitive positioning map. SKU rates unchanged — the research backs the ₹200/student headline for coaching and warns against it for schools.
