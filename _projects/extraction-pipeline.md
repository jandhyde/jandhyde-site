---
layout: project
title: "Extracting structured data from unstructured CRM notes"
slug: extraction-pipeline
date_added: 2026-06-20
status: shipped
tags: [revops, ai, automation]
one_line: "Programmatic extraction that turns tens of thousands of free-text CRM notes into structured, evidence-backed classifications across the renewal book."
published: false
---

**The problem.** Classifying and enriching the renewal book -- churn signals, governance-function coverage, application inventory -- was manual, account by account, and didn't scale. The data that would answer those questions was trapped in tens of thousands of unstructured CRM meeting notes across roughly 1,300 accounts, and the structured CRM fields that should have held it were empty. Two overlapping record types had resisted consolidation for a long time, so even the target schema was unsettled.

**The goal.** Replace manual triage with programmatic extraction and classification across the full book, populate the structured fields, force the long-stalled record-type consolidation, and do it at a known, low cost.

**What I did.** The decision that carried it was distrusting the model on purpose. I don't trust the model's output, I correct it. So a deterministic overlay sits on top: asset-report data and a product-name lookup set the definitive status, and where the model and the overlay disagree the pipeline flags a conflict rather than silently overwriting it, and the customer-facing team validates the flagged cases. Underneath that, one LLM API call per account produces a defined JSON schema with supporting evidence quotes, instead of batch-dumping notes into a model, so every classification is traceable to a quote and the output flows cleanly into downstream systems. And I put explicit cost controls and batch design around it so a full run over the book is a known, small figure -- tens of dollars -- plus scope discipline about what to extract and what to deliberately leave out, with the reasoning stated.

**The output.** Working Python pipelines against commercial LLM APIs that produce structured, classified data with evidence quotes across the book, feeding a governance-coverage record and a newly consolidated application-landscape record. In use.

**Wider application.** The pipeline became the forcing function for the schema consolidation that had been advocated for without progress, and another team now runs the validation step, with output split by account ownership and routed to them. That's real cross-functional reach -- a schema change plus another team's labor pulled in -- though still inside the renewal function, not productized for outside teams.
