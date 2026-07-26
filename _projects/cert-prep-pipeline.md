---
layout: project
title: "Certification study pipeline"
slug: cert-prep-pipeline
date_added: 2026-06-20
status: shipped
tags: [learning-systems, enablement, automation]
one_line: "A repeatable process that turns a sheet of source links into a weighted study track of notes, flashcards, and a practice exam."
published: false
---

**The problem.** Prepping for a cert means turning scattered source pages into something you can actually study, and doing it again for the next cert. The hard parts repeat every time: the official material is spread across modules and help docs, the listed pages are often just shells that link elsewhere, and the published exam weights matter more than reading order. Doing this by hand burns effort on low-stakes domains and gets details wrong in ways that cost rework later.

**The goal.** One replayable process that takes a spreadsheet of source links and produces a finished, weight-prioritized study track -- cleaned notes, per-domain files, a flashcard deck, and a practice exam -- with the judgment calls surfaced at fixed points instead of buried.

**What I did.** Three decisions carried it. The spreadsheet is the interface: everything keys off domain and exam weight, and if weights are missing the process stops and asks rather than guessing. Expensive mistakes got front-loaded into checkpoint gates, because on the first run a weight discrepancy surfaced only after 150-plus flashcards were already made -- pure rework. And I codified "container vs leaf," since a module or trail URL just lists links while the unit pages under it hold the content; the pipeline expands every container down to its leaf pages before fetching, so coverage is traceable. A hard copyright line runs throughout: summarize, never reproduce, but keep functional references verbatim because product names, menu paths, and permission names are load-bearing.

**The output.** An 8-step playbook with the gates; a throttled, idempotent page-cacher; an HTML-to-markdown extractor; a splitter that breaks consolidated files into per-domain pieces; a small quiz engine; and an input spreadsheet template. Every track it produces ships with its own instructions file. It has run end-to-end across several certifications, including Salesforce and a HubSpot transcript variant. No one else uses it.

**Wider application.** None beyond my own prep yet. Each rule in the playbook traces to a specific failure it once caused -- the expand-to-leaf rule came out of a rebuild where the source material was stale and domains had been renamed. That is the method I would reuse for any onboarding or enablement track where the inputs are messy and drilling people on wrong information is costly.
