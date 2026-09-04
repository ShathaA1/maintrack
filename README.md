<div align="center">

# MainTrack

<img src="MainTrack%20Logo.png" alt="MainTrack Logo" width="300"/>

### Smart Maintenance Tracking System

A centralized maintenance management system designed to streamline facility  
maintenance requests, technician assignment, real-time tracking, and operational monitoring.

</div>

---

## Table of Contents

- [Overview](#overview)
- [Key Features](#key-features)
- [System Architecture](#system-architecture)
- [Microservice Architecture](#microservice-architecture)
- [Domain-Driven Design](#domain-driven-design)
- [Main Workflow](#main-workflow)
- [User Roles](#user-roles)
- [Quality Attributes](#quality-attributes)
- [Testing](#testing)
- [Future Improvements](#future-improvements)
- [Project Team](#project-team)

---

## Overview

**MainTrack** is a smart maintenance tracking platform designed for universities
and large facilities.

It provides a centralized workflow for submitting maintenance requests,
automatically assigning technicians, monitoring request progress, integrating
IoT-based fault detection, and providing administrators with operational
dashboards and reports.

The system is designed to reduce maintenance delays, improve communication and
accountability, and provide better visibility into maintenance operations.

---

## Key Features

- **Maintenance Request Management** — Submit, edit, cancel, and track maintenance requests.
- **Automatic Technician Assignment** — Assign technicians based on priority, workload, availability, specialization, and location.
- **Real-Time Tracking** — Monitor request status and receive updates as maintenance work progresses.
- **IoT Fault Detection** — Receive sensor alerts and convert detected faults into maintenance requests.
- **Role-Based Access** — Separate functionality for requesters, technicians, and administrators.
- **Notifications** — Notify users when maintenance request statuses change.
- **Administrative Dashboard** — Monitor requests, users, technician performance, and operational statistics.
- **Reports & Analytics** — Analyze response times, resolution rates, requests, and technician performance.

---

## System Architecture

MainTrack follows a layered client-server architecture that separates the system
into four main layers:

```text
┌─────────────────────────────────────┐
│         Presentation Layer          │
│ Users • Technicians • Administrators│
└──────────────────┬──────────────────┘
                   │
┌──────────────────▼──────────────────┐
│       Application Processing        │
│     Business Logic & Workflows      │
└──────────────────┬──────────────────┘
                   │
┌──────────────────▼──────────────────┐
│          Data Management            │
│     Data Access & Organization      │
└──────────────────┬──────────────────┘
                   │
┌──────────────────▼──────────────────┐
│           Database Layer            │
│ Users • Requests • Logs • Reports   │
└─────────────────────────────────────┘
```

The architecture separates system responsibilities to support organization,
scalability, and maintainability.

---

## Microservice Architecture

MainTrack is structured around specialized services with clearly defined
responsibilities.

| Service | Responsibility |
|---|---|
| **User Management** | Registration, authentication, email verification, and profile management |
| **Request Management** | Creating, updating, and tracking maintenance requests |
| **Technician Management** | Technician assignment based on priority, availability, and workload |
| **Notification** | Sending maintenance request status notifications |
| **Analytics & Reporting** | Generating reports and maintenance analytics |
| **IoT Integration** | Processing fault information received from IoT sensors |

<p align="center">
  <img src="microservice-architecture.png" alt="MainTrack Microservice Architecture" width="750"/>
</p>

---

## Domain-Driven Design

MainTrack applies **Domain-Driven Design (DDD)** to organize the system around
the smart maintenance management domain.

The core domain covers:

- Receiving and managing maintenance requests
- Prioritizing maintenance issues
- Assigning technicians
- Tracking repair progress
- Processing IoT-detected faults
- Sending notifications
- Monitoring maintenance performance

### Bounded Contexts

`Request Management` · `Technician Management` · `User Management` ·
`IoT Monitoring` · `Notification` · `Reporting`

The `MaintenanceRequest` represents the main aggregate and acts as the
aggregate root.

---

## Main Workflow

```text
User
  │
  ▼
Submit Maintenance Request
  │
  ▼
Validate Request
  │
  ▼
Store Request
  │
  ▼
Evaluate Priority
  │
  ▼
Assign Technician
  │
  ▼
Technician Updates Status
  │
  ▼
Send Notification
  │
  ▼
User Tracks Request
```

For IoT-detected faults, sensor information can enter the workflow
automatically and be converted into a maintenance request.

---

## User Roles

### Requester
Submit and manage maintenance requests, track their status and history, and
receive notifications.

### Technician
Access assigned maintenance requests, handle maintenance tasks, and update
request status.

### Administrator
Manage users, monitor maintenance operations, access dashboards and reports,
and monitor IoT alerts.

---

## Quality Attributes

MainTrack was designed with several non-functional requirements in mind:

- **Performance** — Responsive handling of user requests
- **Scalability** — Support for large numbers of simultaneous maintenance requests
- **Security** — Secure authentication and role-based access control
- **Reliability** — Continued operation when IoT communication is unavailable
- **Usability** — Arabic and English interface support
- **Maintainability** — Structured and separated system responsibilities
- **Availability** — High availability during normal operating periods
- **Backup & Recovery** — Support for regular backups and data recovery

---

## Testing

The project considers multiple levels of software testing:

`Unit Testing` · `Integration Testing` · `System Testing` ·
`Black-Box Testing` · `White-Box Testing`

Testing covers key workflows such as authentication, request management,
technician assignment, notifications, and IoT integration.

---

## Future Improvements

Potential extensions include:

- Predictive maintenance
- AI-based fault analysis
- Expanded IoT integration
- Procurement and inventory system integration
- Support for additional facilities and organizations

---

## Project Team

| Team Member |
|---|
| Sarah Algarni |
| Lujain Alqarni |
| **Shatha Alshaikh** |

MainTrack was developed collaboratively as a software engineering academic project.

---

<div align="center">

**MainTrack — Making maintenance operations more structured, visible, and efficient.**

</div>

