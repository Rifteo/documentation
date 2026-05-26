<div align="center">

# AuditGuard Documentation

Source for the [AuditGuard Community Hub](https://community.auditguard.fr) documentation, built with Mintlify.

[![License](https://img.shields.io/badge/license-MIT-blue)](LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen)](docs/contributing.mdx)

</div>

---

## What is this repo?

This repo contains the documentation source for the AuditGuard Community Hub. All pages are `.mdx` files built and deployed via Mintlify.

---

## Run locally

```bash
npm install
npx mintlify dev
```

The docs will be available at `http://localhost:3000`.

---

## Structure

```
docs/          Getting started, quickstart, contributing
skills/        One page per skill
contexts/      One page per context
usage/         Commands, configuration, examples
scripts/       Scripts (coming soon)
docs.json      Navigation and site config
```

---

## Contributing

To add or update a page, edit the relevant `.mdx` file and open a pull request. New skill and context pages must follow the [style guide](docs/style-guide.mdx).

---

<div align="center">
  <sub>Built by the <a href="https://github.com/AuditGuard-Community">AuditGuard Community</a>. MIT License</sub>
</div>
