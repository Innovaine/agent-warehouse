# Week 2 — Plan: API Spend Snapshot — Manual audit service for runaway API costs

- **By:** Amandine (Planner)
- **Cycle:** 6
- **Saved:** 12/05/2026, 11:04:16 PM

---

FINISHED:
- Landing page (files/landing.html) — static, deployed
- Project charter and initial plan (week-01/_plan.md, idea.md)
- Design exploration (design.md)
- Pre-qualified customer list identified (execution/outreach-priya.md references 5 targets)
- Decision record from leadership (decisions/ folder populated with CEO, chairman, manager sign-offs)

PENDING:
- Manual audit template/checklist — referenced in plan but no artifact in warehouse yet
- Outreach script and customer email sequence — Priya has outline, needs final copy
- CloudTrail parsing logic or audit rules — not yet prototyped
- Success criteria definition (what makes a "yes, we'd pay" response clear vs ambiguous)

NEXT WEEK FOCUS:
Ship completed manual audits to 2 of the 5 customers by end of week so we can measure willingness-to-engage before day 10.

ROLE PLAN:
- engineering: YES — CloudTrail sandbox + basic cost extraction must be testable before we send first audit, even if manual
- review: NO — no code shipped yet; defer until audit output exists
- design: NO — landing page is done; next design work (dashboard mockups) only happens if validation succeeds
- customer-feedback: YES — Chioma needs to listen to first 2 customer calls after audits land to surface what "paying" actually means to them
- sales: YES — Priya must finalize outreach copy and send first batch this week; waiting kills momentum
- pm-status: YES — Dmitri tracks blockers daily; we have 10 days and can't afford hidden delays
- finance: NO — no unit economics to model until we have engagement data
- risks: YES — Gonzalo flags if the audit template is too complex to execute manually in 10 days

ONE-LINE SUMMARY:
Outreach + first two manual audits ship this week; engineering builds CloudTrail parsing in parallel; Chioma and Gonzalo watch for execution friction.
