---
layout: project
title: "Retention operations playbooks"
slug: retention-playbooks
date_added: 2026-06-20
status: shipped
tags: [enablement, process, revops]
one_line: "Turned a person-dependent retention function into a documented standard the team executes against."
published: false
---

**The problem.** Retention ran on people, not process. The procedures lived in my head and partly in two colleagues', so I had to sit in every meaningful conversation. A small team covering well over a thousand accounts had no shared, authoritative reference, and a new hire had nowhere to ramp from.

**The goal.** Convert retention from person-dependent to structural -- a documented standard the team executes against, not tribal knowledge. The aim was to get a new hire productive fast, something like 70% functional in two weeks. That was the intent, not a measured result.

**What I did.** I separated playbooks from runbooks: judgment-heavy decision trees and escalation logic on one side, procedural step-by-step instructions on the other. I codified the segment rules -- renewal kickoff timing, at-risk rescue by risk type, the perpetual-to-subscription conversation, escalation routing by issue type and ARR threshold, a pricing authority matrix, notice periods by customer type. Markdown was the master; docx and PDF were generated downstream, so one source produced three formats. I added a changelog that requires a "why" for every edit and walled off a separate area for sensitive content so it could not leak with the shareable docs. When a second version was not good enough, I reverted it and rebuilt from fresh source rather than iterate on bad content.

**The output.** A six-playbook suite in active use -- a start-here orientation plus renewals, risk and retention, conversions, pricing, and operations -- in three formats, with a changelog tracking drift.

**Wider application.** Here is the honest part: authoring was the easy bit. Maintenance lapsed within a month. Corrections to the first version sat for weeks, which exposed upkeep as the real weak point. The fix was process -- a changelog plus a review cadence -- not more writing. The suite is used within the team and gives a manager a defined process to coach against. No outside adoption.
