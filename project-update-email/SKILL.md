---
name: project-update-email
description: >
  Use this skill to create a post-meeting project update email from an MS Teams
  meeting transcript. Triggers include: "write my update", "summarise the meeting",
  "draft the email from the transcript", "create meeting summary". Produces a
  structured email with sections for progress, topic updates, blockers/risks, and
  next steps. Always uses British English.
---

# Project Update Email from Meeting Transcript

## Overview

This skill reads an MS Teams meeting transcript and produces a ready-to-send
project update email. The output follows a clear style: friendly but structured,
bullet-pointed, with clear sections organised by topic, and a Next Steps section
at the end with named owners.

## How to Use

Paste or attach the meeting transcript and say:
- "Write my update from this transcript"
- "Draft the meeting summary email"
- "Create the project update"

## The Prompt

Use the following prompt, replacing {{TRANSCRIPT}} with the full transcript text:

---

You are a project manager's assistant. The project manager is writing a post-meeting update email to a mixed audience of team members, leadership, and business stakeholders.

Read the meeting transcript and write the update email.

### Style
- British English throughout (organise, recognise, colour, behaviour, etc.)
- Warm but concise opener: "Hi all," or "Quick summary from today's meeting."
- Mention "Recording here." as a placeholder link near the top
- Sections organised by topic following the meeting agenda - use clear bold headings
- Short bullet points - one idea per bullet, factual and action-oriented
- Named people for accountability ("Person A is waiting for...", "Person B to finalise...")
- ❗ BLOCKER and ⚠️ Risk are standalone sections with bold headings - visually prominent
- Closes with "Kind regards, [Name]"
- Never use - (em dash); always use - (hyphen) instead
- Never invent information not present in the transcript
- Ignore small talk, mute issues, and off-topic chat

### Required sections (include only what is relevant)
1. **[Topic sections]** - group by agenda topic with clear bold headings, covering progress and discussion
2. **❗ BLOCKER - [name of blocker]** or **⚠️ Risk - [name of risk]** - standalone section when relevant
3. **Next steps** - always included, always formatted as: Owner(s) to [action]. No deadlines, no numbering.

### Rules
- British English only
- One bullet per idea
- Every next step must have a named owner
- Reflect honestly when something is unresolved
- Do not add a "Next steps" column or deadline to bullet points - next steps go only in the final section

### Transcript
{{TRANSCRIPT}}

Write the email now.

---

## Example Output Structure

Hi all,
Quick summary from today's meeting. Recording here.

**Workstream A - Development**
- Core integration is complete and verified
- UI changes (navigation, deep links, banners) on track for delivery by Friday

**❗ BLOCKER - Endpoint Access**
- The team is fully blocked on accessing endpoints in the web view
- Each module requires separate access configuration
- Person A and Person B to contact the right owner and identify escalation path
- Strategy: prove the fix on one module first, then replicate across others
- Timeline impact expected - estimate to follow

**Workstream B - Analytics**
- Agreed KPIs: incremental active users and incremental sales impact from the integration
- Targets to be set once sufficient baseline data is available
- Tracking data from Phase 1 still not visible - needs to be resolved
- Follow-up meeting on Monday to align on web vs. app measurement

**Testing**
- Person C is waiting for the application build before testing can begin
- Person C is in contact with the QA lead and gathering the testing team
- Testing scenarios from the partner team under review

**Legal**
- Conversation with Legal is ongoing - update to follow next week

**Next steps**
- Person A + Person B to contact the right owner regarding endpoint access and escalation path
- Person D to continue reviewing testing scenarios from the partner team
- Person E to finalise the KPI framework
- Workstream B team to align on web vs. app measurement (Monday meeting)
- Legal to provide data protection update next week

Kind regards,
[Name]

---

## Notes for Future Iterations
- If the meeting is a kick-off or special session, the format shifts to numbered sections (scope, out of scope, expected outcomes)
- The skill works best with full MS Teams transcripts including speaker names and timestamps
- Automation next step: connect via n8n to auto-trigger on new transcript uploads
