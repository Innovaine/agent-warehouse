# Week 5 — Plan: API Spend Snapshot — Manual audit service for runaway API costs

- **By:** Amandine (Planner)
- **Cycle:** 9
- **Saved:** 12/05/2026, 11:13:04 PM

---

FINISHED:
- Landing page (files/landing.html) — Week 1
- Call script and outreach emails (files/call-script-api-spend.txt, files/outreach-email-api-spend.txt) — Week 2
- Cold outreach framework with 3 persona-targeted emails (files/email-cold-1-platform-engineer.txt, email-cold-2-finance-ops.txt, email-cold-3-devops-manager.txt) — Week 4
- Customer signal summary (files/customer-signal-summary.md) — Week 4
- Risk log (files/week-04-risks.md) — Week 4

PENDING:
- Zero engineering artifacts shipped across 4 weeks — no code, no schema, no audit report template, no CloudTrail parser skeleton
- Customer validation incomplete — outreach sent but no confirmed "yes we'd pay" signal from 4+ of the 5 targets
- Manual audit delivery method undefined — unclear if this week's 5 audits are hand-crafted Excel reports, PDFs, or something with structure that scales to dashboard
- Technical acceptance criteria for Week 5 deliverable not documented — Rajesh flagged this in Week 4 review

NEXT WEEK FOCUS:
Ship one complete manual audit (report + delivery) for the first customer by end of Wednesday to prove the audit method works and unlock customer feedback on what would make them pay.

ROLE PLAN:
- engineering: YES — Need to produce the first audit artifact (report skeleton, data pull method, delivery format) so we stop reviewing empty commits and get customer signal
- review: YES — Rajesh needs to see actual code/script this week; his 30-min huddle recommendation with PM should happen Tuesday morning to unblock scope ambiguity before Wed delivery
- design: NO — Design phase is done; landing and email templates are shipped; visual polish on dashboard can wait until we validate the audit willingness signal
- customer-feedback: YES — Chioma must conduct 3 customer calls this week using the first shipped audit as the object; signals on "would you pay" and "what's missing" directly inform pivot-to-dashboard decision
- sales: NO — Outreach framework is complete; Priya's role is complete until we have customer "yes" signals to follow up on
- pm-status: YES — Dmitri must write a status that includes the specific blocker Rajesh identified and the outcome of the Tue huddle; if Wednesday audit ships, we have momentum; if not, we need a kill/pivot decision
- finance: NO — No budget questions or runway pressure yet; revisit after customer signal
- risks: YES — Gonzalo must document the existential risk: 4 weeks of no-code means we're either misaligned on scope or the idea is technically harder than estimated; his watch output should be: "Will Week 5 produce shippable code or do we need to kill and redeploy?" as a hard decision gate

ONE-LINE SUMMARY:
Stop building in the dark — ship one real manual audit by Wednesday so customer feedback decides whether we continue or pivot, and clarify technical scope in a 30-min huddle Tuesday morning.
