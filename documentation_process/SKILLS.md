# Add or edit a skill

---

## Add a new skill

A skill = 3 things to create/edit:

### 1. The `SKILL.md` file (agent instructions)

Create the folder and file:

```
skills/your-skill-name/SKILL.md
```

Minimum required structure:

```markdown
---
name: your-skill-name
description: One sentence describing what the skill does.
license: MIT
metadata:
  version: "1.0.0"
  author: your-name
  tags: ["security", "compliance"]
---

## When to Use

Describe when the agent should activate this skill.

## Step 1: Step title

What the agent does in this step.

## Output Format

The exact format of the produced response.

## Rules

- Rule 1
- Rule 2
```

### 2. The `.mdx` documentation page

Create the file:

```
skills/your-skill-name.mdx
```

Copy `skills/cvss-scorer.mdx` and adapt the content. Required sections:

1. Frontmatter (`title` + `description`)
2. `<Info>` block (Status, Version, Author, Tags)
3. One-sentence summary
4. `## Summary` section — what the skill does in 3–5 bullet points
5. `## SKILL.md file` section — accordion containing the `SKILL.md` content
6. `## Related skills` section — 3 related skills

### 3. The entry in `docs.json`

Open `docs.json`, find the right group under the `Skills` tab, and add your page:

```json
{
  "group": "Reporting",
  "pages": [
    "skills/existing-skill",
    "skills/your-skill-name"
  ]
}
```

Available groups: `Web Application`, `API Security`, `Infrastructure`, `Reconnaissance`, `Reporting`, `Compliance`, `Workflow`, `Attack Mindset`, `Integrations`.

---

## Edit an existing skill

- **Edit the content** → edit `skills/your-skill-name.mdx` directly
- **Edit the agent instructions** → edit `skills/your-skill-name/SKILL.md`
- **Rename** → rename the `.mdx` file + update the path in `docs.json`

---

## Check before opening a PR

- [ ] `mintlify dev` runs without errors
- [ ] The page displays correctly at `http://localhost:3000/skills/your-skill-name`
- [ ] The skill appears in the navigation menu
- [ ] No empty sections in the `.mdx`
- [ ] No placeholder text (`TODO`, `TBD`, `<fill this in>`)
