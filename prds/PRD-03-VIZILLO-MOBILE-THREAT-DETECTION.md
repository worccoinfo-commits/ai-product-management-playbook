# Product Requirement Document (PRD): Mobile Threat Scanner & Runtime Risk Scoring
**Product**: Vizillo AI  
**Author**: Rishav Bhardwaj (Technical Product Manager)  
**Status**: Production / Shipped  
**Target Release**: Q2  

---

## 1. Executive Summary & Problem Statement
Non-technical mobile users face escalating exposure to SMS phishing (smishing), fraudulent APK trojans, and invasive apps that secretly request accessibility service hooks or background SMS reading. Most security tools are bloated with battery-draining ad tech.

**Product Objective**: Build a clean, native Android security suite with a "Cyber-Dark" aesthetic that translates complex runtime permission telemetry into an actionable 0–100 threat risk score in real time.

---

## 2. Core Heuristics & Detection Matrix
- **Critical Risk (Score +40)**: `BIND_ACCESSIBILITY_SERVICE` without verified accessibility declaration.
- **High Risk (Score +25)**: `RECEIVE_SMS` + `INTERNET` permission combination in third-party APKs.
- **Medium Risk (Score +15)**: `SYSTEM_ALERT_WINDOW` (overlay injection risk).

---

## 3. UI/UX Design System
- **Aesthetic**: Cyber-Dark glassmorphism built natively in Jetpack Compose.
- **Telemetry**: Color-coded risk cards (Neon Green: Safe, Amber: Caution, Neon Crimson: High Threat Alert).
