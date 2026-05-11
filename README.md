# Mailchimp Email Editor Migration Briefing

Executive briefing on the **NEA → NUNI** email editor migration: where we are, why it has stalled, what it has cost us, and how to finish without losing the HVC base.

**Live briefing:** https://deepakp1308.github.io/mailchimp-email-editor-analysis/

## What's in the briefing

1. **Executive Summary** — 8 top metrics, 5 things a senior exec must take away, 3 decision asks
2. **Situation** — current editor distribution, migration trend over 24 months
3. **Complication** — the 4 things that change the calculus (HVC inversion, CSAT decline, 225K reverters, editor-cited churn)
4. **Key Question** — how to close $565M ARR migration without losing the customers we can't afford to lose
5. **Recommendation** — 3-phase, parity-gated migration playbook with cumulative ARR mitigation
6. **Decision Asks** — 5 specific items with owner and "why now"
7. **Appendix (12 sections)** — methodology, geo/plan/ICP breakdowns, migration trend tables, migrator vs stayer profiles, stayer themes with verbatim VOC, top NUNI complaint topics, editor-cited churn deep dive (annualized), HVC stayer characteristics, sentiment trend, migration outcome breakdown, phase-mitigation calculator, Slack VOC stats

## Headline numbers

| Metric | Value |
|---|---|
| NUNI adoption | 62.5% (1.97M users) |
| Remaining NEA paid base | $565M ARR ($47.1M MRR × 12) |
| HVC ARR concentration on NEA | $281M ARR (38,145 users) |
| CES delta (NUNI vs NEA) | -0.10 (3.90 vs 4.00) |
| Reverters (tried NUNI → went back) | 225,784 |
| Editor-cited churn ARR loss to date | $1.32M (conservative floor) |
| ARR mitigated by Phase 1 | $60M |
| Cumulative ARR mitigated by Phase 2 | $182M |
| ARR protected via Phase 3 hybrid | $281M |

## Data sources

- `mc-business-intelligence.bi_marketing.lcm_marketing_account_base` — current state, plan, MRR, country
- `mc-business-intelligence.bi_activities.users_activities` — editor preference events (24mo)
- `mc-business-intelligence.bi_activities.email_campaign_send_activities` — send activity
- `mc-business-intelligence.bi_product.sent_email_activities` — feature adoption
- `mc-business-intelligence.bi_aggregate.mbr_monthly` — gross churn baselines
- `mc-business-intelligence.mailchimp.users_packages` + `mailchimp.orders` — historical plan + MRR-at-churn
- `mc-business-intelligence.qualtrics.survey_responses` — Exit Survey, CES Edit-an-Email, Nuni Feedback Badge
- Slack: `#hvc_feedback`, `#mc-hvc-escalations`, `#mc-reporting-analytics-feedback` (1,551 editor-related VOCs)

## Caveats

- Editor-cited churn is the **conservative explicit floor** from the structured Exit Survey signal. True editor-attributable churn is 2–5× higher (signal hidden in "Other" / "Difficult to use" / "Performance issues" primary-reason paths).
- ARR figures are MRR × 12 (annualized run-rate); they do not model winback or future expansion.
- Phase user-count and MRR estimates assume current state holds; revisit quarterly as Phase 1 default-flip shifts the population.

## File layout

- `index.html` — single-file standalone briefing. No build, no JS dependencies. Auto light/dark mode.
- `README.md` — this file.
