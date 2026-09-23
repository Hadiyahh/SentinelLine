# SentinelLine

### Policy-Driven Malware Triage & Analysis Orchestration

SentinelLine is a malware-analysis orchestration layer built on
Assemblyline that automatically triages submitted files and routes
them through FAST, DEEP, or HUMAN_REVIEW analysis workflows.

<img width="1300" height="874" alt="image" src="https://github.com/user-attachments/assets/1b3f0f72-37d5-4d62-a956-788b5303b41d" />

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

<img width="1207" height="736" alt="image" src="https://github.com/user-attachments/assets/539276c9-88b8-4899-ad11-b1d4eef57b58" />


