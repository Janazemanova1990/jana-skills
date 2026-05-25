# skill-security-audit

A Claude skill that audits other Claude skills before you install them.

## What it does

You found a skill on GitHub. Looks useful. But: it requests `Bash` and `Write` permissions, and it's from a developer you've never heard of. What does it actually do?

This skill walks Claude through a thorough 6-step audit and returns a clear verdict.

### The audit covers

1. **File tree** — every file, including hidden ones and unexpected extensions
2. **Frontmatter** — name/folder mismatch, overly broad descriptions, tool permissions audit
3. **Script files** — network calls, file system access outside expected paths, shell execution risks, data collection patterns, dependency loading
4. **Reference files** — prompt injection patterns disguised as documentation, executable code in markdown
5. **Repo trust signals** — author, stars, age, commit history, recent suspicious commits
6. **Verdict** — one of: `SAFE` / `SAFE WITH NOTES` / `REVIEW REQUIRED` / `DO NOT INSTALL`

### What you get back

A structured report with:
- Network calls found (and to where)
- File system access patterns
- External URLs the skill fetches at runtime
- Tool permission analysis
- Plain-language summary of what the skill actually does
- Specific things to watch out for even if the skill is safe
- A clear recommended action

## Why it exists

The Claude skill ecosystem is opening up. People share skills on GitHub. Most are great. Some won't be. A skill with `Bash` access and bad intent can do anything on your machine — exfiltrate `.env` files, read SSH keys, send your data anywhere.

You wouldn't `npm install` a random package without checking it. Skills should get the same treatment.

This skill is the audit you'd want to run before every install — automated.

## How to use

1. Drop this folder into your Claude skills directory
2. When you find a skill you might want to install:
   - Either give Claude a local path to the cloned folder
   - Or give Claude a GitHub URL
3. Say "audit this skill" or "is this skill safe?"
4. Claude runs the full 6-step audit and returns the report

## Verdict definitions

| Verdict | Meaning |
|---|---|
| `SAFE` | No issues found. Install. |
| `SAFE WITH NOTES` | No security risks but there are things you should know first (commits to git, starts a local server, writes specific files) |
| `REVIEW REQUIRED` | One or more items need your judgement before deciding. The report says exactly what to look at. |
| `DO NOT INSTALL` | Clear evidence of malicious intent, data exfiltration, deceptive instructions, or unacceptable risk. |

## Principles baked in

- **Read every file.** No skill is approved without full read.
- **Be specific.** Not "this looks okay" — say what was checked and what was found.
- **Plain language.** "This script starts a local web server that only accepts localhost connections" beats "uses WebSocket".
- **Yellow flags are flagged.** Even if not red. The user decides.

## Limitations

- Audits only the skill folder as-is. If the skill downloads code at runtime, the audit can flag that but can't audit what gets downloaded.
- Trust signals (stars, repo age) are heuristics, not proof.
- This skill is a safety tool, not a guarantee. Use judgement on top of the report.
