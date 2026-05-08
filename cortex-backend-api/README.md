# Cortex — Full-Stack Backend API System

> Complete backend infrastructure for a live mobile application and admin panel — built from scratch including database design, API architecture, authentication, PDF generation, and deployment.

![Python](https://img.shields.io/badge/Python-Flask-green)
![MySQL](https://img.shields.io/badge/MySQL-Database-blue)
![JWT](https://img.shields.io/badge/JWT-Authentication-orange)
![Status](https://img.shields.io/badge/Status-Production-brightgreen)

---

## Overview

Cortex is the first full production system I designed and built end-to-end. It powers a live mobile application and a web-based admin panel, handling all business logic, data operations, authentication, PDF generation, certificate creation, and email delivery through a structured REST API suite.

This was built from zero — no existing codebase, no inherited schema. Database design, API architecture, security model, and deployment were all designed from scratch.

---

## Problem Solved

The client needed a backend that could support both a mobile app and an admin panel simultaneously, with different access levels, document generation, and communication features — all running reliably in production.

---

## System Architecture

```
Mobile App  ←→  REST API (Flask)  ←→  MySQL Database
Admin Panel ←→  REST API (Flask)  ←→  MySQL Database
                      ↓
              ┌───────────────┐
              │  Utilities     │
              │  - PDF Gen     │
              │  - Cert Gen    │
              │  - Email SMTP  │
              │  - OTP System  │
              └───────────────┘
```

### Folder Structure

```
cortex/
├── controllers/     # Business logic layer
├── models/          # Database models and queries
├── routes/          # API endpoint definitions
├── utils/           # Shared utilities (PDF, email, templates)
├── config/          # Environment and DB connection
└── app.py           # Application entry point
```

---

## Features

### Core API Modules
- **CRUD operations** across all core business entities
- **User management** — registration, login, profile, password reset
- **OTP system** — time-based OTP generation and verification
- **Password reset links** — secure token-based reset flow with expiry
- **Session management** via JWT tokens (24-hour validity)

### Document Generation
- **Custom PDF generation** — PDFs with images, tables, and dynamic content using PDFKit
- **Report generation** — data reports exportable as formatted PDFs
- **Certificate generation** — automated certificate creation with custom templates

### Question and Assessment System
- API for delivering questions based on custom environment configuration
- Custom answer options per question type
- Result evaluation and scoring logic

### Admin Panel APIs
- Separate admin endpoint set with elevated privileges
- User management, data oversight, and system configuration
- Role-scoped access enforced via JWT claims

### Security
- JWT token authentication — all endpoints protected
- AES + Base64 for password hashing
- Privilege-based access — mobile vs admin scoped at token level
- Input validation and sanitized queries throughout

---

## Tech Stack

| Component | Technology |
|-----------|-----------|
| Language | Python |
| Framework | Flask |
| Database | MySQL |
| Authentication | JWT (24-hour tokens) |
| Password Security | AES + Base64 hashing |
| PDF Generation | PDFKit |
| Email | SMTP |
| Architecture | MVC (Controller / Model / Route) |
| Deployment | Gunicorn + Nginx + Ubuntu |

---

## API Design

- 20+ endpoint modules across mobile and admin
- RESTful conventions throughout
- Consistent response structure: `{status, message, data, error}`
- Structured exception handling with HTTP status codes
- Full API documentation delivered with the system:
  - Endpoint definitions
  - Request/response formats
  - Error codes and messages
  - Exception handling flows

---

## Database Design

- Fully normalized relational schema designed from scratch
- Advanced SQL JOINs for related data retrieval
- Indexed columns for frequently queried fields
- Query performance optimized — ~40% improvement via indexing and refactoring
- Foreign key constraints enforcing data integrity

---

## Deployment

- Deployed on Ubuntu server
- Gunicorn as WSGI application server
- Nginx as reverse proxy
- Environment variables for all secrets — no hardcoded credentials
- Process managed via systemd for automatic restart on failure

---

## Results

- 20+ API endpoints supporting live mobile app in production
- Zero downtime deployment maintained throughout client use
- Full documentation delivered alongside the system
- Reusable utils folder (PDF, email, templates) used across subsequent projects


<!-- ## Demo -->

<!-- Add API response screenshot here -->
<!-- Add Postman collection screenshot here -->
<!-- Add architecture diagram here -->

---

> **Note:** Source code is proprietary (built for VedikIn Solutions). Full code walkthrough available during interview process.
