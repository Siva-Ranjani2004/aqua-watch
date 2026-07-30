<div align="center">

# UrbanFix

### An AI-Based Multimodal Civic Complaint Classification and Management System

**22CSP72 — Project Work II, Phase I** · Team **D05** · Kongu Engineering College

[![Status](https://img.shields.io/badge/status-Phase%20I%20%E2%80%94%20Review%201-blue)]()
[![License](https://img.shields.io/badge/license-MIT-green)]()
[![Made with](https://img.shields.io/badge/AI-EfficientNetV2%20%7C%20DistilBERT%20%7C%20CLIP-orange)]()

</div>

---

UrbanFix is a smart-city solution that lets citizens report civic infrastructure issues — potholes, garbage accumulation, water leakage, sewage overflow, damaged streetlights, road obstructions, and drainage problems — through a mobile app, and uses multimodal AI (image + text + GPS + timestamp) to automatically classify, deduplicate, prioritize, and route those complaints for municipal authorities to act on through a real-time decision-support dashboard.

## Table of Contents

- [Problem Statement](#problem-statement)
- [Objectives](#objectives)
- [Key Features](#key-features)
- [Architecture](#architecture)
- [Tech Stack](#tech-stack)
- [Repository Structure](#repository-structure)
- [Getting Started](#getting-started)
- [Documentation](#documentation)
- [Preliminary Outcomes](#preliminary-outcomes)
- [Roadmap](#roadmap)
- [Team](#team)
- [Contributing / Git Workflow](#contributing--git-workflow)
- [References](#references)
- [License](#license)

---

## Problem Statement

Urban local bodies receive large volumes of civic complaints, but existing complaint-management systems rely on manual reporting and categorization, causing delayed responses and duplicate complaints. Most AI-based tools in this space stop at basic image classification and lack duplicate detection, severity estimation, hotspot analysis, and prioritized decision support — all of which are needed for efficient municipal resource allocation. UrbanFix addresses this by combining computer vision, NLP, and geospatial analytics in a single multimodal pipeline. Full details: [`docs/UrbanFix_Research_Gap_v1.0.docx`](docs/UrbanFix_Research_Gap_v1.0.docx).

## Objectives

- Automatically classify civic issues (potholes, garbage, water leakage, sewage overflow, damaged streetlights, road damage, etc.) from citizen-uploaded images using deep learning.
- Fuse image, complaint text, GPS location, and timestamp through multimodal AI for accurate complaint understanding and department routing.
- Detect duplicate complaints, predict issue severity, and prioritize complaints for efficient resource allocation.
- Provide an AI-powered decision-support dashboard with hotspot detection, real-time analytics, and resolution tracking for municipal authorities.

## Key Features

| Feature | Description |
|---|---|
| AI-based Issue Classification | Classifies reported issues from citizen-uploaded images |
| Complaint Text Understanding | Extracts meaning and context from complaint descriptions |
| GPS-based Complaint Tracking | Geotags every complaint for spatial analysis |
| Duplicate Complaint Detection | Identifies and merges repeated reports of the same issue |
| Severity Prediction | Estimates urgency/impact (Low / Medium / High / Critical) |
| Priority Ranking | AI-based prioritization for efficient resource allocation |
| Hotspot Detection | Surfaces geographic clusters of recurring civic problems |
| Department Routing | Rule + AI-based routing to the correct department/officer |
| Decision Support Dashboard | Real-time analytics for municipal authorities |
| Resolution Tracking | Monitors complaint status from report to resolution |

## Architecture

```text
Citizen → Upload Image + Complaint Text + GPS + Timestamp
              │
              ▼
   PREPROCESSING (OpenCV · Tokenization · GPS/Timestamp Normalization)
              │
              ▼
   MULTIMODAL AI MODELS
   EfficientNetV2 (image) + DistilBERT (text) → Feature Fusion Network
              │
              ▼
   Issue Classification (Multi-class)
              │
              ▼
   ADVANCED AI ANALYTICS
   Duplicate Detection (CLIP + FAISS) · Severity Prediction · Priority Ranking · Hotspot Detection (DBSCAN)
              │
              ▼
   Department Routing → Decision Support Dashboard (Municipality)
```

Full diagram and module-level design: [`docs/UrbanFix_Methodology_v1.0.docx`](docs/UrbanFix_Methodology_v1.0.docx).

## Tech Stack

**AI / ML** — EfficientNetV2 · DistilBERT · CLIP · FAISS · DBSCAN · OpenCV · PyTorch · Scikit-learn
**Mobile App (Citizen)** — Flutter
**Backend** — Python · FastAPI
**Web Dashboard (Municipality)** — React.js
**Database** — PostgreSQL
**Maps** — Leaflet.js / OpenStreetMap

## Repository Structure

```
UrbanFix/
│
├── mobile-app/              # Flutter citizen complaint app
├── dashboard/                # React.js municipality web dashboard
├── backend/                   # FastAPI backend services
├── ai-models/
│   ├── image-classification/    # EfficientNetV2
│   ├── text-analysis/           # DistilBERT
│   ├── duplicate-detection/     # CLIP + FAISS
│   ├── severity-prediction/
│   └── hotspot-detection/       # DBSCAN
│
├── datasets/                 # Training/testing data (not committed — see datasets/README.md)
├── notebooks/                # Exploratory / training notebooks
├── docs/                      # Project documentation (see below)
└── README.md
```

## Getting Started

> The mobile app, backend, and dashboard are under active development for Phase I. The steps below reflect the intended setup once each module lands.

```bash
# Clone the repository
git clone https://github.com/urbanfix-d05/UrbanFix.git
cd UrbanFix

# Backend (FastAPI)
cd backend
python -m venv venv && source venv/bin/activate
pip install -r requirements.txt
uvicorn main:app --reload

# Web Dashboard (React.js)
cd ../dashboard
npm install
npm start

# Mobile App (Flutter)
cd ../mobile-app
flutter pub get
flutter run
```

## Documentation

All Review 1 deliverables live in [`docs/`](docs/):

| Document | Description |
|---|---|
| [`UrbanFix_Literature_Survey_v1.0.docx`](docs/UrbanFix_Literature_Survey_v1.0.docx) | Review of the base paper and reference papers, with critical analysis |
| [`UrbanFix_Research_Gap_v1.0.docx`](docs/UrbanFix_Research_Gap_v1.0.docx) | Identified research gaps and how UrbanFix addresses each |
| [`UrbanFix_Methodology_v1.0.docx`](docs/UrbanFix_Methodology_v1.0.docx) | Full technical methodology, module design, evaluation plan, roadmap |
| [`UrbanFix_Meeting_Minutes_v1.0.docx`](docs/UrbanFix_Meeting_Minutes_v1.0.docx) | Team–guide meeting log for Review 1 |
| [`UrbanFix_Git_Workflow_Commit_Log_v1.0.docx`](docs/UrbanFix_Git_Workflow_Commit_Log_v1.0.docx) | Branching strategy, commit conventions, and commit log |

Each document carries its own version-history table — bump the version number there as it's revised, rather than creating new files, so history stays in Git rather than in filenames.

## Preliminary Outcomes

An initial EfficientNetV2 prototype was trained on a 5-class water-issue subset (Drainage Overflow, Tap Broken, Water Leakage, Water Logging, Water Pollution). It performs strongly on the higher-frequency classes (Drainage Overflow, Water Logging, Water Pollution), with some confusion between the visually similar minority classes Tap Broken and Water Leakage — flagged as a target for further data augmentation and class balancing in Phase 2.

## Roadmap

- [x] Phase 1 — Literature survey & research planning
- [ ] Phase 2 — Data collection & preprocessing pipeline
- [ ] Phase 3 — Image & text model development
- [ ] Phase 4 — Multimodal fusion & issue classification
- [ ] Phase 5 — Duplicate detection & severity prediction
- [ ] Phase 6 — Hotspot detection & priority ranking
- [ ] Phase 7 — Mobile app & dashboard integration
- [ ] Phase 8 — Testing, evaluation & documentation

Full phase-by-phase plan: [`docs/UrbanFix_Methodology_v1.0.docx`](docs/UrbanFix_Methodology_v1.0.docx).

## Team

| Name | Register No. | Role |
|---|---|---|
| Sanjani Prakash M | 23CSR188 | — |
| Sivaranjani S | 23CSR205 | — |
| Yahya Imthiyas S | 23CSR243 | — |

**Guide:** Ramana S

## Contributing / Git Workflow

- `main` is protected — always in a working/presentable state.
- Work happens on `feature/<module>` or `docs/<document>` branches, merged via reviewed pull requests.
- Commit messages follow a Conventional-Commits style: `feat|fix|docs|chore(<scope>): <short description>`.
- Commits are kept small and pushed continuously as work is completed, not batched before deadlines.

Full details: [`docs/UrbanFix_Git_Workflow_Commit_Log_v1.0.docx`](docs/UrbanFix_Git_Workflow_Commit_Log_v1.0.docx).

## References

1. Farhatun Shama, Abdul Aziz, Lamisa Bintee Mizan Deya, "CitySolution: A complaining task distributive mobile application for smart city corporation using deep learning," *SoftwareX*, vol. 27, p. 101829, 2024.
2. K. Sindhu Abhirami, K. Krishna Sai, V. Pardha Siva Sitha Rama Reddy, P. Srinivasa Reddi, "AI-Powered Civic Issue Reporting and Resolution System," *IJRASET*, 2026.
3. Roopesh Kumar B. N., Thanusha S., Shravya R., Shreya P. R., Sunidhi R., "CivicFix: Smart Complaint Routing for Urban Solutions," *IJARCCE*, 2025.

## License

This project is developed for academic purposes as part of 22CSP72, Kongu Engineering College. License to be finalized by the team (MIT recommended for open collaboration).
