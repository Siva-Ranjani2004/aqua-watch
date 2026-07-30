# UrbanFix

> **An AI-Based Multimodal Civic Complaint Classification and Management System**

UrbanFix is an AI-powered smart city solution designed to automate civic complaint analysis and assist municipal authorities in efficient decision-making. The system combines Computer Vision, Natural Language Processing (NLP), and Geospatial Analytics to intelligently classify complaints, predict severity, detect duplicate reports, identify hotspot regions, prioritize complaints, and automatically route them to the appropriate municipal department.

---

# Overview

Traditional civic complaint systems mainly focus on complaint registration and manual categorization, resulting in delayed responses, duplicate complaint processing, and inefficient resource allocation.

UrbanFix introduces a **Multimodal AI Framework** that analyzes multiple sources of information simultaneously:

- Complaint Image
- Complaint Description
- GPS Location
- Timestamp

These inputs are fused into a unified AI representation to provide intelligent complaint analysis and faster municipal decision-making.

---

# Features

- AI-based Civic Issue Classification
- Complaint Text Understanding using NLP
- Multimodal Feature Fusion
- Automatic Department Routing
- Duplicate Complaint Detection
- AI-based Severity Prediction
- Complaint Priority Ranking
- Hotspot Detection
- Municipality Decision Support Dashboard
- Complaint Status Tracking

---

# Supported Civic Issues

UrbanFix can identify various civic infrastructure problems, including:

- Potholes
- Water Leakage
- Sewage Overflow
- Garbage Accumulation
- Waterlogging
- Damaged Streetlights
- Fallen Trees
- Road Damage
- Broken Public Taps
- Drainage Blockages

---

# System Architecture

```text
Citizen Mobile Application (Flutter)

        │

        ▼

Upload Image + Complaint Text

        │

Auto Capture GPS + Timestamp

        │

        ▼

Data Preprocessing

        │

 ┌──────────────┬──────────────┬──────────────┐
 │              │              │
 ▼              ▼              ▼

EfficientNetV2  DistilBERT  GPS & Time Encoder

        │

        └──────────────┬──────────────┘

                       ▼

         Multimodal Feature Fusion Network

                       ▼

      Shared Multimodal Feature Representation

                       │

 ┌────────────┬────────────┬────────────┬────────────┐
 ▼            ▼            ▼            ▼

Issue      Severity     Duplicate    Department
Classification Prediction Detection   Routing
                 │        (CLIP + FAISS)
                 ▼
        Hotspot Detection (DBSCAN)
                 ▼
      AI-based Complaint Prioritization
                 ▼
 Municipality Dashboard (React.js)
```

---

# AI Models

| Module | Model |
|----------|----------------------------|
| Image Feature Extraction | EfficientNetV2 |
| Text Understanding | DistilBERT |
| Multimodal Learning | Feature Fusion Network |
| Duplicate Detection | CLIP + FAISS |
| Severity Prediction | Multimodal AI Model |
| Hotspot Detection | DBSCAN |
| Department Routing | Rule + AI-Based Routing |

---

# Technology Stack

## Artificial Intelligence

- PyTorch
- OpenCV
- EfficientNetV2
- DistilBERT
- CLIP
- FAISS
- Scikit-learn
- DBSCAN

## Backend

- Python
- FastAPI

## Mobile Application

- Flutter

## Web Dashboard

- React.js

## Database

- PostgreSQL

## Maps

- Leaflet.js
- OpenStreetMap

---

# Project Structure

```text
UrbanFix/
│
├── mobile-app/
├── web-dashboard/
├── backend/
├── ai-models/
│   ├── image-classification/
│   ├── text-analysis/
│   ├── multimodal-fusion/
│   ├── duplicate-detection/
│   ├── severity-prediction/
│   ├── hotspot-detection/
│   └── department-routing/
│
├── datasets/
├── notebooks/
│
├── README.md
├── UrbanFix_Literature_Survey_v1.0.docx
├── UrbanFix_Methodology_v1.0.docx
└── UrbanFix_Research_Gap_v1.0.docx
```

---

# Workflow

1. Citizen submits a complaint through the Flutter mobile application.
2. The application collects the complaint image, description, GPS location, and timestamp.
3. The data is preprocessed for AI analysis.
4. EfficientNetV2 extracts image features.
5. DistilBERT extracts text features.
6. A Feature Fusion Network combines image, text, location, and time information.
7. The fused representation performs:
   - Issue Classification
   - Severity Prediction
   - Duplicate Detection
   - Department Routing
8. DBSCAN identifies complaint hotspot regions.
9. Complaints are prioritized based on severity and hotspot analysis.
10. Results are displayed on the municipal web dashboard.

---

# Objectives

- Automate civic issue classification
- Improve complaint understanding using multimodal AI
- Detect duplicate complaints
- Predict complaint severity
- Identify hotspot regions
- Prioritize complaints intelligently
- Support efficient municipal resource allocation
- Enable data-driven decision-making

---

# Expected Outcomes

- Higher complaint classification accuracy
- Reduced duplicate complaint processing
- Faster complaint routing
- Better prioritization of critical issues
- Improved municipal resource utilization
- Intelligent decision support
- Enhanced citizen satisfaction

---

# Future Enhancements

- Multilingual complaint support
- Voice-based complaint submission
- Video complaint analysis
- Predictive infrastructure maintenance
- Integration with IoT smart city sensors
- AI-powered chatbot for citizen assistance

---

# Research Contribution

UrbanFix extends conventional civic complaint systems by introducing a unified **Multimodal AI Framework** that combines Computer Vision, Natural Language Processing, and Geospatial Analytics. By integrating image, text, GPS location, and timestamp into a shared feature representation, the system performs accurate issue classification, severity prediction, duplicate complaint detection, hotspot identification, intelligent department routing, and AI-driven decision support for smart city governance.
