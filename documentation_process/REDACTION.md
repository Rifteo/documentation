# Writing rules

Read before writing or editing a page.

---

## Required format for every page

Every `.mdx` file must start with:

```yaml
---
title: Sentence case title, under 60 characters
description: One informative sentence, not generic.
---
```

Immediately followed by an `<Info>` block:

```mdx
<Info>
  **Status:** Draft | Review | Stable
  **Version:** 1.0.0
  **Author:** your-name
  **Tags:** security, compliance, access, data, infrastructure, process
</Info>
```

---

## Writing rules

**Headings**
- Sentence case: `## What it checks`, not `## What It Checks`
- No skipped levels (no `##` followed directly by `####`)

**Code blocks**
- Always specify the language: ` ```bash `, ` ```json `, ` ```yaml `
- Show realistic values, not `foo` / `bar`

**Tables**
- Always include a header row
- Exact values in inline code: `` `value` ``

**Lists**
- Bullet lists for unordered items
- Numbered lists only for sequential steps

---

## What not to write

- No concluding paragraph that summarizes what was just said
- No placeholder text in a merged PR (`TODO`, `TBD`, `<fill this in>`)
- No more than two uses of "this skill" in a section — use "it" afterward
- No empty sections — if you have no known limitations, write "None at this time"

---

## Tone

Second person, direct, specific.

**Good:** "Checks whether all IAM users have MFA enabled."  
**Bad:** "Helps you improve your security posture by leveraging best practices."

---

## Checklist before PR

- [ ] `mintlify dev` runs without errors
- [ ] Frontmatter has `title` and `description`
- [ ] `<Info>` block present with all 4 fields
- [ ] All code blocks have a language identifier
- [ ] No empty sections
- [ ] No placeholder text
- [ ] The page appears in the navigation at `localhost:3000`
