---
layout: post
title: "Obfluence: A Developer's Confluence Replacement in Obsidian"
date: 2025-05-29 10:00:00 -0700
categories: [obsidian, documentation, productivity]
excerpt_separator: <!--more-->
---

What if Confluence had local-first markdown, full control, and an actual soul? Like many developers, I've wrestled with documentation platforms and eventually built my own solution using Obsidian.

<!--more-->

# 🧠 Obfluence: A Developer's Confluence Replacement in Obsidian

> “What if Confluence had local-first markdown, full control, and an actual soul?”

Like many developers, I’ve wrestled with documentation. Not the writing — the platforms.

We’ve all been there: a slow-loading Confluence page, a broken editor, the vague dread of Atlassian outages. Eventually, I hit my limit. I needed something faster, local, markdown-native — but still structured and powerful.

That’s how *Obfluence* started.

---

## 🛠️ The Goal

I didn’t want another wiki — I wanted something modular, offline, version-controlled, and developer-centric.

So I mapped out what makes Confluence useful, and what makes it painful. The folder structure was good. The page types were clear. But the performance, UX, and editing? Not so much.

---

## 🧩 The Build

I began by mirroring a logical structure:

- `00_Product` — specs, backlog, roadmap
- `01_Architecture` — diagrams, decisions
- `02_Release Notes` — changelogs
- `03_Operations` — CI/CD, infra, monitoring
- `04_Working Session Minutes`
- `05_Meeting Notes`
- `06_Scrum Foundations`
- `07_Knowledge Base`
- `08_Open Business Question Log`

Each folder uses a dynamic `_index.md` to render contents.

---

## 🔌 Essential Plugins

### ✅ Templater
- Automates note creation
- Smart prompts and reusable scaffolds

### 📊 Dataview
- Generates dynamic dashboards and indexes

### 🧩 MetaEdit
- Inline frontmatter control (status, owner, tags)

### ➕ Bonus
- QuickAdd, Advanced Tables, Buttons, Folder Notes

More details in: `Obfluence_Suggested_Plugins.md`

---

## 💡 Lessons Learned

- Metadata consistency makes everything easier
- Recursion with Dataview can be powerful — and tricky
- A consistent template style saves hours
- Structure improves memory and reuse

---

## 💬 Q&A

**Q: Can teams use this?**  
Yes — with Obsidian Sync or Git. It’s team-friendly, local-first, and Git-friendly.

**Q: What makes Obfluence different?**  
It mimics Confluence’s power using only markdown, folders, and smart plugins — with no lock-in or cloud reliance.

**Q: Can I use this for meeting notes or guides?**  
Yes. Templates support everything from retros to runbooks to system diagrams.

---

## 🧠 Technical Appendix

- **Dynamic Indexes**: Auto-rendered `_index.md` files
- **Templates**: Over 30 templater-powered files
- **Dashboards**: Custom views of metadata across your system
- **Frontmatter**: 
  ```yaml
  tags: [template]
  status: draft
  system: architecture
  owner: "@you"
  ```

---

## 🔗 Try Obfluence

- GitHub: `https://github.com/yourusername/obfluence`
- License: MIT
- Included: README, Dashboard, Suggested Plugins, and more
