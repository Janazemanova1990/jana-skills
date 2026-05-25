# project-update-email

Turn an MS Teams meeting transcript into a structured project update email — in your own voice, with named owners on every next step, ready to send.

## What it does

Reads a meeting transcript (typically MS Teams export with speakers + timestamps) and produces a stakeholder-ready email:

- **British English** throughout
- Sections grouped by agenda topic with bold headings
- Bullet points: one idea per bullet, factual, action-oriented
- Named accountability ("Person A is waiting for...", "Person B to finalise...")
- **❗ BLOCKER** and **⚠️ Risk** as standalone visually-prominent sections
- A **Next steps** section at the end with named owners on every action
- Ignores small talk, mute issues, off-topic chat

## Why it exists

Most weeks I have multiple project meetings — each one needs a follow-up email summarising what was discussed and what happens next. Writing those by hand took 30–45 minutes per meeting.

This skill brings it down to a minute. Paste transcript, get email, adjust 2-3 lines, send.

Used in real client work — the example in `SKILL.md` shows the actual output structure (with placeholder names instead of client names for obvious reasons).

## How it works

1. Drop this folder into your Claude skills directory
2. Paste an MS Teams meeting transcript
3. Say "Write my update from this transcript" (or similar)
4. Claude returns a structured email following the rules in [`SKILL.md`](./SKILL.md)

## What you can customise

- **Voice/style** — the SKILL.md has explicit style rules (British English, no em dashes, opener style, sign-off). Adjust to your voice.
- **Sections** — the prompt lists required sections but says "include only what is relevant". Add your own.
- **Owners** — names are extracted from the transcript itself, so no configuration needed.

## Notes

- Works best with full MS Teams transcripts including speaker names and timestamps
- For kick-off meetings the format shifts to numbered sections (scope, out of scope, expected outcomes) — you'll want to add a separate template if you need that often
- Next obvious step: connect this via n8n to auto-trigger on new transcript uploads to a Drive folder (on my list)
