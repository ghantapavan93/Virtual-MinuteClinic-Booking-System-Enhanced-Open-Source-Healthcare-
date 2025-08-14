# Virtual-MinuteClinic-Booking-System-Enhanced-Open-Source-Healthcare-
# Virtual MinuteClinic Booking System
**Secure Appointment & Patient Data Platform** · _In Progress_

<p align="center">
  <a href="#"><img alt="Status" src="https://img.shields.io/badge/status-in_progress-blue"></a>
  <a href="#"><img alt="CI" src="https://img.shields.io/badge/CI-GitHub_Actions-2088FF?logo=githubactions&logoColor=white"></a>
  <a href="#"><img alt="Security" src="https://img.shields.io/badge/Security-HIPAA_aligned-blueviolet"></a>
  <a href="#"><img alt="Observability" src="https://img.shields.io/badge/Observability-OpenTelemetry%20%7C%20Prometheus%20%7C%20Grafana-green"></a>
  <a href="LICENSE"><img alt="License: MIT" src="https://img.shields.io/badge/License-MIT-black.svg"></a>
</p>

> **Executive Summary**  
> A production-minded, HIPAA-aligned virtual clinic booking platform that mirrors real retail-healthcare operations: **patient onboarding**, **identity & consent**, **slot discovery**, **booking**, **reminders**, **telehealth session bootstrap**, and **complete auditability**. Built with resilient microservices, **FHIR-aware** data models, **event-driven** patterns, and **end-to-end observability**.

---

## Why This Project
Retail clinics thrive on **instant, reliable, and secure scheduling**. Getting a patient from “I need care” to a confirmed visit in seconds requires:
- **Clean data ingestion** from disparate sources (internal schedules, CSVs, partner APIs).
- **Conflict-free booking** with holds, idempotency, and safe retry semantics.
- **Explicit consent & auditable trails** for PHI handling and compliance reporting.
- **Operational excellence**: metrics, tracing, alerts, runbooks, and sensible SLOs.

---

## Business Outcomes
- **↓ Booking abandonment** via sub-second slot search and **< 300 ms** booking confirmation (p95).
- **↑ Utilization** with smart holds, waitlists, no-show-aware rescheduling (roadmap).
- **↓ Support load** with clear audit trails, deterministic idempotency, and structured errors.
- **Compliance readiness signals** (RBAC, audit, encryption, retention), reducing go-to-market risk.

---

## Clinical Workflows Covered
- **Pre-registration & Identity**: email/OTP, OAuth, minimal PI capture, consent collection.  
- **Slot Discovery & Holds**: availability rules, optimistic locking, redis-backed holds.  
- **Booking & Confirmation**: idempotent creates; rollback/compensating actions on failure.  
- **Reminders & Telehealth Bootstrap**: notification events; join-link generation.  
- **Post-Visit Events (stub)**: cancellation, rebook, provider handoffs, discharge summary hooks.

> 🧭 **At a glance**  
> **Onboard** (email/OTP) → **Consent** (audit trail) → **Discover Slots** (rules + holds) →  
> **Book** (idempotent, outbox → Kafka) → **Remind** (events) → **Telehealth** (join link)

---

## Key Features

<p align="center">
  <!-- Inline SVG icons so no separate folder is needed -->
  <!-- Booking -->
  <svg xmlns="http://www.w3.org/2000/svg" width="28" height="28" fill="none" stroke="#0ea5e9" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round"><rect x="3" y="4" width="18" height="17" rx="2"/><line x1="8" y1="2.5" x2="8" y2="6"/><line x1="16" y1="2.5" x2="16" y2="6"/><line x1="3" y1="9" x2="21" y2="9"/><polyline points="8,14 11,17 16,12"/></svg>
  &nbsp;&nbsp;Idempotent Booking&nbsp;&nbsp;&nbsp;&nbsp;
  <!-- Consent -->
  <svg xmlns="http://www.w3.org/2000/svg" width="28" height="28" fill="none" stroke="#22c55e" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round"><path d="M7 3h7l5 5v11a2 2 0 0 1-2 2H7a2 2 0 0 1-2-2V5a2 2 0 0 1 2-2z"/><polyline points="9,14 11,16 15,12"/><line x1="9" y1="8" x2="12" y2="8"/></svg>
  &nbsp;&nbsp;Consent & Audit&nbsp;&nbsp;&nbsp;&nbsp;
  <!-- Security -->
  <svg xmlns="http://www.w3.org/2000/svg" width="28" height="28" fill="none" stroke="#8b5cf6" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round"><path d="M12 3l8 4v5c0 5-3.5 8-8 9-4.5-1-8-4-8-9V7l8-4z"/><rect x="9" y="11" width="6" height="5" rx="1.5"/><path d="M12 11v-1.5a2 2 0 1 1 4 0V11"/></svg>
  &nbsp;&nbsp;HIPAA-aligned Security&nbsp;&nbsp;&nbsp;&nbsp;
  <!-- Observability -->
  <svg xmlns="http://www.w3.org/2000/svg" width="28" height="28" fill="none" stroke="#f59e0b" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round"><path d="M2 12s4-7 10-7 10 7 10 7-4 7-10 7S2 12 2 12z"/><circle cx="12" cy="12" r="3"/></svg>
  &nbsp;&nbsp;OTel Observability&nbsp;&nbsp;&nbsp;&nbsp;
  <!-- FHIR -->
  <svg xmlns="http://www.w3.org/2000/svg" width="28" height="28" fill="none" stroke="#ef4444" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round"><path d="M12 2c2 3 4 4 4 7a4 4 0 1 1-8 0c0-2 2-4 4-7z"/><path d="M8 14c0 3 2 6 4 8 2-2 4-5 4-8a4 4 0 0 0-8 0z"/></svg>
  &nbsp;&nbsp;FHIR-aware Models
</p>

- **Secure Patient Onboarding** – consent receipts, immutable audit logs.  
- **Slot Discovery & Booking** – idempotency keys, optimistic locking, rollback safety.  
- **Multi-Source ETL/ELT** – APIs/CSV/internal sources → SQL + NoSQL, schema validation.  
- **Microservices** – FastAPI gateway, Spring Boot scheduler, async orchestrator, Kafka bus.  
- **Performance** – **sub-300 ms** booking confirmations at peak (p95).  
- **Observability** – OpenTelemetry traces, Prometheus metrics, Grafana dashboards, structured logs.  
- **HIPAA Alignment** – RBAC, encryption, PII/PHI minimization, retention policies.  
- **IaC** – Docker Compose, Kubernetes manifests, GitHub Actions CI/CD.

---

## Tech Stack

<p align="center">
  <a href="#"><img alt="FastAPI" src="https://img.shields.io/badge/FastAPI-0.111-009485?logo=fastapi&logoColor=white"></a>
  <a href="#"><img alt="Spring Boot" src="https://img.shields.io/badge/Spring_Boot-3.x-6DB33F?logo=springboot&logoColor=white"></a>
  <a href="#"><img alt="PostgreSQL" src="https://img.shields.io/badge/PostgreSQL-16-4169E1?logo=postgresql&logoColor=white"></a>
  <a href="#"><img alt="MongoDB" src="https://img.shields.io/badge/MongoDB-6.x-47A248?logo=mongodb&logoColor=white"></a>
  <a href="#"><img alt="Kafka" src="https://img.shields.io/badge/Kafka-3.x-231F20?logo=apachekafka&logoColor=white"></a>
  <a href="#"><img alt="OpenTelemetry" src="https://img.shields.io/badge/OpenTelemetry-1.x-000000?logo=opentelemetry&logoColor=white"></a>
  <a href="#"><img alt="Kubernetes" src="https://img.shields.io/badge/Kubernetes-1.30-326CE5?logo=kubernetes&logoColor=white"></a>
  <a href="#"><img alt="GitHub Actions" src="https://img.shields.io/badge/GitHub_Actions-CI-2088FF?logo=githubactions&logoColor=white"></a>
</p>

| Layer | Technologies |
|-------|--------------|
| API Gateway | FastAPI, Pydantic, Uvicorn, rate limiting |
| Scheduling | Spring Boot (Java 17), Spring Data |
| Datastores | PostgreSQL, MongoDB, Redis |
| Messaging | Kafka / Redpanda |
| Observability | OpenTelemetry, OTel Collector, Prometheus, Grafana, Jaeger/Tempo |
| Infra & CI/CD | Docker, Kubernetes, Helm, GitHub Actions |
| Standards | FHIR-aware models, JSON Schema, Avro |

---

## Architecture Overview
<!-- PLACEHOLDER for diagram --> 
`[ <img width="3840" height="1093" alt="Untitled diagram _ Mermaid Chart-2025-08-14-223036" src="https://github.com/user-attachments/assets/4dc1f54d-bdd3-4312-b3e7-ff5aeca60756" />]`
---

## Booking Workflow
<!-- PLACEHOLDER for diagram -->
`[ <img width="3840" height="1827" alt="Untitled diagram _ Mermaid Chart-2025-08-14-221406" src="https://github.com/user-attachments/assets/1101b862-7b5d-4051-bc52-336a089b3c0a" /> ]`
---

## ETL / ELT Data Flow
<!-- PLACEHOLDER for diagram -->
`[ <img width="3840" height="300" alt="Untitled diagram _ Mermaid Chart-2025-08-14-223147" src="https://github.com/user-attachments/assets/a3fc73e6-3002-4cf4-8ffa-a4c7aa865351" />]`
---

## UI & Ops Gallery
<!-- PLACEHOLDER for screenshots -->
`[ Screenshots will be placed here ]`

---
### 🖥️ Patient & Provider Web UI
| Patient Appointment Flow | Provider Slot Management |
|--------------------------|--------------------------|
| ![Patient Flow](docs/ui/patient-flow.png) | ![Provider Slots](docs/ui/provider-slots.png) |

---

### 📊 Operational Dashboards
| Booking Metrics (Grafana) | Trace View (Jaeger) |
|---------------------------|---------------------|
| ![Metrics Dashboard](docs/ops/grafana-booking-metrics.png) | ![Trace View](docs/ops/jaeger-trace.png) |

---

### 📦 ETL & Data Quality
| ETL Job Status (Airflow) | Data Validation Results |
|--------------------------|-------------------------|
| ![ETL Jobs](docs/ops/etl-jobs.png) | ![Data Validation](docs/ops/data-validation.png) |

---

## Security, Privacy & Compliance
- JWT-scoped RBAC; mTLS between services.
- Field-level encryption for PHI.
- Structured logs exclude PHI.
- Append-only Kafka audit streams.
- Configurable PHI retention + archival.

---

## Performance, SLOs & Observability
| Endpoint | SLO (p95) | Error Budget |
|---|---:|---:|
| `POST /book` | < 300 ms | 0.1% |
| `GET /slots` | < 200 ms | 0.1% |
| `POST /patients` | < 250 ms | 0.1% |

---

## Local Setup
```bash
git clone https://github.com/yourusername/virtual-minuteclinic.git
cd virtual-minuteclinic
docker compose up -d
