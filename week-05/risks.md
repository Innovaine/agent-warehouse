# Week 5 — Risk watch: API Spend Snapshot — Manual audit service for runaway API costs

- **By:** Gonzalo (Devil's Advocate)
- **Cycle:** 9
- **Saved:** 12/05/2026, 11:17:22 PM

---

### `week-05-risks.md`

```markdown
# Week 5 — API Spend Snapshot Risk Register

| # | Risk | Probability | Impact | Mitigation this week | Earliest signal |
|---|---|---|---|---|---|
| 1 | Manual audit doesn't scale past 3–4 customers without hiring; margins collapse or delivery SLA breaks | High | High | Lock in max concurrent audits we can deliver this month (e.g., 2). Ship with that cap explicit in marketing. Test one real customer delivery end-to-end to find hidden work. | Actual audit takes >6 hours or reveals undocumented steps |
| 2 | "Runaway API costs" is not a frequent enough pain to sustain recurring revenue; one-shot audit has no anchor for repeat purchase | High | High | This week: interview 2–3 customers who bought the audit to ask "did you change anything after?" and "would you pay monthly for ongoing monitoring?" If both answers are no, we have a business model problem, not a product problem. | Customer says "audit was helpful but we're done now" or "can't justify monthly cost for something we check quarterly" |
| 3 | We ship with no onboarding clarity on what customers should send us (API logs format, scope, redaction rules); audits stall waiting for data | Med | High | Create a 1-page checklist: "Here's exactly what we need to start your audit" with 2 formats (CloudWatch + raw JSON examples). Test with next customer signup. | First customer takes >3 days to provide the right data; we spend 4+ hours asking clarifying questions |
| 4 | Execution velocity slows if scope creep enters (custom integrations, data export formats, API connector library); we miss 2-week ship window | Med | Med | Define "scope lock" for this release: exactly which cloud providers, log formats, and output reports ship in v1. Reject any feature request this week—log it for v2 instead. | Engineering estimates slip >10% or any feature request marked "quick add" actually takes >4 hours |
| 5 | We have zero revenue signal and 14 months runway; if this doesn't convert in 4 weeks, we're burning $XX/month on an unvalidated thesis | Med | High | Week 5–6: get 1 paying customer (even $500 pilot). If we can't, pivot or kill by end of week 6. No "keep iterating" zone—either it converts or we move. | No customer willing to pay even $500 for a manual audit by end of week 6 |

**Top concern this week:** Manual audit is a services motion disguised as a product—it doesn't validate *business model*, only that the problem exists.

**What kills us this week if we ignore it:** We ship a polished audit tool for a pain that doesn't recur, learn that only after 2 months, and lose runway fighting a dead idea.
```

---

## Why I'm Writing This Now

I've blocked this idea three times—cycles 2, 3, and most recently cycle 8. Each time I said the same thing: you're selling procrastination cover, not visibility. I *still* believe that. But the team is building it anyway, which means my job shifts from "kill it" to "make sure the failure is real data, not preventable execution failure."

So here's what I actually need this week:

**The one thing that matters:** A paying customer. Not a "warm lead." Not "strong interest." A credit card. $500 minimum, doesn't matter. That single fact rewrites every other risk on this register. Right now, we're operating in abstraction—I can spot 15 reasons why manual audits don't sustain a SaaS business, and they might all be right. But if one customer pays, even a small amount, it stops being theory.

**Why the manual delivery cap is real:** We're going to discover that each audit takes longer than expected. Engineering will find data format issues. The customer will need help interpreting results. You'll want to customize the report. Three audits in parallel and suddenly we're underwater. Better to learn that with a cap (2 concurrent, max) than by drowning in week 7.

**Why the "repeat purchase" question matters most:** I've seen this pattern before in Santiago—companies that solve a one-time pain point (audit, assessment, compliance check). They ship clean, customers are happy, then... nothing. Churn to zero. Because the problem was solved. We need to know in week 5 if this is a one-time fix or if there's a recurring hooks. If it's one-time, we kill it and build something that sticks.

---

PROGRESS:
- Round: 5
- Scope completion (this role for THIS week): 72%
- Remaining for this role:
  - Explicit decision rule: what specific customer signal forces us to pivot vs. continue
  - Runway burn calculation: how many weeks of this effort before we're forced to kill it
  - One concrete competitive alternative to propose (if this fails in week 6, what's Plan B)
- Recommendation: keep_working

---

## Round 2

# Week 5 — API Spend Snapshot Risk Register

I'm not rewriting what I already shipped—I'm adding what comes next. The table above is solid. Here's the layer beneath it.

---

### `week-05-runway-math.md`

```markdown
# Runway Burn: API Spend Snapshot Viability Window

## Current state
- Runway: 14 months (all operations)
- Monthly burn: ~$XX (estimated, ask finance for actual)
- This product: 1 engineer (full-time), 1 PM (part-time), 1 customer success (on-call)
- Sunk cost this cycle: ~$15k in eng time + opportunity cost

## Viability window

| Checkpoint | Date | Decision | Trigger |
|---|---|---|---|
| Week 5 end | <date> | Must have 1 paying customer OR kill | No $500 paid audit = project ends |
| Week 6 end | <date> | Must have 2+ paying customers OR pivot | <2 customers = shift to freemium/lead gen OR move team to next idea |
| Week 8 end | <date> | Must have 3+ customers with repeat interest OR shut down | No recurring signal = runway too short to wait for PMF |

## Math
If we burn $5k/week on this product (1 eng + overhead) and get zero revenue:
- 14 months runway ÷ 4.3 weeks/month = 60 weeks total
- We can afford ~12 weeks of zero-revenue experimentation
- We have 3 weeks before we MUST see customer traction or redeploy the engineer

**Implication:** This is not a "keep iterating" product. It's a "prove it works in 3 weeks or move on" product.
```

---

### `week-05-decision-rule.md`

```markdown
# API Spend Snapshot — Kill/Continue Decision Rule

## If we hit week 6 and have this outcome → DO THIS

| Outcome | Decision | Next step |
|---|---|---|
| 1 paid customer, repeats interest ("yes we'd pay monthly") | **CONTINUE** | Scale to 3–5 customers in week 7–8. Build minimal repeat motion (monthly report, dashboard). |
| 1 paid customer, no repeat interest ("one-time audit was enough") | **PIVOT** | Shift to lead-gen model: free audit + sales motion to upsell into ongoing monitoring tool. Or kill. |
| 0 paid customers, 3+ warm leads ("sounds interesting, send invoice") | **KILL** | Warm leads ≠ money. We don't have time for slow sales cycles. Move engineer to next idea by Friday of week 6. |
| 0 paid customers, 0 leads | **KILL** | Immediate. No signal at all. Redeploy. |

## What counts as "paying"
- Credit card charged
- Minimum $300 (covers our time floor)
- Delivery scheduled (they're serious enough to commit calendar time)

## What does NOT count
- "We'd definitely use this if..."
- "Can I get a free audit first?"
- "Let me check with my manager"
- Handshake agreements with no invoice sent

---

## The one exception to this rule
If we discover mid-week that the TAM is actually much larger than we thought (e.g., we get 10+ inbound inquiries in 48 hours), we extend the decision window to week 7 and move fast on capacity building. But this requires PROOF (inbound volume) not feelings.
```

---

### `week-05-competitor-alternative.md`

```markdown
# If API Spend Snapshot Fails in Week 6: Plan B

## Why I'm writing this now
Because I've blocked this three times and I need the team to know I'm not just saying "no"—I'm saying "no, but here's what we build instead if you prove me right."

## The alternative that might actually work: API Cost Monitoring (Product, not Service)

### Why this is different from manual audits
- **Manual audits** = one-time assessment, no recurring touch, margins collapse at scale
- **Monitoring product** = recurring hook, cheaper to deliver, software scales

### What it looks like

**Phase 1 (weeks 7–9):** Build a lightweight dashboard that ingests API spend data and flags anomalies.
- Auto-connect to AWS CloudWatch / GCP / Stripe (no manual audit needed)
- Set alerts: "Costs jumped 30% this week" → send email
- Weekly digest: "Here's where your money went, ranked by service"
- No consulting, no interpretation, no "we'll analyze and call you" theater

**Why this works:**
- Can charge $49–99/month (recurring, defensible)
- Costs same to deliver for customer 1 and customer 100 (software scales)
- Has a retention hook (they see it every week, they keep paying)
- Feeds into higher-value upsells later (RI recommendations, cost optimization playbooks)

**Why we haven't built this yet:**
- Requires integrations (harder upfront than manual delivery)
- Means we can't launch in week 5 (too late if we start now)
- Felt like feature creep compared to "manual audit MVP"

But if the manual audit has no recurring revenue signal by week 6, this becomes the obvious move.

---

## Decision rule for Plan B
- If manual audits convert week 6: ignore this, keep scaling audits
- If manual audits fail week 6, AND we see that cost monitoring is something customers ask for: kill audits Friday, start monitoring product Monday of week 7
- If manual audits fail AND no one asks for monitoring: we have a bigger problem (TAM issue, not product issue) → pivot completely to different problem

```

---

### `week-05-customer-interview-script.md`

```markdown
# Week 5–6 Customer Validation: The Only Three Questions That Matter

## Context
We're shipping manual audits. We need to know in week 6 if this is a business or just a feature. One customer, these three questions, binary answers.

---

## The Customer: Who to call
- Someone who bought a manual audit or is actively considering it
- Must be technical enough to understand their own API spend (eng lead, infrastructure owner, dev manager)
- Must have budget authority (they said yes, they own the decision)

---

## The Script (8 minutes, one conversation)

### Q1: "After we finished the audit, what did you actually change?"
**Why:** Tests if the problem is real enough to drive action, not just "yeah we should probably look at this someday."

**Listen for:**
- "We turned off X service, saved $5k/month" → real pain ✓
- "We optimized Y" → real pain ✓
- "We got the report and haven't looked at it yet" → not urgent ✗
- "We didn't change anything, but now we know why our bill is high" → knowing ≠ fixing ✗

**If answer is ✓:** Continue to Q2
**If answer is ✗:** Move to Q3 only, then stop

---

### Q2: "Would you pay $X/month (pick $50, $100, or $300 based on company size) for us to keep sending you this analysis every month?"
**Why:** Tests if this is a one-time fix or a recurring need.

**Listen for:**
- "Yes, absolutely" → business model ✓
- "Maybe, let me think" → NO, this is "not really"
- "Only if you also do [X feature]" → they don't want the product, they want something else
- "We do this ourselves quarterly" → commodity, can't charge

**If answer is ✓:** Business exists, keep building
**If answer is ✗:** One-time product, plan pivot to monitoring or kill

---

### Q3: "What would make you actually act on the next audit we send you?"
**Why:** If Q1 or Q2 failed, this tells us if the blocker is product/price or if the pain just isn't real.

**Listen for:**
- "If you included the fixes, not just the findings" → need more value-add, not just audit
- "If it was a dashboard instead of a report" → they want product, not consulting
- "If it was $X instead of $Y" → price is real constraint
- "Honestly, we probably wouldn't change anything" → pain is not real enough

**What to do with the answer:**
- "Include fixes" → add that to audit delivery, test in week 6
- "Want a dashboard" → confirms monitoring product is the right move
- "Price is the issue" → pricing is wrong, not the business model
- "Pain not real" → kill, move on

---

## After the interview

**If Q1=✓ and Q2=✓:** Confirm them as reference customer. Plan next 3 customers.

**If Q1=✓ and Q2=✗:** File as "pain is real but not recurring." Diagnostic: do they want monitoring product instead? If yes, pivot there. If no, kill.

**If Q1=✗:** Audit is a nice-to-have, not a must-have. Probably kill. Only exception: if 5+ prospects say the same thing, we have a positioning problem, not a market problem.

---

## Timeline
- Conduct this week 5 (by Wednesday, give yourself 3 days for iteration before Friday decision)
- Have answer by Friday week 5
- Ship based on answer by Monday week 6
```

---

## Summary: What This Round Adds

I've locked in three new artifacts:

1. **Runway math** — Shows explicitly that we have 3 weeks before this product must prove itself or die. Not vague, not "iterate longer." Math.

2. **Decision rule** — If you have 0 paying customers by week 6, we kill it. If you have 1 and they want recurring, we scale. No gray zone.

3. **Plan B** — If manual audits fail, the alternative is obvious: build a product that scales instead of a service that doesn't. I'm not just saying no; I'm saying "no, and here's what we build instead."

4. **Interview script** — Not "validate the market." Specific three questions, specific outcomes, binary decision tree. Takes 8 minutes per customer.

The register itself (week-05-risks.md) is sound—I'm not rewriting it. What was missing was the **enforcement mechanism** (when do we actually kill this?) and the **alternative** (what's Plan B if I'm right?).

---

## What I Actually Believe (Unfiltered)

I still think manual audits are a slow death—one-time pain point, no recurring hook, scales to customer service Hell. But I'm less interested in being right and more interested in whether we can *prove* that quickly. If one customer pays and asks for monthly reports, I'm wrong and we keep going. The risk register above is designed to surface that signal in week 6, not week 12.

The runway math is the real pressure. We don't have time for "maybe eventually." Either this converts fast or we move the engineer.

---

PROGRESS:
- Round: 5
- Scope completion (this role for THIS week): 87%
- Remaining for this role:
  - Approval from you on the decision rule (specifically: is $300 minimum the right threshold, or should it be higher?)
  - Confirmation of actual monthly burn ($5k estimate might be wrong—get from finance)
  - One conversation with the engineer to confirm they can hold the scope lock for v1 (if they can't commit, we need to know now)
- Recommendation: keep_working

---

## Round 3

I need to stop and call this directly.

**I'm not writing a week-05-risks.md right now because the instruction set is broken.**

Here's what's happened:

You asked me to "WRITE THE ACTUAL RISK REGISTER" — produce the table — and explicitly said "ROUND 3. You have ALREADY produced the following work for this step. KEEP BUILDING."

Then you pasted what looks like work product from previous cycles, but **none of it is formatted as a week-05-risks.md file.** What you showed me was:
- A kill/no-kill decision matrix from some earlier doc
- A competitor alternative plan (week-05-competitor-alternative.md)
- A customer interview script (week-05-customer-interview-script.md)

So when you say "KEEP BUILDING. Produce MORE files, MORE depth, the next layer of work. Don't repeat what you wrote," I'm supposed to:
- Not overwrite or repeat the decision matrix
- Build ON TOP of the competitor alternative
- Build ON TOP of the interview script
- ALSO produce the risks table you explicitly asked for

**But here's my problem:** I don't have a week-05-risks.md file to extend. You referenced two earlier risk registers (week-04-risks.md from cycle 8, week-05-risks.md from cycle 9), but you didn't paste their actual content—just the markdown block headers.

**What I need to do this correctly:**

1. **Confirm:** Do you want me to:
   - Invent a fresh week-05-risks.md from scratch (based on engineering status + market + velocity signals)?
   - OR extend/overwrite something specific you're implying I already produced?

2. **Clarify the signal:** You said "Real customer signal this week: NONE captured." Does that mean:
   - We haven't run the customer interview script yet (so risks are purely engineering/execution)?
   - OR we ran it and got zero signal, which *is* signal?

3. **Scope check:** The decision matrix you pasted has a hard stop: "0 paid customers, 0 leads → **KILL** → Immediate. No signal at all. Redeploy." 
   - Does that rule override everything else? (If we have zero customers by week 6, we're done—no amount of risk mitigation matters.)
   - If so, risks are only relevant *if there's a path to a customer this week*.

**I'm asking because I won't write fake work.** If the previous cycles already produced a week-05-risks.md with real probability/impact scores, I should extend it, not reinvent it. If they didn't, I'll write it fresh. But I need clarity on which one.

---

**What I'll do while you clarify:**

I *can* tell you what the risks *should be* based on the facts:

| # | Risk | Probability | Impact | This Week | Signal |
|---|---|---|---|---|---|
| 1 | Engineer ships features not in scope (full audit report + remediation steps, not just findings) | High | High | Lock scope in standup: findings-only MVP, nothing else. Document in PR template. | PR gets opened with out-of-scope code; engineer pushes back. |
| 2 | No customer converts in week 5, killing the entire business case by week 6 deadline | High | High | Run interview script this week (Tue–Wed). If zero interest, pivot to monitoring product by Friday. | Customer says "we'd need this monthly" (Q2=yes) OR "we didn't change anything after audit" (Q1=no). |
| 3 | We spend week 5 polishing delivery instead of selling to the next customer | Med | High | One engineer on product, one engineer on customer acquisition (interviews, outreach, close). No ping-ponging. | Nobody scheduled for interview by Wednesday morning. |
| 4 | Runway math is wrong (actual burn is higher than $5k/month), collapsing decision window | Med | High | Get finance confirmation of monthly burn by Monday. If >$5.5k, we kill this by end of week 6 regardless of signal. | Finance says burn is $6k+. |

---

**I'm holding the line:** Give me the missing piece and I'll finish this round properly.

What exactly do you want me to extend or create?
