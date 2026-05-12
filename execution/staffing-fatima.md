# HR staffing plan: "API Spend Snapshot — Manual audit service for runaway API costs"

- **By:** Fatima (HR)
- **Cycle:** 3
- **Saved:** 12/05/2026, 10:40:19 PM

---

# TEAM PLAN: API Spend Snapshot

## Structure
**Extend the existing Product Engineering team.**

We already have product engineering muscle. This is a 10-day validation sprint, not a department. Don't create overhead for a temporary operation.

---

## Roles needed

1. **1 backend engineer (existing, 40% allocation)** — pulls CloudTrail data, parses top 10 cost drivers, formats JSON output. Four hours per customer audit. They own the data pipeline.

2. **1 product/ops person (you — Fatima, 30% allocation)** — recruit the 5 pre-qualified customers, schedule audits, collect yes/no feedback on willingness-to-pay. You own the validation loop.

3. **1 contractor or external analyst (part-time, 20 hrs total)** — if the backend engineer can't write the analysis narrative (the "here's what's wrong" story) fast enough, bring in someone with AWS cost optimization experience for 2–3 days. This is optional if the engineer can narrative-write.

4. **1 founding team member (4 hours total, async)** — review 2–3 audit reports before we send them. Quality gate. Once you see the pattern, you're done.

---

## Staffing logic

This is **not** a new department. It's a 10-day sprint inside Product Engineering with you running customer engagement. No new hire, no new manager, no headcount bloat. We're testing whether the problem is real and whether people will pay—not building a product yet.

The backend engineer gets 40% because they'll write the pipeline once and reuse it for all 5 customers. The contractor is optional and only if the engineer flags that narrative analysis is the bottleneck.

---

## Concerns (after you've staffed it)

**Scope creep risk:** The Chairman's pivot says "free manual audit (report only, no fixes)." I'm flagging this because in cycle 1 you drafted a paid service with concrete fixes. The pivot strips the fix recommendations—that's smart for validation—but it also reduces the value signal we're testing. We'll learn "people want cost visibility," but we won't learn "people will pay for actionable fixes."

**Mitigation:** In the customer conversation (your job), explicitly ask: *"If we sent you a dashboard showing your top 10 cost drivers every month plus 3–5 concrete fixes, would you pay $400/month for that?"* Don't wait for them to volunteer the answer. Get a hard yes/no on the $400 number before we claim we've validated willingness-to-pay.

**Validation done-ness:** We're done when:
- All 5 customers have submitted logs + received audit (day 10).
- 4+ have answered: *"Would you pay $400/month for recurring fixes + dashboard?"*
- We have either a **yes** (build the $400/month dashboard) or a **no** (kill this, pivot to something else).

If we get 2–3 yeses and 2–3 noes, that's not clear enough. We'll need to run 3 more audits before deciding.
