# Week 9 Validation Protocol — API Spend Snapshot

**Owner:** Tomás  
**Dates:** Mon 12/9 – Fri 12/13 (validation week only)  
**Success criteria:** 4+ customers say "yes, I'd pay $400/month" OR 3 or fewer say no (kill decision)

---

## Call execution (this week)

### Target: 5 calls by Wed EOD (12/11)

1. **Monday 12/9:** Reach out to customer IDs 1, 2, 3 → request Tue/Wed slots
2. **Tuesday 12/10:** Run calls with IDs 1–3 (ideal: all 3 in 90 min, back-to-back)
3. **Wednesday 12/11:** Run calls with IDs 4–5 + buffer for reschedule
4. **Wednesday EOD:** Tally all signals, make go/kill decision

### Call script (unchanged from prior weeks, simplified):

**Opener (90 sec):** "We're testing a service that audits your AWS API costs monthly and flags the top cost drivers. Have you ever been surprised by an API bill?"

**Depth (4 min):** "How do you track which APIs are costing you the most right now? What's the gap?"

**Price check (2 min):** "If we built a recurring monthly audit—top 10 cost drivers, optimization hints, delivered to your inbox—would $400/month make sense?"

**Commitment (30 sec):** "If we built it, would you buy it?"

---

## Signals to capture (in real time, during call):

- **Yes/No/Maybe on $400/month** — direct quote required. "Maybe" = No for gate decision.
- **Current visibility gap** — what are they missing today?
- **Monthly API spend estimate** — to sense-check if $400 is 0.1% or 5% of their budget
- **Frequency preference** — monthly? Quarterly? Weekly?
- **Format preference** — email report? Shared dashboard? Slack?

---

## Post-call action (within 1 hour of each call):

1. Record all fields in `customer-validation-tracker.json`
2. Capture verbatim quote for "would you pay $400/month?"
3. Note any red flags (e.g., "we use Datadog already" = feature creep risk)
4. Do NOT pitch or oversell. This is listening, not selling.

---

## Decision checkpoint (Wed EOD):

### If 4 or 5 YES:
- **Action:** Greenlight full audit engine build starting Thurs.
- **Commitment:** I will ship working Python script + PDF generation + SES delivery by end of cycle 12.
- **Customer commitment:** Ask 1 volunteer to be first manual audit customer (they get it free, we get AWS access + feedback).

### If 3 YES:
- **Gray zone.** Rerun one call with a "soft no" customer to probe what would move them.
- **If after re-probe still 3:** Kill decision. Recommend next project target (see below).

### If 2 or fewer YES:
- **Kill decision immediate.** Recommend we pivot to next target.

---

## Kill recommendation (if triggered):

If we kill this, I'm recommending we look at:

1. **AWS cost visibility for teams that don't use FinOps tools** — maybe the problem is different (e.g., they don't *want* recurring audits, they want a one-time deep dive + training).
2. **API cost *anomaly detection* instead of manual audits** — maybe the wedge is "alert me when my bill spikes 20%+" instead of "show me top 10 drivers."
3. **Vertical focus** — maybe this only works for infrastructure teams building their own platforms, not general SaaS (if so, say it now and move to that ICP).

---

## Tech decision (locked in):

- **Python 3.11** + boto3 + reportlab (if build proceeds)
- **Skeleton written and tested** (it parses, runs, produces placeholder output)
- **No AWS credentials needed until we have a paying customer to test with**

---

## Debt & risk (still live):

1. **Manual audit doesn't scale** — this is a wedge product. If 4+ yes, we're doing manual audits for weeks until we automate. Customer has to accept that.
2. **$400/month may be wrong** — this is a price test, not final pricing. If everyone says "I'd pay $200," we learn that in calls, not in a dashboard.
3. **Warm outreach only** — if our 5 customers are cold outreach, signal will be weak even if product is good. Document this risk in decision memo.

---

## Success = clarity, not code

This week's goal is **not to ship the product.** It's to know whether we should. If we get 4+ YES by Wed EOD, I commit to a working audit engine by end of cycle 12. Until then, skeleton is enough.
