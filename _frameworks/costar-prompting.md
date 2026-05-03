---
layout: entry
title: "COSTAR Prompting"
source: "Sheila Teo (originally for Singapore's GovTech prompt engineering competition)"
slug: costar-prompting
date_added: 2026-05-03
tags: [decision-making]
one_line: "A six-part scaffold for writing prompts that turns vague asks into structured ones."
---

## What it's about

COSTAR is a structure for prompt-writing that asks you to specify, in order: Context, Objective, Style, Tone, Audience, and Response format. The point isn't the acronym -- the point is that most people skip three or four of those six things when they prompt, and the model fills in the gap by guessing.

## What stuck

The realization that "Context" and "Response format" are the two pieces almost everyone skips. People will write a paragraph of objective and then forget to say who the output is for or what shape it should take. The model produces something generic, the person blames the model, and the loop continues.

Once I started forcing myself through all six, I noticed that about half the time the act of writing the prompt was the actual work. By the time I'd specified audience and response format, I'd done enough of the thinking that the model's output was just final assembly.

## Where I use it

For almost any prompt that's going to drive a real deliverable -- a research output, a structured analysis, a comparison table, a draft email I'll actually send. I don't use it for casual chat or quick lookups, where the overhead isn't worth it.

The version I use most often:

- C: one or two sentences of background, including any constraints the model wouldn't otherwise know.
- O: a single verb-led objective. If I have two objectives, I split into two prompts.
- S: style only when it matters (legal-ish, plain-language, technical, and so on).
- T: tone only when the default would be wrong -- asking for blunt, or for sympathetic.
- A: audience always. This is the one I used to skip and now treat as required.
- R: response format always. Table, list, prose, structured object -- name it.
