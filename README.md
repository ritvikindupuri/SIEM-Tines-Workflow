# Elastic Security SIEM & Automated Incident Response (Elastic + Tines)

A compact, production-safe demo of a **real-time detection → SOAR triage → email alerting** pipeline.  
It ingests Windows security events with **Elastic Agent (Defend)**, detects **admin-privileged logons** (Win Event **4672**), fires a webhook into **Tines**, auto-summarizes the incident with AI, and notifies analysts by email.



---

## ✨ Highlights

- **End-to-end pipeline:** Windows VM → Elastic Agent → Elastic Security (SIEM/EDR) → Tines SOAR → Email.
- **Detections that matter:** Custom rule for **event.code / winlog.event_id = 4672** (“Special privileges assigned to new logon”) to flag admin-level sessions.
- **Automated triage:** Tines story receives the alert, summarizes key fields, and sends formatted email notifications.
- **Dashboards:** Logon activity visuals (admin vs. non-admin, RDP, logon type, timelines).
- **Scale-minded:** Alert volume control (severity/risk score/thresholds) to prevent fatigue and keep demo safe.

---

## 🏗️ System Architecture

<img width="800" height="345" alt="image" src="https://github.com/user-attachments/assets/8f7a4fb0-929d-4331-893e-27f80861f2fa" />

**Flow:**
1) Windows VM generates events →  
2) **Elastic Agent (Defend)** ships telemetry →  
3) **Elastic Security** correlates + detects →  
4) Detection action sends **webhook** →  
5) **Tines** summarizes + **emails** the incident.

---

## ✅ Quick Start (15–30 min)

### Prerequisites
- Elastic Stack 8.x (Elastic Cloud or local) with **Elastic Security**.
- A **Windows 10/11 VM** (local, lab, or cloud) with admin access.
- **Elastic Agent** installed on Windows VM (policy includes **Elastic Defend** + Windows Event Log).
- **Tines** tenant (free trial is fine) and an **email** integration (SMTP/Gmail, etc.).


Explore the full architecture, setup steps, and automation logic in the file: Elastic Security SIEM & Automated Incident Response Project.
---
