# Swachh Hawa — National Environmental Intelligence

**Live project:** [https://eacs-swachh-hawa.vercel.app/](https://eacs-swachh-hawa.vercel.app/)

Swachh Hawa is an AI-powered command center for national air-quality governance in India. It brings real-time air quality, AI forecasts, sensor health and enforcement into one dashboard, so that pollution data can actually be trusted and acted on.

Built by **TriArch, EACS, RV College of Engineering (RVCE), Bengaluru**
Mentor: **Dr. Niladri Bihari Nayak**

---

## Open the project

Click the link above or paste this in your browser:

```
https://eacs-swachh-hawa.vercel.app/
```

When the page opens it shows "Verifying session…" for a moment before the dashboard loads. Wait a couple of seconds and it will continue.

---

## The problem

Air-quality monitoring in India today has a few clear gaps:

| ID | Gap |
|----|-----|
| G1 | Sparse coverage: too few monitoring stations |
| G2 | Siloed integration: data sits in separate systems |
| G3 | No provenance: hard to prove where a reading came from |
| G4 | Inconsistent data definitions across agencies |
| G5 | No forecasting in day-to-day operations |
| G6 | Unclear decision rights on who acts and when |
| G7 | Privacy handling not ready for the DPDP Act |

## Our approach

We do not replace the existing CPCB and State PCB monitoring network. We add to it. The idea is **coexistence**: keep the reference-grade stations, then add dense low-cost sensors, a trust and provenance layer, forecasting, and governed delivery on top. The target is roughly **10x spatial density** with data strong enough to support enforcement.

---

## What the platform does

- **Real-time national air quality** across India
- **AI forecasts** (72-hour, hyperlocal) so authorities can act before pollution peaks
- **Sensor health monitoring** to see which devices are working and which need calibration
- **Enforcement support** with tamper-evident evidence for regulatory action
- **Privacy-safe public view** where citizens see aggregated data protected with ε-differential privacy

---

## Architecture

The project is backed by a full enterprise architecture made with **ArchiMate 3.x** and the **TOGAF ADM** method. It has these layers:

1. **Motivation and Governance:** drivers, goals, principles, and the ARB, DGC and SRB governance bodies
2. **Business:** stakeholders such as CPCB, State PCBs, Urban Local Bodies, citizens and researchers, with their roles, processes and services
3. **Application:** Kafka ingestion, Trust Engine, Forecasting Ensemble, TimescaleDB, WORM AuditStore, Calibration Engine, API Gateway, AirGPT assistant and the dashboard
4. **Technology:** edge sensors, LoRaWAN backhaul, X.509 device identity and a multi-cloud hybrid platform
5. **Cross-cutting Security:** zero-trust with mTLS, RBAC + JWT, SIEM/SOC and HashiCorp Vault
6. **Cross-cutting Data Governance:** ε-differential privacy, PII tokenisation, data lineage and retention rules under the DPDP Act 2023

A five-phase roadmap takes the system from a proof of concept to full national rollout:

| Phase | Focus |
|-------|-------|
| 0 | Proof of concept and trust validation |
| 1 | Delhi-NCR flagship |
| 2 | Tier-1 metro expansion |
| 3 | Tier-2 and Tier-3 cities |
| 4 | Full national rollout with State PCBs |

Planning-grade estimate: about Rs. 650 Cr capital over 5 years and about Rs. 150 Cr per year to run, roughly Rs. 1,050 Cr in total, against a naive greenfield cost of around Rs. 2,000 Cr.

---

## Tech stack

| Area | Technology |
|------|------------|
| Frontend dashboard | React 19, TanStack Start |
| Hosting | Vercel |
| Ingestion and storage | Kafka, TimescaleDB |
| Forecasting | LightGBM + LSTM |
| Assistant | RAG-based AirGPT |
| Trust and audit | SHA-256 hash chain, Merkle anchors, WORM AuditStore |
| Infrastructure | AWS / Azure, Terraform, GitHub Actions |
| Observability | Prometheus, Grafana |
| Modelling | Archi (ArchiMate 3.x) |

---

## Documentation

- **Architecture diagram (PNG / PDF):** the full TOGAF / ArchiMate target-state diagram with legend and acronym glossary

---

## Team

TriArch, EACS, RV College of Engineering, Bengaluru
Mentor: Dr. Niladri Bihari Nayak

---

*TOGAF® and ArchiMate® are registered trademarks of The Open Group. Cost and scale figures are planning-grade 2026 estimates.*
