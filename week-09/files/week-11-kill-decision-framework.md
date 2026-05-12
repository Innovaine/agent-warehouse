# Week 11 Decision Framework — API Spend Snapshot Continue/Kill Gate

## The Three Conditions (ALL three must hit for kill/pause decision)

**Condition 1: Pipeline emptiness**
- Customer 2 is NOT contracted by close of business week 11
- AND zero qualified prospects in active conversation (defined as: intake call booked, or email thread indicating budget/timeline)

**Condition 2: Labor unit economics don't improve**
- Customer 1 actual time sheet shows ≥12 hours (meaning we broke even, not profitably)
- AND customer 2 (if it exists) also required ≥11 hours (no process improvement signal)

**Condition 3: No recurring signal**
- Customer 1 has not expressed interest in monthly/quarterly recurring audits
- AND customer 1 referral pipeline is empty (zero warm intros from the customer)

## Decision Matrix

| Customer 2 by week 11? | Recurring signal from C1? | Kill or Continue? | Next action |
|---|---|---|---|
| Yes | Yes (monthly retainer or quarterly) | **CONTINUE** | Shift to subscription model; reforecast 12-week horizon |
| Yes | No | **CONTINUE on probation** | Land customer 3 by week 13; if stalls, kill week 14 |
| No | Yes | **CONTINUE on probation** | Customer 1 recurring pays runway; hunt customer 2 in week 12–13 |
| No | No | **KILL** | Reallocate engineering to next idea; archive service code; week 12 sunset |

## Kill Execution (if triggered)
- **When:** Start of week 12
- **Labor reallocation:** 2 engineers → next product idea (TBD); 0.5 ops → customer 1 wind-down support (quarterly retainer only if C1 asks)
- **Runway impact:** Save ~$6,200/wk in direct labor = +3.2 weeks runway
- **Customer 1 handling:** Deliver Q4 audit on retainer schedule if they ask; do not hunt for new one-time audits

## Flip Condition (if ANY of these hit before week 11, extend timeline)
1. **Recurring interest arrives early:** Customer 1 proposes monthly audit by week 10 → immediately shift model, no kill decision
2. **Warm inbound arrives:** Prospect contacts us directly (inbound, not outbound) before week 11 → signals market pull; extend decision to week 13
3. **Customer 1 referral closes:** Any referred customer contracts before week 11 → proves demand is warm; stay on continue path

## Measurement (what "contracted" means)
- Customer 2 must have signed statement of work with scope, price, and delivery date
- Email confirmation from prospect (or signed DocuSign) counts; verbal intent does not
- Must be before close of business Friday, week 11 (COB Oct 25 EOD)