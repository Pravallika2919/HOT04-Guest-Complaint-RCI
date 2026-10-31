# Guest Complaint Root-Cause Intelligence

**Team TechNova | HackNow 2026 (ServiceNow and Accenture) | Problem HOT-04**

> A closed complaint is not a solved problem. We find the cause, so it is fixed once.

---

## The Problem

Hotels fix every guest complaint one by one, but never find out why the same problem keeps coming back. For example, four different guests report "AC not working" in the same room. Staff fix each one and close the ticket, and the real cause stays open.

Who it hurts:
- **Guests** face the same issue again.
- **Staff** repeat the same repair.
- **Managers** see how many complaints there are, not why.

---

## Our Solution

This solution finds the real cause of repeated guest complaints for hotels, by grouping similar complaints into one Problem that is fixed once.

It is built in **ServiceNow Customer Service Management (CSM)** using standard features and simple configuration.

**Our difference: innovation.** The system finds repeats on its own and uses AI to group similar complaints, so the team works on the cause and not only the symptom.

---

## How It Works

### End-to-End Workflow

![End-to-end workflow](images/workflow_01_end_to_end.png)

### Escalation (SLA Escalation Flow)

![Escalation workflow](images/workflow_02_escalation.png)

Each case gets a 4-hour "Complaint Resolution" SLA. If the case is not resolved, the flow raises the priority at 75%, notes the Department Head at 90%, and makes the case Critical with a Management note at 100%.

### From Repeat Complaints to Root Cause (Recurrence Detection and Corrective Action)

![Recurrence to root cause workflow](images/workflow_03_recurrence_to_root_cause.png)

When 3 or more similar complaints come from the same place within 30 days, the case gets a "Recurrence detected" note. AI groups similar complaints, they are linked to one Problem record, and the team confirms the cause and creates a corrective task.

---

## What Is Built in the ServiceNow Instance

| Area | What we built |
|---|---|
| Guest entry | Record Producer **"Raise a Complaint"** (problem, category, room, equipment, details) and a Virtual Agent chat topic |
| Hotel data | Property, floor, room and equipment structure linked to each case |
| Routing | 7 assignment rules, for example AC to Facilities, Cleanliness to Housekeeping, Noise to Front Desk |
| SLA | "Complaint Resolution" SLA of 4 hours |
| Escalation flow | At 75% priority goes up, at 90% a Department Head note, at 100% Critical and a Management note |
| Recurrence detection | Flow that adds "Recurrence detected" when 3 or more similar complaints come from the same place within 30 days |
| AI grouping | Predictive Intelligence Similarity and Clustering on complaint text |
| Root cause | Problem record (for example PRB0040002 with 4 linked cases) and a Create Corrective Action Task flow |
| Feedback | CSAT survey: a rating of 1 to 5 plus a comment |
| Dashboard | Platform Analytics dashboard "Guest Complaint Root-Cause Intelligence" |

---

## Demo

The demo shows one complaint from the first click to the result:

1. Guest raises a complaint (AC not working, Room 501).
2. Case is routed to Facilities and the 4-hour timer starts.
3. The case escalates by itself.
4. The repeat is detected.
5. One Problem is created with 4 linked cases.
6. The guest survey and the manager dashboard show the result.

### 🎬 Main Demo

▶️ **[DEMO serviceNOW.mp4](DEMO%20serviceNOW.mp4)** — Full end-to-end demo of the solution (26 MB)

### 📹 Additional Recordings

| Video | Description |
|---|---|
| [video.mp4](video%20recordings/video.mp4) | Extended demo recording |
| [video2.mp4](video%20recordings/video2.mp4) | Additional demo recording |
| [tab 6.mp4](video%20recordings/tab%206.mp4) | Tab 6 walkthrough |

Where to find the pages in the instance: **Customer Service > Cases > All**, **Problem > All**, **Platform Analytics**.

---

## Screenshots

All screenshots are from our ServiceNow instance during the demo.

### 1. Guest Raises a Complaint (Record Producer "Raise a Complaint")

![Raise a Complaint form](images/01_raise_complaint_form.png)

### 2. Case Created and Routed to Facilities

![Case created](images/02_case_created.png)

### 3. SLA Definition — "Complaint Resolution" (4 Hours)

![SLA definition – 4 hours](images/03_sla_4_hours.png)

### 4. Automatic Escalation Shown in Case Activities

![Escalation activities](images/04_escalation_activities.png)

### 5. "Recurrence Detected" Note on Case

![Recurrence detected](images/05_recurrence_detected.png)

### 6. AI Clustering of Complaints (Predictive Intelligence)

![AI clustering](images/06_ai_clustering.png)

### 7. Four AC Complaints Linked to One Problem (PRB0040002)

![Problem and linked cases](images/07_problem_prb0040002_cases.png)

### 8. Guest Survey Response (CSAT)

![Survey response](images/08_survey_response.png)

### 9. Assignment Rules

![Assignment rules](images/09_assignment_rules.png)

### 10. Manager Dashboard — Platform Analytics

![Dashboard](images/09_dashboard.png)

---

## Results (Demo Data)

These numbers come from our demo data, not from a live hotel.

- **4 complaints → 1 Problem:** 75% less repeat work.
- **27 complaints grouped into 3 clusters** by AI. One cluster is the Floor 5 AC problem.
- **40 complaints** on the manager dashboard. Equipment failure is the top cause, and AC units lead the equipment chart.

---

## Honest Scope

- The AI **groups** similar complaints. The team **confirms** the real cause on the Problem record.
- The dashboard is built with Platform Analytics.
- **Planned, not built yet:** QR code in every room, Integration Hub links to booking, housekeeping and food systems, email alerts, and a mobile app.

---

## What Comes Next

1. **Pilot in one hotel:** test with real complaints and get real numbers.
2. **Connect and extend:** link booking, housekeeping and food systems through Integration Hub, and add email alerts and a mobile app.
3. **Grow to many hotels:** extend property, floor and room to a hotel group, with a QR code in every room.

---

## Repository Contents

```
README.md                          This file
DEMO serviceNOW.mp4                ★ Main demo video (26 MB)
HOT04_Notes.txt                    Build notes (form, SLA, flow, dashboard, AI, business rule, custom fields)
TechNova_Presentation_12d.pptx     Final presentation deck
serivcenow_teamm_problem.pdf       ServiceNow team problem statement
sn_customerservice_case.xlsx       Case data export

images/
  01_raise_complaint_form.png      Guest complaint form (Record Producer)
  02_case_created.png              Case created and routed
  03_sla_4_hours.png               SLA definition (4-hour Complaint Resolution)
  04_escalation_activities.png     Automatic escalation in case activities
  05_recurrence_detected.png       Recurrence detected note on case
  06_ai_clustering.png             AI clustering (Predictive Intelligence)
  07_problem_prb0040002_cases.png  Problem record with 4 linked cases
  08_survey_response.png           CSAT survey response
  09_assignment_rules.png          Assignment rules configuration
  09_dashboard.png                 Manager dashboard (Platform Analytics)
  workflow_01_end_to_end.png       End-to-end workflow diagram
  workflow_02_escalation.png       Escalation workflow diagram
  workflow_03_recurrence_to_root_cause.png  Recurrence to root cause workflow diagram

video recordings/
  video.mp4                        Extended demo recording (129 MB)
  video2.mp4                       Additional demo recording (59 MB)
  tab 6.mp4                        Tab 6 walkthrough (4 MB)

workflows/
  01_end_to_end.mmd                Mermaid source – end-to-end workflow
  02_escalation.mmd                Mermaid source – escalation workflow
  03_recurrence_to_root_cause.mmd  Mermaid source – recurrence to root cause workflow
```

---

## How to Review

The ServiceNow instance used in the build phase is now deactivated, so the demo videos and screenshots show the working solution.

---

## Team TechNova

| Name | Role |
|---|---|
| B. Pravallika (Lead) | Team Lead and Solution Architect |
| K. Meghana | Process and UX Designer |
| K. Rahini | ServiceNow Developer |
| M. Samatha | Data and Analytics Lead |
| G. Hemanjali Bhavani | Integration and QA Engineer |
| S. Dhanush | Presentation and Documentation Lead |

---

## Acknowledgements

Thank you to Accenture and ServiceNow for organizing HackNow 2026, to our mentors for their guidance, and to the judges for their time.
