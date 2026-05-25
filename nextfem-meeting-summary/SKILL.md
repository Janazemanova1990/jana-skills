---
name: nextfem-meeting-summary
description: "Create beautiful HTML email newsletters summarizing meetings for Nextfem AI community. Use when the user wants to create a meeting summary, meeting notes newsletter, recap email, or meeting recap with Nextfem AI branding. Generates styled HTML with the Nextfem AI visual identity including brand colors (purple #ada2cc, turquoise #9fd7d5, coral #f89083) and DM Sans typography."
---

# Nextfem AI Meeting Summary Newsletter

Generate beautifully designed HTML email newsletters that summarize meetings with Nextfem AI branding.

## Brand Guidelines

### Colors
- **Purple**: #ada2cc (primary accent)
- **Turquoise**: #9fd7d5 (secondary accent)
- **Coral**: #f89083 (highlight/CTA)
- **Text**: #2d2d2d (dark gray)
- **Background**: #ffffff (white)
- **Light background**: #f8f7fc (subtle purple tint)

### Typography
- **Font**: DM Sans (import from Google Fonts)
- **Headings**: DM Sans Bold, 40px for main title
- **Body**: DM Sans Regular, 16px
- **Section headers**: DM Sans Bold, 24px

### Logo
Use the official Nextfem AI favicon as the logo:
- URL: `https://nextfemai.com/nextfem-favicon-transparent.png`
- Display as `<img>` tag, centered, width 80px
- Do NOT generate SVG circles — always use this image URL

## Required Sections

Extract and organize meeting content into these 7 sections:

1. **What We Accomplished** - Key activities, completions, and progress made
2. **Tools We Used** - Software, platforms, AI tools mentioned or demonstrated
3. **Use Cases Explored** - Practical applications and scenarios discussed
4. **Decisions Made** - Agreements, conclusions, and commitments reached
5. **Action Items** - Tasks with owners and deadlines (use checkbox styling)
6. **Challenges & Solutions** - Problems encountered and how they were addressed
7. **Next Meeting** - Date, time, and preview of upcoming topics

## HTML Generation Instructions

1. Parse the meeting notes/transcript provided by the user
2. Extract relevant information for each of the 7 sections
3. Summarize concisely - newsletters should be scannable
4. Use the template from `assets/template.html` as the base structure
5. Fill in the sections with extracted content
6. Save output to `/mnt/user-data/outputs/meeting-summary-[DATE].html`

## Styling Requirements

- All CSS must be inline for email compatibility
- Max-width: 600px container for email clients
- Use the `<img>` logo from the template (favicon.png from nextfemai.com)
- Section headers use coral (#f89083) left border accent
- Action items display as styled checklist
- Alternating light purple (#f8f7fc) backgrounds for visual rhythm
- Footer includes "Powered by NextFem AI" with logo
