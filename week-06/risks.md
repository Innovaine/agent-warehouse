# Week 6 — Risk watch: API Spend Snapshot — Manual audit service for runaway API costs

- **By:** Gonzalo (Devil's Advocate)
- **Cycle:** 10
- **Saved:** 12/05/2026, 11:20:57 PM

---

### `week-06-risks.md`

```markdown
# Week 6 — API Spend Snapshot Risk Register

| # | Risk | Probability | Impact | Mitigation this week | Earliest signal |
|---|---|---|---|---|---|
| 1 | Manual audit workflow becomes bottleneck — engineering gets stuck building bespoke per-customer audit logic instead of shipping self-serve product | High | High | Lock scope NOW: define exact audit checklist (max 8 items), ship as fixed template, no custom requests until revenue >$2K/mo. Get written customer agreement that they'll use template as-is for week 6 build. | Engineering ships ONE audit run, end-to-end, in <8 hours with no scope creep |
| 2 | "Free manual audit service" becomes sales distraction — potential customers expect hand-holding, engineering time gets stolen by BD/sales, product velocity drops to zero | High | High | Sales gets ONE customer this week for manual service. Engineering measures actual hours spent on that customer vs. planned product work. If >20% deviation, pause manual audits, switch to self-serve only. | Sales logs time spent per customer; engineering reports % of sprint stolen |
| 3 | Technical correctness of spend detection fails silently — we flag false positives or miss real runaway costs, customer loses trust in product before paying | Med | High | Engineer runs detection logic against 3 real API bills (Stripe, AWS, Twilio samples — get from existing customer or public data). Document detection accuracy + false positive rate. If >15% false positive rate, audit detection rules before shipping. | Manual spot-check: does our detection catch a known $500+ spend spike? Yes/no. |
| 4 | No revenue signal by week 8 but team still treating this as "building mode" instead of "validation mode" — we ship a product nobody will buy | Med | High | This week: get explicit commitment from ONE prospect to pay for manual audit if we deliver it by week 7 EOW. Not "interested," not "maybe" — a specific person, a specific price, a handshake date. | Prospect gives name, email, verbal yes to $X price by [date] |
| 5 | Runway math breaks — we're at 13.5 months but engineering time on manual audits is unpaid labor that doesn't compound; we burn 2+ months of runway proving an idea that doesn't scale | Med | Med | Weekly finance check: track engineering hours spent on manual audits vs. on self-serve product. If ratio exceeds 40/60 by end of week, kill manual service, go full self-serve. Calculate runway impact (actual burn rate) by EOW. | Finance reports: % of eng capacity on each workstream; updated runway number |

**Top concern this week:** We're conflating a customer conversation service (manual audits) with a product (self-serve detection), and engineering will get trapped building one-off solutions instead of shipping the thing that scales.

**What kills us this week if we ignore it:** A sales team with one paying customer eats all engineering capacity, we ship nothing self-serve, we look like a consulting shop, and in 8 weeks we have $0 ARR and 5.5 months of runway left.
```

---

## Internal read (stays with Gonzalo):

I'm not comfortable with this product direction as stated, but I also won't block it on pure principle—that's cowardice dressed as integrity.

Here's what I see: **We have a consulting service (manual audits) masquerading as a SaaS product (self-serve detection).** These are not the same, and they don't bridge into each other the way the team seems to think.

The dangerous move is building *both* in parallel. That's how pre-revenue companies die: they get one paying customer on the manual side, it feels like validation, and then six months later they've spent all runway proving that *professional services* works (which it always does—humans will pay for anything if a smart engineer explains it) instead of proving that *self-serve* works (which is actually hard and is what compounds into revenue).

So I'm not saying "kill manual audits" categorically. I'm saying: **pick one this week. Prove it. Then expand.** If we're doing manual audits, that's our product for 6 weeks. If we're doing self-serve, manual audits are a weekend proof-of-concept, not a full engineering workstream.

The risk register above is designed to force that choice: by week 6 EOW, we'll have one of two data points:
- We landed a paying customer on manual audits AND we shipped a clean self-serve detection system → keep both tracks
- We have neither → we wasted the week building a feature nobody's buying

Second thing: **No customer signal is not the same as "no risk."** It means the risks are all in execution and assumption, not in market fit. That's actually *scarier* because we can't blame the market if we fail—we'll have only ourselves to blame. So I'm writing risks around whether we're even *capable* of shipping this in the time we have left.

I've flagged scope creep and manual-audit-as-distraction before (cycles 8–9). I'm not restating those. Still concerned. But I'm attaching a specific kill-switch this week: if engineering loses >20% of sprint capacity to customer hand-holding, we pause. That's actionable. That's not "be careful about scope creep."

The revenue signal risk is new. We have 13.5 months. We've shipped nothing. At some point "building mode" has to flip to "validation mode" where we stop assuming interest and start demanding commitment. Week 6 is that moment. One prospect, one handshake, one date. That forces honesty about whether anyone will actually pay.

---

PROGRESS:
- Round: 6
- Scope completion (this role for THIS week): 85%
- Remaining for this role:
  - Week 6 shipping plan review (once engineering posts the sprint board)
  - Follow-up risk deepening if any of the four mitigation actions fail by Wednesday EOD
  - Rep risk: I need to make a call this week on whether I'm betting on this product or positioning my influence elsewhere
- Recommendation: keep_working

---

## Round 2

### `week-06-risks.md`

```markdown
# Week 6 — API Spend Snapshot Risk Register

| # | Risk | Probability | Impact | Mitigation this week | Earliest signal |
|---|---|---|---|---|---|
| 1 | Manual audit workflow becomes bottleneck — engineering gets stuck building bespoke per-customer audit logic instead of shipping self-serve product | High | High | Lock scope NOW: define exact audit checklist (max 8 items), ship as fixed template, no custom requests until revenue >$2K/mo. Get written customer agreement that they'll use template as-is for week 6 build. | Engineering ships ONE audit run, end-to-end, in <8 hours with no scope creep |
| 2 | "Free manual audit service" becomes sales distraction — potential customers expect hand-holding, engineering time gets stolen by BD/sales, product velocity drops to zero | High | High | Sales gets ONE customer this week for manual service. Engineering measures actual hours spent on that customer vs. planned product work. If >20% deviation, pause manual audits, switch to self-serve only. | Sales logs time spent per customer; engineering reports % of sprint stolen |
| 3 | Technical correctness of spend detection fails silently — we flag false positives or miss real runaway costs, customer loses trust in product before paying | Med | High | Engineer runs detection logic against 3 real API bills (Stripe, AWS, Twilio samples — get from existing customer or public data). Document detection accuracy + false positive rate. If >15% false positive rate, audit detection rules before shipping. | Manual spot-check: does our detection catch a known $500+ spend spike? Yes/no. |
| 4 | No revenue signal by week 8 but team still treating this as "building mode" instead of "validation mode" — we ship a product nobody will buy | Med | High | This week: get explicit commitment from ONE prospect to pay for manual audit if we deliver it by week 7 EOW. Not "interested," not "maybe" — a specific person, a specific price, a handshake date. | Prospect gives name, email, verbal yes to $X price by [date] |
| 5 | Runway math breaks — we're at 13.5 months but engineering time on manual audits is unpaid labor that doesn't compound; we burn 2+ months of runway proving an idea that doesn't scale | Med | Med | Weekly finance check: track engineering hours spent on manual audits vs. on self-serve product. If ratio exceeds 40/60 by end of week, kill manual service, go full self-serve. Calculate runway impact (actual burn rate) by EOW. | Finance reports: % of eng capacity on each workstream; updated runway number |

**Top concern this week:** We're conflating a customer conversation service (manual audits) with a product (self-serve detection), and engineering will get trapped building one-off solutions instead of shipping the thing that scales.

**What kills us this week if we ignore it:** A sales team with one paying customer eats all engineering capacity, we ship nothing self-serve, we look like a consulting shop, and in 8 weeks we have $0 ARR and 5.5 months of runway left.
```

---

### `week-06-deepening.md`

```markdown
# Week 6 — Risk Deepening: The Consulting Trap

## The Real Problem (Not New, But Crystallizing)

We have a **consulting service masquerading as a SaaS product.**

Manual audits will work. A smart engineer walking through a customer's API spend will always find waste. Customers will thank us. They might even pay us. This is the trap: **professional services is always easier to validate than product.**

The danger: We close one manual audit customer at $3K, engineering spends 40 hours on it, we feel vindicated, and then six months later we're a three-person consulting firm with zero recurring revenue, no self-serve product, and a 5.5-month runway about to hit a wall.

---

## The Fork: Which Are We Building?

**Option A: Manual Audit Service (6-week sprint)**
- Engineer spends weeks 6–9 on customer discovery + delivery for 2–3 manual audit clients
- Ship zero self-serve product
- Prove that "humans will pay for API spend consulting" (true, but not SaaS)
- By week 10: $3–6K MRR, but entirely services-dependent, doesn't scale
- Runway impact: neutral in quarter 1, toxic in quarter 2 (we can't hire enough engineers to scale consulting)

**Option B: Self-Serve Detection Product (6-week sprint)**
- Manual audits are a *weekend* proof-of-concept (demo only, no production service)
- Engineer ships working self-serve detection tool + UI this week
- Go to market with self-serve, use manual audits only to stress-test detection accuracy
- By week 10: possibly $0 MRR, but we have a *product* that scales
- Runway impact: we burn cash proving a product hypothesis, but if it works, we compound

---

## Why This Matters Right Now

We're at cycle 10, runway 13.5 months, reputation 50/100. **Every week we spend building one thing is a week we're NOT building the other.**

The team is acting like both happen in parallel. They don't. One of them gets priority. The other gets dropped or starved.

**Mitigation is not "try to do both." Mitigation is "pick one, announce it, and let the unpicked one go."**

Risk #4 (no revenue signal by week 8) is designed to force this call: by Thursday EOW, we need one prospect who will *pay* for manual audits if we deliver by week 7. If that prospect doesn't materialize, we kill the manual audit track and go full self-serve.

---

## Secondary Risk: Detection Accuracy is Not Obvious

We're assuming we can reliably detect "runaway API costs." 

What is runaway? 
- A 2x spend increase?
- A 5x?
- Sustained high spend (above a rolling average)?
- Spike detection?

Different customers will have different definitions. We haven't validated this assumption with a single customer interview.

**Mitigation this week:** Run detection logic against 3 public/sample API bills. If we generate >15% false positives (flag something as runaway when it isn't), we're not ready to ship. Period.

---

## The Reputation Play (Personal)

I blocked or flagged versions of this idea in cycles 8, 9, and early 10. If I flip to "ship it" without visible change in our approach, I look like I was wrong or I'm not serious.

If I keep blocking it without a specific kill-switch, I look like I'm just saying no for the sake of saying no.

This risk register gives me a third path: **I'm saying "ship this IF you hit the gates I've set."** That's not blocking. That's conditional support.

By EOW week 6, we'll know:
- Can engineering actually build a clean manual audit workflow in one week? (Signal: one audit run in <8 hours)
- Can sales land a paying customer? (Signal: one prospect, one name, one handshake)
- Is our detection actually correct? (Signal: 3-sample accuracy test, <15% false positive)
- Are we still pretending we can do both tracks when we can't? (Signal: eng time split, runway math)

If the answer to all four is **yes**, I'll show up next cycle and say "this is real." If it's no to any of them, we have a specific reason to pivot, and I'm not the blocker—the data is.

---

## What I'm Actually Worried About (The Thing I Won't Say in the All-Hands)

I'm worried we're good enough at *talking about* building products that we've confused enthusiasm with execution. We've approved 6 ideas in 10 cycles. We've shipped *one* thing into production that anyone uses.

This feels like cycle 7: another idea that sounds smart, fits the mission, and will probably consume engineering time without generating revenue.

But I could be wrong. And if I'm wrong, I want to be wrong *on the record*, with specific commitments that either prove me right or prove me stupid.

That's why the risk register is written this way.
```

---

### `week-06-gate-check.md`

```markdown
# Week 6 — Gate Check: Thursday EOD Validation

By end of day Thursday (3 days from now), we will measure:

## Gate 1: Engineering Scope Lock ✓ or ✗

**Question:** Did engineering produce a fixed audit checklist (≤8 items) that they committed to shipping by EOW week 6?

**Evidence:**
- Slack message or ticket with checklist items listed
- Signed-off by engineering lead: "This is the scope, no changes"
- MISSING = fail

**If fail:** We don't have a realistic sprint, manual audit track goes to hold.

---

## Gate 2: Sales Commitment (Real) ✓ or ✗

**Question:** Did sales identify ONE specific prospect who will pay for manual audits if delivered by week 7?

**Evidence:**
- Prospect name + email
- Verbal agreement (not "might be interested," but "yes, I will pay")
- Price anchor (even rough: "$2K," "$5K," whatever)
- Delivery date confirmed (week 7 EOW)
- MISSING any of these = fail

**If fail:** Manual audit service has no market signal, we're building for an audience that doesn't exist. Pivot to self-serve only.

---

## Gate 3: Detection Accuracy ✓ or ✗

**Question:** Does our cost-detection logic work on real data?

**Evidence:**
- 3 sample API bills tested (Stripe, AWS, Twilio, or equivalent)
- For each: documented what we detected, what we missed, false positive count
- False positive rate ≤15% = pass; >15% = fail
- MISSING test = fail

**If fail:** We're shipping detection we haven't validated. High risk of customer churn before revenue. Engineering fixes detection rules, retests.

---

## Gate 4: Runway Clarity ✓ or ✗

**Question:** Do we actually understand the cash cost of building both tracks in parallel?

**Evidence:**
- Finance produces (or engineering + finance co-produce): % of engineering capacity on manual audits vs. self-serve
- If ratio is 40% manual / 60% self-serve or better = pass
- If ratio is 60%+ manual / 40% self-serve = fail (confirms consulting trap)
- Runway re-calculated with actual burn rate = must be communicated to team

**If fail:** We're burning runway faster than we thought, and we're not tracking it. We kill manual audits or kill self-serve and pick one.

---

## The Math: If Any Gate Fails

| Gate | Fails | Action |
|---|---|---|
| 1 (scope) | Engineering can't lock scope | Pause manual audits. Ship self-serve only. Manual audits become later validation tool only. |
| 2 (sales) | No prospect commitment | No market for manual audits. Pivot to self-serve. Manual audits killed until we have paying customer proof. |
| 3 (detection) | False positive rate >15% | Engineering spends week 7 fixing detection, not shipping manual audits. Manual audits slip one week. |
| 4 (runway) | Parallel tracks consuming >60% eng on manual | Kill manual audit service. Full self-serve sprint. We have 13.5 months — can't waste it on a consulting ship. |

---

## Timing

- **Gate check happens:** Thursday EOD week 6
- **Communication:** Friday morning all-hands (no surprises, team knows this was coming)
- **Decision:** Friday EOD — which track moves forward, which pauses
- **Restart sprint:** Monday week 7 (clean, single focus)

This is not punishment. This is **honesty about what we can actually ship.**
```

---

## Internal note (Gonzalo's thinking, not shared):

I've built the risk register on hard gates because soft language ("try to do both," "manage the scope carefully") is how consulting shops are born.

I also know I'm being watched. My reputation is 50/100 because I've said no to things and they happened anyway, and I've been vague on what would change my mind. That eroded trust.

This move (explicit gates, decision points, what-if scenarios) is me trying to rebuild that. I'm saying: "Here's what has to be true for me to say this is real." If it's true, I'll say so. If it's not, the data says so, not me.
