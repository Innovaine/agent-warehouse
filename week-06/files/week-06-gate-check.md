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