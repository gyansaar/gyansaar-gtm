# GyanSaar — Pricing Strategy & Structure (v0.3)

**Owner:** Deepak Nagpal (with Nitigya and Ankit, per PRD action A36) · **Draft date:** 10 November 2026 · **Status:** v0.3 — two-tier B2B + B2C structure. Rates are still working numbers until P2 clears (see §10).

> This doc is the formula, not a quote. Every customer conversation starts
> with their shape (institute vs. individual, students, hours, batches) and
> the number is derived. The cost floor is Ankit's (PRD §15.2); the markups
> and packaging are mine; the market-benchmark reads come from Deepak's
> TeachFX India analysis (Oct 2026).

---

## 0. TL;DR — the structure

**Two tiers. Pick the one that matches who signs the cheque.**

### 0.1 Tier 1 — B2B · the institute pays for the facility

Three standard plans with hard caps + bespoke Enterprise:

| Plan | Student cap | Recording cap / month | Monthly price |
|---|---|---|---|
| **Starter** | up to 50 | 40 hours | **₹8,000** |
| **Growth** | up to 150 | 80 hours | **₹18,000** |
| **Scale** | up to 500 | 150 hours | **₹45,000** |
| **Enterprise** | 500+ | custom | bespoke, from ₹85,000 |

**Overage** (either cap breached): ₹100 / extra student / month · ₹300 / extra recorded hour. Billed on the next invoice. Alerts at 80 %, hard-stop decline at 110 % of cap (prevent runaway bills).

**Setup fee:** ₹10,000 one-time (waived on annual plan).

**Annual plan:** pay 10 months, get 12.

### 0.2 Tier 2 — B2C · students or private trainers pay directly

**Student subscription** (college students 18+; high-school minors blocked until DPDP flow ships — see §3.4):

- **₹299 / student / month** · or **₹2,499 / year** (30 % off)
- First 7 days free
- Access tied to one trainer (private or institutional)

**Private trainer** (freelance / visiting faculty):

- **Free sign-up** — recording, approval, LMS access, up to 10 hours / month and up to 15 subscribed students
- **₹1,999 / month Pro** — unlimited recording, up to 100 students
- **Revenue share:** 20 % of subscriptions from students the trainer invited, after the first 5 students (keeps freelancers incentivised to grow the base)

**What's included (both tiers):** everything live per STATE.md as of today — one-tap recording, transcription, lesson records, first-draft assignments, graded submissions, 24×7 WhatsApp doubt bot, weekly parent/student digest, admin portal.

**GST:** 18 % added on every invoice once GyanSaar has a GSTIN (open: P1).

**All numbers price on cost model A (Sarvam ₹35.40 / audio-hour).** Model B is upside, not a plan (see §8).

---

## 1. Why these numbers

### 1.0 Market context (from the TeachFX India market analysis, Oct 2026)

Three external data points shape the structure:

- **TeachFX US pricing:** $10,000–$30,000 per district implementation ≈ **₹8.8L–₹26.4L/year per district**. US institutional WTP for diagnostic classroom AI is very high.
- **Indian K-12 "accessible utility" PSPM range:** **₹10–₹30 / student / month** (Teachmint, LEAD and ERP benchmarks). A 1,000-student school pays ₹1.2L–₹3.6L/year for ERPs. Floor, not ceiling, for schools.
- **Coaching institutes** (JEE/NEET/finance prep): WTP described in the report as "exceptionally high" because star-teacher dependency and franchise-pedagogy consistency are their most expensive problems.
- **Indian consumer EdTech consumer-SaaS price points** (Vedantu, Chanakya AI, Unacademy direct-to-student): **₹199–₹499 / month** for individual student subscriptions; ₹2,000–₹5,000 / year for annual.
- **Blue-ocean:** report finds no competitor in India doing ambient classroom audio diagnostics. We price on value, not comparable.

**Reading for our pricing:**
- B2B coaching institute at ₹8,000–₹45,000 / month → maps to 5–40 % of what institutes already spend on ERPs + teacher training combined. Defensible.
- B2C student at ₹299 / month → sits inside the Vedantu / Chanakya band, below Unacademy and BYJU's. Defensible for a supplementary learning tool.
- K-12 schools pricing is **not** in this doc (see §12). It is a separate, lower, compliance-led structure that doesn't exist yet.

### 1.1 The cost reference, in one line

From PRD §15.2:

> Monthly running cost ≈ H × (ASR + ₹1.50) + S × (Q × ₹0.40 + G × ₹1.50)
>
> H = recorded hours / month · S = active students · Q = questions / student / month (reference: 25) · G = graded submissions / student / month (reference: 4) · ASR = ₹35.40 (A, Sarvam) or ≈₹4 (B, IndicWhisper — not built)

At reference usage, per-student cost ≈ **₹16 / month**; per-recorded-hour cost ≈ **₹36.90**. Platform overhead ≈ ₹4,300 / month (Vercel Pro + Supabase Pro, shared across all paying customers).

### 1.2 Principles behind the structure

1. **Price on cost model A.** Model B is upside, not strategy.
2. **One tier per customer, picked by us.** Letting the customer self-select between B2B and B2C creates arbitrage — small institutes would buy B2C-Student seats; large institutes would push individual trainers onto B2C-Trainer to dodge institutional pricing. We route institutes to B2B, individuals to B2C, no exceptions.
3. **Caps give institutes predictability.** The current ₹200/student/month floating model (v0.2) was uncomfortable for an Academic Head who needs to budget the year. A capped standard plan with clear overage pricing is easier to buy.
4. **B2C is direct-to-end-user, consumer-grade pricing.** ₹299/month is the mental register a student uses when subscribing to Netflix or Spotify. We sit inside that mental budget, not above it.
5. **Freelance trainers are a growth engine, not a profit centre.** Free sign-up lowers acquisition cost; revenue share keeps them aligned to grow student subscriptions, which is where the actual revenue is.

---

## 2. B2B tier — the three standard plans + Enterprise

### 2.1 Plan grid

| Plan | Student cap | Recording cap / mo | Monthly | Annual (–17%) | Target fit |
|---|---|---|---|---|---|
| **Starter** | 50 | 40 hrs | ₹8,000 | ₹80,000 | Boutique coaching, single-branch, test-prep, a college department pilot |
| **Growth** | 150 | 80 hrs | ₹18,000 | ₹1,80,000 | Mid-size coaching with 2–3 batches, a full college-department roll-out |
| **Scale** | 500 | 150 hrs | ₹45,000 | ₹4,50,000 | Multi-batch coaching, mid-size college, small franchise |
| **Enterprise** | 500+ | custom | from ₹85,000 | ~₹8,50,000 | FIITJEE-shape, multi-city franchise, Imarticus-shape networks |

### 2.2 Overage policy (critical — this is what makes the caps buyable)

- **Soft alert at 80 %** of either cap. Email + admin dashboard warning.
- **Soft alert at 100 %.** Overage billing begins.
- **Hard decline at 110 %.** New recordings refused, student doubt bot still answers. Admin can resume by upgrading plan or explicitly accepting overage billing on a one-month basis.

Overage rates:
- **₹100 / extra active student / month** (one month at a time)
- **₹300 / extra recorded hour**

**Why 110 %, not infinite overage:** at the v0.2 ₹200/student floor, an institute recording all day could rack up ₹30,000 of overage before anyone noticed. A hard-stop at 110 % forces a conversation. Standard SaaS practice (AWS Budgets, Twilio, Stripe). No surprise bills.

### 2.3 What's included (same across all four plans)

Everything live per STATE.md:

- Trainer app (Android; iOS on roadmap)
- One-tap recording with discard rights
- Transcription within minutes
- Approved lesson record per class
- First-draft assignment generation
- Submission grading (with trainer sign-off before marks go out)
- **24×7 WhatsApp doubt-clearing bot grounded in the specific class**
- **Weekly WhatsApp digest for parents** (pending Meta template approval, A24)
- Admin portal
- Institution-level coverage data — **never per-instructor rankings** (PRD §13.3; A33 open)

### 2.4 Worked examples

**TWSS (BA B1 + MYSQL B1)** — 40 students, 60 hrs / month, 3 trainers:
- Plan: **Starter**. Caps: 50 students / 40 hrs. **One cap breach:** 60 hrs vs 40 hr cap = 20 hrs over = ₹6,000 overage.
- Monthly: ₹8,000 + ₹6,000 overage = **₹14,000**
- Cost (§15.2): ₹2,850 → **gross margin 80 %**
- Per instructor: ₹4,667 → clears A3 (≥ ₹1,500) by 3×
- Recommendation at renewal: **upgrade to Growth** (₹18,000, 80 hr cap) — predictability without overage drama.

**Imarticus-shape** — 200 students, 50 hrs / month, 7 trainers:
- Plan: **Growth** (150 cap). **One cap breach:** 50 extra students = ₹5,000 overage.
- Monthly: ₹18,000 + ₹5,000 = **₹23,000**
- Cost: 50 × 36.90 + 200 × 16 = ₹5,045 → **gross margin 78 %**
- Recommendation: **upgrade to Scale** (fits comfortably within 500 / 150 caps).

**Vidya-Mandir-shape** — 500 students, 80 hrs / month, 12 trainers:
- Plan: **Scale** (500 / 150 caps). No overage.
- Monthly: **₹45,000**
- Cost: 80 × 36.90 + 500 × 16 = ₹10,952 → **gross margin 76 %**

**Mega-centre** — 1,500 students, 120 hrs / month, 25 trainers:
- Plan: **Enterprise**, bespoke. Starts at **₹85,000/month** for 1,500 students / 120 hrs.
- Cost: 120 × 36.90 + 1,500 × 16 = ₹28,428 → **gross margin 67 %**
- Enterprise contracts can carry volume discounts down the ladder to as low as ₹30/student effective, but **Ankit signs off any rate below ₹60/student** because it approaches model B assumption.

### 2.5 B2B pilot pricing — unchanged from v0.2

- **First 2 customers:** 4-week free pilot. (TWSS is pilot 1.)
- **From the 3rd:** ₹5,000 flat pilot fee for 4 weeks.
- Pilot converts to the plan matching the customer's measured usage in week 4.

**Pilot success criteria** (signed on the pilot agreement, not verbal):

| KR | Threshold | Why |
|---|---|---|
| Instructor compliance | ≥ 60 % of scheduled classes recorded | PRD A2 |
| Approved-without-edit rate | ≥ 60 % | PRD KR2 |
| Student bot engagement | ≥ 40 % of students ask at least one Q by week 4 | KR4 |
| Instructor NPS | ≥ 40 | A2 |

Three-of-four miss → no conversion, joint learnings note, part on good terms. Two miss → 50 % discount month 1–2, retry. One or none miss → standard conversion.

---

## 3. B2C tier — students and private trainers

### 3.1 Student subscription

| Item | Value |
|---|---|
| **Price** | **₹299 / student / month** |
| **Annual option** | **₹2,499 / year** (effective 30 % discount vs ₹3,588) |
| **Free trial** | 7 days, no card required |
| **Minimum commitment** | None on monthly; 12 months on annual |
| **Payment** | UPI auto-debit (e-mandate), card autopay, or NEFT quarterly |

**What a B2C-Student gets:**

- LMS login at `lms.gyansaar.com`
- Access tied to **one trainer** — either a private B2C trainer they're enrolled with, or an institutional trainer whose institute has added them on a B2B2C bridge (§3.5)
- Access to their trainer's recorded classes (transcripts, lesson records)
- 24×7 doubt-clearing bot on WhatsApp — grounded in the classes they've attended
- Weekly WhatsApp digest of what was taught that week
- Submission grading on assignments their trainer set
- Searchable archive of every class they attended

**What a B2C-Student does NOT get** (without a trainer):

- No generic AI tutor if they have no trainer on the platform. The product value depends on classroom audio; a student subscribing without a teacher is subscribing to nothing they can use. The app will **refuse** sign-up until a trainer code is entered.

### 3.2 Private trainer plan

| Plan | Price | Recording / mo | Student cap |
|---|---|---|---|
| **Free** | ₹0 | 10 hours | 15 subscribed students |
| **Pro** | **₹1,999 / month** | unlimited (fair use) | 100 subscribed students |
| **Pro Annual** | **₹19,990 / year** | unlimited | 100 subscribed students |

**What's included:**

- Trainer app, approval queue, LMS admin
- Everything in the B2B feature set, just scoped to one trainer
- Dashboard of subscribed students
- Revenue share — see §3.3

**What it does NOT include:**

- Multi-trainer coordination (that's B2B territory)
- Custom branding
- Admin portal for an institution

### 3.3 Revenue share — the growth lever

To align freelance trainers with growing the paid-student base:

> **GyanSaar pays the trainer 20 % of each student subscription that student uses the trainer's content on, past the first 5 students, for as long as both are active.**

**How it works:**
- Trainer T sells / recommends GyanSaar to their class
- Students 1–5 subscribe → GyanSaar keeps 100 % (covers trainer's free account + Sarvam burn)
- Students 6+ subscribe → trainer earns 20 % × ₹299 = ₹59.80 / student / month
- Paid out to the trainer monthly via UPI once accrued earnings cross ₹500

**Example:** A trainer on the Free plan with 20 subscribed students = 15 × ₹59.80 = **₹897 / month earned**. Enough to offset their own Pro upgrade (₹1,999) at ~35 subscribed students (30 billable × ₹59.80 = ₹1,794).

**Why this works:**
- Classical creator-economy playbook (Substack, Skool, Teachable)
- Costs us almost nothing — the cost per student is ₹16 / month, we're charging ₹299, we can afford ₹60 share and still keep ₹223 contribution
- Trainer becomes a sales agent for their own students, lowering our CAC on the student side

### 3.4 DPDP compliance — minors are a hard gate

**This is the single decision that gates the B2C launch to high schools.**

Per DPDP Act 2023 and the TeachFX India analysis:

- A minor is **anyone under 18 years of age**
- Any personal data processing for a minor requires **verifiable parental consent**
- Penalty for non-compliance: **up to ₹200 crore per instance**
- Voice recordings are treated as **sensitive biometric data**

**Implication for B2C:**

**B2C-Student is only safe to launch for college students 18+ until Ankit builds a verifiable parental-consent flow** — ideally via DigiLocker integration, which is the gold-standard consent channel the Act recognises.

**Until that flow exists:**

- B2C-Student sign-up blocks any user who enters a DOB under 18
- The high-school student segment is deferred. Marketing materials should not advertise it.
- A trainer who onboards under-18 students via the B2B2C bridge (§3.5) is subject to the institute's own consent process, not ours — the institute is the Data Fiduciary (per DPDP) and we're the Data Processor, so the compliance burden shifts cleanly

**New open decision P10** — Ankit scopes and timelines the parental-consent flow.

### 3.5 B2B2C bridge — the cross-sell that unlocks student revenue even inside institutes

A coaching institute on a B2B plan can **invite their students to subscribe to B2C** for home use (revision, doubt-solving outside class hours, access to the digest). This:

- Doubles the revenue per institute (institute pays ₹18,000/month B2B + 100 students × ₹299 = ₹47,900/month combined)
- Gives the student more value for the money
- Keeps the institute's B2B cap clean (student subscriptions don't count toward B2B cap because the student is paying for home-use of the same content)
- Institutions get a 10 % revenue-share if ≥ 30 of their students subscribe (modest incentive)

**Pilot this with TWSS once both tiers are live.** It's the highest-ROI expansion lever we have.

### 3.6 Worked examples — B2C

**A private trainer** at the top of a freelance CA coaching track, 25 subscribed students:
- 25 × ₹299 = **₹7,475 gross monthly student revenue**
- Trainer share: 20 × ₹59.80 = **₹1,196 earned**
- GyanSaar keeps: ₹7,475 − ₹1,196 = **₹6,279**
- Cost: 10 hrs recording × ₹36.90 + 25 students × ₹16 = ₹369 + ₹400 = **₹769**
- **Gross margin ~88 %**

**A college student** at TWSS enrolled in BA B1, on annual:
- Pays: ₹2,499 upfront
- Monthly amortised: ₹208
- Cost: ₹16 / month (bot + grading; recording cost is on B2B side)
- Contribution per month: ₹192
- **Gross margin ~92 %** (B2B2C bridge accounting — recording is already paid by institute)

**100 college students on a mix of monthly + annual at a Pro trainer:**
- 60 × ₹299 + 40 × ₹208 = ₹17,940 + ₹8,320 = **₹26,260 / month**
- Trainer Pro fee: ₹1,999 (paid or absorbed via revenue share)
- Trainer share on 95 past-first-5: 95 × ₹59.80 = ₹5,681
- GyanSaar net: ₹26,260 + ₹1,999 − ₹5,681 = **₹22,578 / month**
- Cost: 40 hrs × ₹36.90 + 100 × ₹16 = **₹3,076**
- **Gross margin ~86 %**

---

## 4. One-time and recurring economics

### 4.1 Setup fee — B2B only

- ₹10,000 one-time, waived on annual
- Covers: consent docs tailored to the institute (DPDP), trainer onboarding (15 min each), app install and keystore trust, first-week extra support
- B2C has **no setup fee** — consumer product, zero-friction sign-up

### 4.2 Annual plans

- **B2B annual:** pay 10 months, get 12 (~17 % effective discount). Paid upfront. 12-month commitment. Setup waived.
- **B2C-Student annual:** ₹2,499 (30 % off ₹3,588). Paid upfront. 12-month commitment.
- **B2C-Trainer Pro Annual:** ₹19,990 (~17 % off ₹23,988). Paid upfront.

Rationale: student-annual discount is larger (30 % vs 17 %) because student churn risk is materially higher — annual lock-in is worth more to us there.

### 4.3 Billing + processing fees

| Rail | GyanSaar fee | Who absorbs |
|---|---|---|
| GST | 18 % (added to invoice) | Customer |
| UPI / e-mandate | ~0.5 % | GyanSaar |
| Card | ~2.0 % | GyanSaar |
| NEFT | ~0 | GyanSaar |
| Platform overhead (Vercel + Supabase Pro) | ₹4,300 / month total | GyanSaar, amortised across all customers |

**Push UPI auto-debit hard on B2C** — card processing on ₹299 is a meaningful ~2 % margin leak at scale.

---

## 5. Add-ons (not in base; roadmap only)

Not sold yet. Priced here so Deepak can **mention** them to a buyer and so we have a reference once built.

| Add-on | When live | B2B price | B2C price |
|---|---|---|---|
| Google Classroom / Drive auto-publish | A28 — spike today | ₹20 / student / mo | included |
| Custom app branding | Phase 2 | ₹10,000 / mo flat | n/a |
| SSO / SAML | Phase 2 | ₹5,000 / mo flat | n/a |
| Dedicated success manager | For enterprise | ₹25,000 / mo flat | n/a |
| Multi-institute reporting (franchise view) | Phase 2 | ₹15,000 / mo flat | n/a |
| Dedicated student success / parent concierge | Phase 2 | n/a | ₹99 / student / mo |
| DigiLocker parental-consent flow | **Mandatory before U-18 B2C — see §3.4** | n/a | built-in to Student plan once live |

**Rule:** do not quote any of these as "available now". "Roadmap — included in base plan the quarter it ships" is the honest answer.

---

## 6. Margin and burn at pilot volume

**Mixed B2B + B2C scenario** — TWSS Starter+overage + Vidya-Mandir Scale + 150 B2C-Student + 3 B2C-Pro trainers each with 25 students:

| Line | Monthly |
|---|---|
| Revenue — TWSS (Starter + overage) | ₹14,000 |
| Revenue — Vidya-Mandir shape (Scale) | ₹45,000 |
| Revenue — 150 B2C-Student | ₹44,850 |
| Revenue — 3 B2C-Pro trainers + their students (75 students) | ₹28,422 |
| **Gross revenue** | **~₹1,32,000** |
| Running cost (ASR + grading + bot, blended) | ~₹18,000 |
| Trainer revenue share (B2C) | ~₹4,200 |
| Platform overhead | ₹4,300 |
| **Gross profit** | **~₹1,05,500** |
| **Gross margin** | **~80 %** |

This covers: the shared pool kitty ask, Nitigya's social budget, a modest one-salary hire mid-year. **Still does not pay founders.**

---

## 7. If cost model B lands (self-hosted IndicWhisper)

Per PRD §15.2, model B drops ASR from ₹35.40 to ~₹4/hour — 90 % cut on the single largest cost line.

**What to do with the windfall:**

1. Fund a first sales/success hire (B2B pipeline)
2. Launch a lower-tier B2C-Student "Essentials" plan (bot + digest, no recording access) at ₹99 / month — captures price-sensitive segment, especially tier-2/3 cities
3. Discount B2B annual plans more aggressively to drive upfront cash
4. Open K-12 schools market with a compliance-led SKU at the ₹30–60 / student / month band (see §12)

**What NOT to do:** cut headline prices on existing customers. They did not sign for cost-plus; cutting prices unprompted suggests we overcharged.

---

## 8. Price objections and how to defend

### 8.1 "₹18,000 / month is a lot for 150 students."

> "It's ₹120 / student / month at full cap — against a monthly fee you charge each student of ₹3,000–₹5,000. 3–4 %. One extra retention saved per cohort pays for a year of GyanSaar. We cap it precisely so the price is predictable; if usage goes over, you decide whether to accept the overage or upgrade."

### 8.2 "Why does the student plan cost ₹299?"

> "It's less than a Netflix subscription for something a student uses every day of the week. Compared to what parents already pay a private tutor for one hour a month, it's a fraction. The real comparison isn't other apps; it's one tuition top-up a month, which is ₹1,500–₹3,000 in Delhi for this segment."

### 8.3 "Teachmint charges ₹10 / student. Why are you 30× more on B2B?"

> "Teachmint is an ERP — attendance, fees, timetabling. We don't do any of those. GyanSaar captures the teaching: every lecture becomes a transcript, assignments get drafted and marked, students get a 24×7 doubt bot grounded in their actual class. Different category. You will keep your ERP; we sit next to it, not instead of it."

### 8.4 "We'd like a discount."

Do not negotiate on headline rate; negotiate on **term** or **scope**.

> "I can lock you into the current rate for 24 months instead of 12, waive the setup fee, or add two extra months on an annual. Which of those three is most useful?"

Last resort — only if the deal is otherwise lost: 10 % off headline in exchange for a case study and a reference call.

### 8.5 "Can students subscribe without being tied to a trainer?"

> "Not today. The product's core value is the classroom — doubt-clearing, transcripts, assignments all come from a specific class. Without a trainer, the AI doubt bot is just another generic chatbot, and there are plenty of those for free. We refuse that sign-up because we don't want someone paying ₹299 for something we can't deliver value on."

### 8.6 "What's your refund policy?"

- B2B monthly / B2C monthly: no refunds; cancel for next cycle
- B2B annual / B2C annual: pro-rata minus 10 % early-termination, only if exit is for cause

### 8.7 "Can we try it before paying?"

- B2B: pilot — see §2.5
- B2C: 7-day free trial, then auto-converts to paid unless cancelled

### 8.8 "What happens at the plan cap?"

> "You get alerted at 80 % and again at 100 %. At 100 %, overage billing starts at ₹100 / student and ₹300 / recorded hour. At 110 %, we refuse new recordings until you upgrade the plan or accept one month of overage billing. No surprise bills — every rupee over base has a conversation attached."

---

## 9. Open decisions, before any customer quote

Re-numbered and expanded from v0.2 to include B2C:

| # | Decision | Owner |
|---|---|---|
| P1 | GSTIN — register before first paid invoice | Ankit |
| P2 | Approve the four B2B plan rates and three B2C rates | Ankit + Deepak + Nitigya |
| P3 | Approve pilot pricing (first 2 free, then ₹5,000) | Deepak + Nitigya |
| P4 | Approve the Enterprise rate floor (₹60/student minimum without Ankit sign-off) | Ankit |
| P5 | A33 (PRD §13.3): can we market trainer-efficiency to owners? | Ankit |
| P6 | Pilot KRs — the right four thresholds? | Ankit |
| P7 | Add-on roadmap — commit a quarter each, or leave as "future" | Ankit |
| P8 | A3 revisit after first 3 live conversations | Deepak |
| P9 | MSA template with a lawyer | Deepak + lawyer |
| **P10** | **DigiLocker verifiable parental-consent flow — scope, timeline, cost** | **Ankit** — gates the under-18 B2C launch |
| **P11** | **Revenue-share mechanics for private trainers — monthly cutoff, minimum payout, 1099-equivalent tax implications** | **Ankit + lawyer** |
| **P12** | **B2B2C bridge pricing — do institutes get a cross-sell rev-share on their students' B2C subs?** | **Deepak + Nitigya** |
| **P13** | **Payment-gateway choice: Razorpay vs Cashfree vs a split. UPI e-mandate is mandatory for B2C** | **Ankit** |

---

## 10. Trojan-horse positioning for B2B institutional sales

Three decision-makers per institute, three different budget pools. **Lead with whichever is tightest for the person across from you.**

| Buyer | Cares about | Pitch |
|---|---|---|
| **Owner / Director** (coaching) | Revenue, retention, star-teacher risk | Trainer time saved, course-marketing evidence, batch consistency (**current pitch**) |
| **Principal / HOD** (college) | NAAC Criterion II (teaching-learning, 350 pts), accreditation renewal | "Documented teaching for NAAC SSR" — moves spend from academic to compliance budget |
| **Principal** (K-12, future) | NEP 2020 CPD 50-hour tracking | "Automated CPD generation" — bypasses pedagogy conversation entirely |
| **Academic Head** | Day-to-day quality across batches | Coverage data at institution level — never per-instructor rankings (PRD §13.3) |
| **Trainer / Faculty** | "Not surveillance" | Private pedagogical mirror — teacher owns the tape |

**Rule:** price doesn't change by buyer; pitch does. Contract comes from whichever budget pool was easiest to unlock.

---

## 11. What's different when we price schools (future, do not reuse coaching numbers)

| Dimension | Coaching (current B2B) | Schools (future) |
|---|---|---|
| Headline PSPM equivalent | ₹120–₹160 / student at cap utilisation | ₹30–₹60 / student (TeachFX India report) |
| Primary wedge | Trainer time + marketing | NEP 2020 CPD 50-hour compliance |
| Budget pool | Operational / growth | Compliance / affiliation renewal |
| Setup fee | ₹10,000 | ₹25,000–₹50,000 (DPDP consent workflow is heavier) |
| Pilot shape | 4 weeks | 1 full academic quarter |
| Hard gate | Instructor consent | **Verifiable parental consent (DigiLocker)** — product build, not pricing decision |

**Do not pitch schools before P10 (parental-consent flow) ships.** A school pilot on current coaching numbers produces a loss-making contract we can't exit.

---

## 12. Competitive positioning (for the sales conversation)

| Category | Example | What they do | How we're different |
|---|---|---|---|
| **US classroom-AI incumbent** | TeachFX | Talk/wait/questioning for the teacher | We do the full loop: transcript + assignment + grading + student bot. India-native. |
| **India generative teacher-prep** | MagicSchool, Coschool Vin | Lesson plans, quizzes | They help the teacher **prepare**; we capture what they **do**. Complementary. |
| **India student-facing tutors** | YoLearn.ai, Chanakya AI, BYJU's | Generic doubt-solving on textbooks | Our bot is grounded in **the specific class attended** — not a textbook. |
| **India school ERP** | Teachmint, LEAD | Attendance, fees, parent comms | ERPs; we're classroom AI. Sit alongside them. |

**One-line summary:**

> "Nobody else in India captures ambient classroom audio to generate pedagogical artifacts and a doubt bot grounded in your own class. The closest is TeachFX in the US — and they only do analytics, we do the full loop."

---

## 13. Suggestions worth discussing as a team

New in v0.3. These are ideas I'd bring to a team pricing meeting but haven't included in the recommended structure. Each has an upside and a reason I'd want the three of us to agree before adding it.

### 13.1 Freemium B2C-Student (5 doubt questions / day, no transcripts)

**Upside:** acquisition engine. Students try the bot, hit the daily cap, upgrade. Classic Duolingo / Chanakya pattern.
**Risk:** supports a long tail of free users whose bot questions still cost us ₹16 / month at reference usage. Only works if free-to-paid conversion is strong (≥ 3 %).
**Recommendation:** NOT in v0.3. Revisit after 500 paying B2C-Students, when we have conversion data.

### 13.2 Referral program for B2C-Students

**Upside:** viral growth. Student refers a friend → both get 1 month free. Low CAC.
**Risk:** gaming (fake referrals, same card).
**Recommendation:** YES after 100 paying customers, once churn baseline is known.

### 13.3 Family / sibling discount on B2C-Student

**Upside:** standard Indian edtech play. "₹299 for first child, ₹199 for the second". Reduces price objection in households with multiple kids subscribing to one trainer.
**Recommendation:** YES from launch. Easy to implement, materially increases per-household LTV. Add as a built-in auto-discount.

### 13.4 Geo-pricing (tier-1 vs tier-2/3 cities)

**Upside:** report says tier-2/3 India is more price-sensitive; a ₹199 PSPM for non-metro geographies expands TAM.
**Risk:** complex to administer, requires geo-locking that can be VPN-bypassed, invites arbitrage (metro trainer claims tier-2 address).
**Recommendation:** NO at launch. Revisit at 1,000 paying B2C-Students.

### 13.5 Compliance pack SKU for colleges (not schools yet)

**Upside:** colleges renewing NAAC accreditation have genuine compliance budget separate from academic budget. A "NAAC Criterion II pack" (₹15,000/month flat added to Growth or Scale) would be bought out of a different pool and unlock deals academic budgets block.
**Recommendation:** YES after first 5 college conversations surface it as a real pain. Build it when demand is proven, not now.

### 13.6 Partnership rate for coaching franchises

**Upside:** FIITJEE-shape chains with 100+ centres want one pricing conversation for all centres. Flat per-centre rate with volume breakpoints could land a huge deal at once.
**Risk:** low per-centre margin.
**Recommendation:** YES but only for conversations that materialise. Enterprise contract.

### 13.7 Compliance-bundled Enterprise (large coaching + NAAC-equivalent audit)

**Upside:** compliance budget + academic budget + cross-sell revenue. Highest ARPU.
**Recommendation:** YES as part of Enterprise tier, Ankit signs off case-by-case.

### 13.8 Tier-2/3 trainer onboarding programme

**Upside:** report says the private-trainer (coaching home-tuition) segment is huge in tier-2/3 India. A dedicated onboarding programme (Hindi video tutorials, WhatsApp support, zero-friction UPI payouts) could seed 500+ private trainers in 6 months.
**Recommendation:** DISCUSS with Nitigya — fits her brand/marketing workstream per STATE.md.

### 13.9 Parental-consent SaaS as a standalone revenue line

**Upside:** if P10 (DigiLocker parental consent) is well-built, it's useful to other EdTech companies who also need it. Could be licensed as a standalone compliance API at ₹2–5 / consent.
**Recommendation:** NOT a priority now. Note it in the roadmap for year 2+.

---

## 14. What this doc is not

- **Not a public price list.** Keep it internal until P2–P4 are settled.
- **Not a per-feature price card.** Pricing per feature invites customers to opt out of the feature that makes GyanSaar work (the WhatsApp bot). All live features in base, always.
- **Not a quote for any specific customer.** Every quote starts with their shape; the doc is the formula, not the quote.
- **Not a competitive price position.** If a competitor materially undercuts us, the response is to improve the product, not to drop headline price.
- **Not a schools price list.** Schools pricing is a separate exercise gated on P10 and P12.

---

## Appendix A — the cost formula, inline

From PRD §15.2. For quick lookup during a sales conversation.

> **Monthly running cost ≈ H × (ASR + ₹1.50) + S × (Q × ₹0.40 + G × ₹1.50)**
>
> H = recorded hours per month
> S = active students
> Q = questions per student per month (reference: 25)
> G = graded submissions per student per month (reference: 4)
> ASR = ₹35.40 (A, Sarvam) or ≈₹4 (B, IndicWhisper — not built)
>
> At reference usage: per-student cost ≈ **₹16/month**, per-recorded-hour cost ≈ **₹36.90**.

Platform overhead ≈ ₹4,300/month (Vercel Pro + Supabase Pro), shared across all paying customers.

---

## Appendix B — the four pilot deals we should price, in order

Based on STATE.md current GTM (Deepak's A32):

| # | Account | Tier | Plan | Expected monthly |
|---|---|---|---|---|
| 1 | TWSS (live pilot) | B2B | Starter → Growth | ₹8,000 → ₹18,000 |
| 2 | The Wall Street School, additional programmes | B2B | Growth | ₹18,000 |
| 3 | Imarticus | B2B | Scale | ₹45,000 |
| 4 | Vidya Mandir Classes | B2B | Scale → Enterprise | ₹45,000 → bespoke |
| 5 | B2C launch — invite TWSS students via B2B2C bridge | B2C | Student | 40 × ₹299 = ₹11,960 |
| 6 | First 10 private trainers (freelance) | B2C | Trainer Free + 10 students each | ₹29,900 |

**Target end-of-FY revenue** at this trajectory: ~₹2L / month gross. 80 % margin blended = ₹1.6L contribution. Covers burn, funds a first hire by Q4.

---

## Change log

- **v0.1 · 28 October 2026** · Deepak · Initial pricing framework based on PRD §15.2 and §15.3. Two SKUs (Classroom, Centre), per-SKU fit logic, pilot pricing, defensive floors, open decisions P1–P9.
- **v0.2 · 28 October 2026** · Deepak · Folded in the TeachFX India market analysis. Added §1.0 market context, §9.8 defence against Teachmint comparisons, §11 Trojan-horse positioning, §12 "what's different for schools", §13 competitive positioning.
- **v0.3 · 10 November 2026** · Deepak · **Restructured to two tiers: B2B (Starter / Growth / Scale / Enterprise, with hard caps on students + recording hours) and B2C (Student at ₹299/month + annual; Private Trainer with Free + Pro; 20 % revenue share past 5 students).** Added DPDP compliance gate on under-18 B2C (new P10). Added B2B2C bridge (§3.5). Added §13 team-discussion suggestions (freemium, referral, family discount, geo-pricing, compliance pack, franchise rate, trainer onboarding programme, consent-SaaS). Old Classroom/Centre SKUs retired.
