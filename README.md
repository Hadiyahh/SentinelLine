# SentinelLine

### Policy-Driven Malware Triage & Analysis Orchestration

SentinelLine is a malware-analysis orchestration layer built on
[Assemblyline](https://cybercentrecanada.github.io/assemblyline4_docs/)
that automatically triages submitted files and routes them through
FAST, DEEP, or HUMAN_REVIEW analysis workflows.

<img
  width="1300"
  alt="SentinelLine Trace Overview dashboard showing FAST, DEEP, and HUMAN_REVIEW routes"
  src="https://github.com/user-attachments/assets/1b3f0f72-37d5-4d62-a956-788b5303b41d"
/>

## How It Works

```text
File Upload
    ↓
RECEIVED
    ↓
TRIAGE
    ↓
ROUTE
    ↓
Policy Configuration
    ↓
SUBMIT → Assemblyline
    ↓
WAIT
    ↓
SCORE
    ↓
RESPOND
    ↓
API Response + Audit Logs
                   ↓
             Audit Dashboard
```

## Human-in-the-Loop Escalation

Files requiring analyst attention are surfaced in a dedicated review
queue with their routing policy, score, recommendation, status, and
trace history.

<img width="1207" alt="SentinelLine analyst review queue showing HUMAN_REVIEW escalations" src="https://github.com/user-attachments/assets/539276c9-88b8-4899-ad11-b1d4eef57b58" />

## End-to-End Trace Example

A suspicious Windows executable triggered a persistence-related YARA
rule and received an initial risk score of 40.

SentinelLine routed it to the `DEEP` policy, submitted it to Assemblyline
using the `DYNAMIC_OFFLINE` configuration, waited for analysis to
complete, and returned a `QUARANTINE` recommendation.

| Field | Result |
|---|---|
| File | `Backdoor.Win32.Poison.cnoo_4a33.exe` |
| YARA Match | `Triage_Persistence` |
| Route | `DEEP` |
| Policy | `DYNAMIC_OFFLINE` |
| Final Score | `40` |
| Recommendation | `QUARANTINE` |
| Status | `complete` |

## Project Presentation

For a visual walkthrough of SentinelLine's architecture, routing policies,
audit workflow, testing, and current limitations:

[View the SentinelLine Project Presentation](SentinelLine_Presentation.pdf)
