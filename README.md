<div align="center">

# AuditGuard Community Hub

**The first open source toolkit purpose built for AI security agents.**

Skills, contexts, and live bug bounty data. Everything your agent needs to run a real engagement, installed in one command.

[![Skills](https://img.shields.io/badge/skills-29-brightgreen)](https://github.com/AuditGuard-Community/skills)
[![Contexts](https://img.shields.io/badge/contexts-4-blue)](https://github.com/AuditGuard-Community/context-mcp)
[![License](https://img.shields.io/badge/license-MIT-blue)](LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen)](docs/contributing.mdx)

</div>

---

## The problem

Ask an agent to hunt for IDOR bugs. It will improvise. It misses verb inconsistency checks, skips GraphQL object exposure, and never tests parameter pollution. You re-prompt five times, spend 3x the tokens, and still get an incomplete result.

The agent is not dumb. It lacks a methodology.

---

## What is here

| Resource | Count | What it does |
|----------|-------|-------------|
| **Skills** | 29 | Battle-tested methodology files your agent reads before starting a task |
| **Contexts** | 4 | Engagement-specific knowledge bases loaded before an engagement starts |
| **Scripts** | Coming soon | Standalone automation scripts for security and compliance tasks |

---

## Quickstart

**Skills**, install via the CLI:

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

**Contexts**, install via the MCP server:

```bash
git clone https://github.com/AuditGuard-Community/context-mcp
cd context-mcp
pip install -e .

auditguard-context install
```

Then ask your agent: `get the web-app-pentest context`

---

## Skills

### Web Application

| Skill | What it does |
|---|---|
| `xss-hunter` | Full XSS methodology: reflected, stored, DOM, filter bypass, CSP evasion, mXSS |
| `xxe-phantom` | XXE injection: file read, blind OOB, SSRF chaining, SVG and XLSX vectors |
| `ssti-hunter` | Server-side template injection with engine fingerprinting and RCE exploitation |
| `js-analyzer` | JavaScript analysis for secrets, endpoints, sinks, and prototype pollution |
| `hpp-hunter` | HTTP parameter pollution detection and exploitation |
| `clickjacking-hunter` | Clickjacking detection and PoC generation |
| `redirect-forge` | Open redirect discovery and OAuth code theft chaining |

### API Security

| Skill | What it does |
|---|---|
| `idor-hunter` | Systematic IDOR and BOLA detection with multi-account testing and bypass techniques |
| `jwt-cracker` | JWT attacks: alg:none, weak secret brute-force, RS256 to HS256, kid injection |

### Infrastructure

| Skill | What it does |
|---|---|
| `ssrf-hunter` | SSRF detection and exploitation including internal recon, cloud metadata, and filter bypass |
| `nuclei-template-writer` | Writes production-ready Nuclei templates from vulnerability descriptions |
| `check-exploit` | Checks if a CVE has a public exploit and assesses exploitability |

### Reconnaissance

| Skill | What it does |
|---|---|
| `attack-surface` | Maps the full attack surface before testing begins |
| `scope-grill` | Validates and clarifies engagement scope |
| `vuln-diagnose` | Diagnoses ambiguous or incomplete vulnerability reports |

### Reporting

| Skill | What it does |
|---|---|
| `finding-writer` | Converts raw notes into a structured, report-ready finding |
| `pentest-report` | Assembles a full pentest report from individual findings |
| `bugbounty-reporter` | Converts raw findings into triage-ready reports |
| `cvss-scorer` | Computes exact CVSS v3.1 base score and vector from a vulnerability description |
| `risk-assessor` | Business risk assessment from technical findings |
| `remediation-planner` | Generates specific, prioritized remediation plans |

### Compliance

| Skill | What it does |
|---|---|
| `compliance-gap-analyzer` | Identifies compliance gaps against security frameworks |
| `control-lookup` | Maps controls across ISO 27001, SOC2, NIST, and PCI-DSS |

### Workflow

| Skill | What it does |
|---|---|
| `find-skills` | Discovers and loads the right skill for any security task |
| `engagement-handoff` | Structures engagement handoff notes between team members |
| `ctf-writeup` | Formats CTF challenge writeups |
| `caveman` | Ultra-compressed comms mode for fast-paced testing sessions |
| `skill-benchmark` | Benchmarks skill performance with and without the agent |

### Integrations

| Skill | Tool | What it does |
|---|---|---|
| `hexstrike-forge` | HexStrike | Full pentest engagement: 5-phase workflow, parallel execution, triage gates, and report-ready findings from a single prompt |

---

## Contexts

| Context | What it covers |
|---------|---------------|
| `web-app-pentest` | Full web app pentest: recon, auth, injection, business logic |
| `cloud-audit` | AWS/Azure/GCP: IAM, storage exposure, networking, logging, secrets |
| `code-audit` | Source code security review: secrets, auth logic, injection sinks, crypto |
| `ad-pentest-unauthenticated` | Unauthenticated AD pentest: host discovery, SMB null sessions, AS-REP roasting, Kerberoasting |

---

## Contributing

Skills and contexts are built by practitioners, for practitioners. If you have a methodology that works, the community needs it.

The short version:

1. Create a folder named after your skill or context
2. Add `SKILL.md` or `CONTEXT.md` with the required format
3. Open a pull request

Read the [contribution guide](docs/contributing.mdx) for the full process.

---

<div align="center">
  <sub>Built by the <a href="https://github.com/AuditGuard-Community">AuditGuard Community</a>. MIT License</sub>
</div>
