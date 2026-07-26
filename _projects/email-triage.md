---
layout: project
title: "Email triage assistant"
slug: email-triage
date_added: 2026-06-20
status: shipped
tags: [automation, ai, revops]
one_line: "A no-code Custom GPT that turns a batch of inbound emails into one prioritized report, cutting daily triage from hours to minutes."
published: false
---

**The problem.** Sorting inbound email across a large customer book ran to two-plus hours a day. The cost was not just the time. At-risk signals sat buried under forwarded threads and went stale before I saw them, and the decision fatigue from grinding through the queue degraded my choices by mid-afternoon, right when the harder calls landed.

**The goal.** Cut triage time and stop losing time-sensitive signals -- without an IT project or engineering help, using only tools already in front of me.

**What I did.** Three decisions carried it. Every email gets exactly one of six categories, including a deliberate BOUNDARY category for scope-creep work that is not mine to own, so the framework names the "decline this" pile instead of letting it pile up. I kept the export step manual on purpose: automating the pull out of the mail client turned into an IT project, and the manual step forces a quick scan of what I am feeding in before I trust the output. And I added one mechanical auto-escalation rule -- anything from the executive team is flagged at least THIS WEEK -- so the highest-stakes senders never sink in the queue. The GPT itself was built in enterprise ChatGPT in about two hours of prompt iteration, taught the product line, the executive team, the customer segments, and the internal risk vocabulary.

**The output.** A working, in-use Custom GPT; a six-category-plus-priority framework; and a teaching deck with a talk track. The workflow is plain: drag emails out as .eml files, upload a batch, get back one prioritized report. My own triage dropped from about two hours a day to 10 to 15 minutes.

**Wider application.** In daily use by a three-person retention team. I packaged it as a portable pattern and prepared a peer talk, but the talk's posture is explicit -- not pitching, not asking for adoption -- and I deliberately do not share the prompt itself. There is no documented adoption beyond the team. The transferable part is the restraint: keep a manual checkpoint where automating it would cost more than it saves, and treat the prompt as the asset, not the giveaway.
