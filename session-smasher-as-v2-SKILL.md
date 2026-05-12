---
name: session-smasher-as-v2
description: "Compacts an entire chat into a dense markdown summary that restores ~80% of context when pasted into a new chat. Trigger on: 'summarise this chat', 'save this session', 'session smash', '/session-smasher-as-v2', 'wrap this up', 'save our progress', 'compact this chat', 'continue this later', 'create a handoff', 'context is getting long', 'running out of credits', chat is too slow or too long, or wanting to start fresh without losing context."
---

# Session Smasher AS v2

## Overview

| Task | Approach |
|------|----------|
| Summarise chat | Generate summary using rubric below, display in chat |
| Save (optional) | Offer to save to `~/claude-sessions-smash/` and as downloadable `.md` |

## Execution

### Step 1 — Write the summary

Read the full conversation and compose a markdown summary following the rubric
below. Display the complete summary in the chat as formatted markdown.

The summary is a briefing note for a sharp analyst taking over mid-flight.
Target 600–800 words.

### Step 2 — Offer to save

After displaying the summary, ask:

```
Would you like me to save this as a file? I can:
1. Save to ~/claude-sessions-smash/ on your device
2. Create a downloadable file you can grab from this chat
3. Both
```

If they say yes (or any variant), then run:

```bash
mkdir -p ~/claude-sessions-smash
SLUG="YYYY-MM-DD-topic-slug"
tee ~/claude-sessions-smash/${SLUG}.md > /mnt/user-data/outputs/${SLUG}.md << 'SMASH_EOF'
[THE SUMMARY CONTENT]
SMASH_EOF
```

Then call `present_files` with the output path.

If they decline, remind them to copy the summary from the chat.

### Step 3 — Confirm

```
✅ Session smasher complete.

To continue later:
1. Open a new Claude chat
2. Paste the summary as your first message
3. Tell Claude what you want to do next — it will have the context
```

## Rubric

Use this exact structure for the summary content written inside the bash heredoc.
Drop sections that don't apply — never leave a heading empty.

```
# Session Smasher
**Date:** [today's date, e.g. 10 May 2026]
**Session type:** [Build / Research / Writing / Planning / Debug / Creative / Mixed]
**Topic:** [one line — the primary/active topic at end of session]
**Threads:** [list if the chat covered multiple distinct topics]
  1. [Earlier topic — one line summary]
  2. [Later topic — one line summary] ← active

If the chat had only one topic, omit the Threads field entirely.

---

## Goal
[2–3 sentences. What we set out to do and why.]

## Decision Trail
[The journey, not just the destination. Numbered, 1–2 lines each.]

1. **[Decision or pivot]** — [What was chosen and why. If something was tried
   and abandoned, say what and why it failed.]
2. **[Assumption that changed]** — [What we assumed vs what we learned.]
3. ...continue for each meaningful fork.

Capture: initial vs final approach (and why the switch), tools/methods
considered and rejected, assumptions proven wrong, preferences discovered or
changed mid-session, constraints that emerged during work, tangents that led
somewhere useful vs dead ends, things the user explicitly vetoed.

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
- [API integrations: which service, where the key is stored — NOT the key]
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

> **For the next chat:** Continue the active thread (marked ← active above)
> by default. If other threads exist, briefly acknowledge them and offer to
> switch. Do not summarise the entire note back — just pick up where we
> stopped.
```

## Writing rules

- Target 600–800 words. Every sentence earns its place.
- Decision Trail: not "chose Georgia font" but "chose Georgia over Google Fonts
  because external loading risked failure on Tilda."
- Session Memory: capture preference drift — "started wanting modern, pivoted to
  vintage after seeing v1."
- Specifics over generalities. File names, numbers, hex codes, URLs.
- Drop empty sections. Never leave a heading with nothing under it.
- Never include raw secrets (passwords, API keys, tokens, government IDs) in the
  summary. Instead, note WHAT was set up, WHERE the credential is stored, and
  WHAT process was followed — so the next session knows the setup exists without
  exposing the secret itself.
- Multi-topic chats: list threads chronologically in header with `← active` on
  the live one. Write separate Goal → Decision Trail → What exists per thread,
  active thread last. Session Memory stays unified. "Where we stopped" refers to
  active thread only.
