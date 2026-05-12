# Week 9 — Customer Validation: API Spend Snapshot
## Direct Willingness-to-Pay Signal

**Owner:** Tomás  
**Target completion:** Wednesday EOD, Week 9  
**Decision rule:** If 4+ of 5 say "yes, we'd pay $400/month," write the audit script. If 3 or fewer, kill the project.

---

## Qualified customers to contact (drawn from prior outreach):

| Name | Title | Company | Context | Status | Notes |
|------|-------|---------|---------|--------|-------|
| [name pending outreach review] | [role] | [company] | [why they're qualified] | Pending | [call booked?] |
| [name pending outreach review] | [role] | [company] | [why they're qualified] | Pending | [call booked?] |
| [name pending outreach review] | [role] | [company] | [why they're qualified] | Pending | [call booked?] |
| [name pending outreach review] | [role] | [company] | [why they're qualified] | Pending | [call booked?] |
| [name pending outreach review] | [role] | [company] | [why they're qualified] | Pending | [call booked?] |

---

## Call script (adapted from week-05):

1. **Opener (2 min):** "We're exploring a service that audits your AWS API costs and flags the top cost drivers. Have you ever been surprised by an API bill?"
2. **Problem depth (5 min):** "How do you currently track which APIs are costing you the most? What's missing?"
3. **Price signal (3 min):** "If you could get a recurring audit—updated quarterly, showing your top 10 cost drivers and optimization paths—what would that be worth to you? Would $400/month make sense?"
4. **Commitment (1 min):** "If we built this, would you use it? Would you pay?"

---

## Signals to capture:

- **Yes/No on $400/month:** Direct quote or clear statement.
- **Current pain:** What's their cost visibility gap right now?
- **Frequency preference:** Monthly? Quarterly?
- **Integration preference:** Standalone report, dashboard, or email?

---

## Post-call action:

- Record notes within 1 hour of call
- Tally yes/no signal
- If 4+ yes: write Python audit script same day
- If 3 or fewer: prepare kill decision and recommend next project target
