# Container Vulnerability Management Program

A **sanitized, reference implementation** of an enterprise container and Kubernetes vulnerability management program — the governance, process, and ownership model used to run risk-based vulnerability management across a large multi-cluster Kubernetes / AKS estate scanned with **Aqua Security** (image, registry, CI/CD, and runtime) alongside a **CNAPP/CSPM** layer.

> ⚠️ **Sanitized portfolio artifact.** This repository contains **generic templates and methodology only**. It includes no employer-internal data, no real cluster names, registries, findings, or configurations. All names, thresholds, and examples are illustrative and provided to demonstrate approach and structure.

## Why this exists

Most container vulnerability programs fail not because the scanner misses CVEs, but because there is no **operating model** around the scanner: unclear ownership, no risk-based prioritization, no SLAs, and scanner output that never becomes audit-ready evidence. This repository codifies the operating model — who does what, in what order, against which SLAs, mapped to which controls.

## What this demonstrates

- **Risk-based prioritization** — ranking findings by exploitability and business impact rather than raw CVSS, and elevating confirmed attack-path / toxic-combination findings above standalone CVEs.
- **A clear ownership model** — a RACI matrix separating the platform/KaaS team from cluster owners, closing the accountability gaps that stall remediation.
- **SLA-driven remediation** — triage, ownership routing, and mean-time-to-remediate (MTTR) tracking.
- **Shift-left + runtime** — image scanning, admission control, and runtime protection embedded into CI/CD.
- **EOL / version compliance** — driving end-of-life Kubernetes clusters onto supported versions.
- **Control-mapped evidence** — converting scanner output into NIST 800-53 / ISO 27001 / FedRAMP-aligned artifacts for audit, ATO, and leadership.

## Repository structure

| Path | Contents |
| --- | --- |
| [`docs/aqua-vulnerability-management-handbook.md`](aqua-vulnerability-management-handbook.md) | The program handbook — scope, tooling, scanning workflow, prioritization model, SLAs, metrics. |
| [`docs/standard-operating-procedures.md`](standard-operating-procedures.md) | The SOP suite (SOP-01 … SOP-07) for the day-to-day workflow. |
| [`governance/raci-matrix.md`](raci-matrix.md) | The KaaS-Team-vs-Cluster-Owner RACI matrix. |
| [`templates/remediation-ticket-template.md`](remediation-ticket-template.md) | A standardized remediation ticket / work item template. |
| [`templates/risk-acceptance-template.md`](risk-acceptance-template.md) | A time-boxed risk acceptance / exception template. |

## Companion repositories

- **Container Vulnerability Remediation Plan (CVRP)** — the 15-section, control-mapped remediation plan template.
- **Kubernetes Version-Compliance Tracker** — working code that flags EOL cluster versions and computes version-compliance.

## License

Released under the [MIT License](LICENSE) — reuse and adapt freely with attribution.
