---
layout: entry
title: "Iterative Prompt Engineering Loop"
source: "Widely circulated as the 'become my prompt engineer' meta-prompt; original author unclear"
slug: iterative-prompt-engineering-loop
date_added: 2026-05-03
tags: [decision-making]
one_line: "Have the model write your prompt for you, one question at a time, until you say stop."
---

## What it's about

Hand the model a one-paragraph instruction that asks it to (1) ask you what the prompt should be about, (2) produce a "Revised Prompt" plus a "Questions" section based on your answer, and (3) keep iterating until you say stop. Instead of writing a prompt cold, you co-write it in a loop where the model keeps surfacing the things you forgot to specify.

## What stuck

This works because the bottleneck on most prompts isn't generation -- it's elicitation. You know what you want, but not all of it, and not in a form the model can use. The loop forces the elicitation to happen explicitly, one question at a time, instead of in the back of your head while you're trying to write.

The other thing it does, which is less obvious: it slows you down. If you use this loop, you usually end up with a sharper prompt than you would have written, but you also end up with a clearer picture of the actual decision you're trying to make. Half the time the loop produces a final prompt I don't need anymore, because the questions were the work.

## Where I use it

Mostly for prompts I'm going to reuse -- system prompts for projects, recurring research prompts, anything I'd be embarrassed to ship at half-quality. I don't use it for one-off questions, where it's overkill.

I also use it as a debugging tool when a prompt keeps producing bad output. Rather than tweaking word by word, I'll start the loop fresh, paste in the failing prompt as the starting point, and let the model ask me what's actually missing.
