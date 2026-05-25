# nextfem-meeting-summary

Generate beautifully designed HTML email newsletters that summarise NextFem AI community meetings — fully branded, email-client-compatible, ready to send.

## What it does

Takes meeting notes or a transcript, returns a complete HTML email with:
- NextFem AI branding (colours, DM Sans typography, logo)
- 7 structured sections (Accomplished, Tools, Use Cases, Decisions, Action Items, Challenges, Next Meeting)
- Inline CSS for maximum email client compatibility
- 600px max-width container
- Coral-accented section headers with alternating light backgrounds

## Why it exists

[NextFem AI](https://nextfemai.com) is a community I founded for women working with AI. After each meeting I was hand-styling recap emails. After the third one I codified the whole thing into this skill.

Now: meeting notes → one prompt → finished newsletter at `/mnt/user-data/outputs/meeting-summary-[DATE].html`.

## Brand guidelines (built in)

- **Purple** `#ada2cc` — primary accent
- **Turquoise** `#9fd7d5` — secondary accent
- **Coral** `#f89083` — section highlights / CTAs
- **Font:** DM Sans (Google Fonts)
- **Logo:** [`nextfemai.com/favicon.png`](https://nextfemai.com/favicon.png) — 80px, centered

## Files

- [`SKILL.md`](./SKILL.md) — the skill definition (frontmatter + instructions)
- [`assets/template.html`](./assets/template.html) — the HTML email template with placeholders

## How to use

1. Drop this folder into your Claude skills directory
2. Provide Claude with meeting notes and ask for a NextFem meeting summary
3. Claude returns a complete branded HTML newsletter

## Notes

- The HTML uses table-based layout (not flexbox/grid) — that's intentional for email client compatibility (looking at you, Outlook)
- All CSS is inlined for the same reason
- The favicon URL is hardcoded to `nextfemai.com/favicon.png` — swap it if you fork for your own community
