# Business Requirement Document (BRD)

## 1. Executive Summary
The purpose of this project is to define the requirements for a Financial Brokerage CRM. The system will reduce client onboarding time from 5 days to 24 hours and automate the detection of trade execution anomalies to improve customer support efficiency.

## 2. Stakeholders
* **Project Sponsor:** Chief Operating Officer (COO)
* **Primary Users:** Account Managers, Compliance Officers, Customer Support Agents
* **Technical Team:** Database Architects, Backend Developers

## 3. Scope
**In-Scope:**
* Automated KYC document upload and expiration tracking.
* Automated flagging of trade execution price discrepancies.
* Unified dashboard for Account Managers.

**Out-of-Scope:**
* The core trade execution engine (the CRM only reads ledger data).
* Direct payment gateway integration.

## 4. Business Process Flow (As-Is vs To-Be)

*Note: GitHub automatically renders the following Mermaid code into a visual flowchart.*

### To-Be Automated KYC & Trade Reconciliation Flow

```mermaid
graph TD
    A[Client Uploads KYC/Trade Inquiry] --> B{Is it a Trade Query?}
    
    B -- Yes --> C[System checks Terminal vs Ledger data]
    C --> D{Is there a price discrepancy?}
    D -- Yes --> E[Auto-flag for Support Review]
    D -- No --> F[Auto-reply: Execution matches ledger]
    
    B -- No --> G[System reads KYC Expiration Date]
    G --> H{Is Document Valid?}
    H -- Yes --> I[Auto-Approve & Activate Account]
    H -- No --> J[Auto-Email Client for new Document]
    
    E --> K[Support Agent Dashboard]
    I --> L[Account Manager Dashboard]
