# Mailchimp Email Editor — Product Usage Assessment

Diagnostic report on how customers use Mailchimp's two email editors:
- **New** (drag-drop, multichannel) — `content_type='multichannel'`
- **Classic** (template-based) — `content_type='template'`

**Live dashboard:** https://deepakp1308.github.io/mailchimp-email-editor-analysis/

## Scope

Trailing 90 days of campaign-object data from `mc-business-intelligence.bi_reporting.emails_bulk` (~25M campaigns, 1.45M creator accounts).

Per the briefing, New and Classic are reported separately — funnel and microstep metrics are **not** pooled.

## What's in the report

1. Headline scorecard (3 stats + 3 finding cards)
2. Data validation (brief §4 prerequisite)
3. Population sizing (lifecycle cohorts × editor)
4. Send-tier funnel A2 (Tier 0 → Tier 3 per editor)
5. Where drafts get stuck — wizard-step distribution (A4 proxy)
6. Draft-state cohort A6 (considered-rejection / in-progress / stalled / cold)
7. Time-to-send distribution A8 (P50/P75/P90/P95 per editor)
8. Back-and-forth signals (test sends per published campaign)
9. Template-library health A14 (the Classic alter-template anomaly)
10. Lifecycle × editor delta A7 (the migration win)
11. Errors and compliance blocks A5 (partial)
12. AI assist usage A12 (directional only)
13. New vs Classic delta summary
14. Decision-lens recommendations (L1–L4)
15. Answers to all 27 priority questions from brief §11
16. Instrumentation gap report (brief §10.8)
17. Closing narrative
18. SQL appendix

## Data gaps acknowledged

The briefing requires editor event-log analysis (microstep funnel, path mining, friction-score, undo / autosave / render telemetry, support-ticket joins). Those sources were not accessible:

- `rsg-events-pipeline-prod.ingest_v2.events` — 403 access denied
- Client telemetry stream — no table located
- Support tickets tagged "editor" — not located
- Block counters in `emails_bulk` are not populated for the New editor (real instrumentation bug)

Per the brief: "If data gaps prevent any of these, stop and produce the instrumentation gap report instead of guessing." That report is §15.

## File layout

- `index.html` — single-file standalone dashboard. No build, no JS dependencies. Renders with system fonts. Auto-adapts to dark mode.
