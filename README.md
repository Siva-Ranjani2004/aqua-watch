# UrbanFix

**An AI-Based Multimodal Civic Complaint Classification and Management System**

UrbanFix is a research-based smart city solution that leverages artificial intelligence to improve municipal civic infrastructure management. The system enables citizens to report civic issues — potholes, garbage accumulation, water leakage, sewage overflow, damaged streetlights, road obstructions, and drainage problems — and assists municipal authorities in efficiently managing complaints through intelligent multimodal analysis, prioritization, and decision support.

**Project Code:** 22CSP72 – Project Work II, Phase I
**Team Number:** D05
**Team Guide:** Ramana S
**Team Members:**
- Sanjani Prakash M (23CSR188)
- Sivaranjani S (23CSR205)
- Yahya Imthiyas S (23CSR243)

**Institution:** Kongu Engineering College, Perundurai

---

## Table of Contents

- [Problem Statement](#problem-statement)
- [Research Gap](#research-gap)
- [Objectives](#objectives)
- [Key Features](#key-features)
- [AI Technologies](#ai-technologies)
- [Architecture Design](#architecture-design)
- [Proposed Work](#proposed-work)
- [Modules of the Project](#modules-of-the-project)
- [Technology Stack](#technology-stack)
- [Project Structure](#project-structure)
- [Outcomes](#outcomes)
- [Literature Survey](#literature-survey)
- [References](#references)
- [Application Domains](#application-domains)

---

## Problem Statement

Urban areas frequently face public infrastructure issues such as potholes, garbage accumulation, water leakage, sewage overflow, damaged streetlights, road obstructions, and drainage problems. Existing complaint management systems rely heavily on manual reporting, categorization, and routing, resulting in delayed responses and duplicate complaints.

Moreover, most current AI-based solutions are limited to image classification and lack advanced capabilities such as multimodal complaint analysis, duplicate detection, severity assessment, and complaint prioritization. There is therefore a critical need for an intelligent, AI-powered multimodal public issue management system that can improve complaint handling, resource allocation, and municipal decision-making.

---

## Research Gap

- Existing civic complaint systems primarily rely on single-modal analysis (image or text) and do not integrate image, complaint text, GPS location, and timestamp for comprehensive complaint understanding.
- Duplicate complaints are not automatically detected, leading to redundant processing, delayed resolution, and inefficient utilization of municipal resources.
- Most existing approaches lack severity prediction and hotspot detection, making it difficult for authorities to prioritize critical civic issues and allocate resources effectively.
- Current systems provide limited AI-driven decision support, with inadequate real-time analytics, automated department routing, and performance monitoring for efficient complaint management.

---

## Objectives

- Automatically classify various civic issues such as potholes, garbage accumulation, water leakage, sewage overflow, damaged streetlights, and road damage from citizen-uploaded images using deep learning.
- Enhance complaint understanding by integrating image, complaint text, GPS location, and timestamp through multimodal AI for accurate complaint analysis and department routing.
- Detect duplicate complaints, predict issue severity, and prioritize complaints using AI techniques for efficient municipal resource allocation.
- Provide an intelligent decision support dashboard with hotspot detection, real-time analytics, complaint tracking, and performance insights for faster, data-driven decision-making by municipal authorities.

---

## Key Features

| Feature | Description |
|---|---|
| AI-based Civic Issue Classification | Automatically categorizes reported issues from images |
| Complaint Text Understanding | Extracts meaning and context from complaint descriptions |
| GPS-based Complaint Tracking | Geotags every complaint for spatial analysis |
| Duplicate Complaint Detection | Identifies and merges repeated reports of the same issue |
| Severity Prediction | Estimates the urgency/impact of a reported issue (Low / Medium / High / Critical) |
| Priority Ranking | AI-based prioritization of complaints for efficient resource allocation |
| Hotspot Detection | Surfaces geographic clusters of recurring civic problems |
| Department Routing | Rule + AI-based routing of complaints to the appropriate department/officer |
| AI-powered Decision Support Dashboard | Centralized real-time analytics for municipal authorities |
| Resolution Tracking | Monitors complaint status from report to resolution |

---

## AI Technologies

| Module | Technology |
|---|---|
| Image Preprocessing | OpenCV (Resize, Normalize, Denoise, Augment) |
| Image Feature Extraction / Classification | EfficientNetV2 |
| Text Preprocessing | Cleaning, Tokenization, Stopword Removal |
| Text Feature Extraction | DistilBERT / BERT |
| Multimodal Fusion | Feature Fusion Network (Image + Text + Location + Time) |
| Duplicate Detection | CLIP Embeddings + FAISS |
| Severity Prediction | Multimodal Severity Prediction Model |
| Hotspot Detection | DBSCAN (Geo-spatial Clustering) |
| Decision Support | Analytics Dashboard |

---

## Architecture Design

```text
Citizen
        │
        ├── Upload Image
        ├── Complaint Description (Text)
        ├── GPS Location
        └── Timestamp
                │
                ▼
        ┌───────────────── PREPROCESSING ─────────────────┐
        │  Image Preprocessing   Text Preprocessing         │
        │  (OpenCV)              (Cleaning, Tokenization,   │
        │                         Stopword Removal)         │
        │                Data Normalization (GPS, Timestamp)│
        └───────────────────────┬──────────────────────────┘
                                 ▼
        ┌────────────────── MULTIMODAL AI MODELS ──────────────────┐
        │  Image Feature Extraction (EfficientNetV2)                │
        │  Text Feature Extraction (BERT / DistilBERT)               │
        │  Multimodal Fusion (Image + Text + Location + Time)        │
        │              ▼                                             │
        │       Issue Classification (Multi-class Classification)    │
        └───────────────────────┬────────────────────────────────────┘
                                 ▼
        ┌────────────────── ADVANCED AI ANALYTICS ─────────────────┐
        │  Duplicate Detection   Severity Prediction                │
        │  (Siamese/CLIP+FAISS)  (Low/Medium/High/Critical)          │
        │  Priority Ranking      Hotspot Detection                  │
        │  (AI-based)            (DBSCAN Geo-spatial Clustering)    │
        └───────────────────────┬────────────────────────────────────┘
                                 ▼
                        Department Routing
        (Rule + AI-based Routing to Appropriate Department / Officer)
```

---

## Proposed Work

- Develop a multimodal AI-based civic complaint analysis system by integrating EfficientNetV2 for image feature extraction, DistilBERT for complaint text understanding, and a Feature Fusion Network to combine image, text, GPS location, and timestamp for accurate issue classification and department routing.
- Implement intelligent complaint analysis through duplicate complaint detection using CLIP Embeddings + FAISS and AI-based severity prediction to estimate issue urgency and support effective complaint prioritization.
- Perform hotspot detection and resource optimization using DBSCAN clustering and AI-based prioritization to identify recurring civic issues and assist municipal authorities in efficient resource allocation.
- Develop an AI-powered decision support dashboard using React.js and FastAPI to monitor complaints, visualize hotspot regions, track complaint resolution, and provide real-time analytics for data-driven decision-making.

---

## Modules of the Project

### Citizen Platform (Mobile App — built with Flutter)

**Module 1: User Authentication & Complaint Management**
User registration and login, complaint submission with image upload, GPS location capture, and complaint status tracking.

**Module 2: AI-Based Issue Classification**
Image preprocessing, civic issue classification using EfficientNetV2, complaint text analysis using DistilBERT, and multimodal feature fusion.

**Module 3: Intelligent Complaint Analysis**
Duplicate complaint detection using CLIP + FAISS, severity prediction (AI model), complaint prioritization, and hotspot detection using DBSCAN.

**Module 4: Decision Support Dashboard**
Complaint analytics, hotspot visualization on map, complaint progress monitoring, and resource allocation support for municipal decision-making.

### Municipality Platform (Web Dashboard — built with React.js + FastAPI)

- Real-time Overview & Analytics
- Hotspot Visualization on Map
- Complaint Management & Tracking
- Resource Allocation & Decision Support

---

## Technology Stack

**Artificial Intelligence**
EfficientNetV2 · DistilBERT / BERT · CLIP · FAISS · DBSCAN · OpenCV · PyTorch · Scikit-learn

**Mobile App (Citizen Platform)**
Flutter

**Backend**
Python · FastAPI

**Frontend (Municipality Dashboard)**
React.js

**Database**
PostgreSQL

**Maps**
Leaflet.js / OpenStreetMap / Google Maps

---

## Project Structure

```
UrbanFix/
│
├── mobile-app/            # Flutter citizen complaint app
├── dashboard/              # React.js municipality web dashboard
├── backend/                 # FastAPI backend services
├── ai-models/
│   ├── image-classification/   # EfficientNetV2
│   ├── text-analysis/          # DistilBERT
│   ├── duplicate-detection/    # CLIP + FAISS
│   ├── severity-prediction/
│   └── hotspot-detection/      # DBSCAN
│
├── datasets/
├── notebooks/
├── docs/
└── README.md
```

---

## Outcomes

An initial image classification model was trained to identify civic water-related issues (Drainage Overflow, Tap Broken, Water Leakage, Water Logging, Water Pollution) from citizen-uploaded photographs.

**Sample Prediction Output**

```
Prediction
======================================
waterpollution : 69.35%
WaterLogging   : 22.42%
```

**Confusion Matrix (5-class model)**

| True \ Predicted | DrainageOverflow | TapBroken | WaterLeakage | WaterLogging | waterpollution |
|---|---|---|---|---|---|
| DrainageOverflow | 43 | 0 | 0 | 3 | 0 |
| TapBroken | 0 | 5 | 1 | 0 | 3 |
| WaterLeakage | 0 | 0 | 6 | 4 | 2 |
| WaterLogging | 0 | 1 | 1 | 60 | 5 |
| waterpollution | 0 | 0 | 0 | 0 | 45 |

The model shows strong performance on high-frequency classes (DrainageOverflow, WaterLogging, waterpollution), with some confusion among visually similar minority classes (TapBroken, WaterLeakage), indicating a direction for further data augmentation and class balancing.

---

## Literature Survey

| Feature | Paper 1 | Paper 2 | Paper 3 |
|---|---|---|---|
| **Title** | CitySolution: A Complaining Task Distributive Mobile Application for Smart City Corporation Using Deep Learning | AI-Powered Civic Issue Reporting and Resolution System | CivicFix: Smart Complaint Routing for Urban Solutions |
| **Authors** | Farhatun Shama, Abdul Aziz, Lamisa Bintee Mizan Deya | K. Sindhu Abhirami, K. Krishna Sai, V. Pardha Siva Sitha Rama Reddy, P. Srinivasa Reddi | Roopesh Kumar B. N., Thanusha S., Shravya R., Shreya P. R., Sunidhi R. |
| **Dataset Used** | Custom dataset of civic issue images (Damaged Road, Flood, Trash, Homeless People) | Custom urban issues dataset of annotated images (Electrical Poles, Road Signs, Fallen Trees, Garbage, Potholes) | Civic complaint images with Google Maps location data |
| **Algorithm** | Teachable Machine (MobileNet + CNN + Transfer Learning) | YOLOv8s + Qwen2.5 LLM | Machine Learning-based Image Classification using CNN |
| **Prediction Target** | Complaint Category Classification | Urban Issue Detection & Description Generation | Complaint Classification & Smart Routing |

---

## References

**Base Paper**
- **Title:** CitySolution: A Complaining Task Distributive Mobile Application for Smart City Corporation Using Deep Learning
- **Journal:** SoftwareX (Elsevier)
- **Year:** 2024

**Reference Paper 1**
- **Title:** AI-Powered Civic Issue Reporting and Resolution System
- **Journal:** International Journal for Research in Applied Science & Engineering Technology (IJRASET)
- **Year:** 2026

**Reference Paper 2**
- **Title:** CivicFix: Smart Complaint Routing for Urban Solutions
- **Journal:** International Journal of Advanced Research in Computer and Communication Engineering (IJARCCE)
- **Year:** 2025

---

## Application Domains

- Smart Cities
- Municipal Governance
- Urban Civic Infrastructure
- Civic Complaint Management
- Artificial Intelligence
- Computer Vision
- Natural Language Processing
- Geospatial Analytics
