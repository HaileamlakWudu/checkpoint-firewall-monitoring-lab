

# Check Point Firewall Monitoring and Log Analysis
## Practical Assessment – README

### 1. Project Overview

This project documents the practical assessment of Check Point Firewall monitoring, logging, query analysis, event investigation, and audit verification.

The assessment covers two main areas:

- **Part A – Logging and Query Analysis**
- **Part B – Gateway Monitoring and Audit Evidence**

The practical work was performed using Check Point SmartConsole, SmartView Monitor, and SmartView Web.

The purpose of this assessment is to demonstrate the ability to review firewall logging configurations, use predefined and custom queries, interpret firewall events, monitor gateway health, and compare firewall logs with administrative audit records.

### 2. Assessment Tasks Completed

#### Part A – Logging and Query Analysis

| Task | Description |
|---|---|
| A1 | Reviewed logging and indexing configuration |
| A2 | Reviewed predefined queries and firewall rules |
| A3 | Created and tested custom queries |
| A4 | Interpreted a firewall event |

#### Part B – Monitoring and Audit Evidence

| Task | Description |
|---|---|
| B1 | Reviewed gateway status and system counters |
| B2 | Compared firewall event evidence with audit records |

### 3. Key Findings

#### 3.1 Firewall Event Investigation

One recorded event showed a Telnet connection attempt targeting the Check Point Security Gateway.

| Field | Recorded value |
|---|---|
| Date | November 15, 2026 |
| Time | 1:48:07 PM |
| Source hostname | droplet-mahaputra.id |
| Source IP | 188.166.223.22 |
| Destination | icdfa-r82-cluster2 |
| Destination IP | 172.17.1.11 |
| Service | Telnet |
| Protocol | TCP |
| Destination port | 23 |
| Policy name | Orion-Layers-cp |
| Access rule | Stealth Rule |
| Rule number | 2 |
| Action | Drop |

The event indicates that the Telnet connection attempt matched the Stealth Rule and was dropped by the firewall.

This confirms that the recorded attempt was blocked. The event alone does not establish the sender's identity or prove malicious intent.

#### 3.2 Gateway Monitoring

The monitored gateway was `icdfa-r82-cluster2`.

| Metric | Observed value |
|---|---|
| Gateway status | OK |
| Gateway IP | 172.17.1.11 |
| Version | R82 |
| Operating system | Gaia Kernel Version 4.18 |
| Uptime | 1 day and 8 hours |
| Working mode | High Availability (Active Up) |
| Member state | Standby |
| Warnings | None |
| Active real memory | 4,748.18 MB |
| Free real memory | 27,123.88 MB |
| Highest CPU total utilization | 44% on CPU 4 |
| Free space on `/var/log` | 79.82 GB |

The observed memory utilization was approximately 14.90%.

These values represent the monitoring snapshot captured during the assessment and should not be interpreted as proof of long-term gateway stability.

#### 3.3 Audit Record Comparison

The SmartView Web audit record showed:

| Field | Recorded value |
|---|---|
| Date | November 14, 2026 |
| Time | 9:55:52 PM |
| Administrator | c44-s772 |
| Object type | firewall_application |
| Performed on | icdfa-r82-cluster |
| Client IP | 10.42.7.4 |
| Operation | Policy Installation |
| Audit status | Success |

The audit record documents a successful policy installation. It is a separate record from the Telnet event, which occurred on November 15, 2026. The two records should not be treated as evidence that the policy installation directly caused the Telnet connection to be dropped.

### 4. Saved SmartConsole Query

The saved favorite query used during the custom-query assessment was:

`C44-s772-favorites`

This is the saved favorite name used in SmartConsole.

### 5. Project Evidence Structure

All screenshots are retained using their original filenames. The following folder structure is recommended for organizing the evidence.

```text
CheckPoint-Firewall-Assessment/
│
├── README.md
│
├── Report/
│   └── CheckPoint-Firewall-Assessment-Report.docx
│
└── Evidence/
    │
    ├── 01-Gateway-Logging/
    │   ├── E1-gwand servers.PNG
    │   ├── e2- gateways.PNG
    │   ├── e2- gateways-logs.PNG
    │   └── e2- gateways-logs-storage.PNG
    │
    ├── 02-SME-Logging/
    │   ├── e3-sme.PNG
    │   ├── e3-sme-logs.PNG
    │   └── e3-sme-logs-stroage.PNG
    │
    ├── 03-SMS-Logging/
    │   ├── e4-sms.PNG
    │   ├── e4-sms-logs.PNG
    │   └── e4-sms-logs-storage.PNG
    │
    ├── 04-Predefined-Queries/
    │   ├── e5-random-log.PNG
    │   ├── e5-random-log-access-rule.PNG
    │   ├── e5-random-log-predefine quary today.PNG
    │   └── e5-random-log-predefine with hour.PNG
    │
    ├── 05-Custom-Queries/
    │   ├── e6-log-top-source-services.PNG
    │   ├── e6-timezone-script.PNG
    │   ├── e7-ip quary accept.PNG
    │   ├── e7-ip quary drop.PNG
    │   └── e7-ip quary drop favorite.PNG
    │
    ├── 06-Firewall-Event/
    │   └── e8-random log.PNG
    │
    ├── 07-Gateway-Monitoring/
    │   ├── e9-smartview mon.PNG
    │   ├── e9-smartview mon-getway.PNG
    │   ├── e10-gW cluster.PNG
    │   └── e11-gW cluster2 cpu desk.PNG
    │
    └── 08-SmartView-Audit/
        ├── e12-Smartview.PNG
        ├── e13-Smartview-log.PNG
        └── e14-Smartview-audit-log.PNG
```

### 6. Evidence Reference

The evidence screenshots support the practical tasks as follows:

| Assessment task | Evidence |
|---|---|
| A1 – Logging and indexing configuration | Gateway, SME, and SMS logging screenshots |
| A2 – Predefined queries and firewall rules | `e5-random-log...` screenshots |
| A3 – Custom queries | `e6-...` and `e7-...` screenshots |
| A4 – Firewall event interpretation | `e8-random log.PNG` |
| A4 – Top Sources and Top Services | `e6-log-top-source-services.PNG` |
| B1 – Gateway monitoring | `e9-...`, `e10-...`, and `e11-...` screenshots |
| B2 – SmartView Web and audit evidence | `e12-...`, `e13-...`, and `e14-...` screenshots |


### 7. Conclusion

The practical assessment demonstrated the use of Check Point monitoring and logging tools to review gateway configurations, examine firewall events, build and test queries, monitor system counters, and inspect administrative audit records.

The recorded Telnet connection attempt was dropped by the Stealth Rule. The gateway monitoring snapshot showed an OK status with no reported warnings. The audit evidence also documented a successful policy installation by administrator `c44-s772`.

The screenshots and accompanying report provide supporting evidence for the completed assessment tasks.

**Note:** This README summarizes the work and its findings. The detailed report and original screenshots should be submitted together as the assessment evidence package.

