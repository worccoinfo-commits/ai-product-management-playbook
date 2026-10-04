# Product Requirement Document (PRD): On-Device Biometric Anti-Fraud Engine
**Product**: Tatch Connect (Mobile Social Discovery)  
**Author**: Rishav Bhardwaj (Technical Product Manager)  
**Status**: Production / Shipped  
**Target Release**: Q3  

---

## 1. Executive Summary & Problem Statement
In social discovery and community mobile applications, fraudulent accounts, AI-generated bots, and catfishing degrade user trust and increase churn by up to 40%. Traditional CAPTCHAs are solved by botnets, while third-party cloud ID verification services introduce high SaaS costs ($1.50–$3.00/verification) and severe privacy liabilities under GDPR and CCPA.

**Product Objective**: Architect a zero-cost, 100% on-device facial liveness and verification engine that stops bot registrations without transmitting biometric image files to external servers.

---

## 2. Goals & Success Metrics
- **Bot Account Reduction**: Reduce fraudulent account creation by ≥ 90%.
- **Onboarding Completion**: Maintain a verification completion rate of ≥ 92% with < 5 seconds total verification latency.
- **Privacy & Compliance**: 0 raw face images stored on cloud databases.

---

## 3. User Personas & Journey
- **Legitimate User**: Onboards, performs 2 micro-gestures (e.g. slight head turn, blink), receives instant verified checkmark.
- **Adversary / Bot**: Attempts static photo spoofing, deepfake replay, or headless emulator registration; blocked by Euler angle yaw/pitch heuristics.

---

## 4. Technical Architecture & Constraints
- **Client-Side Framework**: Flutter (v3.6+), CameraX stream.
- **Inference Engine**: Google ML Kit (facial landmarks) + TensorFlow Lite (192-dim MobileFaceNet embedding).
- **Backend Sync**: Supabase (PostgreSQL) storing mathematical hashes with Euclidean distance verification (< 0.6 threshold).
