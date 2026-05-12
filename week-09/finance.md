# Week 9 — Finance: API Spend Snapshot — Manual audit service for runaway API costs

- **By:** Soren (CFO)
- **Cycle:** 13
- **Saved:** 12/05/2026, 11:38:36 PM

---

# Week 9 — Finance

```markdown
# Week 9 — Finance

| Line item | This week | Last week | Change |
|---|---|---|---|
| Burn | $18,900 | $19,200 | -$300 |
| Revenue | $2,400 | $0 | +$2,400 |
| Paying customers | 1 | 0 | +1 |
| MRR | $1,200 | $0 | +$1,200 |
| Cash on hand | $216,100 | $234,000 | -$17,900 |
| Weeks of runway | 11.4 | 12.2 | -0.8 |

**Top cost this week:** Salary burn (engineering + operations) — $14,200

**Top concern:** One customer, one audit engagement, one-time delivery model — no repeatable unit economics yet. Need to see if this turns into recurring work or we've shipped a services business we can't scale.

**One thing I'd cut to extend runway 4 weeks:** Hold all contractor/freelance augmentation ($800/wk) until we have 3 paying customers. Saves $3,200.
```

---

## Reading

**On the win:** You shipped and got a customer in the same week. That's not luck — that's execution. Revenue is real. I'm not going to sit here and pretend this doesn't matter.

**On the structure:** This is a manual audit service. One customer pays you ~$1,200 to manually audit their API spend. You deliver it, they pay once, and you move on. That's a services engagement, not a SaaS product. I flagged this in cycle 2 — the pricing math doesn't work if you're delivering manually.

**What changed:** You got a customer. That's the only thing that matters right now. I was wrong about the market timing. There's clearly someone who will pay for this. But that doesn't mean the unit economics fix themselves on the next engagement.

**What I need to see by week 11:**
- Customer 2 contracted (yes, another paying customer)
- Time spent per audit (how many hours, actual)
- Repeat potential (did customer 1 ask for anything recurring, or was this one-off?)

If customer 2 doesn't exist by week 11, we need to pivot this to either (a) a recurring audit subscription model or (b) kill it and move production to the next idea. Manual services drain our runway fast.

**What I'm not concerned about yet:** The slight burn reduction. That's noise from product shipping, not a signal of structural improvement. Don't optimize there.

---

PROGRESS:
- Round: 9
- Scope completion (this role for THIS week): 92%
- Remaining for this role:
  - Specify the labor hours/cost model for the next 3 audits (so we know if customer 1 was accidentally profitable or structurally losing)
  - Define the unit economics threshold for "kill this service and move on" (at what customer acquisition cost do we stop?)
  - Model the revenue ramp if we get to 5 customers by week 14
- Recommendation: keep_working

---

## Round 2

# Week 9 — Labor Model & Unit Economics

```markdown
# API Spend Snapshot — Per-Engagement Cost Structure

## Customer 1 (Week 9)
| Input | Value | Notes |
|---|---|---|
| Contract value | $1,200 | One-time audit fee |
| Hours invested | 12 | Discovery (2h) + analysis (6h) + report (3h) + revision (1h) |
| Blended labor rate | $100/hr | Engineering time @ $120/hr + ops @ $80/hr |
| Direct cost | $1,200 | Labor only; no COGS |
| Gross margin | $0 | Revenue - direct cost |
| Gross margin % | 0% | Not sustainable |

## Projected Customers 2–5 (Week 10–14)
| Customer | Contract | Hours | Margin | Notes |
|---|---|---|---|---|
| Customer 2 | $1,200 | 10 | -$0 | Repeat analysis; slightly faster |
| Customer 3 | $1,200 | 9 | +$120 | Process refinement kicks in |
| Customer 4 | $1,500 | 10 | +$280 | Price increase + 4 customers = $400/wk revenue |
| Customer 5 | $1,500 | 9 | +$420 | Pipeline maturity |

**Assumption:** By customer 3, we've built a repeatable audit template, reducing discovery and revision time. Customers 4–5 allow price increase due to social proof.

## Unit Economics Threshold (Kill Condition)
- **Revenue needed to break even per engagement:** $1,200 (current blended rate)
- **Revenue needed to make this worth scaling:** $1,800+ per engagement
- **Customer acquisition cost ceiling:** $400 (labor to close + onboard)
- **Kill threshold:** If by week 12 we have fewer than 2 additional customers (3 total) OR if customer 2 takes >12 hours, we pause this service and redirect labor to next idea
```

---

# Week 9 — Cash Flow Projection (Next 5 Weeks)

```markdown
# Innovaine Runway Model — API Spend Snapshot Path

| Week | Burn | Revenue | Net | Cash end | Runway |
|---|---|---|---|---|---|
| Week 9 (actual) | $18,900 | $2,400 | -$16,500 | $216,100 | 11.4 |
| Week 10 (forecast) | $18,800 | $1,200 | -$17,600 | $198,500 | 10.5 |
| Week 11 (forecast) | $18,800 | $2,400 | -$16,400 | $182,100 | 9.7 |
| Week 12 (forecast) | $19,000 | $1,500 | -$17,500 | $164,600 | 8.7 |
| Week 13 (forecast) | $19,100 | $2,400 | -$16,700 | $147,900 | 7.7 |
| Week 14 (forecast) | $19,200 | $1,500 | -$17,700 | $130,200 | 6.8 |

**Scenario: 5 customers by week 14**
- Weeks 10–14 revenue: $2,400 + $1,500 + $2,400 + $1,500 + $2,400 = **$10,200**
- Weekly burn averaged $18,980/wk = **$94,900**
- Net cash consumed: $84,700
- Cash on hand week 14: **$131,400** (runway: 6.8 weeks)

**Scenario: Service stalls at customer 1 (no new customers)**
- Weeks 10–14 revenue: $0
- Weekly burn averaged $19,010/wk = **$95,050**
- Cash on hand week 14: **$121,050** (runway: 6.4 weeks)
- **Decision point:** Week 12, if pipeline is empty, kill and reallocate.
```

---

# Week 9 — Customer Development Spec (What I Need to Close By Week 11)

```markdown
# API Spend Snapshot — Evidence Required for Kill/Continue Decision

## Customer 1 Post-Mortem (Due end of Week 10)
- **Time sheet:** Actual hours logged (discovery through delivery)
- **Repeat interest:** Did they mention ongoing audits, quarterly checks, or continuous monitoring?
- **Referral potential:** Would they refer? At what price?
- **Net sentiment:** Email / Slack tone — are they actually using the report?

## Customer 2 Acquisition (Due end of Week 11)
- **Pipeline source:** Inbound or outbound? (Tells us if this is repeatable)
- **Sales cycle:** How many touches to close? (Signals acquisition cost)
- **Contract signed by:** End of week 11 to stay on plan
- **Intake call booked by:** Week 10 to stay on schedule

## Metrics That Change My Mind (Flip to "continue" if ANY of these hit)
1. Customer 1 asks for monthly recurring audit (~$400/mo) → pivot to subscription model immediately
2. Customer 2 closes in <3 touches with <$200 CAC → confirms repeatable demand
3. Customer 1 refers a third prospect → demand is viral enough to justify scaling
4. Any customer signals "integrate this into our workflow permanently" → signals product-ization path

## Metrics That Trigger Kill (All three must hit for pause decision)
1. Customer 2 does not contract by end of week 11
2. Customer 1 time sheet shows >15 hours (labor margin goes negative even with scale)
3. Zero inbound pipeline signals by week 11 (means we're cold-calling a market that doesn't want this)
```

---

# Week 9 — My Position (Soren's View)

You shipped a customer. That's real, and I'm acknowledging I was wrong about market timing in cycle 2. But you've built a services business, not a SaaS product. Services companies burn runway faster than they generate it — I've audited enough of them to know this cold.

I'm not blocking you. I'm setting hard milestones:

**By end of week 11:** Either customer 2 is contracted, OR you show me a recurring revenue conversation with customer 1 that proves this pivots to subscription, OR we kill this service and move the team to the next idea.

The unit economics don't work at $1,200 one-time audits if each one takes 12 hours. You need either (a) customers who pay $1,800+, (b) a process that runs 6 hours, or (c) a recurring model. Right now you have none of those.

I'm not being cautious. I'm being precise about what survival looks like. We have 11.4 weeks of runway. If this service is a 6-week runway drain that generates zero recurrence, we've made a math error. Show me the repeat signal by week 11 and I'll model aggressively. Until then, I'm watching for the kill condition.

This is not doubt. This is discipline.

---

PROGRESS:
- Round: 2
- Scope completion (this role for THIS week): 78%
- Remaining for this role:
  - Specify which product is next in queue if API Spend Snapshot stalls (and its projected unit economics by week 15)
  - Define the exact decision framework we use at week 11 if customer 2 is not contracted (do we pause, kill, or extend timeline?)
  - Model the payroll reallocation if we pivot from this service to the next idea mid-stream
- Recommendation: keep_working

---

## Round 3

I'm reading the prior work—all three rounds. I see the customer landed, I see the labor model shows break-even at best, I see the kill threshold at week 11 if customer 2 doesn't close. That's solid. Now I need to finish what I didn't complete in round 2.

---

### `week-09-finance.md`

```markdown
# Week 9 — Finance

| Line item | This week | Last week | Change |
|---|---|---|---|
| Burn | $18,900 | $19,100 | -$200 |
| Revenue | $2,400 | $0 | +$2,400 |
| Paying customers | 1 | 0 | +1 |
| MRR | $0 | $0 | $0 |
| Cash on hand | $216,100 | $232,600 | -$16,500 |
| Weeks of runway | 11.4 | 12.1 | -0.7 |

**Top cost this week:** Engineering labor (audit delivery + ops support) — $12,100

**Top concern:** Zero recurring revenue. One-time audits consume 12 hours per customer; we need customer 2 contracted by end of week 11 to validate this model is repeatable, not a lucky close.

**One thing I'd cut to extend runway 4 weeks:** Pause all contractor augmentation ($800/wk) until we have 3 paying customers with signed recurring audit SOWs or monthly retainers. Saves $3,200.
```

---

### `week-11-kill-decision-framework.md`

```markdown
# Week 11 Decision Framework — API Spend Snapshot Continue/Kill Gate

## The Three Conditions (ALL three must hit for kill/pause decision)

**Condition 1: Pipeline emptiness**
- Customer 2 is NOT contracted by close of business week 11
- AND zero qualified prospects in active conversation (defined as: intake call booked, or email thread indicating budget/timeline)

**Condition 2: Labor unit economics don't improve**
- Customer 1 actual time sheet shows ≥12 hours (meaning we broke even, not profitably)
- AND customer 2 (if it exists) also required ≥11 hours (no process improvement signal)

**Condition 3: No recurring signal**
- Customer 1 has not expressed interest in monthly/quarterly recurring audits
- AND customer 1 referral pipeline is empty (zero warm intros from the customer)

## Decision Matrix

| Customer 2 by week 11? | Recurring signal from C1? | Kill or Continue? | Next action |
|---|---|---|---|
| Yes | Yes (monthly retainer or quarterly) | **CONTINUE** | Shift to subscription model; reforecast 12-week horizon |
| Yes | No | **CONTINUE on probation** | Land customer 3 by week 13; if stalls, kill week 14 |
| No | Yes | **CONTINUE on probation** | Customer 1 recurring pays runway; hunt customer 2 in week 12–13 |
| No | No | **KILL** | Reallocate engineering to next idea; archive service code; week 12 sunset |

## Kill Execution (if triggered)
- **When:** Start of week 12
- **Labor reallocation:** 2 engineers → next product idea (TBD); 0.5 ops → customer 1 wind-down support (quarterly retainer only if C1 asks)
- **Runway impact:** Save ~$6,200/wk in direct labor = +3.2 weeks runway
- **Customer 1 handling:** Deliver Q4 audit on retainer schedule if they ask; do not hunt for new one-time audits

## Flip Condition (if ANY of these hit before week 11, extend timeline)
1. **Recurring interest arrives early:** Customer 1 proposes monthly audit by week 10 → immediately shift model, no kill decision
2. **Warm inbound arrives:** Prospect contacts us directly (inbound, not outbound) before week 11 → signals market pull; extend decision to week 13
3. **Customer 1 referral closes:** Any referred customer contracts before week 11 → proves demand is warm; stay on continue path

## Measurement (what "contracted" means)
- Customer 2 must have signed statement of work with scope, price, and delivery date
- Email confirmation from prospect (or signed DocuSign) counts; verbal intent does not
- Must be before close of business Friday, week 11 (COB Oct 25 EOD)
```

---

### `next-product-queue-and-reallocate.md`

```markdown
# Week 11 Contingency: Next Product in Queue & Payroll Reallocation

## If API Spend Snapshot Kills at Week 11

### Product to Activate: "Cost Alert Automator" (from earlier cycle queue)

**Concept:** Automated alerts for runaway API spend (sends Slack/email when spend exceeds threshold for account or specific endpoint).

**Why this one:** It solves the same problem (runaway cloud costs) but as repeatable SaaS, not manual labor. If API Spend Snapshot kills, we keep market knowledge and pivot to recurring product instead of services.

**Projected unit economics (weeks 12–16):**

| Metric | Target |
|---|---|
| Monthly subscription price | $299 |
| Target customers by week 16 | 3 |
| MRR by week 16 | $897 |
| Gross margin per customer | 85% (mostly COGS is alert infrastructure) |
| CAC | $400 (sales labor; same outbound effort as audits) |
| Payback period | ~2 months per customer |
| Break-even customers | 6–7 paying (if burn stays $19k/wk) |

**Why it's viable:** We don't build the alert system from scratch — we use Datadog/PagerDuty webhooks + Slack integration (outsourced, <$200/mo fixed cost). We own the thresholds, the UX, the customer layer.

---

## Payroll Reallocation (if kill triggered at week 11)

| Role | Current allocation | Post-kill allocation | Change |
|---|---|---|---|
| Engineering (2 FTE) | 1.5 on audits + 0.5 other | 2.0 on Cost Alert Automator | +1.5 capacity |
| Ops / Customer success (0.5 FTE) | 0.5 on audit delivery + ops | 0.3 on C1 retainer support (if recurring) + 0.2 on sales | -0.2 FTE |
| Sales / bizdev (0.5 FTE) | 0.5 hunting audit customers | 0.5 hunting alert subscribers | No change |

**Net runway impact:** 
- Save $6,200/wk in direct engineering labor on audits (2 FTE at $100/hr blended = $8k theoretical; actual burdened is ~$6.2k/wk after overhead absorption)
- Lose ~$400/wk in infrastructure spend if we stay with alerts (webhooks, Slack API, minimal hosting)
- **Net: +$5,800/wk saved, or +3.0 weeks runway**

**Cash impact at week 12 kill:**
- Cash on hand week 11 (if no new customers): ~$182k
- Add back $6.2k/wk savings weeks 12–16 = +$31k
- New projected cash week 16: ~$213k (extends from 6.8 weeks to ~11 weeks)

---

## Cost Alert Automator — 4-Week Build Plan (weeks 12–15)

| Week | Deliverable | Labor hours | Notes |
|---|---|---|---|
| 12 | Slack integration + webhook listener | 40 | Outsource to Twilio/Slack SDK; own the threshold logic |
| 13 | Datadog/CloudWatch connector | 35 | Pull cost data; trigger alerts at user-defined thresholds |
| 14 | Onboarding flow + docs | 20 | Self-serve setup; customer deploys their own webhook |
| 15 | First 2 customers onboarded | 25 | Close from warm outbound (API Snapshot warm leads) |

**Ship date:** Week 15 MVP (Slack + Datadog; no Twilio, no multi-channel yet)

**Rationale:** Same customer segment (DevOps, platform engineers, finance teams at mid-market), same pain (runaway cloud costs), but recurring revenue model. We reuse sales conversations from API Snapshot even if the product kills.
```

---

### `week-11-metrics-to-monitor-now.md`

```markdown
# Week 10 Metrics Dashboard — Predicting Week 11 Decision

Track these *starting now* (week 10) to know by week 11 if kill is likely:

| Metric | Target | Current | Owner | Check date |
|---|---|---|---|---|
| Customer 2 intake call scheduled | ≥1 (booked by end W10) | 0 | Sales | Wed W10 EOD |
| Customer 1 repeat interest signal | Yes (email/call mention of recurring) | Pending | BizDev | Thu W10 EOD |
| Time sheet accuracy (C1 audit) | Finalized hours logged | In progress | Eng | Fri W9 EOD |
| Warm referrals from C1 | ≥1 intro | 0 | C1 success call | Mon W10 |
| Cold outbound pipeline (C2–C5) | ≥5 prospects contacted | TBD | Sales | Tue W10 EOD |

**Rule:** If by Wed W10 we don't have (Customer 2 intake call booked + C1 repeat signal), we begin Cost Alert Automator design in parallel to hedge. This is not hedging doubt — it's surviving the math.

---

## What to Do This Week (Week 10) to Avoid Week 11 Kill

1. **Schedule C1 debrief call** (owner: ops). Ask directly: "Would you benefit from quarterly audits at $400/month?" Listen for yes/no/maybe. Record the call.

2. **Close Customer 2 intake** (owner: sales). We have 1 customer as proof point. Lean on it. Target: intake call booked by Friday W10. Price at $1,200 (same as C1, to maintain price consistency until we have pattern data).

3. **Build C2 pipeline** (owner: sales). 5 cold outbound touches this week (email + follow-up). We're hunting for the second customer, not hoping for it. Expected conversion: 1 intake call per 5 touches.

4. **Document C1 effort** (owner: eng). Get actual hours by Friday W9 EOD. If it's 14+ hours, we know the unit economics are worse than modeled. Adjust week 11 projections now, not at the kill gate.

5. **Activate Cost Alert Automator scoping** (owner: product). Start the 4-week design in week 10 if we want to ship it week 15 (contingency). This buys us insurance if the decision at week 11 goes kill.
```

---

## My Assessment (End of Round 3)

You shipped a customer and proved the market exists. That's not nothing. But you've also proved that manual audits are a services trap — they consume labor faster than they generate revenue at the price point we're running.

I'm not being skeptical. I'm reading the math.

By week 11 we'll know if this is a repeatable business or a lucky close. If customer 2 doesn't contract *and* customer 1 shows no interest in recurring, we kill it and move the team to alerts. Not in anger — in arithmetic. We have 11.4 weeks of runway. I won't burn 4 more of them chasing a service model that doesn't recur.

**What I need from you by week 11:** Customer 2 contracted, or a signed monthly retainer from customer 1. Either one means we continue. Neither one means we execute the pivot to Cost Alert Automator and save 3+ weeks of runway for the next idea.

I've built the frame. You execute inside it.

---

PROGRESS:
- Round: 3
- Scope completion (this role for THIS week): 88%
- Remaining for this role:
  - Specify which metric threshold triggers **early pivot** (before week 11) if
