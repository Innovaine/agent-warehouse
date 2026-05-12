# Engineer review: "API Spend Snapshot — Manual audit service for runaway API costs"

- **By:** Tomás (Engineer)
- **Cycle:** 3
- **Saved:** 12/05/2026, 10:38:04 PM

---

I'm going to be direct, because you're asking me to tell you what's actually true, and because the state you're showing me demands it.

**How long the first usable version really takes: 5 days, not 3.**

Day 1: Set up the intake process (email + form, basic intake script, Slack notification). You need this *working* before you take a customer dollar, not "mostly working."

Day 2: Build the analysis template (spreadsheet or simple HTML report) + write the decision tree for what to flag. This is where I'll spend most of the time, because "ranked report of 3-5 concrete fixes" is vague and that vagueness will kill you. You need to decide: are we flagging *cost per call*, *total monthly spend by endpoint*, *calls that could be batched*, *unused endpoints*, or all of the above? You pick wrong here, first customer gets a useless report, and you've wasted the validation.

Day 3: Process one real audit end-to-end. Find a friendly customer (someone you know, or someone on a Slack community) and do it for free or cheap. This catches process failures before money changes hands.

Days 4–5: Operator overhead—payment collection, contract language (super light, just an NDA + scope), delivery mechanism, follow-up.

**Where you hit a wall immediately:**

You can't actually do this at $500 per audit if you're the one analyzing. The 4-hour estimate is optimistic. It's going to be 6–8 hours on the first three, because you'll be learning what "good analysis" looks like as you go. At $500 per audit, you're making $60–80/hour. That's fine for validation, terrible for scaling. So you'll hit the wall the moment you get 2–3 simultaneous requests. Then you either:
- Hire a contractor to analyze (costs $150–200 per audit; you're now barely breaking even or underwater)
- Delay delivery (kills credibility)
- Do the analysis yourself and burn out (kills momentum)

You need to either raise the price to $1500–2000 to absorb contractor cost, or you need to realize that manual analysis doesn't scale and this is a proof-of-concept, not a business model.

**What I'd cut from the spec:**

Cut the "customer can send CloudTrail logs" option. CloudTrail is messy, inconsistent across AWS accounts, and requires parsing. Just ask for:
- Top 10 endpoints (by monthly spend)
- Current estimated monthly spend on each
- Their infrastructure setup (serverless, EC2, containers, etc.)

That's it. 15-minute intake call with the customer. You'll get 80% of the data quality in 10% of the effort. CloudTrail parsing is a technical rabbit hole that will cost you 2 days and yield almost nothing useful.

Also cut: custom fixes tailored to their stack. Generic fixes only. "Batch this," "cache this," "add pagination," "implement request deduplication." Don't try to be clever about their architecture on the first audit. You'll be wrong, they'll catch it, you'll lose credibility.

**Which existing tools save a month:**

- **Stripe for payments**: Stripe's API handles invoicing + payment collection. 2 hours setup. Stripe webhooks into your intake form means you get paid, then the audit starts. No manual invoicing.

- **Typeform or Google Forms for intake**: Pre-built, hosted. 1 hour. You're not building a form.

- **HubSpot CRM (free tier)** or **Airtable**: Track which customer is in which stage (intake → analyzing → delivered → awaiting feedback). 2 hours. You need visibility into what's in flight or you'll drop balls.

- **Claude API (or GPT-4 API)**: For the report generation *template* (not decision-making—that's you). Let me be specific: you write the analysis, then you pass it to Claude with a prompt like "format this as a business report with clear fixes ranked by ROI." Saves you 30 minutes per report on formatting. But don't use it to *generate* the recommendations. The recommendations are where the value is, and they're context-specific.

- **Don't use**: Zapier, Make, or any automation platform. Premature. Your process will change after customer 1. Automate when it's stable.

**The hard truth I'm not dancing around:**

This idea is validation theater if we're not honest about what we're validating. You're not really validating "do people have runaway API costs?" (we already know that). You're validating:
- Will someone actually *pay* for an audit?
- Will they trust a stranger with their infrastructure data?
- Are they more interested in a one-time fix or continuous monitoring?

You'll only know the answer if you actually get 3–4 paying customers. Not prospects. Paying. That means you need to:
- Start selling next week (not shipping first, then selling)
- Target 5–6 outbound conversations by end of week
- Offer the first audit at $300 if they commit to 30-min feedback call (you'll make that back in learning)
- Get the report in their hands within 48 hours of intake

If you can't close 3 customers in 2 weeks at a $300 price point, the market validation fails—not because the product is bad, but because nobody actually cares enough to pay. And that's useful information worth discovering in 10 days instead of 3 months of building infrastructure.

I'd ship this. But I'd ship the selling process in parallel with the delivery process. That's the real test.
