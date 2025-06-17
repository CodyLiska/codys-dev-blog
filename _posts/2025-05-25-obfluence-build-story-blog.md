---
layout: post
title: "From Frustration to Flow From Frustration to Flow: How I Replaced Confluence with Obsidian"
date: 2025-05-25 20:22:00 -0700
categories: [confluence, organization, project-management]
excerpt_separator: <!--more-->
---

> “I just wanted documentation that respected my time — and my keyboard.”

---

## It Started with Friction

I didn’t set out to build a Confluence replacement. I just wanted to document a few projects. But every time I opened Confluence, I found myself… waiting.

Waiting for the page to load.  
Waiting for the editor to catch up.  
Waiting for Atlassian to stop charging me for something that barely worked offline.

Eventually, I stopped writing.

And that’s when it clicked — the _tool_ was getting in the way of the _thinking_.

So I went looking for something better.

---

## I Already Had Obsidian. I Just Needed to Build _Around_ It.

Obsidian is great. It’s fast, flexible, and markdown-native. But it’s also a blank canvas. I knew I’d have to design something from the ground up that worked like a documentation system — something structured, scalable, and team-friendly.

My goal wasn’t to replicate Confluence. It was to **reimagine it for developers**.

---

## Step One: Folder Architecture

I started with the bones — the structure.

I mirrored the kinds of pages I usually saw (and liked) in Confluence:

```
00_Product/
01_Architecture/
02_Release Notes/
03_Operations/
04_Working Session Minutes/
05_Meeting Notes/
06_Scrum Foundations/
07_Knowledge Base/
08_Open Business Question Log/
```

Each folder would contain multiple documents. But more importantly, each would have an `_index.md` file that could dynamically show its contents.

---

## Step Two: The Plugins That Made It Possible

Obsidian is powerful on its own, but the magic comes from plugins. Here’s what unlocked the real power:

### Templater Templater

Let me create pre-filled templates that auto-prompt for things like:

- Owner
- System
- Tags
- Description

Templates weren’t just static scaffolds — they were interactive.

### Dataview Dataview

This plugin completely changed how I thought about Obsidian. It turned folders into dashboards.

With a bit of JavaScript, I could:

- Render tables of documents
- Group by status, owner, or tags
- Show last modified dates
- Even recursively walk subfolders

### MetaEdit + QuickAdd MetaEdit + QuickAdd

Together, they gave me real metadata control. I could toggle a note’s status from `Draft` to `Final` with a hotkey, or create new notes from dropdowns.

---

## What Didn’t Work

There were plenty of false starts.

- I accidentally built an index that looped infinitely
- I had to rewrite every template to standardize frontmatter keys
- `tp.user.input` kept failing until I toggled "User Scripts"
- Unicode smart quotes crashed my PDF export multiple times

But I learned fast — mostly because I _had to_.

---

## What I Was Really Trying to Build

Looking back, it wasn’t just a better documentation system.

I was building a **thinking system** — one where writing was fast, organizing was automatic, and reading was frictionless.

I wanted something that:

- Lives in Git
- Works offline
- Feels like code
- Looks clean
- Scales with projects

And I think I got there.

---

## The Final Output

I named it **Obfluence** — a blend of _Obsidian_ and _Confluence_.

It includes:

- Modular folder structure Modular folder structure
- From Frustration to Flow Over 30 smart templates
- Dynamic dashboards Dynamic dashboards
- Auto-updating indexes Auto-updating indexes
- MIT licensed and ready to share MIT licensed and ready to share

Everything lives in Obsidian. No more waiting. No more clunky UIs. Just local markdown that _works_.

---

## What I Learned

- Metadata is your best friend
- Consistency makes automation possible
- Good UX isn’t about design — it’s about friction
- The tools we use should disappear when we’re thinking

---

## What’s Next

I’m making this public for others to use. If you’re tired of bloated tools, or just want a documentation system that respects your time, give _Obfluence_ a try.

It won’t do everything for you. But it will get out of your way.

And sometimes, that’s all you need.

---

## GitHub

> Coming soon: `github.com/yourusername/obfluence`

MIT licensed. No lock-in. Just markdown, your brain, and a system that makes sense.
