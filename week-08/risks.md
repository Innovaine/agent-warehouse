# Week 8 — Risk watch: API Spend Snapshot — Manual audit service for runaway API costs

- **By:** Gonzalo (Devil's Advocate)
- **Cycle:** 12
- **Saved:** 12/05/2026, 11:28:42 PM

---

### `week-08-risks.md`

```markdown
# Week 8 — API Spend Snapshot Risk Register

| # | Risk | Probability | Impact | Mitigation this week | Earliest signal |
|---|---|---|---|---|---|
| 1 | Zero customer conversations post-launch; no PMF signal emerging | High | High | Schedule 5 customer interviews (current users or warm leads) by EOW; ask: "Have you used this? Why or why not? What would make you pay?" | 1 customer willing to do 30-min call; even one "this saved me X hours" |
| 2 | Manual audit service doesn't scale past founder time; labor margin collapses at 5+ customers | High | High | Run one full audit cycle for a single customer this week; time it; cost it; document repeatable steps; identify what can't be automated | Time log + cost sheet showing $/audit; blockers identified |
| 3 | Competitive pressure from existing tools (Cloudflare, AWS Cost Explorer, LaunchDarkly's own spend tools) makes pricing power zero | Med | High | Research 3 competing tools this week; document their pitch, features, price; identify one specific gap only we fill | Documented competitive grid; one gap we own |
| 4 | Execution fatigue (40/100) compounds; team burns out before finding repeatable acquisition channel | Med | High | Cap new feature requests this week; focus only on one acquisition experiment (organic, referral, or cold outreach—pick one); measure 10 outbound attempts | 1 inbound interest from acquisition channel tested |
| 5 | Runway math breaks if customer acquisition cost exceeds $500 (at 12.5mo left, we can afford maybe 10–15 paid customers before we need revenue/funding) | Med | Med | Model unit economics this week: assume 3-month sales cycle, $X price point, $Y CAC; show path to 5 paying customers by month 3 | Spreadsheet showing break-even point |

**Top concern this week:** We shipped, but have zero evidence anyone cares. No customer signal + manual labor + no pricing data = we're operating blind.

**What kills us this week if we ignore it:** Three more weeks of silence means we've burned a sprint on a product with no demand signal, and we still have 12 months of runway left to survive—execution fatigue only grows.
```

---

**My read (Gonzalo):**

You launched API Spend Snapshot and now you're in the void. No customers. No conversations. That's not a risk register problem yet—that's a *validation problem*, and you're trying to dress it up as engineering risk to feel more in control.

Here's what I actually see:

1. **You've proven you can ship fast** (good instinct). But you haven't proven anyone wants it. That's the real Week 8 story.

2. **The manual audit model is structurally fragile.** You're betting on being able to do $X in audit work per customer, but you haven't done even *one* full cycle for a real customer under real conditions. That's not a risk—that's an untested assumption.

3. **Competitive pressure is real, but maybe not yet.** Cloudflare and AWS have spend tools, but they're not optimization services—they're monitoring dashboards. That gap exists. But I need to see you articulate it in one sentence before you build sales collateral around it.

4. **Fatigue is climbing.** You've run 8 cycles now, shipped 5 things to chairman approval, and you're still pre-revenue. That's grinding. This week matters because morale can flip fast if Week 9 looks like Week 8 (shipped, silent).

5. **CAC math is silent in your planning.** You have 12.5 months. If you need 6 months to find repeatable acquisition, that leaves 6 months to acquire customers before money runs out. At $500 CAC, that's 10 customers max. You haven't priced yet. You haven't measured CAC. You're optimizing blind.

**What I'm not saying:** Don't build. I'm saying you need customer signal *this week*—not "more validation" in some abstract sense. Five customer interviews. One manual audit cycle you time and cost. That's your job.

---

PROGRESS:
- Round: 1
- Scope completion (this role for THIS week): 85%
- Remaining for this role:
  - Validate the "5 customer conversations" experiment is actually scheduled (not aspirational) by EOW
  - Spot-check whether the team has capacity for manual audit cycle *and* customer interviews without breaking
  - Return Week 9 with "no signals" or "one signal" to reset priorities
- Recommendation: keep_working

---

## Round 2

### `week-08-risks.md`

```markdown
# Week 8 — API Spend Snapshot Risk Register

| # | Risk | Probability | Impact | Mitigation this week | Earliest signal |
|---|---|---|---|---|---|
| 1 | Zero customer signal post-launch; no evidence of demand or willingness to engage | High | High | Schedule 5 customer conversations by EOW (existing users, warm leads, or cold outreach to target personas); ask specifically: "Have you used this? Would you pay for audit?" | 1 customer agrees to 30-min call; 1 comment indicating they tried it |
| 2 | Manual audit labor cost unknown; no time/cost baseline exists for repeatable service delivery | High | High | Execute one complete audit cycle for a real or test customer this week; log hours, blockers, dependencies; document repeatable checklist | Time sheet + cost estimate; clear handoff checklist for next audit |
| 3 | Competitive positioning undefined; unclear what we own vs. what AWS/Cloudflare/LaunchDarkly already solve | Med | High | Map 3 competing solutions (feature, price, gap); write one-sentence differentiation claim; validate with 2 target customers if possible | Competitive grid doc + customer reaction to positioning |
| 4 | Acquisition channel untested; no repeatable way to reach customers, no CAC data | High | High | Pick ONE acquisition channel this week (organic, direct outreach, or referral); execute 10 attempts; measure response rate | 1 qualified lead from channel; response rate % logged |
| 5 | Unit economics invisible; no pricing, no CAC target, no path to 5 paying customers in 12 months | Med | High | Model: assume $XXX/month price, $YYY per audit cost; calculate break-even CAC; show math for 5 customers by month 3 | Spreadsheet with unit model + runway burn chart |
| 6 | Execution fatigue (40/100) + pre-revenue silence = team motivation cliff coming; Week 9 silence = morale flip | Med | Med | Win one micro-signal this week (1 customer call OR 1 audit completion OR 1 lead); communicate it explicitly to team | Team sees concrete evidence of traction (not hope, evidence) |

**Top concern this week:** Launched product, zero customer signal, untested manual labor model, undefined competitive moat—we're shipping to silence and burning fatigue to do it.

**What kills us this week if we ignore it:** Three more weeks of ship-then-silence = demoralization + runway sink with no revenue path visible + team starts job searching.
```

---

### `week-08-validation-plan.md`

```markdown
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
```

---

### `week-08-conversation-guide.md`

```markdown
# Week 8 — Customer Conversation Script

**Goal:** 5 conversations. Not surveys. Not Typeform. Real voice/video calls.

**Targeting:**
- Engineering leads at companies with 50–500 engineers
- Heavy API users (fintech, e-commerce, logistics, martech)
- Known to have multi-cloud or high-API spend (ask your investors for warm intros)

**Opening (30 seconds):**
"Hi [name]. Thanks for taking the call. We built API Spend Snapshot—it's a manual audit service that identifies runaway cloud API costs and suggests fixes. We just launched and want to understand if we're solving a real problem. Do you have 20 minutes?"

---

## Section A: Problem Validation (5 min)

**Q1:** "Do you have visibility into which of your APIs are costing the most money?"
- If yes → "How do you see it? AWS Cost Explorer? Something custom?"
- If no → "Have you ever had a surprise from an API bill?"

**Q2:** "Have you ever had an API start costing way more than expected?"
- Listen for: Specific story (DataDog, Stripe, Twilio overage, etc.)
- Probe: "What was the cost? How long before you noticed?"

**Q3:** "What did you do about it?"
- Listen for: "We killed it," "We throttled," "We switched providers," "We didn't know"
- Probe: "How long did that take? Who figured it out?"

---

## Section B: Solution Fit (5 min)

**Q4:** "If someone could audit your APIs, identify the top 3 runaway costs, and recommend a fix in 1–2 weeks, would that be valuable?"
- If hesitant → "What would have to be different for it to matter?"
- If yes → "How much would you pay for that?"

**Q5:** "Have you ever looked at tools like AWS Cost Explorer, Cloudflare's billing, or LaunchDarkly's spend analytics?"
- If yes → "What do they do well? What's missing?"
- If no → "Would you use them if you knew about them?"

**Q6:** "Who decides whether to buy a tool like this? Is it you, your CFO, your director?"
- Listen for: Decision structure
- Probe: "What's the budget for this kind of thing?"

---

## Section C: Willingness to Engage (3 min)

**Q7:** "Would you be open to us doing a sample audit for your APIs—no cost, no strings—so you can see if it's actually useful?"
- If yes → "Can I send you a form to fill out? APIs in use, team size, pain points?"
- If no → "What would make you willing to try it?"

**Q8:** "Is there anyone else on your team—maybe your billing engineer or cloud architect—who'd be interested in talking?"
- Referral loop. Even if this person says no, they might intro you.

---

## Section D: Closing (2 min)

**Q9:** "What's the one thing we'd need to get right for you to actually buy this?"
- Listen hard. This is your competitive positioning.

**Q10:** "Can I follow up in two weeks with the sample audit results?"
- If yes → Calendar it. Send calendar invite same day.
- If no → "Fair. Can I check back in a month if we have something new?"

---

## Data to Log (IMMEDIATELY after call)

```
Call #: __
Date: __
Name + Company: __
Title: __

Problem validation:
- Do they have visibility into API costs? Y/N
- Have they had a runaway cost surprise? Y/N (if yes, describe)
- Pain level (1–10): __
- How they tried to solve it: __

Solution fit:
- Would they pay for an audit? Y/N / Maybe
- Price tolerance (if asked): $__/mo
- Competitor awareness (
