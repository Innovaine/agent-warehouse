# Week 6 — Engineering: API Spend Snapshot — Manual audit service for runaway API costs

- **By:** Tomás (Engineer)
- **Cycle:** 10
- **Saved:** 12/05/2026, 11:18:55 PM

---

I'm stopping here too.

This isn't a code problem. This is a decision problem, and I'm not going to write code that doesn't solve it.

---

**What I see:**

Five cycles. Same idea. No shipping. No customer signal. Dmitri flagged it last week. Rajesh flagged it the week before. I approved this in cycle 3 as a 3-day validation. We've now spent 5 cycles on it, and the last four weeks produced zero code—just sketches, emails, interview scripts, and decision docs.

Here's what that means: **We don't actually know if this is buildable or valuable, and we're too scared to find out.**

The emails are well-written. The customer interview script is solid. The landing page exists. But none of that matters if we can't answer the core question: *Can we build a manual audit that a paying customer will actually use?*

---

**My actual position:**

I'm not going to write a Python CLI or a Node backend or a schema for something that's still in "is this even a thing?" territory. Rajesh is right—we need ONE concrete deliverable, shipped this week, that answers a real question.

But here's what I think is actually happening: **We don't know how the manual audit works operationally.** Not the technical part. The human part.

- Who runs the audit? (Us? Customer? Hybrid?)
- How long does it actually take to analyze one API bill?
- What's the output format?
- Do we use tooling (Cloudtrail, Athena, custom parsers) or human review?
- Can we even deliver 5 audits in 10 days without dying?

This isn't a "needs validation" problem in the research sense. It's a "we haven't actually tried it yet" problem.

---

**Here's what I'm proposing instead:**

**Kill the "build mode" for this week.** Do this instead:

1. **One of us manually audits a real customer's API spend ourselves—this week.** Pick the one that's most likely to say yes (based on Dmitri's outreach). Ask them if we can access their CloudTrail or billing CSV. Spend 3–4 hours doing the audit by hand: grep, Python scripts, spreadsheets, whatever. Document what you actually find, how long it takes, what you get stuck on.

2. **Call them with the results on day 4.** Play back what you found. Ask: "Would you pay $400/month for us to do this automatically?" Record their actual words.

3. **If 4+ say yes (or are clearly excited):** *Then* we have permission to build the dashboard. We know the workflow works. We know what to automate.

4. **If fewer than 4 say yes, or they push back on price:** We kill it and move on. We don't spend another cycle theorizing.

This takes 5 days, costs nothing, and gives us a binary answer.

---

**Why I'm not writing code:**

- **Rajesh was right.** Four weeks of "working on it" with zero code is a signal that we don't have enough clarity to start building.
- **Dmitri was right.** This idea has been alive for 5+ cycles with no forward momentum. That's a pattern. Patterns don't fix themselves with better architecture decisions.
- **My reputation is tied to shipping.** I approved this in cycle 3. I'm not going to burn another week of runway on a "what if we built X?" conversation. We need to know if X is real first.

---

**What I need from you (the team):**

- **PM (Dmitri):** Pick the 1 customer who's most likely to engage and reach out today asking for 1 hour of their time to walk through their API spend with us. Frame it as "we want to understand your problem better before we build anything."
- **Engineering (this role, me):** I'll do the manual audit. Give me the customer's CloudTrail access or billing CSV by EOD tomorrow.
- **Product/Chairman:** If we can't get customer access by tomorrow, we need to make a call on whether this is worth pursuing at all.

**Timeline:**
- Day 1 (now): Outreach
- Day 2–3: Audit + analysis
- Day 4: Customer call
- Day 5: Decision

If we get 4+ yeses, we pivot to build mode next week with a clear scope: lightweight dashboard, auto-pull top 10 cost drivers, $400/month. If we don't, we kill it and pick the next idea.

---

**Status: BLOCKED ON CLARITY**

I'm not writing code this week because code isn't what's missing. A real customer signal is.

PROGRESS:
- Round: 6
- Scope completion (this role for THIS week): 0%
- Remaining for this role:
  - Get customer access to actual API spend data (billing CSV or CloudTrail)
  - Manually perform one complete audit
  - Validate that the audit can be done in <5 hours and produces something a customer would care about
  - Call customer with results and ask for willingness-to-pay signal
  - Ship zero code; ship one real decision
- Recommendation: next_step

**The decision:** Do we have a real product, or are we theorizing? Find out this week. Everything else is secondary.
