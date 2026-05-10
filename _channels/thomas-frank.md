---
layout: entry
title: "Thomas Frank"
slug: thomas-frank
date_added: 2026-05-03
tags: [knowledge-management, productivity]
one_line: "Long-form Notion walkthroughs -- the closest thing to a reference implementation of PARA in Notion I've found."
# TODO: confirm channel URL and add as `link:` field
---

## What it's about

Thomas Frank's channel is a working library of how to build knowledge-management systems in Notion -- relational databases, linked views, templates, rollups, the small mechanics that don't show up in product marketing.

## What stuck

His full second-brain build ([video](https://youtu.be/Y__243RqBeM)) is the architecture I used as the starting point for my own Notion. The specific moves worth calling out:

- The four core databases (Tasks, Notes, Projects, Areas/Resources) live on a separate backend page. Front-end dashboards pull from them via Linked Views, so the raw databases never get edited directly.
- Areas and Resources share a single database, differentiated by a Type property, with a self-relation so a Resource can roll up under a parent Area.
- Inboxes are filtered views showing only items that haven't been categorized yet. Once a Project or Area/Resource is assigned, the item disappears from the inbox.
- An Archive checkbox on every database hides old items from active views without deleting them.

The unified Areas/Resources database is elegant in Notion terms but blurs a distinction PARA treats as load-bearing -- worth knowing going in if you're thinking about adopting the pattern wholesale.

## Where I use it

The four-database backend is what I built my own setup on. A year in, running it against PARA's strict definitions surfaced enough schema drift to warrant a rebuild. The architecture is solid; the discipline of keeping it aligned with PARA doesn't happen on its own.

The longer story of that audit is in [Building a Second Brain, applied](/notes/building-a-second-brain-applied/).
