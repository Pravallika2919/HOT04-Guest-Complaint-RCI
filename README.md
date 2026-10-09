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
| Guest intake | Record Producer **Raise a Complaint** creates a Case |
| Routing | 7 assignment rules (category to team), for example AC to Facilities, Cleanliness to Housekeeping |
| SLA | **Complaint Resolution** SLA, 4 hours, 24x7 |
| Escalation | Flow **Complaint SLA Escalation**: at 75% of the SLA the case priority is raised to High and a work note is added |
| AI | Predictive Intelligence **Similar Guest Complaints** (similarity, GloVe corpus) and **Guest Complaint Patterns** (clustering, 3 clusters) |
| Root cause | Problem record **PRB0040002** (recurring AC failure, Floor 5) linked to 4 cases, with cause, workaround and fix notes |
| Dashboard | **Guest Complaint Root-Cause Intelligence**: complaints by root cause, floor, equipment, department, category, and total |
| CSAT | Survey **Guest Complaint Resolution CSAT** (1-5 rating plus comment), triggered when a Case is Closed or Resolved |

## Key finding in the demo data
Equipment failure is the top root cause, concentrated in **AC Unit - Room 501 (Floor 5)**. The Problem record captures this, with a recommended preventive-maintenance fix.

## Repository contents
- `screenshots/` : numbered screenshots 01-20 of every component
- `data/` : Cases export (sn_customerservice_case.xlsx)
- `HOT04_Notes.txt` : names of everything built
- Demo video link: (add link here)

## Next phase (not built yet)
- Virtual Agent for guest intake
- Performance Analytics trends
- Multi-level escalation (department head, general manager)
- Automatic corrective-action tasks on Problem records
- Recurrence rule (for example 3 similar complaints in 30 days opens a Problem)

## Notes
Data is demo data created for the hackathon. Some components (trained AI models, dashboards, survey responses) may not move with an update set, so the screenshots and demo video are the main proof.
