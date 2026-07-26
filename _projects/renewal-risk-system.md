---
layout: project
title: "Renewal risk early-warning system"
slug: renewal-risk-system
date_added: 2026-06-20
status: shipped
tags: [revops, forecasting, data-modeling]
one_line: "Turned free-text renewal notes into a structured registry and a deterministic, auditable loss forecast that powers a weekly executive risk review."
published: false
---

**The problem.** Renewal risk lived in free-text CRM notes. You can't sort, count, or model on free text, and a book of well over a thousand renewals can't be triaged by reading every note each cycle. Churn got caught reactively, close to the renewal date, too late to act. And "we have several million at risk" is not decision-useful -- leadership needs the likely year-end loss and whether the team is on track to its retention target, not gross exposure.

**The goal.** See churn risk early and consistently across the whole book, and convert the at-risk pile into a probability-weighted loss forecast that answers one question: are we going to hit the gross-retention target, and if not, what save rate gets us there?

**What I did.** First, I added structure to the notes without forcing people into a rigid form: two orthogonal bracket-tag dimensions placed at the start of the field so they survive the CRM's text truncation -- a risk-reason tag for why an account is at risk, and a mitigation-status tag for what we're doing about it. Separating "why at risk" from "what we're doing" is what makes both categorization and the save model possible, with simple precedence and fallback rules for messy reality: first tag wins when two are present, and an untagged field defaults to monitoring and gets flagged as a data-quality issue. Second, I built the forecast deterministically, not with an LLM, specifically so the output is explainable and auditable to executives: a save probability assigned by mitigation tag (negotiation highest, down to expected-loss at zero), probable loss as ARR times one minus the save rate, summed across the book. Third, I framed it against an explicit loss budget -- the gross-retention target, in the mid-90s, implies a maximum allowable loss -- and back-solved for the save rate required to land on target. I ran sensitivity on the weakest assumption, the largest and least-certain monitoring bucket, and carved one large account out as an explicit assumed-save so that assumption is visible, not buried. The reporting weights at-risk ARR as churn-risk-percent times invoiced amount rather than counting raw dollars, with a firm rule against fabricated usage analytics or ROI models. Omit over fake.

**The output.** A tagged working registry of about 190 rows across roughly 160 accounts; a deterministic risk model producing an average 231-day lead time on churn-risk identification; a probability-weighted loss bridge with a required-save-rate figure; and a set of live, auto-refreshing dashboards. It powers a standing weekly executive risk review rather than a one-off report -- operational, not decorative. Still in use.

**Wider application.** The weekly review is attended by the executive team, so this is genuine leadership-level use, but only inside the company. The tagging standard itself is mostly authored and maintained by me, lightly used by a couple of others and imperfectly followed -- roughly a fifth of rows are missing a tag, and some off-spec tags show up in the wild. So it's a real standard with drift, not team-wide adoption. The transferable idea is the deterministic, explainable forecast framed against a loss budget.
