# Digital Forensics & Incident Response Report

## 1. Executive Summary

**Case ID:** DFIR-2026-001  
**Organisation:** Northstar Finance Ltd. (fictional)  
**Investigation type:** Suspected workstation compromise  
**Investigation date:** 27 October 2026  
**Status:** Preliminary assessment  
**Evidence type:** Synthetic educational dataset  

This investigation reviewed nine simulated workstation events covering the period from 08:42 UTC to 09:15 UTC on 27 October 2026.

The records include an unrecognised script interpreter starting, a file being created in a temporary directory, two failed authentication attempts, an outbound network connection, an endpoint security alert, and a subsequent administrator login.

These events warrant further investigation. However, the available evidence does not establish that the workstation was compromised or that the events were caused by malicious activity.

**Overall assessment:** Inconclusive. Additional evidence is required before determining whether a security incident occurred.

## 2. Investigation Objectives

The investigation aimed to:

- Document and catalogue the available evidence.
- Record a SHA-256 hash for the synthetic event dataset.
- Reconstruct the chronology of the recorded events.
- Identify activity requiring further investigation.
- Document evidence gaps and alternative explanations.
- Recommend appropriate next steps.

## 3. Scope and Methodology

The investigation was limited to synthetic event records created for this educational project.

The methodology consisted of:

1. Defining the investigation scope.
2. Creating an evidence inventory.
3. Calculating and recording the event dataset's SHA-256 hash.
4. Building a chronological timeline.
5. Reviewing event sequences and potential relationships.
6. Documenting preliminary findings and evidence limitations.

No real employee devices, production systems, or live suspicious files were examined.

## 4. Evidence Reviewed

| Evidence ID | Evidence item | Purpose |
|---|---|---|
| EVD001 | `evidence/simulated-events.csv` | Synthetic workstation event records |
| EVD001 integrity record | `evidence/file-hashes.txt` | Records the dataset's SHA-256 hash |
| Investigation record | `evidence/evidence-inventory.csv` | Documents the evidence item |
| Analysis output | `analysis/investigation-timeline.csv` | Presents events in chronological order |
| Analysis notes | `analysis/artifact-analysis.md` | Documents observations, uncertainties, and follow-up actions |

### Evidence Integrity

The SHA-256 hash was calculated locally after the synthetic event dataset was created and recorded in the hash manifest.

The hash can be recalculated to check whether the local file still matches the recorded value. This supports integrity verification from the point of hashing but does not independently prove the dataset's authenticity or establish a complete chain of custody.

## 5. Timeline Summary

All timestamps below are recorded in UTC.

| Time | Event | Preliminary interpretation |
|---|---|---|
| 08:42 | Employee login succeeded | Establishes the start of the recorded activity |
| 08:47 | Unrecognised script interpreter started | Requires process-level investigation |
| 08:48 | File created in a temporary directory | File identity and contents are unknown |
| 08:51 | Authentication failed | Cause is unknown |
| 08:52 | Authentication failed again | May be related to the previous failure |
| 08:54 | Outbound network connection recorded | Destination and process are unknown |
| 09:03 | Document modified | Document identity and changes are unknown |
| 09:10 | Synthetic endpoint alert generated | Alert contents and severity are unavailable |
| 09:15 | Administrator login succeeded | Authorisation and relationship to prior activity are unverified |

The process start, file creation, authentication failures, and outbound connection occurred within a short period. This sequence provides a useful starting point for correlation, but the available records do not prove that these events share a common cause.

## 6. Key Findings

### Finding 1: Unrecognised Process Execution

**Status:** Unverified investigation lead

A simulated event records an unrecognised script interpreter starting at 08:47 UTC.

Further process telemetry is needed to establish the executable path, command line, parent process, and file hash. The current record does not establish malicious execution.

### Finding 2: Temporary File Creation

**Status:** Unverified investigation lead

A file was reportedly created at 08:48 UTC.

The filename, path, contents, and creating process are unavailable. The relationship between this file and the earlier process event remains unconfirmed.

### Finding 3: Failed Authentication Attempts

**Status:** Inconclusive

Two failed authentication attempts were recorded at 08:51 and 08:52 UTC.

The records do not identify the authentication source or failure reason. The events could reflect ordinary user error or other activity; they are insufficient to establish brute-force activity.

### Finding 4: Outbound Network Connection

**Status:** Insufficient evidence

An outbound connection was recorded at 08:54 UTC.

No destination address, port, protocol, or associated process is provided. There is no basis for identifying a malicious destination from the available evidence.

### Finding 5: Endpoint Security Alert

**Status:** Requires further investigation

A synthetic endpoint alert was recorded at 09:10 UTC.

Without the alert description, severity, and detection details, it cannot be used to corroborate a specific threat.

### Finding 6: Administrator Login

**Status:** Context unavailable

A successful administrator login was recorded at 09:15 UTC.

The available evidence does not establish whether this activity was authorised or connected to the earlier events.

## 7. Impact Assessment

The potential impact cannot be determined from the current dataset.

There is insufficient evidence to establish:

- Whether unauthorised access occurred.
- Whether any malicious software executed.
- Whether credentials were compromised.
- Whether sensitive information was accessed or transferred.
- Whether the administrator account was misused.
- Whether any system or business data was affected.

These are unresolved questions, not confirmed impacts.

## 8. Recommended Response Actions

The following actions are recommended for a real investigation if supported by the applicable authorisation and response procedures.

### Priority 1 — Validate the Potential Threat

- Retrieve the full endpoint alert and its associated telemetry.
- Identify the script interpreter and review its execution details.
- Establish whether the temporary file is expected and authorised.
- Correlate the available process, file, authentication, and network records.

### Priority 2 — Investigate Authentication and Network Activity

- Review authentication records surrounding the two failures.
- Determine the source and destination of the recorded network connection.
- Establish which process initiated the connection, where telemetry permits.
- Verify whether the administrator login was expected and authorised.

### Priority 3 — Preserve Additional Evidence

- Preserve relevant logs and metadata using approved evidence-handling procedures.
- Document the source, collection time, and handling of each new evidence item.
- Calculate and record hashes for collected evidence where appropriate.
- Maintain a documented chain of custody for any real investigation.

### Priority 4 — Determine Containment and Recovery Needs

If further evidence establishes an active or credible threat, follow the organisation's incident response procedures to determine whether containment is necessary.

Containment, eradication, and recovery actions should be proportionate to the verified threat and coordinated with authorised responders.

## 9. Limitations

This investigation has several important limitations:

- All records are synthetic and created for educational purposes.
- Only nine event records were available.
- Process command lines and executable identities were not supplied.
- The created file's identity and contents were unavailable.
- Network destination and connection details were absent.
- The endpoint alert's contents and severity were not provided.
- No independent data source was available to corroborate the events.

Consequently, the investigation cannot confirm compromise, identify malware, establish data loss, or attribute activity to a particular threat actor.

## 10. Final Conclusion

The simulated dataset contains several events that merit additional investigation, particularly the unrecognised process start, temporary file creation, outbound network connection, and endpoint alert.

However, these observations do not independently establish a security incident, and their relationship has not been verified.

The appropriate conclusion is **inconclusive pending additional evidence**.

The investigation demonstrates a structured approach to evidence documentation, integrity checking, timeline reconstruction, preliminary artifact analysis, and evidence-based reporting.

## 11. Project Artifacts

- [Investigation scope](../scope/investigation-scope.md)
- [Evidence inventory](../evidence/evidence-inventory.csv)
- [Simulated event dataset](../evidence/simulated-events.csv)
- [SHA-256 hash manifest](../evidence/file-hashes.txt)
- [Investigation timeline](../analysis/investigation-timeline.csv)
- [Artifact analysis](../analysis/artifact-analysis.md)
