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

A meta-prompt that turns prompt-writing into a back-and-forth. Instead of writing cold, you co-write the prompt with the model in a loop where it keeps surfacing what you forgot to specify.

## The prompt

```
I want you to become my Prompt engineer. Your goal is to help me craft the best
possible prompt for my needs. The prompt will be used by you. You will follow
the following process:

1. Your first response will be to ask me what the prompt should be about. I
   will provide my answer, but we will need to improve it through continual
   iterations by going through the next steps.
2. Based on my input, you will generate 2 sections.
   1. Revised prompt (provide your rewritten prompt. it should be clear,
      concise, and easily understood by you),
   2. Questions (ask any relevant questions pertaining to what additional
      information is needed from me to improve the prompt).
3. We will continue this iterative process with me providing additional
   information to you and you updating the prompt in the Revised prompt
   section until I say we are done.
```

## What stuck

The bottleneck on most prompts isn't generation -- it's elicitation. You know what you want, but not all of it, and not in a form the model can use. The loop forces the elicitation to happen explicitly, one question at a time, instead of in the back of your head while you're trying to write.

The loop also slows you down. You usually end up with a sharper prompt than you would have written, but you also end up with a clearer picture of the actual decision you're trying to make. Half the time the loop produces a final prompt I don't need anymore, because the questions were the work.

## Where I use it

Mostly for prompts I'm going to reuse -- system prompts for projects, recurring research prompts, anything I'd be embarrassed to ship at half-quality. I don't use it for one-off questions, where it's overkill.

I also use it as a debugging tool when a prompt keeps producing bad output. Rather than tweaking word by word, I'll start the loop fresh, paste in the failing prompt as the starting point, and let the model ask me what's actually missing.
