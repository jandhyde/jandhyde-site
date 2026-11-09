---
layout: project
title: "Agentforce (AI-201) study system"
slug: agentforce
date_added: 2026-07-26
status: shipped
tags: [learning-systems, enablement, ai]
one_line: "Turning a scattered Salesforce certification curriculum into a book, a flashcard deck, and a full-length practice exam."
---

**The problem.** The learning material for a Salesforce certification is buried across dozens of Trailhead pages you have to navigate to and read one at a time, and a fair amount of what's on them isn't tested. The official study estimate for this exam is around 40 hours. Most of that isn't learning -- it's clicking through pages and reading around the parts that matter.

**The goal.** Get the relevant material into one place, strip it down to the terminology and practices the exam actually tests, and turn that into active-recall material -- flashcards and practice tests -- rather than pages to re-read.

**What I did.** Handed Claude Cowork the cert prep landing page with instructions to crawl every sublink and write each page out as markdown. The first pass only went one level deep and missed dozens of Trailhead pages, so the crawl instructions had to be rewritten to be explicit about depth -- worth noting because "crawl this site" reads as unambiguous right up until you check the output. With the pages captured, I had Cowork cut anything not strictly relevant to the certification, then group the remaining files by the exam's study topics. The grouped markdown was converted to EPUB, which is the change that mattered most: the curriculum stopped being a website I had to sit in front of and became a book I could read anywhere.

**The output.** The EPUB loads into the Kindle app, so studying happens wherever I am and progress tracks itself. For earlier certs I had pasted every Trailhead link into a Notion project as a checkbox and ticked them off as I went; that scaffolding is gone. From the same markdown I generated an Anki deck, and I loaded the markdown into NotebookLM for a second set of flashcards and short quizzes. NotebookLM's quizzes run short, so I had Cowork build a practice test center that serves 60, 120, or 180 questions at a time to match real exam length.

One thing worth recording: NotebookLM wrote better questions out of the gate than the general-purpose model did. Getting Opus to produce questions at realistic exam difficulty took a lot of iterating -- it defaulted to questions that were too easy and too literal. Fable, which I was trying for the first time, got there on its first attempt. The purpose-built tool won until the model caught up.

**Wider application.** The same pattern -- build the context as markdown first, then generate testing material from it -- was used at work to stand up a testing center for the customer success team. CSMs open the internal site, pick a topic, test themselves, and their progress is tracked over time.
