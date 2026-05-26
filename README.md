<div align="center">

<br/>

# AuditGuard Community Hub

**Install proven pentest methodologies into Claude Code, Gemini CLI, Cursor, and 50+ other agents in one command.**

<br/>

[![Skills](https://img.shields.io/badge/skills-29-blueviolet?style=for-the-badge)](https://github.com/AuditGuard-Community/skills)
[![Contexts](https://img.shields.io/badge/contexts-4-blue?style=for-the-badge)](https://github.com/AuditGuard-Community/context-mcp)
[![License](https://img.shields.io/badge/license-MIT-green?style=for-the-badge)](LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen?style=for-the-badge)](docs/contributing.mdx)

<br/>

</div>

---

### The problem

Ask an agent to hunt for IDOR bugs. It will improvise. It misses verb inconsistency checks, skips GraphQL object exposure, and never tests parameter pollution. You re-prompt five times, spend 3x the tokens, and still get an incomplete result.

The agent is not dumb. It lacks a methodology.

---

### What's here

| Resource | Count | What it does |
|----------|-------|-------------|
| **Skills** | 29 | Battle-tested methodology files your agent reads before starting a task |
| **Contexts** | 4 | Engagement-specific knowledge bases: web app pentest, cloud audit, code audit, and more |
| **Scripts** | Growing | Standalone automation scripts for common security and compliance tasks |

---

### Quickstart

**Skills**  install via the CLI:

```bash
git clone https://github.com/AuditGuard-Community/skills-cli
cd skills-cli
npm link

auditguard-skills add bugbounty-reporter
```

Not sure which skill to use? Install `find-skills` first:

```bash
auditguard-skills add find-skills
```

**Contexts**  install via the MCP server:

```bash
git clone https://github.com/AuditGuard-Community/context-mcp
cd context-mcp
pip install -e .

auditguard-context install
```

Then ask your agent: `get the web-app-pentest context`

---

### Skills

| Category | Skills |
|----------|--------|
| Web Application | `xss-hunter`, `xxe-phantom`, `ssti-hunter`, `js-analyzer`, `hpp-hunter`, `clickjacking-hunter`, `redirect-forge` |
| API Security | `idor-hunter`, `jwt-cracker` |
| Infrastructure | `ssrf-hunter`, `nuclei-template-writer`, `check-exploit` |
| Reconnaissance | `attack-surface`, `scope-grill`, `vuln-diagnose` |
| Reporting | `finding-writer`, `pentest-report`, `bugbounty-reporter`, `cvss-scorer`, `risk-assessor`, `remediation-planner` |
| Compliance | `compliance-gap-analyzer`, `control-lookup` |
| Workflow | `find-skills`, `engagement-handoff`, `ctf-writeup`, `caveman`, `skill-benchmark` |
| Integrations | `hexstrike-forge` |

---

### Contexts

| Context | What it covers |
|---------|---------------|
| `web-app-pentest` | Full web app pentest: recon, auth, injection, business logic |
| `cloud-audit` | AWS/Azure/GCP: IAM, storage exposure, networking, logging, secrets |
| `code-audit` | Source code security review: secrets, auth logic, injection sinks, crypto |
| `ad-pentest-unauthenticated` | Unauthenticated AD pentest: host discovery, SMB null sessions, AS-REP roasting, Kerberoasting |

---

### Contributing

Skills and contexts are built by practitioners, for practitioners. If you have a methodology that works, the community needs it.

The short version:

1. Create a folder named after your skill or context
2. Add `SKILL.md` or `CONTEXT.md` with the required format
3. Open a pull request

Read the [contribution guide](docs/contributing.mdx) for the full process. It takes 10 minutes.

---

<div align="center">
  <sub>Built by the <a href="https://github.com/AuditGuard-Community">AuditGuard Community</a>  MIT License</sub>
</div>
