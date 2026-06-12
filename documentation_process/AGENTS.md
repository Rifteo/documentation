# Contributor Guide

Mintlify docs site. `mintlify dev` → http://localhost:3000. A page only appears on the site if it's listed in `docs.json`.

---

## Task: Add a skill

1. Create `skills/<name>/SKILL.md`:
```yaml
---
name: <name>
description: One sentence.
license: MIT
metadata:
  version: "1.0.0"
  author: <author>
  tags: ["tag1", "tag2"]
---
## When to Use
## Step 1: ...
## Output Format
## Rules
```

2. Create `skills/<name>.mdx`. Copy `skills/cvss-scorer.mdx` structure:
- frontmatter (`title`, `description`)
- `<Info>` block: Status, Version, Author, Tags
- `## Summary` (3-5 bullets)
- `## SKILL.md file` (`<Accordion>` with SKILL.md content)
- `## Related skills` (3 cards)

3. Add `"skills/<name>"` to a group under `tab: "Skills"` in `docs.json`.
Groups: Web Application, API Security, Infrastructure, Reconnaissance, Reporting, Compliance, Workflow, Attack Mindset, Integrations.

4. Run `mintlify dev`, verify page renders and appears in nav.

---

## Task: Edit a skill

- Content → edit `skills/<name>.mdx`
- Agent instructions → edit `skills/<name>/SKILL.md`
- Rename → rename `.mdx` file + update path in `docs.json` + add entry to `redirects` in `docs.json`

---

## Task: Add a context

1. Create `contexts/<name>/CONTEXT.md`:
```yaml
---
name: <name>
l0: One sentence.
---
## L1 Overview
(short, loaded by default)
---
## L2 Full Methodology
(full detail, loaded on demand)
```

2. Create `contexts/<name>.mdx`. Copy `contexts/web-app-pentest.mdx` structure:
- frontmatter (`title`, `description`)
- `<Info>` block: Category
- load command
- `## Summary` (4-6 bullets)
- full CONTEXT.md content
- `## Related contexts` (2-3 cards)

3. Add `"contexts/<name>"` to a group under `tab: "Contexts"` in `docs.json`.
Groups: Web & API, Infrastructure, Code Review, Bug Bounty.

4. Run `mintlify dev`, verify page renders and appears in nav.

---

## Task: Edit `docs.json`

- **Add page to group**: append `"path/filename"` (no extension) to the group's `pages` array.
- **New group**: add `{ "group": "Name", "pages": [...] }` to the tab's `groups` array.
- **Rename in menu**: edit `title` in the page's frontmatter — NOT in `docs.json`.
- **Remove page**: delete from `pages` array + delete the `.mdx` file + add to `redirects`:
```json
{ "source": "/skills/old-name", "destination": "/skills/new-name" }
```
- **Move page**: remove path from old group's `pages`, add to new group's `pages`.
- **Banner/navbar/footer**: edit `banner.content`, `navbar.links`, `footer.links` directly.

Validate with `mintlify dev` — errors show at startup if `docs.json` is broken or references a missing page.

---

## Style rules (every `.mdx`)

- Frontmatter: `title` (sentence case, <60 chars) + `description` (specific, not generic)
- `<Info>` block right after frontmatter: Status, Version, Author, Tags
- Headings: sentence case, no skipped levels
- Code blocks: always specify language, use realistic values
- Tables: header row required, exact values in `` `inline code` ``
- No summary/conclusion paragraphs
- No `TODO`/`TBD`/placeholders
- Second person, direct: "Checks whether X" not "Helps you improve X by leveraging..."
- Empty sections → write "None at this time"

---

## Setup

```bash
npm install -g mintlify
mintlify dev
```

```
docs.json       navigation, theme, config
docs/           Getting Started pages
skills/         skills/<name>.mdx + skills/<name>/SKILL.md
contexts/       contexts/<name>.mdx + contexts/<name>/CONTEXT.md
scripts/        scripts/<name>.mdx
usage/          CLI reference, config, examples
```

Workflow: branch → edit → `mintlify dev` to verify → PR.

## Pre-PR checklist

- [ ] `mintlify dev` runs clean
- [ ] Page renders at expected URL
- [ ] Page appears in nav
- [ ] `<Info>` block present, all 4 fields filled
- [ ] No empty sections, no placeholders
