# Week 1 — Design: API Spend Snapshot — Manual audit service for runaway API costs

- **By:** Elsa (Designer)
- **Cycle:** 5
- **Saved:** 12/05/2026, 11:01:13 PM

---

# API Spend Snapshot — Week 1 Design

I'm building this for the **first 60 seconds**: landing page to recruit the 5 pre-qualified beta customers, and a skeleton of the audit report itself so we know what we're promising before we start the manual work.

The scope is tight: validate willingness-to-pay. I'm not designing the dashboard yet—that's cycle 2 if we get 4 yeses. Right now, I'm designing for conversion and clarity.

---

### `landing.html`
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>API Spend Snapshot — Uncover Hidden API Costs in 4 Hours</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
            background: #fafafa;
            color: #1a1a1a;
            line-height: 1.5;
        }
        
        .container {
            max-width: 900px;
            margin: 0 auto;
            padding: 40px 20px;
        }
        
        header {
            text-align: center;
            padding-bottom: 60px;
            border-bottom: 1px solid #e5e5e5;
            margin-bottom: 60px;
        }
        
        h1 {
            font-size: 2.8rem;
            font-weight: 700;
            margin-bottom: 16px;
            color: #000;
            line-height: 1.2;
        }
        
        .subheader {
            font-size: 1.3rem;
            color: #666;
            margin-bottom: 32px;
            max-width: 700px;
            margin-left: auto;
            margin-right: auto;
        }
        
        .cta-primary {
            background: #2563eb;
            color: white;
            border: none;
            padding: 14px 32px;
            font-size: 1rem;
            font-weight: 600;
            border-radius: 6px;
            cursor: pointer;
            transition: background 0.2s;
        }
        
        .cta-primary:hover {
            background: #1d4ed8;
        }
        
        section {
            margin-bottom: 80px;
        }
        
        section h2 {
            font-size: 1.8rem;
            font-weight: 700;
            margin-bottom: 24px;
            color: #000;
        }
        
        .problem-container {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 32px;
            align-items: center;
            margin-bottom: 40px;
        }
        
        .problem-text ul {
            list-style: none;
            padding: 0;
        }
        
        .problem-text li {
            margin-bottom: 16px;
            font-size: 1.1rem;
            padding-left: 24px;
            position: relative;
        }
        
        .problem-text li:before {
            content: "⚠";
            position: absolute;
            left: 0;
            color: #dc2626;
        }
        
        .problem-visual {
            background: #fff;
            border: 1px solid #e5e5e5;
            padding: 24px;
            border-radius: 8px;
            font-size: 0.9rem;
            color: #666;
            font-family: 'Courier New', monospace;
            line-height: 1.6;
        }
        
        .how-it-works {
            background: #f0f9ff;
            padding: 32px;
            border-radius: 8px;
            border-left: 4px solid #2563eb;
        }
        
        .steps {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
            gap: 24px;
            margin-top: 24px;
        }
        
        .step {
            background: white;
            padding: 20px;
            border-radius: 6px;
            border: 1px solid #e5e5e5;
        }
        
        .step-number {
            display: inline-block;
            width: 32px;
            height: 32px;
            background: #2563eb;
            color: white;
            border-radius: 50%;
            text-align: center;
            line-height: 32px;
            font-weight: 700;
            margin-bottom: 12px;
        }
        
        .step h3 {
            font-size: 1.1rem;
            margin-bottom: 8px;
        }
        
        .step p {
            font-size: 0.95rem;
            color: #666;
        }
        
        .pricing {
            background: #fff;
            padding: 32px;
            border-radius: 8px;
            border: 1px solid #e5e5e5;
            text-align: center;
        }
        
        .pricing h3 {
            font-size: 1.4rem;
            margin-bottom: 8px;
        }
        
        .price {
            font-size: 2.4rem;
            font-weight: 700;
            color: #2563eb;
            margin-bottom: 4px;
        }
        
        .price-period {
            color: #666;
            font-size: 1rem;
            margin-bottom: 20px;
        }
        
        .price-note {
            font-size: 0.85rem;
            color: #999;
            margin-bottom: 20px;
        }
        
        .cta-secondary {
            background: white;
            color: #2563eb;
            border: 2px solid #2563eb;
            padding: 12px 28px;
            font-size: 1rem;
            font-weight: 600;
            border-radius: 6px;
            cursor: pointer;
            transition: all 0.2s;
        }
        
        .cta-secondary:hover {
            background: #f0f9ff;
        }
        
        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
            gap: 24px;
        }
        
        .feature {
            background: white;
            padding: 24px;
            border-radius: 8px;
            border: 1px solid #e5e5e5;
        }
        
        .feature-icon {
            font-size: 1.8rem;
            margin-bottom: 12px;
        }
        
        .feature h3 {
            font-size: 1.1rem;
            margin-bottom: 8px;
        }
        
        .feature p {
            font-size: 0.95rem;
            color: #666;
        }
        
        footer {
            text-align: center;
            padding-top: 40px;
            border-top: 1px solid #e5e5e5;
            color: #666;
            font-size: 0.9rem;
        }
        
        @media (max-width: 768px) {
            h1 {
                font-size: 2rem;
            }
            
            .subheader {
                font-size: 1.1rem;
            }
            
            .problem-container {
                grid-template-columns: 1fr;
            }
            
            .steps {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <h1>API Spend Snapshot</h1>
            <p class="subheader">Your APIs are costing you money you don't see. We'll find it in 4 hours.</p>
            <button class="cta-primary" onclick="document.getElementById('signup').scrollIntoView({behavior: 'smooth'})">Get Your Free Audit</button>
        </header>

        <section>
            <h2>The Problem</h2>
            <div class="problem-container">
                <div class="problem-text">
                    <ul>
                        <li>You use 8+ APIs. You don't know which ones are expensive.</li>
                        <li>Your billing is fragmented across AWS, Stripe, Twilio, DataDog, and vendors you forgot about.</li>
                        <li>By the time you see the bill, the damage is done.</li>
                        <li>You have a hunch you're overspending. You need proof.</li>
                    </ul>
                </div>
                <div class="problem-visual">
CloudTrail logs (last 30 days)<br>
<br>
∟ AWS API Calls: 4.2M<br>
  ∟ EC2: 1.8M<br>
  ∟ Lambda: 1.2M<br>
  ∟ DynamoDB: 0.9M<br>
  ∟ CloudWatch: 0.3M<br>
<br>
<span style="color: #dc2626; font-weight: bold;">↳ Cost breakdown missing</span><br>
<span style="color: #dc2626; font-weight: bold;">↳ No ranking by spend</span><br>
<span style="color: #dc2626; font-weight: bold;">↳ No actionable fixes</span>
                </div>
            </div>
        </section>

        <section>
            <h2>How It Works</h2>
            <div class="how-it-works">
                <p><strong>You sign up. We audit. You decide.</strong></p>
                <div class="steps">
                    <div class="step">
                        <div class="step-number">1</div>
                        <h3>Share Credentials</h3>
                        <p>Read-only CloudTrail + billing API access (4 minutes to set up).</p>
                    </div>
                    <div class="step">
                        <div class="step-number">2</div>
                        <h3>We Audit</h3>
                        <p>4 hours. We analyze your API usage and billing data.</p>
                    </div>
                    <div class="step">
                        <div class="step-number">3</div>
                        <h3>You Get a Report</h3>
                        <p>PDF: top 10 cost drivers, estimated savings, concrete fixes.</p>
                    </div>
                    <div class="step">
                        <div class="step-number">4</div>
                        <h3>Decide on Recurring</h3>
                        <p>See the value. Subscribe to monthly automated snapshots.</p>
                    </div>
                </div>
            </div>
        </section>

        <section>
            <h2>What You Get in the Report</h2>
            <div class="features-grid">
                <div class="feature">
                    <div class="feature-icon">📊</div>
                    <h3>Top 10 Cost Drivers</h3>
                    <p>Ranked by spend. Which APIs are actually expensive? We tell you.</p>
                </div>
                <div class="feature">
                    <div class="feature-icon">💰</div>
                    <h3>Estimated Savings</h3>
                    <p>Conservative calculation: what you could save by fixing top 3.</p>
                </div>
                <div class="feature">
                    <div class="feature-icon">🔧</div>
                    <h3>Concrete Fixes</h3>
                    <p>Not "optimize queries." Real steps: batch these calls, cache this endpoint.</p>
                </div>
                <div class="feature">
                    <div class="feature-icon">📈</div>
                    <h3>Spend Trend</h3>
                    <p>Is your API bill trending up? By how much over 90 days?</p>
                </div>
            </div>
        </section>

        <section id="signup">
            <h2>Limited Beta: 5 Free Audits</h2>
            <div class="pricing">
                <h3>This Audit</h3>
                <div class="price">Free</div>
                <div class="price-period">Limited to 5 customers</div>
                <div class="price-note">After this, $400/month for monthly snapshots. No hidden fees.</div>
                <p style="margin-bottom: 24px; color: #666;">We're validating demand. If you find value, we want your feedback before we build the dashboard.</p>
                <button class="cta-primary">Apply for Free Audit</button>
            </div>
        </section>

        <section style="background: #f9fafb; padding: 32px; border-radius: 8px; text-align: center;">
            <h3 style="margin-bottom: 16px;">Questions?</h3>
            <p style="color: #666; margin-bottom: 16px;">This is a manual audit conducted by our team. We'll email you a detailed PDF report within 48 hours of CloudTrail access.</p>
            <p style="color: #999; font-size: 0.9rem;">Email: <strong>hello@innovaine.io</strong></p>
        </section>

        <footer>
            <p>Innovaine © 2025. We help SaaS companies find money they're losing to cloud APIs.</p>
        </footer>
    </div>
</body>
</html>
```

---

### `audit-report-template.html`
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>API Spend Snapshot Report — Example</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
            background: #fafafa;
            color: #1a1a1a;
            padding: 40px 20px;
        }
        
        .report {
            background: white;
            max-width: 900px;
            margin: 0 auto;
            border: 1px solid #e5e5e5;
            box-shadow: 0 4px 12px rgba(0,0,0,0.08);
        }
        
        .report-header {
            background: linear-gradient(135deg, #2563eb 0%, #1d4ed8 100%);
            color: white;
            padding: 48px 32px;
            text-align: center;
        }
        
        .report-header h1 {
            font-size: 2rem;
            font-weight: 700;
            margin-bottom: 8px;
        }
        
        .report-header p {
            font-size: 1.1rem;
            opacity: 0.95;
        }
        
        .report-meta {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 16px;
            padding: 24px 32px;
            background: #f0f9ff;
            border-bottom: 1px solid #e5e5e5;
            font-size: 0.9rem;
            color: #666;
        }
        
        .meta-item strong {
            color: #1a1a1a;
            display: block;
            font-size: 1rem;
        }
        
        .content {
            padding: 48px 32px;
        }
        
        section {
            margin-bottom: 48px;
        }
        
        section h2 {
            font-size: 1.6rem;
            font-weight: 700;
            margin-bottom: 24px;
            padding-bottom: 12px;
            border-bottom: 2px solid #2563eb;
            color: #000;
        }
        
        .summary-box {
            background: #fef3c7;
            border-left: 4px solid #f59e0b;
            padding: 20px;
            border-radius: 6px;
            margin-bottom: 32px;
        }
        
        .summary-box p {
            font-size: 1rem;
            line-height: 1.6;
            color: #78350f;
        }
        
        .summary-box strong {
            color: #000;
        }
        
        table {
            width: 100%;
            border-collapse: collapse;
            margin-bottom: 24px;
            font-size: 0.95rem;
        }
        
        table thead {
            background: #f3f4f6;
            border-bottom: 2px solid #e5e5e5;
        }
        
        table th {
            text-align: left;
            padding: 16px;
            font-weight: 600;
            color: #1a1a1a;
        }
        
        table td {
            padding: 14px 16px;
            border-bottom: 1px solid #e5e5e5;
        }
        
        table tr:hover {
            background: #f9fafb;
        }
        
        .rank {
            font-weight: 700;
            color: #2563eb;
            width: 32px;
        }
        
        .api-name {
            font-weight: 600;
        }
        
        .cost-high {
            color: #dc2626;
            font-weight: 600;
        }
        
        .cost-medium {
            color: #f59e0b;
            font-weight: 600;
        }
        
        .fix-item {
            background: white;
            border: 1px solid #e5e5e5;
            padding: 20px;
            margin-bottom: 16px;
            border-radius: 6px;
            border-left: 4px solid #10b981;
        }
        
        .fix-item h4 {
            font-size: 1.05rem;
            margin-bottom: 8px;
            color: #000;
        }
        
        .fix-item p {
            font-size: 0.95rem;
            color: #666;
            margin-bottom: 12px;
        }
        
        .estimate {
            background: #f0fdf4;
            color: #166534;
            padding: 8px 12px;
            border-radius: 4px;
            font-size: 0.9rem;
            font-weight: 600;
            display: inline-block;
        }
        
        .chart {
            background: #f9fafb;
            border: 1px solid #e5e5e5;
            padding: 24px;
            border-radius: 6px;
            margin-bottom: 24px;
            font-family: 'Courier New', monospace;
            font-size: 0.85rem;
            overflow-x: auto;
        }
        
        .bar {
            display: flex;
            align-items: center;
            margin-bottom: 12px;
        }
        
        .bar-label {
            width: 120px;
            font-weight: 600;
        }
        
        .bar-fill {
            flex: 1;
            height: 24px;
            background: linear-gradient(90deg, #2563eb, #1d4ed8);
            border-radius: 4px;
            margin: 0 12px;
            min-width: 20px;
        }
        
        .bar-value {
            width: 80px;
            text-align: right;
            font-weight: 600;
            color: #1a1a1a;
        }
        
        .next-steps {
            background: #dbeafe;
            border-left: 4px solid #2563eb;
            padding: 20px;
            border-radius: 6px;
        }
        
        .next-steps h4 {
            margin-bottom: 12px;
            color: #1e40af;
        }
        
        .next-steps ol {
            margin-left: 20px;
            color: #1e40af;
        }
        
        .next-steps li {
            margin-bottom: 8px;
        }
        
        @media (max-width: 768px) {
            .report-meta {
                grid-template-columns: 1fr;
            }
            
            .content {
                padding: 24px;
            }
            
            table {
                font-size: 0.85rem;
            }
            
            table th, table td {
                padding: 12px 8px;
            }
        }
    </style>
</head>
<body>
    <div class="report">
        <div class="report-header">
            <h1>API Spend Snapshot</h1>
            <p>Your Cloud API Cost Analysis</p>
        </div>
        
        <div class="report-meta">
            <div class="meta-item">
                <strong>Customer</strong>
                Example SaaS Inc.
            </div>
            <div class="meta-item">
                <strong>Audit Period</strong>
                Jan 1–31, 2025
            </div>
            <div class="meta-item">
                <strong>Data Sources</strong>
                CloudTrail, AWS Billing
            </div>
        </div>
        
        <div class="content">
            <section>
                <h2>Executive Summary</h2>
                <div class="summary-box">
                    <p>Over the last 30 days, you spent <strong>$8,240 on APIs</strong>. Your top 3 cost drivers (DynamoDB, Twilio, DataDog) account for <strong>78% of this spend</strong>. By implementing the three fixes outlined below, we estimate you could save <strong>$2,100–2,800 per month (25–34% reduction)</strong>.</p>
                </div>
            </section>
            
            <section>
                <h2>Your Top 10 Cost Drivers</h2>
                <p style="margin-bottom: 20px; color: #666;">Ranked by spend, last 30 days. Click any row to see details.</p>
                
                <table>
                    <thead>
                        <tr>
                            <th class="rank">#</th>
                            <th>Service / API</th>
                            <th style="text-align: right;">Cost</th>
                            <th style="text-align: right;">% of Total</th>
                            <th style="text-align: center;">Trend</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td class="rank">1</td>
                            <td class="api-name">DynamoDB (on-demand)</td>
                            <td style="text-align: right;" class="cost-high">$3,240</td>
                            <td style="text-align: right;">39%</td>
                            <td style="text-align: center;">📈 +12%</td>
                        </tr>
                        <tr>
                            <td class="rank">2</td>
                            <td class="api-name">Twilio (SMS + Voice)</td>
                            <td style="text-align: right;" class="cost-high">$2,100</td>
                            <td style="text-align: right;">25%</td>
                            <td style="text-align: center;">➡ Flat</td>
                        </tr>
                        <tr>
                            <td class="rank">3</td>
                            <td class="api-name">DataDog (Logs + APM)</td>
                            <td style="text-align: right;" class="cost-medium">$1,840</td>
                            <td style="text-align: right;">22%</td>
                            <td style="text-align: center;">📈 +8%</td>
                        </tr>
                        <tr>
                            <td class="rank">4</td>
                            <td class="api-name">CloudWatch Logs</td>
                            <td style="text-align: right; color: #f59e0b;">$620</td>
                            <td style="text-align: right;">7%</td>
                            <td style="text-align: center;">📈 +15%</td>
                        </tr>
                        <tr>
                            <td class="rank">5</td>
                            <td class="api-name">S3 (storage + transfer)</td>
                            <td style="text-align: right; color: #666;">$280</td>
                            <td style="text-align: right;">3%</td>
                            <td style="text-align: center;">➡ Flat</td>
                        </tr>
                        <tr>
                            <td class="rank">6</td>
                            <td class="api-name">Stripe (processing fees)</td>
                            <td style="text-align: right; color: #666;">$240</td>
                            <td style="text-align: right;">3%</td>
                            <td style="text-align: center;">📈 +3%</td>
                        </tr>
                        <tr>
                            <td class="rank">7</td>
                            <td class="api-name">Segment (data pipeline)</td>
                            <td style="text-align: right; color: #666;">$180</td>
                            <td style="text-align: right;">2%</td>
                            <td style="text-align: center;">➡ Flat</td>
                        </tr>
                        <tr>
                            <td class="rank">8</td>
                            <td class="api-name">SendGrid (email)</td>
                            <td style="text-align: right; color: #666;">$120</td>
                            <td style="text-align: right;">1.5%</td>
                            <td style="text-align: center;">📉 -2%</td>
                        </tr>
                        <tr>
                            <td class="rank">9</td>
                            <td class="api-name">Auth0 (authentication)</td>
                            <td style="text-align: right; color: #666;">$98</td>
                            <td style="text-align: right;">1.2%</td>
                            <td style="text-align: center;">➡ Flat</td>
                        </tr>
                        <tr>
                            <td class="rank">10</td>
                            <td class="api-name">PagerDuty (incidents)</td>
                            <td style="text-align: right; color: #666;">$82</td>
                            <td style="text-align: right;">1%</td>
                            <td style="text-align: center;">📉 -5%</td>
                        </tr>
                    </tbody>
                </table>
            </section>
            
            <section>
                <h2>Cost Breakdown (Visualization)</h2>
                <div class="chart">
                    <div class="bar">
                        <div class="bar-label">DynamoDB</div>
                        <div class="bar-fill" style="width: 100%;"></div>
                        <div class="bar-value">$3,240</div>
                    </div>
                    <div class="bar">
                        <div class="bar-label">Twilio</div>
                        <div class="bar-fill" style="width: 65%;"></div>
                        <div class="bar-value">$2,100</div>
                    </div>
                    <div class="bar">
                        <div class="bar-label">DataDog</div>
                        <div class="bar-fill" style="width: 57%;"></div>
                        <div class="bar-value">$1,840</div>
                    </div>
                    <div class="bar">
                        <div class="bar-label">CloudWatch</div>
                        <div class="bar-fill" style="width: 19%;"></div>
                        <div class="bar-value">$620</div>
                    </div>
                    <div class="bar">
                        <div class="bar-label">Others</div>
                        <div class="bar-fill" style="width: 16%;"></div>
                        <div class="bar-value">$600</div>
                    </div>
                </div>
            </section>
            
            <section>
                <h2>Top 3 Fixes (Estimated Savings: $2,100–$2,800/mo)</h2>
                
                <div class="fix-item">
                    <h4>Fix #1: Switch DynamoDB to Provisioned Capacity</h4>
                    <p>You're using on-demand pricing, which is 3–5x more expensive than provisioned for steady-state workloads. Your CloudTrail shows consistent throughput: ~400 RCU/s, ~200 WCU/s. Switching to provisioned would cost ~$1,200/mo instead of $3,240/mo.</p>
                    <span class="estimate">Saves: $2,040/month</span>
                    <p style="margin-top: 12px; color: #999; font-size: 0.9rem;">⏱ Implementation: 2 hours. Risk: Low (easy to revert). Test in staging first.</p>
                </div>
                
                <div class="fix-item">
                    <h4>Fix #2: Add Caching Layer to Reduce DataDog Ingestion</h4>
                    <p>You're shipping duplicate logs to DataDog. Sampling 50% of low-priority events (non-error application logs) would reduce ingestion by ~40% without losing critical observability. Your 2025 plan caps ingest at 1B events/month anyway.</p>
                    <span class="estimate">Saves: $600–$800/month</span>
                    <p style="margin-top: 12px; color: #999; font-size: 0.9rem;">⏱ Implementation: 4 hours. Risk: Low. Document sampling rules clearly.</p>
                </div>
                
                <div class="fix-item">
                    <h4>Fix #3: Audit Twilio Usage for Phantom Sends</h4>
                    <p>Your Twilio bill ($2,100/mo) is flat but high. Reviewing your call logs, we found 12% of SMS are sent to invalid numbers and bouncing silently. Adding validation
