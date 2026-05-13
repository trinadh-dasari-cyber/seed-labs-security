# 🔎 Splunk Log Analysis & Threat Hunting

**Academic project — SIEM log analysis and threat hunting using Splunk as part of MS Cybersecurity coursework at University of Central Missouri**

---

## Overview

This project was completed as part of my MS Cybersecurity program at the University of Central Missouri. I ingested and analyzed Windows and Linux logs in Splunk, built SPL correlation searches targeting known attack patterns, and produced structured threat hunting reports mapped to MITRE ATT&CK — simulating real-world SOC analyst workflows.

---

## Academic Context

- **Institution:** University of Central Missouri
- **Program:** MS Cybersecurity
- **Focus:** SIEM engineering, threat detection, log analysis

---

## Log Sources Used

- **Windows Security Logs** — Event IDs: 4624, 4625, 4648, 4672, 4688
- **Linux Syslogs** — Auth failures, sudo usage, cron activity

---

## What Was Done

### Log Ingestion & Normalization
- Ingested Windows Security event logs and Linux syslogs into Splunk
- Configured index management and sourcetype parsing for consistent log structure
- Normalized field names for cross-source correlation

### SPL Correlation Searches Built

**Brute-force detection — 10+ failed logins in 5 minutes:**

    index=windows EventCode=4625
    | bin _time span=5m
    | stats count as FailCount by src_ip, user, _time
    | where FailCount > 10

**Privilege escalation — account added to admin group:**

    index=windows EventCode=4728 OR EventCode=4732
    | table _time, src_user, user, Group_Name, host

**Lateral movement — unusual remote login pattern:**

    index=windows EventCode=4624 Logon_Type=3
    | stats dc(host) as UniqueHosts by user
    | where UniqueHosts > 3

### Real-Time Alerting
- Configured alerts for brute-force attempts, privilege escalation sequences, and lateral movement
- Applied alert throttling to reduce noise on high-volume log sources

### Threat Hunting Reports
- Investigated flagged events and reconstructed attack timelines
- Mapped findings to MITRE ATT&CK tactics and techniques
- Produced structured hunting reports aligned to SOC analytical workflows

---

## What I Learned

- How enterprise SIEM platforms ingest and normalize multi-source log data
- How to write SPL searches that detect real attack patterns
- How SOC analysts think through lateral movement and privilege escalation scenarios
- How MITRE ATT&CK maps to actual log events and detection logic

---

## MITRE ATT&CK Coverage

- **T1110** — Brute Force (Credential Access) → Failed login correlation
- **T1078** — Valid Accounts (Privilege Escalation) → Admin group membership changes
- **T1021** — Remote Services (Lateral Movement) → Cross-host login analysis

---

## Skills Demonstrated

`Splunk` `SPL` `Log Analysis` `Threat Hunting` `MITRE ATT&CK` `SIEM Engineering` `Windows Event Logs` `Linux Syslog` `Incident Response`
