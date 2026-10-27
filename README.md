# Digital Forensics & Incident Response Investigation

**Case ID:** DFIR-2026-001  
**Organisation:** Northstar Finance Ltd. (fictional)  
**Investigation type:** Suspected workstation compromise  
**Status:** Completed preliminary assessment  
**Evidence:** Synthetic data created for educational purposes

## Overview

This project demonstrates a simulated Digital Forensics and Incident Response (DFIR) investigation involving a fictional employee workstation.

The investigation examines synthetic authentication, process, file, network, and security-alert events. It documents the evidence, records a SHA-256 hash, reconstructs a timeline, assesses potential indicators of suspicious activity, and produces an incident investigation report.

The project follows an evidence-led approach: observations are distinguished from hypotheses, evidence gaps are documented, and conclusions are limited to what the available records support.

**Key conclusion:** The available simulated evidence warrants further investigation but is insufficient to confirm a workstation compromise.

## Objectives

- Establish and document the investigation scope.
- Catalogue the available evidence.
- Calculate and record a SHA-256 hash for the synthetic event dataset.
- Reconstruct a chronological event timeline.
- Identify suspicious activity requiring further investigation.
- Document evidence gaps and alternative explanations.
- Produce a structured incident investigation report.
- Recommend appropriate investigation and response actions.

## Investigation Scenario

An employee at Northstar Finance Ltd. reports unusual workstation behaviour. A simulated investigation is initiated to examine available event records and determine whether they support a finding of compromise.

The synthetic dataset contains nine events between 08:42 UTC and 09:15 UTC on 27 October 2026.

Notable events include:

- An unrecognised script interpreter starting.
- A file being created in a temporary directory.
- Two failed authentication attempts.
- An outbound network connection being recorded.
- A synthetic endpoint security alert being generated.
- A subsequent administrator login.

These events are investigation leads, not proof of malicious activity.

## Repository Structure

```text
digital-forensics-incident-response/
├── README.md
├── scope/
│   └── investigation-scope.md
├── evidence/
│   ├── evidence-inventory.csv
│   ├── file-hashes.txt
│   └── simulated-events.csv
├── analysis/
│   ├── investigation-timeline.csv
│   └── artifact-analysis.md
└── reports/
    └── incident-investigation-report.md
```

## Investigation Methodology

### 1. Scope Definition

Defined the fictional case, investigation objectives, authorised activities, and exclusions before analysing the simulated records.

### 2. Evidence Inventory

Documented the available event dataset and its synthetic origin in an evidence inventory.

### 3. Evidence Integrity

Calculated the SHA-256 hash of the event dataset and recorded it in a hash manifest.

The hash provides a reference for checking whether the file has changed since hashing. It does not independently establish authenticity or a complete chain of custody.

### 4. Timeline Reconstruction

Organised the nine events chronologically to identify activity that may warrant correlation.

### 5. Artifact Analysis

Reviewed process, file, authentication, network, and security-alert records. Documented observations, possible explanations, and missing evidence.

### 6. Incident Reporting

Produced a preliminary report describing the findings, impact uncertainties, limitations, and recommended follow-up actions.

## Key Findings

| Observation | Assessment | Further evidence needed |
|---|---|---|
| Unrecognised script interpreter started | Unverified investigation lead | Process path, command line, parent process, hash |
| File created in a temporary directory | Unverified investigation lead | Filename, path, metadata, contents |
| Two failed authentication attempts | Inconclusive | Authentication source and failure reasons |
| Outbound network connection recorded | Insufficient evidence | Destination, protocol, associated process |
| Synthetic endpoint alert generated | Requires investigation | Alert details, severity, detection context |
| Administrator login succeeded | Context unavailable | Source, authorisation, related activity |

### Incident Assessment

The event sequence between 08:47 UTC and 08:54 UTC deserves further investigation because it includes process execution, file creation, authentication failures, and network activity.

However, the available records do not establish that these events are causally related.

The investigation did not confirm malware execution, unauthorised access, credential compromise, or data exfiltration.

**Final assessment: Inconclusive pending additional evidence.**

## Project Artifacts

| Artifact | Description |
|---|---|
| [Investigation Scope](scope/investigation-scope.md) | Case boundaries and methodology |
| [Evidence Inventory](evidence/evidence-inventory.csv) | Evidence identification and source |
| [Simulated Events](evidence/simulated-events.csv) | Nine synthetic workstation events |
| [SHA-256 Manifest](evidence/file-hashes.txt) | Recorded evidence hash |
| [Investigation Timeline](analysis/investigation-timeline.csv) | Chronological event sequence |
| [Artifact Analysis](analysis/artifact-analysis.md) | Findings, uncertainties, and follow-up |
| [Investigation Report](reports/incident-investigation-report.md) | Final preliminary assessment |

## Skills Demonstrated

- Digital forensics fundamentals
- Evidence inventory and documentation
- SHA-256 file integrity verification
- Timeline reconstruction
- Log and artifact analysis
- Preliminary incident assessment
- Evidence correlation and analytical reasoning
- Incident response recommendations
- Technical reporting
- GitHub documentation and version control

## Limitations

This is a simulated educational exercise. The dataset contains only nine synthetic records and does not include full process telemetry, file contents, detailed authentication logs, network destinations, or endpoint alert metadata.

No real system was examined, and no actual compromise was established.

## Ethical Considerations

The project uses fictional organisations, usernames, and synthetic event records. It does not include real employee information, live malware, production-system data, or unauthorised system access.

## Future Improvements

Potential extensions include:

- Developing a Python script to sort events and generate the timeline automatically.
- Adding additional synthetic process and network telemetry.
- Verifying file hashes programmatically against the manifest.
- Creating automated checks for missing evidence fields.
- Adding a documented chain-of-custody template.
- Expanding the case with a second evidence source for event correlation.

---

**Portfolio note:** This project demonstrates a structured approach to a simulated forensic investigation. All findings are limited to the synthetic evidence supplied.
