# business-analysis-case-studies

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

---

📌 **References**
1. Internal claim system benchmarks & business data


6. What Could Go Wrong (Risks and Mitigation)

There are a few risks to watch out for. 
First, the AI will find so many claims that our investigation team could get overwhelmed. 
To prevent this, we will need to expand our team and utilize AI to prioritize claims, allowing them to focus on the most critical ones first. 
There's also a risk that our team could get tired from too many alerts, so we need to make sure the system only flags what's truly necessary. 
We will also be very careful with data privacy. Finally, we need to have a plan in case the AI technology has problems, and we will provide training and support to help our team get used to the new way of working.
