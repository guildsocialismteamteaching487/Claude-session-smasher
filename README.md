May 12 Updates:
> **File save is now optional** - Summary displays in chat first, save when you want.  
> **Paste prompt added** — Can't install? Use the paste prompt.md file. Same output, works everywhere.  
> **Enterprise users** — If you see a security warning, it's a false positive, so can safely ignore. Details below.

# Session Smasher

# Session Smasher

**Stop losing context when you start a new Claude chat.**

Turns long Claude sessions into a clean, structured "handoff note" so any new chat picks up exactly where you left off — with full context, decision history, active threads, preferences, setups, and approved or rejected paths already preserved.

---

> A generic summary costs you 5–8 re-orientation messages in the new chat.
> Session Smasher cuts that to 0–2. That's roughly 3,000–5,000 tokens saved
> per new session — just from not having to re-explain yourself.

---

## Install

1. Download `session-smasher-as-v2.skill`
2. Claude.ai → Customize → Skills → Save skill → upload the file
3. Open a **new** chat → type `/session-smasher-as-v2`

> **Important:** The skill is only available in chats opened *after* installation. If you get "not mounted" in an older chat, open a new one.

## What makes this different

Most summaries tell the next chat *what happened*. Session Smasher tells it *why*, *who*, *what failed*, and *exactly where to continue*.

- **Decision trails** — not just what was chosen, but what was tried, rejected, and why. The next chat won't re-explore dead ends.
- **Thread awareness** — if the chat covered multiple topics, it marks the active thread and tells the next chat to continue there.
- **Preference memory** — captures what you liked, what you vetoed, and what changed mid-session. The next chat already knows your taste.
- **Setup & credentials** — APIs configured, workflows that worked, where keys are stored. Never the secrets — just what was set up and where.
- **Prioritised next steps** — numbered, actionable, ready to execute.

## How to use

1. At the end of any chat, type `/session-smasher-as-v2`
2. The summary appears in the chat — copy it
3. Optionally save it as a downloadable file when prompted
4. Open a new chat, paste the summary, and continue

## Note 1: Can't install the skill?

If you're on an Enterprise/Team account, a restricted environment, or the skill shows "not mounted" — paste the contents of [`session-smasher-paste-prompt.md`](session-smasher-paste-prompt.md) into your chat instead. Same rubric, same output, works everywhere. No installation needed.

## Note 2: Note for Enterprise users

Some Enterprise accounts may show a prompt injection warning when the skill runs. This is a security classifier being cautious — the skill is entirely local. It reads your conversation, writes a summary, and optionally saves a file to your device. It does not call external APIs, send data anywhere, or access anything outside the current chat. If the warning persists, use the paste prompt instead — it bypasses the skill layer entirely and produces identical output.

## Output

- Summary displayed in chat — copy and paste into your next session
- Optional file save to `~/claude-sessions-smash/` and as a downloadable `.md`
- 600–800 words — structured for scanning, not reading

## Files in this repo

| File | What it is |
|------|-----------|
| `session-smasher-as-v2.skill` | The skill file — install this in Claude |
| `session-smasher-as-v2-SKILL.md` | The raw rubric — read what the skill does |
| `session-smasher-paste-prompt.md` | Paste prompt — works without installation |

## License

MIT
