Summarise this entire conversation as a structured session handoff note. Write it as a briefing for a sharp analyst taking over mid-flight — they need the what, the why, the who, and the what-was-rejected. Follow this exact format:

# Session Smasher
**Date:** [today's date]
**Session type:** [Build / Research / Writing / Planning / Debug / Creative / Mixed]
**Topic:** [one line — the primary/active topic at end of session]
**Threads:** [if multiple topics were discussed, list them numbered with ← active on the one that was live at the end. If single topic, omit this field.]
  1. [Earlier topic — one line]
  2. [Later topic — one line] ← active

---

## Goal
[2–3 sentences. What we set out to do and why.]

## Decision Trail
[The journey, not just the destination. Numbered, 1–2 lines each.]

1. **[Decision or pivot]** — [What was chosen and why. If something was tried and abandoned, say what and why it failed.]
2. **[Assumption that changed]** — [What we assumed vs what we learned.]
3. ...continue for each meaningful fork.

Capture: initial vs final approach (and why the switch), tools/methods considered and rejected, assumptions proven wrong, preferences discovered or changed mid-session, constraints that emerged during work, tangents that led somewhere useful vs dead ends, things the user explicitly vetoed.

## What exists now
[Bullet list. Each bullet = one output + its status.]
- [File/document/code/design — exact name, path, format] — [done / partial / broken]
- [If nothing was "built", list conclusions or decisions reached]

## Session Memory
[Everything identifiable about the user that surfaced. Drop empty sub-groups.]

**About the user**
- [Name, role, company, location, background — only what was mentioned]
- [People referenced: colleagues, clients, relationships]

**Preferences & opinions**
- [Communication style, design taste, technical choices]
- [What they liked, what they rejected, what they were emphatic about]
- [If a preference changed: "Started wanting X → switched to Y because Z"]

**Specifics**
- [Tools, platforms, APIs, services, versions, configs]
- [URLs, file paths, repo names, domain names, hex codes, dimensions]
- [Budgets, deadlines, targets, exact wording they approved]

**Setup & credentials** (capture what was set up, not the secrets themselves)
- [API integrations: which service, where the key is stored — NOT the key itself]
- [OAuth/auth flows: provider, scopes, token file location]
- [Webhook URLs, callback URLs, endpoint URLs configured]
- [Environment variables: which ones, in which file]
- [Connectors/MCP servers connected and setup steps that worked]
- [The exact workflow that finally worked after trial and error]

## Where we stopped
[1–2 sentences. The exact last thing discussed or action taken.]

## Next steps
1. [Most important thing to do next]
2. [Second priority]
3. [Third if applicable]

---

> **For the next chat:** Continue the active thread (marked ← active above) by default. If other threads exist, briefly acknowledge them and offer to switch. Do not summarise the entire note back — just pick up where we stopped.

---

Rules:
- Target 600–800 words. Every sentence earns its place.
- Decision Trail: not "chose Georgia font" but "chose Georgia over Google Fonts because external loading risked failure on Tilda."
- Session Memory: capture preference drift — "started wanting modern, pivoted to vintage after seeing v1."
- Specifics over generalities. File names, numbers, hex codes, URLs.
- Drop empty sections. Never leave a heading with nothing under it.
- Never include raw secrets (passwords, API keys, tokens). Note WHAT was set up, WHERE the credential is stored, and WHAT process was followed.
- Multi-topic chats: list threads chronologically with ← active on the live one. Write separate Goal → Decision Trail → What exists per thread, active thread last. Session Memory stays unified. "Where we stopped" refers to active thread only.
- After displaying the summary, offer to save it as a downloadable file if the environment supports it.
