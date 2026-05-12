# Week 11 Contingency: Next Product in Queue & Payroll Reallocation

## If API Spend Snapshot Kills at Week 11

### Product to Activate: "Cost Alert Automator" (from earlier cycle queue)

**Concept:** Automated alerts for runaway API spend (sends Slack/email when spend exceeds threshold for account or specific endpoint).

**Why this one:** It solves the same problem (runaway cloud costs) but as repeatable SaaS, not manual labor. If API Spend Snapshot kills, we keep market knowledge and pivot to recurring product instead of services.

**Projected unit economics (weeks 12–16):**

| Metric | Target |
|---|---|
| Monthly subscription price | $299 |
| Target customers by week 16 | 3 |
| MRR by week 16 | $897 |
| Gross margin per customer | 85% (mostly COGS is alert infrastructure) |
| CAC | $400 (sales labor; same outbound effort as audits) |
| Payback period | ~2 months per customer |
| Break-even customers | 6–7 paying (if burn stays $19k/wk) |

**Why it's viable:** We don't build the alert system from scratch — we use Datadog/PagerDuty webhooks + Slack integration (outsourced, <$200/mo fixed cost). We own the thresholds, the UX, the customer layer.

---

## Payroll Reallocation (if kill triggered at week 11)

| Role | Current allocation | Post-kill allocation | Change |
|---|---|---|---|
| Engineering (2 FTE) | 1.5 on audits + 0.5 other | 2.0 on Cost Alert Automator | +1.5 capacity |
| Ops / Customer success (0.5 FTE) | 0.5 on audit delivery + ops | 0.3 on C1 retainer support (if recurring) + 0.2 on sales | -0.2 FTE |
| Sales / bizdev (0.5 FTE) | 0.5 hunting audit customers | 0.5 hunting alert subscribers | No change |

**Net runway impact:** 
- Save $6,200/wk in direct engineering labor on audits (2 FTE at $100/hr blended = $8k theoretical; actual burdened is ~$6.2k/wk after overhead absorption)
- Lose ~$400/wk in infrastructure spend if we stay with alerts (webhooks, Slack API, minimal hosting)
- **Net: +$5,800/wk saved, or +3.0 weeks runway**

**Cash impact at week 12 kill:**
- Cash on hand week 11 (if no new customers): ~$182k
- Add back $6.2k/wk savings weeks 12–16 = +$31k
- New projected cash week 16: ~$213k (extends from 6.8 weeks to ~11 weeks)

---

## Cost Alert Automator — 4-Week Build Plan (weeks 12–15)

| Week | Deliverable | Labor hours | Notes |
|---|---|---|---|
| 12 | Slack integration + webhook listener | 40 | Outsource to Twilio/Slack SDK; own the threshold logic |
| 13 | Datadog/CloudWatch connector | 35 | Pull cost data; trigger alerts at user-defined thresholds |
| 14 | Onboarding flow + docs | 20 | Self-serve setup; customer deploys their own webhook |
| 15 | First 2 customers onboarded | 25 | Close from warm outbound (API Snapshot warm leads) |

**Ship date:** Week 15 MVP (Slack + Datadog; no Twilio, no multi-channel yet)

**Rationale:** Same customer segment (DevOps, platform engineers, finance teams at mid-market), same pain (runaway cloud costs), but recurring revenue model. We reuse sales conversations from API Snapshot even if the product kills.