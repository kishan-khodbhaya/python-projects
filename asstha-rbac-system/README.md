# Asstha — Enterprise Project Management & Document Workflow System

> End-to-end project tracking, multi-department document routing, performance reporting, and Windows utility suite — built and deployed for a government-adjacent surveying and design organization.

![Python](https://img.shields.io/badge/Python-Backend-green)
![Flask](https://img.shields.io/badge/Flask-API-black)
![MySQL](https://img.shields.io/badge/MySQL-Database-blue)
![Jenkins](https://img.shields.io/badge/Jenkins-CI%2FCD-red)
![Status](https://img.shields.io/badge/Status-Production-brightgreen)

---

## Overview

Asstha is the most comprehensive system I have built. It covers backend API design, database architecture, project management, Windows desktop application development, server deployment, and CI/CD setup — all for a single client over an 8-month engagement.

The system manages the complete lifecycle of surveying and design projects across four departments, tracking every task, sub-task, department handoff, and document routing step — with real-time notifications, performance reports, and multi-format exports at every level.

---

## Problem Solved

The organization managed 40-50 active projects simultaneously, each with 80-90 tasks, some with 10-15 sub-tasks per task. Projects moved between four departments — Surveying, Design, Data Operations, and Admin — with a formal document routing process involving Circle, Division, Sub-Division, and Taluka levels for signature approval.

All of this was tracked manually. There was no visibility into task status, department performance, or document routing stage. Missed deadlines and lost documents were regular problems.

Asstha replaced the entire manual process with a tracked, notified, reportable system.

---

## System Architecture

```
Four Departments:
Surveying → Design → Data Operations → Admin

Document Flow:
Raw document (Survey) → Designed document (Design)
→ Circle → Division → Sub-Division → Taluka (signatures)
→ Return path if rejected (back to originating department)

Project Tracking:
Project assigned to department
→ Department HR assigns tasks to employees
→ Employee marks task complete
→ All sub-tasks complete → task complete
→ All tasks complete → project moves to next department
→ Every event logged → all stakeholders notified
```

### Roles and Access

| Role | Permissions |
|------|-------------|
| Admin | Full system access, user management, all reports |
| HOD (Head of Department) | Department projects, task assignment, department reports |
| Data Operator | Project creation, task updates, routing management |
| HR | Task assignment to employees within department |
| Employee | Own task view, task completion marking |
| Surveyor | Raw document upload, survey-specific workflows |

---

## Backend — API and Database

### What Was Built
- Complete REST API suite with RBAC at every endpoint
- Department management APIs
- Project lifecycle APIs — creation, assignment, stage progression
- Task and sub-task management with completion tracking
- Real-time notification triggers on every state change
- Document routing APIs — Circle, Division, Sub-Division, Taluka flows
- Return path logic — rejected documents routed back to originating department

### Performance Reporting APIs
- **Employee reports** — tasks assigned, completed on time, completed late
- **Department reports** — project throughput, task completion rates, efficiency metrics
- **Project reports** — full lifecycle timeline, stage durations
- **Geographic reports** — Circle, Division, Sub-Division, Taluka level breakdowns
- **Custom time frame** — all reports filterable by date range
- **Combined views** — Circle + Department combination reports
- **Export formats** — PDF, Excel, CSV for every report type
- **Visualization** — Pie chart and table format for all reports

### Database Design
- Fully normalized schema supporting 40-50 concurrent projects with 80-90 tasks each
- Optimized queries for real-time dashboard loading
- Foreign key relationships enforcing department and project integrity
- Indexed for frequent report generation queries

---

## Windows Desktop Applications

Four standalone Python desktop applications built for the same project:

### App 1 — Excel to PDF Converter
Converts formatted Excel sheets to structured PDF documents for submission and archiving.

### App 2 — Document Merger
Merges multiple Excel files and PDF documents into a single consolidated file — used for combining survey data from multiple sources.

### App 3 — Survey Document Builder
Creates formal survey department documents using images only — field surveyors capture images; this app formats them into the required document structure.

### App 4 — Multi-Sheet Excel Builder
Generates Excel workbooks with multiple structured sheets from input data — used for data operations reporting.

### VBA Macro Suite
Several VBA macros built for the same project:
- Sheet cleaning and validation macros
- Data aggregation across multiple sheets
- Sheet summarization using Google Gemini API
- Data integrity validation with error flagging

---

## Project Management

Alongside development, I managed the full project lifecycle for 8 months:
- Client meetings and requirement gathering
- Timeline planning and milestone tracking
- Frontend team coordination
- Sprint planning and delivery management
- Client presentation of system features at multiple review stages
- Deployment planning and go-live coordination

---

## Deployment

Two in-house Ubuntu servers configured and deployed:

- **Remote access** — servers accessible from anywhere via configured tunnels
- **File transfer** — Windows-to-Ubuntu file system integration for easy uploads
- **Terminal access** — secure remote terminal access configured
- **Failsafe** — server recovery configured for unexpected shutdowns
- **CI/CD** — Jenkins configured for automatic deployment on each commit
- **Reverse proxy** — Nginx configured for routing and SSL termination
- **Real-time communication** — RTC configured for live system features
- **File sharing** — Samba configured for controlled Windows-Ubuntu file sharing
- **Cloudflare Tunnel** — external access secured via Cloudflare

---

## Tech Stack

| Component | Technology |
|-----------|-----------|
| Language | Python |
| API Framework | Flask |
| Database | MySQL |
| Authentication | JWT with RBAC |
| Desktop UI | Tkinter |
| Spreadsheet Automation | Excel, VBA, openpyxl |
| AI Integration | Google Gemini API (VBA macros) |
| CI/CD | Jenkins |
| Deployment | Ubuntu, Gunicorn, Nginx |
| Tunneling | Cloudflare Tunnel |
| File Sharing | Samba |

---

## Results

- Complete replacement of manual project tracking for 40-50 simultaneous projects
- Real-time visibility into task status across all departments and employees
- Document routing process formalized and tracked — no more lost documents
- Performance reports available on demand at employee, department, and project level
- 8-month project delivered and in active production use
- Star Performer of the Year 2024 award received during this project


<!-- ## Demo -->

<!-- Add system dashboard screenshot here -->
<!-- Add project tracking view screenshot here -->
<!-- Add report export screenshot here -->
<!-- Add Windows app screenshot here -->
<!-- Add demo video link here -->

---

> **Note:** Source code is proprietary (built for VedikIn Solutions / client). This is the project I am most proud of and most prepared to walk through in detail. Full code and system walkthrough available during interview process.
