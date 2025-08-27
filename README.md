# business-analysis-case-studies

case-studies: AI-Enhanced Claim Part Identification

1. Executive Summary
This document outlines the business requirements for implementing an Artificial Intelligence (AI) solution to automate the identification of special claim parts. The current manual process is slow, inconsistent, and fails to scale, resulting in missed opportunities and operational bottlenecks.
The proposed AI solution will automate this identification task, significantly increasing both the volume and accuracy of detections. This project will enable the business to handle a higher volume of claims efficiently, improve the accuracy of claim assessments, and reduce revenue leakage from missed items.
However, the success of this automation will create a new bottleneck in the downstream investigation process. This BRD also outlines the requirements for managing this new challenge, including workflow redesign, capacity planning, and new triage mechanisms.

2. Project Overview & Scope

2.1 Problem Statement
The manual process for identifying special claim parts is a major bottleneck. It relies on specialized human knowledge, which is difficult to scale across 77 lines of business. This leads to:
•	Inconsistent Performance: Claim handlers miss approximately 30% of true claim parts (70% recall).[1]
•	Low Throughput: Only 1.82% of claims are flagged, which is far below the expected rate, indicating a significant number of unidentified cases.[1]
•	Inability to Scale: As claim volumes grow, the manual process cannot keep up, limiting business growth and efficiency.

2.2 Business Objectives
•	Increase Accuracy: Increase the recall rate for claim part identification to be higher than the 70% human baseline.
•	Improve Efficiency: Dramatically increase the number of identified claim parts to align with true business estimates (around 27% of claims).[1]
•	Enhance Scalability: Create a process that can handle growing claim volumes without a proportional increase in manual effort.
•	Reduce Leakage: Minimize financial losses from unidentified or missed claim parts.
2.3 Scope
•	In-Scope:
o	Development and deployment of an LLM-based AI model for claim part identification.
o	Integration of the AI with existing claims systems.
o	Creation of a triage workflow for prioritizing AI-generated leads.
o	Development of a feedback mechanism for investigators to improve the AI.
o	Creation of dashboards to monitor process performance.
•	Out-of-Scope:
o	Changes to the initial customer claim submission process.
o	Re-platforming of the core claims management system.

3. Stakeholders
•	Business Owner: Accountable for project success and ROI.
•	Claim Handlers: Users of the current system.
•	Claim Part Investigators: End-users of the new AI-driven workflow.
•	Data Science Team: Responsible for building and maintaining the AI model.
•	IT & DevOps: Responsible for infrastructure, deployment, and security.
•	Legal & Compliance: To ensure data privacy and regulatory adherence.
 
4. Process Models
4.1 As-Is Process (Current State)
1.	A customer submits a claim.
2.	A Claim Handler manually registers the claim and reads the notes.
3.	The Claim Handler uses their knowledge to identify if a special claim part exists.
4.	If identified, the case is forwarded to an Investigator. (This happens infrequently).
4.2 To-Be Process (Future State)
1.	A customer submits a claim, and a Handler registers it.
2.	The AI System automatically scans the claim text and notes.
3.	The AI identifies a potential claim part and assigns a confidence score.
4.	A Triage System automatically prioritizes the case based on score and business value.
5.	An Investigator receives a prioritized queue of cases to review.
6.	The Investigator provides feedback on the AI's accuracy, which helps the model learn.

5. Requirements
5.1 Functional Requirements
•	FR-01: The AI system must be able to read unstructured text from claim descriptions and notes.
•	FR-02: The AI must identify and classify specific claim parts with a recall rate greater than 70%.
•	FR-03: The system must provide a structured output (e.g., JSON format) for easy integration.[1]
•	FR-04: A triage module must automatically sort and rank identified claims for investigators.
•	FR-05: Investigators must have a simple interface to confirm, correct, or dismiss AI findings.
•	FR-06: The system must provide a dashboard with key performance indicators (e.g., number of claims identified, queue length, processing time).
5.2 Non-Functional Requirements
•	NFR-01: All data processing must comply with privacy regulations (e.g., PII masking, data residency in Sweden).[1]
•	NFR-02: The system must be scalable to handle the full volume of company claims.
•	NFR-03: The system must be highly available during business hours.
•	NFR-04: The user interface for investigators must be intuitive and require minimal training.

6. What Could Go Wrong (Risks and Mitigation)

There are a few risks to watch out for. 
First, the AI will find so many claims that our investigation team could get overwhelmed. 
To prevent this, we will need to grow that team and use the AI to sort claims so they can tackle the most important ones first. 
There's also a risk that our team could get tired from too many alerts, so we need to make sure the system only flags what's truly necessary. 
We will also be very careful with data privacy. Finally, we need to have a plan in case the AI technology has problems, and we will provide training and support to help our team get used to the new way of working.
