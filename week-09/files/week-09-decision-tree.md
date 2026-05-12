# Week 9 — Decision Tree: Which Risk Kills Us First?

## Assumption Stack (top = most fragile)

1. **Someone cares enough to pay** (Risk #1, #4)
   - Upstream question: Does runaway API cost exist as a *felt* problem?
   - If NO: product is vapor. Pivot or kill.
   - If YES: proceed to next layer.
   - Test: Call 5 target customers TODAY. Ask: "In the last 30 days, did an API bill surprise you or spike unexpectedly?" Listen for YES + emotion. (Not: "Would you use a tool?" Ask: "How did you find out?")
   - Time to signal: 4 hours.

2. **We're solving the right *job* (Risk #2)
   - If they caught it manually and forgot about it → point-in-time audit is fine.
   - If they caught it via alert/monitoring tool → we're making a worse product than Datadog already does.
   - If they didn't catch it at all → bigger problem, different product.
   - Test: Slack integration (48 hrs). If 50%+ of signups turn it on, we nailed UX. If <20%, we're solving for wrong motion.
   - Time to signal: 5 days.

3. **We can reach them at scale** (Risk #5)
   - Even if problem + solution are real, if we have no distribution, we die.
   - This is NOT a "marketing strategy" problem. It's a "can we ship one repeatable motion" problem.
   - Test: Execute ONE channel (e.g., email 20 target customers + post 1 community) this week. Target: 20 signups from a single source.
   - Time to signal: 7 days.

4. **Economics work** (Risk #4)
   - If Risk #1 passes (someone pays) but first customer is $50/month LTV, we're not a business.
   - This forces a hard conversation early instead of week 16.
   - Test: Define LTV floor (e.g., $500/month minimum). When first customer pays, does it exceed that?
   - Time to signal: 14 days (when first deal closes).

## Kill-Fastest Priority (if we do nothing)

**By Friday EOD, we MUST have:**
- ✓ At least 2/5 target customers confirm "yes, runaway costs happen to us"
- ✓ Slack integration deployed and measurable
- ✓ ONE repeatable distribution motion live and trackable

**If we don't have all three by Friday:**
- We trigger a "emergency pivot assessment" Monday morning.
- That means: is this the wrong product, or just wrong execution? We get 2 weeks to answer. Then board meeting.

## What "Winning Week 9" Looks Like

- 5+ customers on call saying "yeah, that happens"
- Slack integration live; 30%+ adoption rate
- One distribution channel producing 10+ qualified signups
- First customer conversation scheduled for next week

If we have 3/4 of these by Friday, we keep velocity. If we have <2/4, we need a re-plan before cycle 10.