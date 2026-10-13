# HOT-04: Guest Complaint Root-Cause Intelligence

**Team TechNova** | Lead: B. Pravallika | HackNow 2026 (ServiceNow / Accenture)

Built on a ServiceNow lab instance using out-of-the-box Customer Service Management (CSM), Platform Analytics and Predictive Intelligence.

## Problem
Hotels log guest complaints, but repeat problems (for example a faulty AC on one floor) are handled one by one. Nobody sees the root cause behind them.

## What we built

| Area | What was built |
|---|---|
| Foundation data | Hotel account, 5 guest contacts, location tree (Floors 1-5, Restaurant, Room Service, Rooms), 7 teams (groups), configuration items (AC units, lift, kitchen chiller) |
| Case setup (CSM) | 7 complaint categories; custom fields **Root Cause** and **Floor**; business rule *Set Floor from Location* |
| Guest intake | Record Producer **Raise a Complaint** and a **Virtual Agent** topic (Raise a Complaint) both create a Case |
| Routing | 7 assignment rules (category to team), for example AC to Facilities, Cleanliness to Housekeeping |
| SLA | **Complaint Resolution** SLA, 4 hours, 24x7 |
| Escalation | Three tiers: **Complaint SLA Escalation** (75%, priority High), **Tier 3** (90%, Department Head work note), **Tier 4** (100%, priority Critical, Management work note) |
| Recurrence | Flow **Complaint Recurrence Detection**: 3 or more cases with the same category and location in 30 days sets priority High and adds a work note |
| AI | Predictive Intelligence **Similar Guest Complaints** (similarity, GloVe corpus) and **Guest Complaint Patterns** (clustering, 3 clusters) |
| Root cause | Problem record **PRB0040002** (recurring AC failure, Floor 5) linked to 4 cases, with cause, workaround and fix notes. Flow **Create Corrective Action Task** creates a Problem Task for Facilities when a Problem is created |
| Dashboard | **Guest Complaint Root-Cause Intelligence**: 7 charts: complaints by root cause, floor, equipment, department, category, total, and complaints over time |
| CSAT | Survey **Guest Complaint Resolution CSAT** (1-5 rating plus comment), triggered when a Case is Closed or Resolved |

## Key finding in the demo data
Equipment failure is the top root cause, concentrated in **AC Unit - Room 501 (Floor 5)**. The Problem record captures this, with a recommended preventive-maintenance fix.

## Repository contents
- `screenshots/` : numbered screenshots 01-35 of every component (21-35 show tiered escalation, recurrence detection, corrective-action task, Virtual Agent, the 7-chart dashboard and the management case)
- `data/` : Cases export (sn_customerservice_case.xlsx)
- `docs/` : idea submission document
- Demo video link: (add link here)

## Differences from the idea document (stated honestly)
- **Performance Analytics** is not available on this instance. Analytics run on Platform Analytics dashboards, including a trend chart.
- **Integration Hub** connections to hotel systems (PMS, Housekeeping, F&B) are mocked for the hackathon, as stated in the idea document. Real connections are a production step.
- **Mobile Agent App** is a production step and is not part of this demo.
- **Escalated cases** get a higher priority and a work note for the Supervisor, Department Head and Management. Management sees every case on the dashboard. A "Hotel Management" group and a Critical demo case assigned to it show the management view. Automatic reassignment to a management group is a next step.

## Notes
Data is demo data created for the hackathon. Some components (trained AI models, dashboards, survey responses) may not move with an update set, so the screenshots and demo video are the main proof.
