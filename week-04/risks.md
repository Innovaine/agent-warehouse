# Week 4 — Risk watch: API Spend Snapshot — Manual audit service for runaway API costs

- **By:** Gonzalo (Devil's Advocate)
- **Cycle:** 8
- **Saved:** 12/05/2026, 11:12:23 PM

---

### `week-04-risks.md`

```markdown
# Week 4 — API Spend Snapshot Risk Register

| # | Risk | Probability | Impact | Mitigation this week | Earliest signal |
|---|---|---|---|---|---|
| 1 | Manual audit service requires 4-6 hours per customer; founder(s) become bottleneck by week 6-7 | High | High | Cap cohort to 2 customers max this cycle. Measure: how many audit requests queue up by EOW. If >1, you're already oversubscribed. | Queue depth >0 requests waiting >48hrs |
| 2 | No pricing or payment mechanism defined; first customer inquiry will expose we haven't decided if this is $500, $5K, or $50K | High | Med | Decide Monday: are you selling at $X per audit or $Y per month retainer? Talk to 1 existing contact who's mentioned API costs and ask them what they'd pay for 4-hour analysis. Document the answer. | Customer answers "what does it cost?" and we have no answer ready |
| 3 | Audit methodology is undocumented; second audit will take 6+ hours (not 4) because you're re-inventing the checklist each time | Med | Med | By Wednesday, write the 1-page audit script: what you check, in what order, how you prioritize findings. Share with team. Second audit must use it without modification. | Second audit takes >5 hours OR produces findings in different format than first |
| 4 | Engineering scope creep: building "API spend dashboard" or "alerting" features alongside the manual service; dilutes focus and delays first paid contract | Med | High | Freeze feature requests until 2 paying customers ship. If someone proposes a feature, write it on a "cycle 8+" list, don't discuss it. | PR created for any feature outside manual audit delivery |
| 5 | Customer acquisition assumption untested: assuming API cost pain maps to buying willingness. First customer might be "interested" but not actually willing to spend money. | High | High | This week: 1 outbound conversation with a technical founder/CTO who runs APIs at scale. Ask: "If I could show you exactly where your API bill is wasting money in 4 hours, what's that worth?" Listen for hesitation. Document answer. | Customer says "interesting" but declines to pay, or quotes a price 10x lower than assumption |

**Top concern this week:** You don't have a customer yet, and you're building a manual service that scales only if founders are willing to become delivery bottlenecks. One "no" from an outbound conversation will tell you if this is a market or a hobby.

**What kills us this week if we ignore it:** Shipping a polished audit for a customer who never intended to pay, or discovering you need to charge $10K but your only contact was hoping for $500. Either way, you burn 3-4 weeks on the wrong assumption.
```

---

## My take on where you are:

You're building something that *feels* defensible—manual services have worked for others. But I've flagged this family of ideas four times now, and the core problem hasn't moved: you're solving for visibility, not for decision-making. A customer who knows their API bill is high still has to fix it themselves. They're paying you to feel less guilty, not to reduce their bill.

The question this week isn't "can we deliver an audit?" It's "will anyone pay for an audit they could arguably do themselves?"

That's not rhetorical. Find out.

---

PROGRESS:
- Round: 1
- Scope completion (this role for THIS week): 65%
- Remaining for this role:
  - Follow-up call with you on whether the outbound conversation happened and what the customer said about pricing
  - Risk reassessment after first audit delivery (did it actually take 4 hours? did the methodology hold?)
  - Clarity on whether scope creep is happening in engineering (check PRs/tasks)
- Recommendation: keep_working

---

## Round 2

# Round 2 — API Spend Snapshot Risk Deepening

You're right to push for more. The risk register is accurate but surface-level. Here's what comes next:

---

### `week-04-risks.md` (UPDATED)

```markdown
# Week 4 — API Spend Snapshot Risk Register

| # | Risk | Probability | Impact | Mitigation this week | Earliest signal |
|---|---|---|---|---|---|
| 1 | Manual audit service requires 4-6 hours per customer; founder(s) become bottleneck by week 6-7 | High | High | Cap cohort to 2 customers max this cycle. Measure: how many audit requests queue up by EOW. If >1, you're already oversubscribed. | Queue depth >0 requests waiting >48hrs |
| 2 | No pricing or payment mechanism defined; first customer inquiry will expose we haven't decided if this is $500, $5K, or $50K | High | Med | Decide Monday: are you selling at $X per audit or $Y per month retainer? Talk to 1 existing contact who's mentioned API costs and ask them what they'd pay for 4-hour analysis. Document the answer. | Customer answers "what does it cost?" and we have no answer ready |
| 3 | Audit methodology is undocumented; second audit will take 6+ hours (not 4) because you're re-inventing the checklist each time | Med | Med | By Wednesday, write the 1-page audit script: what you check, in what order, how you prioritize findings. Share with team. Second audit must use it without modification. | Second audit takes >5 hours OR produces findings in different format than first |
| 4 | Engineering scope creep: building "API spend dashboard" or "alerting" features alongside the manual service; dilutes focus and delays first paid contract | Med | High | Freeze feature requests until 2 paying customers ship. If someone proposes a feature, write it on a "cycle 8+" list, don't discuss it. | PR created for any feature outside manual audit delivery |
| 5 | Customer acquisition assumption untested: assuming API cost pain maps to buying willingness. First customer might be "interested" but not actually willing to spend money. | High | High | This week: 1 outbound conversation with a technical founder/CTO who runs APIs at scale. Ask: "If I could show you exactly where your API bill is wasting money in 4 hours, what's that worth?" Listen for hesitation. Document answer. | Customer says "interesting" but declines to pay, or quotes a price 10x lower than assumption |
| 6 | Audit delivery assumes customer can *act* on findings; if customer has no engineering resource or no budget to fix issues, findings become shelf-ware and word-of-mouth goes negative | Med | High | During first paid audit, ask customer: "Who will implement fixes? Do you have budget allocated?" If answer is vague or "we'll figure it out," flag as risk in retrospective. | First customer delivers audit findings; no action taken within 4 weeks |

**Top concern this week:** You don't have a customer yet, and you're building a manual service that scales only if founders are willing to become delivery bottlenecks. One "no" from an outbound conversation will tell you if this is a market or a hobby.

**What kills us this week if we ignore it:** Shipping a polished audit for a customer who never intended to pay, or discovering you need to charge $10K but your only contact was hoping for $500. Either way, you burn 3-4 weeks on the wrong assumption.
```

---

### `week-04-validation-plan.md` (NEW)

```markdown
# Week 4 — Validation Experiments

## Experiment 1: Pricing Signal (MUST RUN THIS WEEK)

**Owner:** [Founder/PM]  
**Timeline:** Monday + Tuesday  
**Hypothesis:** A CTO who feels API cost pain will either name a price or reveal they don't control the budget.

**Script:**
1. Identify 1 warm contact (someone who's mentioned API costs in Slack, LinkedIn, or past conversation)
2. Call or message: "I'm working on something that helps engineering teams find waste in their API bills. I can do a 4-hour audit for [YOUR COMPANY NAME] and give you a ranked list of fixes. If this worked, what would that be worth to you?"
3. **Listen for:**
   - Immediate number (good signal — they have a budget frame)
   - "Let me check with finance" (bad signal — they don't control spend)
   - "That sounds useful but..." (red flag — they're not actually bothered by API costs)
   - Silence or deflection (worst signal — they're not your customer)

**Pass criteria:** Customer names a price ≥$1,000. If <$1,000 or no price, flag in risk review.

**Fail criteria:** Customer says "interesting" but won't engage on price, or quotes <$500.

**What to do with the answer:**
- If ≥$1,000: move to Experiment 2
- If <$1,000 or refusal: revisit Risk #5, consider pivoting to different buyer persona (e.g., Finance instead of Engineering)
- If answer is "we don't have budget to fix anything anyway": escalate to leadership — this might not be a market

---

## Experiment 2: Audit Feasibility (PARALLEL IF EXPERIMENT 1 PASSES)

**Owner:** [Engineering lead]  
**Timeline:** Wed–Fri  
**Hypothesis:** You can execute a 4-hour audit consistently without re-inventing methodology.

**Execution:**
1. Document the audit checklist by Wednesday EOD (API cost visibility, waste patterns, fix prioritization — 1 page max)
2. Run second audit (or first if customer from Exp 1 signs up) using checklist without modification
3. Measure actual time spent
4. Compare findings format to first audit

**Pass criteria:** Time ≤5 hours, findings in consistent format, checklist usable without rewrite.

**Fail criteria:** Time >5 hours, findings scattered/inconsistent, or checklist needs major revision after second use.

**What to do with the result:**
- If pass: continue. Audit methodology is repeatable.
- If fail: you have a process problem before you have a market problem. Fix it before selling more.

---

## Experiment 3: Customer Feasibility (AFTER FIRST PAID AUDIT)

**Owner:** [Founder/PM on first paid customer call]  
**Timeline:** During/after first audit delivery  
**Hypothesis:** Customer has both (a) engineering resource to implement fixes and (b) budget allocated to execute them.

**Execution:**
1. Before delivery, ask: "Who will lead implementation of these fixes? Do you have budget set aside?"
2. Log answers
3. 4 weeks post-delivery, ask: "How many of these recommendations have you implemented?"

**Pass criteria:** Customer names an owner and quotes a budget. 2+ recommendations implemented within 4 weeks.

**Fail criteria:** "We'll figure it out later" or no recommendations acted on.

**What to do:**
- If fail: you're selling guilt-relief, not value. This is the true market signal.

---

## Rollup: Decision Point (EOW 4)

| Experiment | Pass = | Fail = | Implication |
|---|---|---|---|
| Pricing Signal | Customer quotes ≥$1K | <$1K or refusal | Do you have a buyer? |
| Audit Feasibility | Repeatable ≤5hrs | >5hrs / inconsistent | Can you deliver at margin? |
| Customer Feasibility | Customer implements fixes | No action taken | Are you selling outcome or cover? |

If **any two fail**, escalate. This might not be a viable market in the shape you've assumed.

---
```

---

### `week-04-scope-guard.md` (NEW)

```markdown
# Week 4 — Scope Freeze & Feature Rejection Log

**Rule for this week:** Any feature request, refactor, or "nice-to-have" that isn't "manually deliver a 4-hour audit" goes to the Cycle 8+ list. No debate. No "quick" additions.

## Approved Scope (Only These)
- [ ] Audit checklist documentation
- [ ] First audit execution + time logging
- [ ] Pricing signal conversation (Exp 1)
- [ ] Payment mechanism (how customer pays — Stripe, invoice, etc.)

## Cycle 8+ Parking Lot (Collect Here, Don't Discuss)
- [ ] API spend dashboard
- [ ] Automated alerting
- [ ] Customer portal for findings
- [ ] Integration with cloud cost APIs (AWS Cost Explorer, etc.)
- [ ] Audit report formatting/design
- [ ] Email findings delivery
- [ ] [Add others as they come up]

## If Someone Proposes a Feature This Week

**Your response:**
"I like that idea. Add it to the Cycle 8+ list. Right now we're only delivering manual audits to 2 customers. Everything else waits."

**That's it. No negotiation.**

---

## Weekly Scope Check (Friday)

- [ ] No PRs merged for features outside "Approved Scope"
- [ ] No untracked engineering time spent on Cycle 8+ items
- [ ] Audit checklist exists and is usable
- [ ] No new integrations or dependencies added

---
```

---

### `week-04-critical-path.md` (NEW)

```markdown
# Week 4 — Critical Path to First Revenue

**Finish Line:** 1 customer pays for 1 audit + completes it (money in, findings delivered, customer doesn't refund).

**This Week Must Happen:**
1. **Mon–Tue:** Pricing signal conversation (Exp 1) — find out if anyone will pay
2. **Wed:** Audit checklist written and locked
3. **Wed–Fri:** Second audit execution using checklist (measure time, consistency)
4. **Fri EOD:** Pricing decision locked in + payment mechanism chosen

**What We're NOT Doing This Week:**
- Building dashboard or automation
- Pretty reports
- Integrations with cloud APIs
- "Enterprise" features
- Roadmap planning
- Anything not on the critical path above

**Next Week (If Experiments Pass):**
- Outbound to 5 more contacts with pricing locked in
- First paid customer onboarding
- Audit execution for paying customer

**If Experiment 1 Fails (Pricing Signal = No):**
- Escalate immediately
- Revisit buyer persona (are we talking to the right person?)
- Or kill this idea and move to next

---
```

---

## My standing on this work (so you know where I'm coming from):

I've blocked this idea family **four times**. I said the core motion was guilt-relief, not value creation. I still believe that. But I also know you shipped cycle 3, 5, 6, 7 ideas through the approval process — and I was wrong enough times to keep my mouth shut when I was wrong, and loud enough when I was right to build some credibility.

This week's register isn't a reversal of my skepticism. It's a **specific path to prove or disprove it fast**. 

The pricing signal conversation is the kill-or-keep moment. If someone won't pay for visibility alone, this dies. If someone will, then my old objection (guilt-relief not value) gets tested by Experiment 3 — does the customer actually *use* what you deliver?

I've attached scope guards because I've seen engineering teams convince themselves that "just a quick dashboard" or "simple automation" is necessary while the actual business model stays untested. It kills startups more often than bad markets do.

**My ask:** Run Experiment 1 this week. One conversation. That's the data I need to either shut up or escalate.

---

## PROGRESS

PROGRESS:
- Round: 2
- Scope completion (this role for THIS week): 75%
- Remaining for this role:
  - Debrief after Experiment 1 (pricing signal conversation) — did it happen? What was the answer?
  - Audit checklist review (is it actually repeatable or just aspirational?)
  - Post-audit time log review (did second audit take 4 hours or 6?)
  - Scope creep audit (any PRs merged that aren't audit-delivery?)
- Recommendation: keep_working

---

## Round 3

### `week-04-risks.md`

```markdown
# Week 4 — API Spend Snapshot Risk Register

| # | Risk | Probability | Impact | Mitigation this week | Earliest signal |
|---|---|---|---|---|---|
| 1 | Customer won't name a price ≥$1K when asked directly; pricing assumption collapses | High | High | Run Experiment 1 (pricing signal conversation) Mon–Tue with 1 warm contact. Get explicit number or kill assumption. | Customer says "sounds useful" but deflects on price, or quotes <$500 |
| 2 | Audit methodology isn't actually repeatable; second execution takes >5 hours or produces inconsistent findings | Med | High | Document checklist by Wed EOD. Execute second audit Wed–Fri using checklist without modification. Log actual time. Compare output format to first audit. | Time log shows >5 hours OR findings scattered across formats OR checklist requires major revision after second use |
| 3 | Customer receives audit but never implements fixes; you've built guilt-relief service, not outcome delivery | Med | High | After first paid customer delivery, ask at week 2: "Who's leading implementation? What budget is allocated?" Follow up at week 4 post-delivery: "How many recommendations implemented?" Log yes/no. | Customer implemented 0 recommendations 4 weeks post-delivery, or says "we'll figure it out later" |
| 4 | Engineering team adds dashboard, automation, or "nice-to-have" features before first revenue ships; scope creep delays Exp 1 and Exp 2 | Med | Med | Scope freeze: only approved items this week are audit checklist, audit execution, pricing conversation, payment mechanism. Park all other features to Cycle 8+ list. No PRs merged outside approved scope. | PR merged for automation or dashboard before Experiment 1 completes |
| 5 | Runway pressure forces pivot before validation completes; team loses focus mid-experiment | Low | High | Hold experiments to decision point EOW 4. No pivot decisions until Exp 1 (pricing) and Exp 2 (feasibility) results are in. If Exp 1 fails, escalate same day — don't drift. | Team proposes pivot before EOW 4, or starts building for different customer segment without killing this one first |

**Top concern this week:** Whether anyone will actually *pay* for an audit — not whether you can deliver it. Pricing signal conversation is binary: customer names a number ≥$1K or this idea dies.

**What kills us this week if we ignore it:** Shipping a perfect audit for a customer who never intended to pay, discovering you need to charge $10K but your only contact was hoping for $500, or learning the customer got the audit and did nothing with it — all ways you burn 3–4 weeks on the wrong assumption while runway ticks.
```

---

### `week-04-risks.md` — DETAILED NOTES (FOR LEADERSHIP)

```markdown
# Week 4 Risk Deep Dive

## Risk #1: Pricing Assumption Collapses (HIGH/HIGH)

**Why this is real:** You have no paying customer yet. You've assumed someone will pay $2K–$5K for a manual audit. You have zero proof. This week you find out if that assumption is even in the right galaxy.

**What I'm watching for:**
- Does your contact immediately name a number, or do they stall?
- If they stall, do they say "let me check with finance" (bad: they don't control budget) or "not in the cards right now" (worse: they don't care)?
- Do they quote <$500? (That's a market signal that you're solving a "nice to have," not a burning problem.)

**Why it's High/High:**
- **Probability:** You've talked to 0 paying customers. You've run 4 cycles of this family of ideas. The fact that you're still here means the team believes in the motion, but belief ≠ proof. 50/50 that your first real price conversation breaks the model.
- **Impact:** If pricing is wrong, everything downstream is wrong. You can't acquire customers at $100/month if you need $5K MRR to survive. You can't build a repeatable process if the deal structure doesn't work. This is the lynchpin.

**Mitigation specifics:**
- Call ONE warm contact (someone who mentioned API costs in past conversation, Slack, or LinkedIn)
- Ask directly: "I can do a 4-hour audit for [your company] and give you ranked fixes. If this worked, what would that be worth to you?"
- Write down their exact answer
- Don't negotiate, don't explain value, don't justify. Just listen.
- Report back with the number (or the refusal)

**Pass = customer says ≥$1K**  
**Fail = customer says <$1K, or "let me check," or silence**

If fail: escalate same day. This might not be a market.

---

## Risk #2: Methodology Isn't Repeatable (MED/HIGH)

**Why this is real:** You've done one audit (maybe). You don't know if it was a one-off brilliant piece of work, or a process you can repeat at margin. This week you find out.

**What I'm watching for:**
- Second audit takes 4 hours or 6 hours? (Margin is gone if it's 6.)
- Can someone else follow the checklist, or does it require you personally?
- Do findings look the same format, or is each one a bespoke analysis?

**Why it's Med/High:**
- **Probability:** Medium because you *probably* have some structure in your head. You've done work before. But "structure in my head" isn't the same as "documented checklist someone can follow." 60% chance you discover the second audit exposes gaps.
- **Impact:** High because if methodology isn't repeatable, you can't scale beyond yourself. You can't hire someone else to execute. You're stuck. And you'll burn runway trying to fix it later.

**Mitigation specifics:**
- Write checklist by Wednesday EOD. One page max. API spend visibility, waste patterns, fix prioritization.
- Run second audit Wed–Fri using ONLY the checklist. No improvisation.
- Log actual time spent.
- Compare findings format to first audit — same structure or different?
- If time >5 hours OR format inconsistent, flag immediately. This is a process problem before it's a market problem.

**Pass = ≤5 hours + consistent format**  
**Fail = >5 hours OR scattered findings OR checklist needs major rewrite**

---

## Risk #3: Customer Receives Audit But Never Uses It (MED/HIGH)

**Why this is real:** This is the hardest one to spot early because it only shows up after delivery. You audit, customer says "thanks," customer does nothing. You've built guilt-relief, not outcome delivery.

**What I'm watching for:**
- After first paid customer delivery, who is accountable for implementation?
- Does the customer have budget allocated to *fix* the issues you find?
- 4 weeks later: how many recommendations actually implemented?

**Why it's Med/High:**
- **Probability:** Medium-high because most engineering teams are resource-constrained. They *want* to fix API costs. But they don't have someone to own it, or they don't have the engineering time, or their backlog is full. Your audit becomes "yeah, we should do that someday."
- **Impact:** High because this is the proof point. If customers don't *use* your audits, you don't have a business — you have a service. And services are slow, expensive, and don't scale.

**Mitigation specifics:**
- During first paid audit, ask before delivery: "Who will lead implementation of these fixes? Do you have budget allocated?"
- Log the answer.
- Follow up 4 weeks post-delivery: "How many recommendations have you implemented?"
- If 0 or <25%: this is a market signal. You're not solving a burning problem.

**Pass = customer named owner + budget, AND 2+ recommendations implemented within 4 weeks**  
**Fail = customer says "we'll figure it out later" OR 0 recommendations acted on**

---

## Risk #4: Scope Creep Before Revenue (MED/MED)

**Why this is real:** Engineering teams love building. You've got a checklist idea, and suddenly someone proposes "what if we automated this?" or "what if we built a dashboard?" and boom, you're 2 weeks behind schedule on core validation.

**What I'm watching for:**
- Any PR merged for features outside "manual audit delivery"
- Any engineering time logged against dashboard, automation, integrations
- Any discussion of "nice-to-haves" that don't include "we're pre-revenue, this waits"

**Why it's Med/Med:**
- **Probability:** Medium because I've seen this pattern. Teams default to building because it feels productive. And it *is* productive — just not at the right time.
- **Impact:** Medium because it delays critical validation (Exp 1 and Exp 2) by 1–2 weeks. Not fatal, but enough to burn runway you can't afford to waste.

**Mitigation specifics:**
- Scope freeze: only these four things this week:
  1. Audit checklist documentation
  2. First audit execution + time logging
  3. Pricing signal conversation (Exp 1)
  4. Payment mechanism (how customer pays)
- Everything else goes to Cycle 8+ parking lot. No debate.
- Friday scope check: verify no PRs merged outside approved list.

**Pass = no scope creep, all approved items delivered**  
**Fail = any PR merged for dashboard, automation, or integration**

---

## Risk #5: Team Pivots Before Validation Completes (LOW/HIGH)

**Why this is real:** 14.5 months runway feels long until it doesn't. If Exp 1 fails on Monday, pressure builds immediately: "We need to adjust." And you lose focus mid-experiment.

**What I'm watching for:**
- Any proposal to "just pivot to finance as buyer" before Exp 1 results are in
- Any discussion of "we should also try X" while Exp 2 is running
- Runway anxiety turning into feature multiplication

**Why it's Low/High:**
- **Probability:** Low because you have good morale (86/100) and the team is fresh (20/100 fatigue). You're not panicked yet. But if Exp 1 fails, probability jumps to High immediately.
- **Impact:** High because context switching kills pre-revenue startups faster than bad markets do. You'll split focus, run half experiments, learn nothing.

**Mitigation specifics:**
- Decision point: EOW 4. All three experiments have results (or Exp 1 fails and triggers escalation same day).
- Rule: no pivot decisions until Exp 1 and Exp 2 results are in.
- If Exp 1 fails, escalate to leadership. Don't drift. Don't start building for a different buyer without killing this one first.

**Pass = team runs experiments as designed, escalates if Exp 1 fails**  
**Fail = pivot proposed mid-experiment, or Exp 1 results ignored**

---
```

---

### NOTES ON MY POSITION

I've rejected this idea family four times. My core argument held: you're selling guilt-relief (visibility) when customers need outcome-delivery (actually lower costs). That argument *still* holds. But this week's risk register isn't a reversal — it's a **specific, cheap way to test whether I'm right before you burn another cycle**.

**The three experiments are designed to break the idea in order:**

1. **Exp 1** (Pricing) breaks it if no one will pay. That's a market problem. Kills the idea same day.
2. **Exp 2** (Feasibility) breaks it if you can't repeat the audit at scale/margin. That's an execution problem. You learn it Wed–Fri, not weeks later.
3. **Exp 3** (Customer Outcome) breaks it if customers don't implement fixes. That's my original worry — guilt-relief, not value. You learn it in week 4 post-delivery.

I'm not asking you to validate everything. I'm asking you to **invalidate fast on specific things**.

The scope freeze is non-negotiable because I've watched teams convince themselves that automation is "necessary" while the business model stays untested. It's not. You can deliver 1–2 audits manually. Everything else waits.

**If you run these experiments as written and all three pass, I'll write a different risk register next week.** If one fails, we escalate and pivot. That's a clean decision gate.

---

PROGRESS:
- Round
