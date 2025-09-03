# BizChat Multi‑AI Optimization

case-studies: AI-Enhanced Claim Part Identification

# Business Requirements Document (BRD)

## 1. Executive Summary
This document outlines the business requirements for implementing an **Artificial Intelligence (AI)** solution to automate the identification of special claim parts.  

The **current manual process** is:
- Slow
- Inconsistent
- Unable to scale  

This results in **missed opportunities** and **operational bottlenecks**.  

The proposed AI solution will:
- Automate identification of claim parts  
- Increase both **volume** and **accuracy** of detections  
- Improve claim assessment accuracy  
- Reduce **revenue leakage** from missed items  

⚠️ However, the success of this automation will also create a **new bottleneck** in the downstream investigation process.  
This BRD includes requirements for:
- Workflow redesign  
- Capacity planning  
- Triage mechanisms  

---

## 2. Project Overview & Scope

### 2.1 Problem Statement
The manual process for identifying special claim parts is a **major bottleneck** across 77 lines of business.  

Key issues:
- **Inconsistent Performance**: ~30% of claim parts missed (70% recall) [1]  
- **Low Throughput**: Only **1.82%** of claims flagged, far below expected [1]  
- **Not Scalable**: Process cannot handle increasing claim volumes  

### 2.2 Business Objectives
- **Increase Accuracy**: Achieve recall higher than 70% human baseline  
- **Improve Efficiency**: Raise detection to ~27% of claims [1]  
- **Enhance Scalability**: Handle growth without proportional manual effort  
- **Reduce Leakage**: Minimize financial loss from missed claims  

### 2.3 Scope
**In-Scope**  
- Development of an **LLM-based AI model**  
- Integration with existing claim systems  
- Triage workflow for AI-generated leads  
- Feedback loop for investigators  
- Dashboards for monitoring performance  

**Out-of-Scope**  
- Changes to **customer claim submission**  
- Re-platforming of the **core claim management system**  

---

## 3. Stakeholders
- **Business Owner** → Accountable for ROI & success  
- **Claim Handlers** → Current users of the system  
- **Claim Part Investigators** → End-users of AI workflow  
- **Data Science Team** → Build & maintain AI model  
- **IT & DevOps** → Infra, deployment, security  
- **Legal & Compliance** → Data privacy & regulations  

---

## 4. Process Models

### 4.1 As-Is Process (Current State)
1. Customer submits a claim  
2. Handler registers claim & reads notes  
3. Handler manually identifies special parts  
4. If found → Forwarded to investigator *(rare)*  

### 4.2 To-Be Process (Future State)
1. Customer submits a claim → Handler registers it  
2. **AI scans** claim text & notes  
3. AI identifies part & assigns **confidence score**  
4. **Triage system** prioritizes case  
5. Investigator reviews **prioritized queue**  
6. Investigator provides **feedback** → AI improves  

---

## 5. Requirements

### 5.1 Functional Requirements
- **FR-01**: AI must read unstructured claim text  
- **FR-02**: AI must identify/classify claim parts with **>70% recall**  
- **FR-03**: System outputs structured format (e.g., `JSON`) [1]  
- **FR-04**: Triage module auto-sorts & ranks claims  
- **FR-05**: Investigator UI for confirm/correct/dismiss  
- **FR-06**: Dashboard with KPIs (identified claims, queue length, processing time)  

### 5.2 Non-Functional Requirements
- **NFR-01**: Compliance with privacy (PII masking, Sweden residency) [1]  
- **NFR-02**: Scalable for full claim volume  
- **NFR-03**: High availability during business hours  
- **NFR-04**: Simple UI, minimal training required
  
## 6. What Could Go Wrong (Risks and Mitigation)

### Key Risks & Mitigation Strategies

- **Investigation Overload**  
  - *Risk*: AI may surface too many claims, overwhelming investigators  
  - *Mitigation*: Expand team capacity and use AI-driven triage to prioritize the most critical cases  

- **Alert Fatigue**  
  - *Risk*: Too many notifications could reduce team efficiency and focus  
  - *Mitigation*: Optimize alerting so only high-value, necessary claims are flagged  

- **Data Privacy Issues**  
  - *Risk*: Handling sensitive claim data may cause compliance or security risks  
  - *Mitigation*: Strict adherence to privacy regulations, data masking, and secure storage  

- **AI System Reliability**  
  - *Risk*: AI model or system failures could disrupt workflows  
  - *Mitigation*: Define fallback processes, ensure monitoring, and create contingency plans  

- **Change Management & Training**  
  - *Risk*: Investigators may struggle to adapt to the new AI-driven workflow  
  - *Mitigation*: Provide training, documentation, and ongoing support for smooth adoption  
