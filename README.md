# Session Smasher

**Stop losing context when you start a new Claude chat.**

> A generic summary costs you 5–8 re-orientation messages in the new chat.
> Session Smasher cuts that to 0–2. That's roughly 3,000–5,000 tokens saved
> per new session — just from not having to re-explain yourself.

## What is this?

Session Smasher is a Claude skill that reads your entire chat and writes a
structured handoff note — the what, the why, the who, and what was rejected.
Paste it into any new chat and Claude picks up mid-flight without asking a
single clarifying question.

## Install

1. Download `session-smasher-as-v2.skill`
2. Claude.ai → Customize → Skills → Save skill → upload the file
3. Open a new chat → type `/session-smasher-as-v2`

## What makes this different

Most summaries tell the next chat *what happened*. Session Smasher tells it
*why*, *who*, *what failed*, and *exactly where to continue*.

- **Decision trails** — not just what was chosen, but what was tried, what was
  rejected, and why. The next chat won't re-explore dead ends.
- **Thread awareness** — if the chat covered multiple topics, it marks the
  active thread and tells the next chat to continue there.
- **Preference memory** — captures what you liked, what you vetoed, and what
  changed mid-session. The next chat already knows your taste.
- **Setup & credentials** — APIs configured, workflows that worked, where keys
  are stored. Never the secrets themselves — just what was set up and where.
- **Prioritised next steps** — numbered, actionable, ready to execute.

## Output

- Saves to `~/claude-sessions-smash/` on your device
- Also available as a downloadable `.md` file in chat
- 600–800 words — structured for scanning, not reading

## Version

v2 — May 2026

## License

MIT
