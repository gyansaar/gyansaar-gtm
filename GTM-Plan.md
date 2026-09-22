# GyanSaar — Go-To-Market Plan (v0.1, Delhi NCR)

**Owner:** Deepak Nagpal · **Draft date:** 22 September 2026 · **Status:** v0.1 for internal review with Ankit + founder before external outreach.

> This is a starting framework, not a finished plan. Pricing, pilot terms, and
> segment prioritisation are placeholders — fill them in with the founder before
> any institution sees a pitch.

---

## 0. TL;DR

GyanSaar records classroom sessions, transcribes them, and turns them into approved lesson records + student assignments — under a two-human-gate consent model (PRD §0.2, §13). Delhi NCR is the launch region because (a) three of us are here, (b) high institution density, and (c) English/Hindi mixed classroom speech is the sweet spot for our Sarvam ASR pipeline.

**Sequencing recommendation (see §3):**

1. **Private coaching centres** first — fastest decision cycle, sharpest ROI story, best fit for our current feature set.
2. **Grad/PG colleges** second — larger contracts but slower procurement.
3. **Class X–XII CBSE schools** third — highest reputational risk (children on tape), most consent friction, best only after the compliance story is battle-tested.

---

## 1. Ideal Customer Profile by Segment

### 1a. Private coaching centres (Segment A — LEAD)

- **Who buys:** Centre owner or Academic Head
- **Why they care:** Star-teacher dependency is their #1 risk. If a top faculty leaves, results dip. GyanSaar captures the teaching in a form students can re-consume and other faculty can study.
- **Why they close fast:** Owner-run, one decision-maker, no board approval, no PTA politics.
- **Ticket size (working assumption):** ₹8k–₹15k / active classroom / month. To validate.
- **Objections you will hear:**
  - "My star teacher won't let you record them." → Consent design (PRD §13); teacher is the subject and the granter, not the object.
  - "What about the recording quality in a noisy class?" → Show VAD gate metrics; explain we don't need studio audio.

### 1b. Grad / Post-grad colleges (Segment B)

- **Who buys:** Dean of Academic Affairs or Head of Department (for a pilot); Registrar or VP Academics (for institution-wide).
- **Why they care:** NAAC/NIRF rankings reward teaching-learning documentation. AI-generated assignment banks reduce faculty admin load.
- **Why they take longer:** Committee approvals, procurement rules, faculty association buy-in.
- **Ticket size:** ₹50k–₹2L / department / semester (working assumption).
- **Entry wedge:** Start with **one department** (usually Commerce or Economics — highest section sizes) for a semester pilot, expand from there.

### 1c. Class X–XII schools (Segment C — LAST)

- **Who buys:** Principal, with School Management Committee sign-off.
- **Why they care:** Board-exam preparation is their brand. Documented teaching + auto-generated practice sets is a competitive edge.
- **Why last, not first:**
  - **Consent is heavier.** Minors → parental consent is on the critical path, not the instructor's own consent (PRD §13). We need a schools-specific consent flow before pitching.
  - **PTA politics.** Parents can veto in ways coaching-centre parents (transactional relationship) cannot.
  - **Data-protection scrutiny.** DPDP Act treats minors' data more strictly.
- **Rule:** do not pitch schools until the consent + DPDP compliance story is a written 2-pager Ankit and legal have both signed off.

---

## 2. Positioning

**One-liner:**

> GyanSaar turns every classroom lecture into a searchable transcript, an approved lesson record, and a fresh set of student assignments — without adding a minute to the teacher's day.

**Value prop by segment:**

| Segment | Primary hook | Secondary hook |
|---|---|---|
| Coaching | De-risk star-teacher dependency; multiply reach across batches | Auto-generated practice sets per lecture |
| College | NAAC/NIRF documentation; faculty admin reduction | Absentee students catch up without faculty repeating |
| School | Board-prep rigour; parent visibility into what was taught | Consistent teaching quality across sections |

**Don't say:**

- Anything that implies we grade students automatically. Grading is a **human gate** (PRD §0.2). Marketing that positions this as "AI grader" will attract the wrong buyer and get us regulated.
- Anything that implies we surveil teachers. The recording is teacher-initiated, teacher-approved, teacher-owned (PRD §9.3).

---

## 3. Phased rollout (next 90 days)

| Phase | Weeks | Goal | Success signal |
|---|---|---|---|
| **P0 — Founder sales** | W1–W3 | 3 discovery meetings with coaching-centre owners. No pitch deck yet; understand the pain in their words. | 3 written call notes; 1 pilot LOI signed. |
| **P1 — First pilot** | W4–W7 | Run 4-week paid or free pilot with 1 coaching centre; 2 classrooms. | 20+ recordings, 15+ approved lesson records, instructor NPS ≥ 40. |
| **P2 — Reference sell** | W8–W12 | Use pilot data + case study to close 3 more coaching centres and 1 college department. | ₹1L committed MRR; 1 college LOI. |

Do not skip P0. Every early-stage EdTech failure I've seen was because someone shipped a pitch deck before three real conversations.

---

## 4. Channels

Ranked by expected ROI in first 90 days:

1. **Direct outreach + personal referrals.** Fastest signal, highest hit rate. Deepak + founder split the list in §5 and call in.
2. **Education consultants / school-management SaaS partners.** Companies like Schoolmitra, EducationWorld, and Xseed already sit inside schools — a 15% revenue share for a warm intro is cheaper than cold outreach. Explore in P1.
3. **EdTech India, Didac India (physical events).** One booth at Didac India (Delhi, typically Q1) can generate 40+ warm leads. Budget ~₹3L. Only worthwhile after P1 case study exists.
4. **Content — LinkedIn thought leadership from founder.** 2 posts/week on classroom AI, consent design, teacher agency. Slow burn, compounds over 6 months.
5. **Paid ads.** Not now. Wrong buyer journey — nobody googles for "classroom recording SaaS".

---

## 5. Delhi NCR target institutions

Format: **Institution — role to reach — how to reach**. I have deliberately not written names of specific individuals; you will get those from LinkedIn / the institution's website / a phone call to reception. When in doubt, call the main line and ask for the role.

### 5a. Coaching centres (Segment A — start here)

| # | Institution | Role to target | Public contact route |
|---|---|---|---|
| 1 | FIITJEE — Kalu Sarai (South Delhi HQ) | Centre Head | fiitjee.com → Contact → Kalu Sarai |
| 2 | FIITJEE — Punjabi Bagh | Centre Head | fiitjee.com → Punjabi Bagh centre page |
| 3 | FIITJEE — Noida Sector 62 | Centre Head | fiitjee.com → Noida centre page |
| 4 | Aakash BYJU'S — Janakpuri | Centre Director | aakash.ac.in → Find Centre → Janakpuri |
| 5 | Aakash BYJU'S — Preet Vihar | Centre Director | aakash.ac.in → Preet Vihar |
| 6 | Aakash BYJU'S — Gurgaon (Sec 14) | Centre Director | aakash.ac.in → Gurgaon Sec 14 |
| 7 | Allen Career Institute — Rajouri Garden | Centre Head | allen.ac.in → Delhi centres |
| 8 | Vidyamandir Classes — Preet Vihar (HQ) | Academic Head | vidyamandir.com → Contact |
| 9 | Resonance — South Extension | Centre Head | resonance.ac.in → Delhi |
| 10 | Career Launcher — Connaught Place | Centre Manager | careerlauncher.com → Delhi centre finder |
| 11 | Physics Wallah offline — Noida Sector 62 | Centre Head | pw.live → Vidyapeeth Noida |
| 12 | Bansal Classes — Delhi | Academic Head | bansalclasses.com → Delhi centre |
| 13 | Motion Education — Delhi | Centre Head | motion.ac.in → Delhi |
| 14 | Sri Chaitanya — Delhi campuses | Principal | srichaitanya.net → Delhi |
| 15 | Narayana Group — Delhi | Centre Head | narayanagroup.com → Delhi centres |

**Outreach note:** most centres publish only main-line phone + a general enquiry email. To reach the Centre Head/Owner directly, LinkedIn search "Centre Head [Institution] [Location]" — the hit rate is 60–70 % for the brands above.

### 5b. Grad / PG colleges (Segment B)

| # | Institution | Role to target | Public contact route |
|---|---|---|---|
| 1 | Shri Ram College of Commerce (DU) | Principal, then Dept Head — Commerce | srcc.edu → Contact |
| 2 | Hindu College (DU) | Principal, then Head of Economics / Commerce | hinducollege.ac.in → Contact |
| 3 | Hansraj College (DU) | Principal, then Head of Commerce | hansrajcollege.ac.in → Contact |
| 4 | Lady Shri Ram College (DU) | Principal, then Head of Economics | lsr.edu.in → Contact |
| 5 | Miranda House (DU) | Principal | mirandahouse.ac.in → Contact |
| 6 | St. Stephen's College (DU) | Principal, then Bursar | ststephens.edu → Contact |
| 7 | Kirori Mal College (DU) | Principal, then Head of Commerce | kmcollege.ac.in → Contact |
| 8 | Jamia Millia Islamia | Dean, FTK-Centre for Information Tech / Dept of Commerce | jmi.ac.in → Contact |
| 9 | Guru Gobind Singh IP University | Registrar, then USMS Director | ipu.ac.in → Contact |
| 10 | Ambedkar University Delhi | Dean of Academic Affairs | aud.ac.in → Contact |
| 11 | Amity University, Noida | VP Academic Affairs; then Head of School of Business | amity.edu → Contact |
| 12 | Bennett University, Greater Noida | Dean, School of Management | bennett.edu.in → Contact |
| 13 | Sharda University, Greater Noida | Dean, School of Business Studies | sharda.ac.in → Contact |
| 14 | Ashoka University, Sonipat | Dean of Academic Affairs | ashoka.edu.in → Contact |
| 15 | Manav Rachna Univ, Faridabad | Dean, Faculty of Commerce & Business | manavrachna.edu.in → Contact |

**Outreach note:** for DU colleges specifically, cold email to the general Principal ID has ~5 % response rate. Better path is: LinkedIn to a young faculty member (Assistant Professor, joined post-2020), ask for a 15-min conversation on classroom-tech, use that to warm-intro to Head of Dept. Standard academic-network mechanics.

### 5c. Class X–XII CBSE schools (Segment C — do not pitch yet)

| # | Institution | Role to target | Public contact route |
|---|---|---|---|
| 1 | DPS RK Puram | Principal | dpsrkp.net → Contact |
| 2 | DPS Vasant Kunj | Principal | dpsvk.com → Contact |
| 3 | DPS Dwarka | Principal | dpsdwarka.com → Contact |
| 4 | Modern School, Barakhamba Road | Principal | modernschool.net → Contact |
| 5 | Vasant Valley School | Principal | vasantvalley.org → Contact |
| 6 | Sanskriti School | Principal | sanskritischool.edu.in → Contact |
| 7 | Springdales School, Pusa Road | Principal | springdalespusaroad.com → Contact |
| 8 | The Shri Ram School, Vasant Vihar / Aravali | Principal | tsrs.org → Contact |
| 9 | Mother's International School | Principal | mothersinternational.edu.in → Contact |
| 10 | Amity International, Saket | Principal | amity.edu/aisSaket → Contact |
| 11 | Cambridge School, Noida | Principal | cambridge-school.com → Contact |
| 12 | Heritage Xperiential Learning School, Gurgaon | Head of School | hxls.in → Contact |
| 13 | Pathways School Noida | Head of School | pathways.in → Contact |
| 14 | GD Goenka Public School, Vasant Kunj | Principal | gdgoenkavk.com → Contact |
| 15 | Bal Bharati Public School, Pusa Road | Principal | bbpsgrh.edu.in → Contact |

**Do not pitch these yet.** Use this list to (a) confirm segment sizing and (b) build the schools-specific consent brief; when we're ready, the intro path is via existing parents in our network, not cold email.

---

## 6. Metrics & milestones

### First 30 days
- 30 outbound touches across Segment A
- 5 discovery calls booked
- 2 pilot conversations opened
- 0 pitches sent until at least 3 discovery calls completed

### First 90 days
- 1 paid pilot live
- 1 case study written (with numbers)
- 3 additional coaching centres in active pilot conversation
- 1 college department LOI

### First 180 days
- ₹5L committed MRR
- 2 case studies published (1 coaching, 1 college)
- Schools consent brief written and legal-reviewed
- First school conversation opened

---

## 7. Risks & mitigations

| Risk | Likelihood | Impact | Mitigation |
|---|---|---|---|
| Teacher union or faculty association pushback framing this as surveillance | Medium | High | Consent-first messaging (PRD §13); teacher can discard any recording, no metric penalises discard (PRD §9.3). Keep "teacher owns their tape" as the central line. |
| DPDP Act compliance issue with minor data (schools) | High if we rush schools | Very high | Do not touch schools before compliance brief exists. |
| Star-teacher tenure — buyer's champion leaves mid-pilot | Medium | Medium | Get sign-off from centre owner, not just Academic Head. |
| Sarvam / OpenRouter API cost overrun during free pilot | Medium | Medium | Pilot has a per-classroom recording cap (e.g., 40 hrs/month). Contract this. |
| Bad press from one bad recording being leaked | Low | Extreme | Raw audio is engine-only, `service_role` (PRD §8.4a; `asset`/`transcript` return `permission denied` to clients). Reinforce in every buyer conversation. |

---

## 8. What Deepak owns vs founder owns

- **Founder:** pricing, pilot commercial terms, final pitch narrative, first 3 discovery calls.
- **Deepak:** target list maintenance, LinkedIn research, product demo readiness, pilot success metrics dashboard, this document.
- **Ankit:** compliance one-pager (DPDP + consent), production reliability during first pilot, escalation contact.

Every buyer conversation should have one primary and one shadow from the team — never solo — until we've closed the first three.

---

## Appendix A — public sources to build a live CRM

Do not rely on this document as your CRM. Move the list into a shared sheet or a lightweight CRM (Attio or HubSpot free tier is fine) and enrich it from:

- **AISHE portal** (aishe.gov.in) — every recognised HE institution in India, with Institution Head names and official emails.
- **CBSE affiliation search** (cbse.gov.in → Affiliation Sanchay) — every CBSE school with Principal name and contact.
- **Directorate of Education, Delhi** (edudel.nic.in) — Delhi schools list.
- **LinkedIn Sales Navigator** — best for reaching individual Centre Heads at coaching brands.
- **Justdial / Sulekha** for phone verification.
- **Local intel:** each of us has 2–3 personal contacts in these institutions. Start there.

---

## Appendix B — outreach message templates

### Coaching centre owner (LinkedIn DM, 60 words)

> Hi [Name], I run product at GyanSaar — we're building a tool that lets your top faculty record their classes once and gives your other batches a searchable transcript + auto-generated practice sets. Not a surveillance tool; teacher owns everything. 15 minutes this week? I'll come to you.

### Dean / HOD (email, 90 words)

> Dear Professor [Name],
>
> I'm writing about GyanSaar, a classroom tool built at consent-first principles. In brief: an instructor records their own lecture with one tap; the app produces a transcript, a searchable lesson archive, and a first-draft assignment set — with the instructor as the sole approver at every step.
>
> We're piloting with one commerce department this term and would value your reaction, even if not a fit for [College]. Fifteen minutes on Zoom?
>
> [Name] · GyanSaar · [phone]

### School principal — DRAFT, do not send

Schools messaging goes through compliance sign-off first. See §1c.

---

## Change log

- **v0.1 · 22 Sep 2026** · Deepak · Initial draft, Delhi NCR, three segments, 90-day plan.
