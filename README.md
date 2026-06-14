# BankFlow_v1.0.0
# BankFlow KYC Processor: Enterprise RPA & Data Integration Engine

📊 Project Overview
BankFlow KYC Processor is a production-grade, transactional Blue Prism automation designed to streamline the Know Your Customer (KYC) onboarding pipeline for financial institutions. Built strictly around enterprise scalability and compliance guidelines, the system reads incoming client application data, orchestrates multi-page process switching, logs transactional states directly to a relational database for auditing, and triggers real-time HTML communications via Microsoft Outlook.

The entire project is packaged into a self-contained deployment artifact (`.bprelease`), modeling a professional DevOps release cycle.

---

🏛️ System Architecture
The platform is engineered using a decoupled, modular **Producer/Consumer Design Pattern** split across two main automated processes to manage system memory and workload execution efficiently.

```text
[Raw Input Data] ──► [BankFlow - Application Intake (Producer)] ──► [BankFlow_Intake_Queue]
                                                                            │
                                                                            ▼
[Relational SQL Audit] ◄── [BankFlow- KYC Processor (Consumer)] ◄─── [Get Next Item (Lock)]
          │
          ▼
[Outlook HTML Notification]
