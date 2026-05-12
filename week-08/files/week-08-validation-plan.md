# Week 8 — Validation Experiments (Non-negotiable)

## Experiment 1: Customer Conversation Sprint
**Owner:** Product  
**Timeline:** Mon–Wed EOW  
**Target:** 5 conversations (mix of existing users, warm leads, target personas)

**Script opening:**
- "We launched API Spend Snapshot for engineering teams burning cash on cloud APIs. Have you used it, or does the problem ring true?"
- "If we could show you exactly which APIs are runaway costs and suggest fixes, would that be worth paying for?"

**Data to capture:**
- Did they try it? Yes/No + why
- Willingness to talk: Yes/No
- Estimated pain (scale 1–10): __
- Price sensitivity: "Would you pay $X/mo?" (test $500, $1000, $2000)
- One specific use case or blocker

**Success criteria:** 1 customer willing to do a deeper engagement call OR 2+ customers confirm problem resonates

**Killer question:** "What would have to be true for you to *pay* for this?"

---

## Experiment 2: Manual Audit Labor Baseline
**Owner:** Engineering + Product  
**Timeline:** This week, one full cycle  
**Target:** One complete audit for a real or test customer (internal if necessary)

**Scope:** Pick one SaaS customer (real if we have warm intro, internal shadow if not)
- List all APIs in use (from docs or interview)
- Estimate spend per API (from CloudWatch, billing, or educated guess)
- Identify top 3 runaway costs
- Recommend one fix (kill unused API, throttle over-calling, or switch provider)
- Document every step + time spent

**Data to capture:**
- Total time (hours)
- Where we got stuck (data access? API docs? math?)
- What could be automated vs. manual
- Cost to deliver (your hourly rate × hours)

**Success criteria:** Repeatable checklist + time estimate ±20% + one concrete blocker identified

**Killer question:** "At this labor cost, what price per audit lets us survive?"

---

## Experiment 3: Competitive Gap Mapping
**Owner:** Product  
**Timeline:** Wed  
**Target:** Documented grid + one-sentence differentiation

**Research targets:**
1. AWS Cost Explorer (free, built-in, what does it show?)
2. Cloudflare Billing + Analytics (for edge/API customers)
3. LaunchDarkly's spend insights (if they have it)

**Per tool, document:**
- Core feature (what does it measure?)
- Price (free, tiered, custom?)
- UX (dashboard, alerting, recommendations?)
- Gap we see (what can *we* do they can't?)

**Success criteria:** Grid completed + one verified gap (test it with a customer conversation)

**Killer question:** "Why would a team choose us over the free AWS tool?"

---

## Experiment 4: Acquisition Channel Test
**Owner:** Growth/Product  
**Timeline:** Mon–Fri  
**Target:** 10 attempts on ONE channel; measure response

**Pick your channel** (choose one, not all):
- **Organic:** Post 2 threads on Hacker News / Dev.to / Reddit /r/devops; measure clicks, replies
- **Direct outreach:** Email 10 engineering leads at API-heavy companies (Stripe, Twilio, Plaid, Vercel, etc.); measure reply rate + qualification
- **Referral:** Ask 5 warm intros from investors, advisors, or early users; measure 2 meetings booked

**Data to capture per channel:**
- Attempts: 10
- Replies: __
- Qualified interest: __
- Response rate: __ %
- Cost per attempt: $0 or $X

**Success criteria:** ≥2 qualified conversations OR ≥20% response rate

**Killer question:** "Does this channel actually work, or are we guessing?"

---

## Experiment 5: Unit Economics Model
**Owner:** Finance/Product  
**Timeline:** Thu  
**Target:** One spreadsheet showing break-even

**Assumptions (you fill in):**
- Monthly price per audit: $XXX (test $500, $1000, $2000)
- Audits per customer per month: Y (probably 1–4)
- Manual audit cost (labor): $YYY
- Gross margin per customer: % 
- Target CAC: $ZZZ (implied by runway)
- Sales cycle: 3 months (assumption to validate)

**Output:**
- Breakeven customers: __
- Breakeven CAC: $__
- Runway at various CAC: (if CAC=$500, we can afford __ customers before money runs out)
- Path to 5 customers by Month 3: (requires X outbound/week at Y% conversion)

**Success criteria:** Model exists + one realistic path to 5 customers visible + team agrees on pricing range to test

**Killer question:** "At our actual labor cost, what has to be true about price/CAC for us to survive?"

---

## Weekly Cadence
- **Mon:** Kick off Exp 1, 2, 4
- **Wed:** Exp 3 complete; review Exp 1 early results; adjust outreach if needed
- **Thu:** Exp 5 model complete; all-hands review unit economics
- **Fri EOW:** Consolidate signals; decide Week 9 priorities

## Success Definition (ANY ONE = Week 8 wins)
- 1 customer says "yes, I'd use this" + agrees to follow-up
- 1 manual audit completed with time/cost baseline
- Competitive gap articulated + validated with customer
- Acquisition channel shows ≥20% response rate
- Unit economics model shows path to survival

---

**If NONE of these hit by Friday:** 
Pivot decision required. Either (a) reprice/reposition based on findings, (b) shift to different customer segment, or (c) kill and redeploy to next idea.