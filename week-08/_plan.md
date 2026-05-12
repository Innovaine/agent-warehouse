# Week 8 — Plan: API Spend Snapshot — Manual audit service for runaway API costs

- **By:** Amandine (Planner)
- **Cycle:** 12
- **Saved:** 12/05/2026, 11:25:27 PM

---

# WEEK 8 BRIEF — API Spend Snapshot

FINISHED:
- Landing page and call script (week 1-2)
- Cold outreach email templates to 3 buyer personas (week 4)
- Customer signal summary showing soft interest from ~8 conversations (week 4-7)
- Week 7 PM status and code review flagging zero shipping for 4 consecutive cycles

PENDING:
- Actual manual audit delivery (not started)
- Customer commits to paid pilot (not secured — only soft signals)
- Dashboard prototype or cost-pull integration (not built)
- Definition of what "4+ customers say yes" actually means (verbal yes vs. contract vs. email confirmation — unclear)

NEXT WEEK FOCUS:
Execute the manual audit on 2–3 pre-qualified customers by end of week 8, capture their exact response to "would you pay $400/month for this recurring," and use that signal to kill or pivot by cycle 12.

ROLE PLAN:
- engineering: YES — Build the minimal audit script (CloudTrail CSV pull + top 10 cost drivers report template). 3 days max. Stop if scope creeps.
- review: NO — No code to review until script is shipped; Rajesh can validate output format once there's a working artifact.
- design: NO — No design work needed for manual audit. Reactivate only if we commit to dashboard in cycle 9+.
- customer-feedback: YES — Chioma runs the 2–3 audit conversations this week. Records exact commitment language ("I would pay," "maybe," "no"). Logs in customer-feedback.md by Friday EOD.
- sales: NO — Priya is not the bottleneck this week; Chioma can own the audit handoff and feedback capture.
- pm-status: YES — Dmitri writes end-of-week status: audits shipped (Y/N), customer response captured (Y/N), go/no-go decision on dashboard pivot stated clearly.
- finance: NO — No financial review needed until we have paying customers or a pivot decision.
- risks: YES — Gonzalo flags: if 0 customers agree to paid model by Friday, this is dead; if 1–2 agree, we're unclear on demand; if 3+ agree, we can fund a dashboard build in cycle 9. Writes decision gate.

ONE-LINE SUMMARY:
Ship 2–3 live manual audits, capture hard customer commitment signals on pricing, and make kill/pivot decision by end of week.

---

**My read:** We've been in soft-signal land for 4 cycles. This week we move to **hard signal or dead**. The audit is the bet. If customers won't say "yes, I'd pay" when they see their actual runaway costs, this idea doesn't survive cycle 12. I'm approving engineering and customer-feedback because we finally have a testable gate. Dmitri's status memo needs to be specific: not "building toward dashboard," but "learned X from audits, decision is now Y." That's executable.
