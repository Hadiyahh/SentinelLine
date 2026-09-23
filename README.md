# SentinelLine

### Policy-Driven Malware Triage & Analysis Orchestration

SentinelLine is a malware-analysis orchestration layer built on
Assemblyline that automatically triages submitted files and routes
them through FAST, DEEP, or HUMAN_REVIEW analysis workflows.

![SentinelLine Audit Dashboard](docs/images/dashboard-overview.png)

## How It Works

File Upload
    ↓
TRIAGE
    ↓
FAST / DEEP / HUMAN_REVIEW
    ↓
Assemblyline
    ↓
SCORE
    ↓
Recommendation
    ↓
Audit Dashboard

### Human-in-the-Loop Escalation

Files requiring analyst attention are automatically surfaced in a
dedicated review queue.

![Analyst Review Queue](docs/images/analyst-review.png)

## End-to-End Trace Example

A suspicious Windows executable triggered a persistence-related
YARA rule and received an initial risk score of 40.

SentinelLine routed it to the DEEP policy, submitted it to
Assemblyline using the DYNAMIC_OFFLINE configuration, waited for
analysis to complete, and returned a QUARANTINE recommendation.

![Trace Details](docs/images/trace-details.png)

## End-to-End Trace Example

A suspicious Windows executable triggered a persistence-related
YARA rule and received an initial risk score of 40.

SentinelLine routed it to the DEEP policy, submitted it to
Assemblyline using the DYNAMIC_OFFLINE configuration, waited for
analysis to complete, and returned a QUARANTINE recommendation.

![Trace Details](docs/images/trace-details.png)
