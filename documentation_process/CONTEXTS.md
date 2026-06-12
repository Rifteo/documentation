# Add or edit a context

---

## Add a new context

A context = 3 things to create/edit:

### 1. The `CONTEXT.md` file (content for the agent)

Create the folder and file:

```
contexts/your-context-name/CONTEXT.md
```

Required structure:

```markdown
---
name: your-context-name
l0: One sentence describing what this context covers.
---

## L1 Overview

When to use this context and what it covers at a high level.
Loaded by default at session start — keep it short.

---

## L2 Full Methodology

Full content: phases, techniques, tools, commands, report format.
Loaded only when the agent needs the full detail.
```

- **L0** = a single sentence (`l0` field in the frontmatter)
- **L1** = short overview, loaded automatically
- **L2** = full methodology, loaded on demand

### 2. The `.mdx` documentation page

Create the file:

```
contexts/your-context-name.mdx
```

Copy `contexts/web-app-pentest.mdx` and adapt it. Required sections:

1. Frontmatter (`title` + `description`)
2. `<Info>` block (Category)
3. Command to load the context
4. `## Summary` section — what the context covers in 4-6 bullet points
5. The full `CONTEXT.md` content (phases, commands, etc.)
6. `## Related contexts` section — cards linking to 2-3 related contexts

### 3. The entry in `docs.json`

Open `docs.json`, find the right group under the `Contexts` tab, and add your page:

```json
{
  "group": "Web & API",
  "pages": [
    "contexts/existing-context",
    "contexts/your-context-name"
  ]
}
```

Available groups: `Web & API`, `Infrastructure`, `Code Review`, `Bug Bounty`.

---

## Edit an existing context

- **Edit the documentation** → edit `contexts/your-context-name.mdx`
- **Edit the agent content** → edit `contexts/your-context-name/CONTEXT.md`

---

## Check before opening a PR

- [ ] `mintlify dev` runs without errors
- [ ] The page displays correctly at `http://localhost:3000/contexts/your-context-name`
- [ ] The context appears in the navigation menu under the Contexts tab
- [ ] L0, L1, and L2 are all present in `CONTEXT.md`
