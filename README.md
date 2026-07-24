# Vendor Risk Scoring Tool

A weighted, multi-category scoring engine for third-party / vendor risk
assessment — built to make a 0–100 risk score fully explainable, not a
black box.

[**Live demo →**](https://bertrandnkali.github.io/vendor-risk-scoring-tool/)

> ⚠️ \*\*This is a portfolio / methodology demo.\*\* All vendors, assessment
> histories, and industry benchmark figures in the tool are synthetic
> and illustrative — not real companies or real industry statistics.
> It isn't connected to any live security-ratings feed and isn't a
> certified risk-rating product.

## What it does

Score a vendor (or a whole portfolio at once) across six weighted
categories and get back a 0–100 score, a risk tier, and a specific
recommendation — with every category's contribution visible, not just
the final number.

|Category|Weight|What it measures|
|-|-|-|
|Security Posture Trend|25|Recency-weighted average of past assessment scores (2/4/8/all-period blend, weighted 40/30/20/10)|
|Assessment Consistency|20|Variance across assessment history — a vendor that swings between great and bad is riskier than one that's steadily mediocre|
|Criticality \& Data Exposure|15|Data classification handled, business dependency, single-point-of-failure risk|
|Industry Benchmark|15|Vendor's own score vs. a sector peer baseline|
|Contractual Terms|15|Cyber insurance, right-to-audit clause, liability cap adequacy, breach notification SLA|
|Certification \& Disclosure|10|SOC 2 / ISO 27001 status, open critical findings, breach history|

**Kill condition:** an unremediated critical/high finding, a breach
disclosed in the last 12 months, or missing certification while
handling Confidential/Restricted data caps the total score at 40,
regardless of how strong every other category looks. One serious flag
can't be quietly averaged away by good numbers elsewhere.

## Two ways to use it

* **Score a Vendor** — full single-vendor assessment with the complete
category breakdown, supporting metrics, and a save-to-register option.
* **Batch Scan** — paste a CSV of multiple vendors, get a ranked table
back with a click-to-expand detail card for each one, so you're not
trading the audit trail away for speed.

Six synthetic example vendors are pre-loaded so you can try it
immediately with no setup.

## How to run it

No build step, no dependencies. Either:

* Open `index.html` directly in any browser, or
* Use the [live demo link](https://bertrandnkali.github.io/vendor-risk-scoring-tool/) above.

Saved assessments in the Vendor Register persist via `localStorage` in
your own browser — nothing is sent anywhere.

## Built with

Vanilla HTML/CSS/JS — no frameworks, no build tooling. Built iterating
with [Claude](https://claude.ai) (Anthropic's AI assistant): describing
the desired scoring logic, reviewing generated code, and manually
verifying the math (weighted averages, variance calculations, kill-
condition logic) against hand-computed reference values before trusting
any of it.

## License

MIT License

