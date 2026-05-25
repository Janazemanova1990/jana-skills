# jana-skills

A collection of [Claude skills](https://docs.claude.com/en/docs/agents-and-tools/agent-skills/overview) I've built for my work and for the Nextfem AI community.

A skill is a folder with a `SKILL.md` (instructions + frontmatter) and optionally supporting files (templates, references, scripts). Claude reads it on demand when the task matches its description.

## Skills in this repo

### [`nextfem-meeting-summary`](./nextfem-meeting-summary)
HTML email newsletter generator for [Nextfem AI](https://nextfemai.com) community meetings. Takes meeting notes, returns a fully branded HTML email — colours, typography, structure, all on-brand and inline-styled for email clients.

**Use case:** community meeting → polished recap newsletter in one prompt.

### [`project-update-email`](./project-update-email)
Turns an MS Teams meeting transcript into a structured project update email. Used in real client work — outputs in British English, with named owners on every next step, and bold ❗ BLOCKER / ⚠️ Risk callouts.

**Use case:** 45-minute project meeting → ready-to-send stakeholder email in under a minute.

### [`skill-security-audit`](./skill-security-audit)
A skill that audits other skills. Before you install a skill from GitHub or any external source, this one walks Claude through a 6-step audit: file tree, frontmatter, prompt injection patterns, network calls, file system access, repo trust signals. Returns a clear SAFE / SAFE WITH NOTES / REVIEW REQUIRED / DO NOT INSTALL verdict.

**Use case:** stop trusting random skills you found on GitHub. Audit first.

## How to use these skills

1. Clone or download the folder of the skill you want
2. Drop it into your Claude skills directory (location depends on your setup — see [Claude skills docs](https://docs.claude.com/en/docs/agents-and-tools/agent-skills/overview))
3. Claude will load it when a matching task comes up

## About

Built by Jana — project manager, builder, founder of [Nextfem AI](https://nextfemai.com).

These skills exist because I needed them. Sharing them in case they're useful to someone else.
