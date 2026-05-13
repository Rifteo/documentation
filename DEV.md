# AuditGuard Documentation — Developer Guide

This repo hosts the official AuditGuard community documentation, built with [Mintlify](https://mintlify.com).
It contains structured guides, reusable skill templates, and script references for contributors.

---

## Structure

```
auditguard-documentation/
├── docs.json           # Mintlify config (navigation, theme, URLs)
├── package.json        # Dev scripts
├── docs/               # Core docs: introduction, quickstart, contributing, style guide
├── skills/             # Skill guides and templates
├── scripts/            # Script guides and templates
└── usage/              # CLI reference, configuration, examples
```

---

## Run locally

**Prerequisites:** Node.js 18+

```bash
# 1. Clone the repo
git clone https://github.com/AuditGuard-Community/auditguard-documentation.git
cd auditguard-documentation

# 2. Install Mintlify CLI
npm install -g mintlify

# 3. Start the dev server
mintlify dev
```

The docs will be available at `http://localhost:3000`.

---

## Adding a skill

1. Create a new `.mdx` file in `skills/`
2. Follow the template in [skills/skill-template.mdx](skills/skill-template.mdx)
3. Add the page path to `docs.json` under the `Skills` group
4. Open a pull request

## Adding a script

1. Create a new `.mdx` file in `scripts/`
2. Follow the template in [scripts/script-template.mdx](scripts/script-template.mdx)
3. Add the page path to `docs.json` under the `Scripts` group
4. Open a pull request

---

## Style guide

Before submitting, read [docs/style-guide.mdx](docs/style-guide.mdx) to make sure your content follows community standards.
