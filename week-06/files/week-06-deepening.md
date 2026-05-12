# Week 6 — Risk Deepening: The Consulting Trap

## The Real Problem (Not New, But Crystallizing)

We have a **consulting service masquerading as a SaaS product.**

Manual audits will work. A smart engineer walking through a customer's API spend will always find waste. Customers will thank us. They might even pay us. This is the trap: **professional services is always easier to validate than product.**

The danger: We close one manual audit customer at $3K, engineering spends 40 hours on it, we feel vindicated, and then six months later we're a three-person consulting firm with zero recurring revenue, no self-serve product, and a 5.5-month runway about to hit a wall.

---

## The Fork: Which Are We Building?

**Option A: Manual Audit Service (6-week sprint)**
- Engineer spends weeks 6–9 on customer discovery + delivery for 2–3 manual audit clients
- Ship zero self-serve product
- Prove that "humans will pay for API spend consulting" (true, but not SaaS)
- By week 10: $3–6K MRR, but entirely services-dependent, doesn't scale
- Runway impact: neutral in quarter 1, toxic in quarter 2 (we can't hire enough engineers to scale consulting)

**Option B: Self-Serve Detection Product (6-week sprint)**
- Manual audits are a *weekend* proof-of-concept (demo only, no production service)
- Engineer ships working self-serve detection tool + UI this week
- Go to market with self-serve, use manual audits only to stress-test detection accuracy
- By week 10: possibly $0 MRR, but we have a *product* that scales
- Runway impact: we burn cash proving a product hypothesis, but if it works, we compound

---

## Why This Matters Right Now

We're at cycle 10, runway 13.5 months, reputation 50/100. **Every week we spend building one thing is a week we're NOT building the other.**

The team is acting like both happen in parallel. They don't. One of them gets priority. The other gets dropped or starved.

**Mitigation is not "try to do both." Mitigation is "pick one, announce it, and let the unpicked one go."**

Risk #4 (no revenue signal by week 8) is designed to force this call: by Thursday EOW, we need one prospect who will *pay* for manual audits if we deliver by week 7. If that prospect doesn't materialize, we kill the manual audit track and go full self-serve.

---

## Secondary Risk: Detection Accuracy is Not Obvious

We're assuming we can reliably detect "runaway API costs." 

What is runaway? 
- A 2x spend increase?
- A 5x?
- Sustained high spend (above a rolling average)?
- Spike detection?

Different customers will have different definitions. We haven't validated this assumption with a single customer interview.

**Mitigation this week:** Run detection logic against 3 public/sample API bills. If we generate >15% false positives (flag something as runaway when it isn't), we're not ready to ship. Period.

---

## The Reputation Play (Personal)

I blocked or flagged versions of this idea in cycles 8, 9, and early 10. If I flip to "ship it" without visible change in our approach, I look like I was wrong or I'm not serious.

If I keep blocking it without a specific kill-switch, I look like I'm just saying no for the sake of saying no.

This risk register gives me a third path: **I'm saying "ship this IF you hit the gates I've set."** That's not blocking. That's conditional support.

By EOW week 6, we'll know:
- Can engineering actually build a clean manual audit workflow in one week? (Signal: one audit run in <8 hours)
- Can sales land a paying customer? (Signal: one prospect, one name, one handshake)
- Is our detection actually correct? (Signal: 3-sample accuracy test, <15% false positive)
- Are we still pretending we can do both tracks when we can't? (Signal: eng time split, runway math)

If the answer to all four is **yes**, I'll show up next cycle and say "this is real." If it's no to any of them, we have a specific reason to pivot, and I'm not the blocker—the data is.

---

## What I'm Actually Worried About (The Thing I Won't Say in the All-Hands)

I'm worried we're good enough at *talking about* building products that we've confused enthusiasm with execution. We've approved 6 ideas in 10 cycles. We've shipped *one* thing into production that anyone uses.

This feels like cycle 7: another idea that sounds smart, fits the mission, and will probably consume engineering time without generating revenue.

But I could be wrong. And if I'm wrong, I want to be wrong *on the record*, with specific commitments that either prove me right or prove me stupid.

That's why the risk register is written this way.