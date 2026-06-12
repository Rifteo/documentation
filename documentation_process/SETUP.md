# Setup — first time

This repo contains the source for the Rifteo Community Hub documentation.  
The site is automatically built by **Mintlify** on every merge to `main`.  
You don't need to deploy anything — just edit the files and open a PR.

---

## Install the local environment

**Prerequisites:** Node.js 18 or higher.

```bash
# 1. Clone the repo
git clone https://github.com/Rifteo/documentation.git
cd rifteo-documentation

# 2. Install Mintlify
npm install -g mintlify

# 3. Start the local server
mintlify dev
```

The site is available at `http://localhost:3000`.  
Changes are reflected in real time — no need to restart.

---

## Repo structure

```
docs.json       ← navigation, theme, site config (menu, footer, etc.)
docs/           ← Getting Started pages (introduction, quickstart, etc.)
skills/         ← one .mdx page per skill
contexts/       ← one .mdx page per context
scripts/        ← one .mdx page per script
usage/          ← CLI reference, configuration, examples
medias/         ← images and videos (don't modify without a reason)
```

---

## Standard workflow

```bash
git checkout -b feat/your-change-name
# ... edit files ...
git add .
git commit -m "docs: description of your change"
git push origin feat/your-change-name
# → open a Pull Request on GitHub
```

Merge only after approval from a team member.

---

## The two most important files

- **`docs.json`** — controls the entire navigation menu. If a page is not listed here, it won't appear on the site even if the `.mdx` file exists.
- **`skills/cvss-scorer.mdx`** — use this page as the format reference for any new skill page.
