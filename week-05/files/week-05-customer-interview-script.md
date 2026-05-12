# Week 5–6 Customer Validation: The Only Three Questions That Matter

## Context
We're shipping manual audits. We need to know in week 6 if this is a business or just a feature. One customer, these three questions, binary answers.

---

## The Customer: Who to call
- Someone who bought a manual audit or is actively considering it
- Must be technical enough to understand their own API spend (eng lead, infrastructure owner, dev manager)
- Must have budget authority (they said yes, they own the decision)

---

## The Script (8 minutes, one conversation)

### Q1: "After we finished the audit, what did you actually change?"
**Why:** Tests if the problem is real enough to drive action, not just "yeah we should probably look at this someday."

**Listen for:**
- "We turned off X service, saved $5k/month" → real pain ✓
- "We optimized Y" → real pain ✓
- "We got the report and haven't looked at it yet" → not urgent ✗
- "We didn't change anything, but now we know why our bill is high" → knowing ≠ fixing ✗

**If answer is ✓:** Continue to Q2
**If answer is ✗:** Move to Q3 only, then stop

---

### Q2: "Would you pay $X/month (pick $50, $100, or $300 based on company size) for us to keep sending you this analysis every month?"
**Why:** Tests if this is a one-time fix or a recurring need.

**Listen for:**
- "Yes, absolutely" → business model ✓
- "Maybe, let me think" → NO, this is "not really"
- "Only if you also do [X feature]" → they don't want the product, they want something else
- "We do this ourselves quarterly" → commodity, can't charge

**If answer is ✓:** Business exists, keep building
**If answer is ✗:** One-time product, plan pivot to monitoring or kill

---

### Q3: "What would make you actually act on the next audit we send you?"
**Why:** If Q1 or Q2 failed, this tells us if the blocker is product/price or if the pain just isn't real.

**Listen for:**
- "If you included the fixes, not just the findings" → need more value-add, not just audit
- "If it was a dashboard instead of a report" → they want product, not consulting
- "If it was $X instead of $Y" → price is real constraint
- "Honestly, we probably wouldn't change anything" → pain is not real enough

**What to do with the answer:**
- "Include fixes" → add that to audit delivery, test in week 6
- "Want a dashboard" → confirms monitoring product is the right move
- "Price is the issue" → pricing is wrong, not the business model
- "Pain not real" → kill, move on

---

## After the interview

**If Q1=✓ and Q2=✓:** Confirm them as reference customer. Plan next 3 customers.

**If Q1=✓ and Q2=✗:** File as "pain is real but not recurring." Diagnostic: do they want monitoring product instead? If yes, pivot there. If no, kill.

**If Q1=✗:** Audit is a nice-to-have, not a must-have. Probably kill. Only exception: if 5+ prospects say the same thing, we have a positioning problem, not a market problem.

---

## Timeline
- Conduct this week 5 (by Wednesday, give yourself 3 days for iteration before Friday decision)
- Have answer by Friday week 5
- Ship based on answer by Monday week 6