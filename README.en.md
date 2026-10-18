# premise-and-config-audit · Premise & Config Audit

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE.md)
[![Agent Skill](https://img.shields.io/badge/Agent%20Skill-SKILL.md-blue.svg)](SKILL.md)
[![Premortem](https://img.shields.io/badge/premortem-assumption%20testing-brightgreen.svg)](SKILL.md)

SynomosAI four-pillar system: **Identity · Traceability · Governance · Symbiosis**.

> This repo is part of the [SynomosAI](https://github.com/SynomosAI) skill ecosystem.

**Keywords**: premise validation · assumption testing · premortem · config audit · config drift · toolchain inventory · AWS Well-Architected · SRE config

A methodology skill: before starting, falsify the riskiest assumptions (don't treat guesses as facts); when auditing tools / configs, inventory the real state first and then benchmark against standards. Diagnosis only — it never changes your config on its own; sensitive actions are listed as P0 and wait for your confirmation.

## Quick Start

Prerequisite: no runtime dependencies (methodology / checklist skill).

```bash
git clone https://github.com/SynomosAI/premise-and-config-audit.git
cd premise-and-config-audit
cat SKILL.md
```

```text
Triggers: premise · assumption · validation · audit · config drift
toolchain · redundancy · activation gap · why did the plan go sideways
```

## What it covers

- **Premise validation (5 steps)**: enumerate assumptions -> rank by importance x evidence -> cheapest real test -> impact assessment -> re-architect on verified facts.
- **Config audit prism (4 steps)**: inventory real state (measure, don't recall) -> benchmark (AWS Well-Architected / SRE / identity governance) -> diagnose (good / gap / redundancy) -> tiered P0/P1/P2 advice.
- **Tool visibility discipline**: audit hidden (dotfile) directories explicitly to avoid false-negative "not found" conclusions.

## Audit document example (excerpt)

```text
Config audit snapshot
  connectors: claimed 20 -> actually connected 4 (others were built and paused)
  skills: 77 installed -> 15 active in last 30 days
  diagnosis: over-planned, under-activated; 3 overlapping clusters
  P0: retire 3 redundant skills (pending user confirmation)
```

## License

MIT License. © 2026 注册老炮@MedXpert. See [LICENSE.md](LICENSE.md).

## Disclaimer

Theoretical-positioning and tooling exploration. External methods (AWS Well-Architected, Google SRE, Premortem) are paraphrased from public sources; verify independently before formal citation.
