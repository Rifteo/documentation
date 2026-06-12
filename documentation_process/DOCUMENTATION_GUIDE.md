# Rifteo Documentation — Maintainer Guide

Built with [Mintlify](https://mintlify.com). Source lives in this repo. Deploy is automatic on merge to `main`.

---

## Run locally

```bash
npm install -g mintlify
mintlify dev
```

Available at `http://localhost:3000`.

---

## Repo structure

```
docs.json          navigation, theme, site config
docs/              introduction, quickstart, contributing, style-guide
skills/            one .mdx page per skill
contexts/          one .mdx page per context
scripts/           one .mdx page per script
usage/             CLI reference, configuration, examples
```

---

## Common tasks

**Add a skill page**
1. Create `skills/your-skill-name.mdx`
2. Add `"skills/your-skill-name"` to the correct group in `docs.json`

**Add a context page**
1. Create `contexts/your-context-name.mdx`
2. Add `"contexts/your-context-name"` to the correct group in `docs.json`

**Add a navigation group**
Edit `docs.json` → find the correct `tab` → add a new `{ "group": "...", "pages": [...] }` entry.

**Rename or remove a page**
Delete or rename the `.mdx` file and update the path in `docs.json`. Add a redirect in the `redirects` array if the old URL was public.

---

## Claude Code prompts

```
Add a skill page for <name> that <what it does>.
Use skills/cvss-scorer.mdx as the reference format.
Add it to docs.json under the <group> group.
```

```
Update all pages that reference <old term> to use <new term>.
```

```
Check docs.json for pages listed in navigation that don't have a corresponding .mdx file.
```
