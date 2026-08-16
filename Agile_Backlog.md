# Agile Backlog & Traceability Matrix

## Epic 1: KYC Compliance Workflow

**User Story 1.1:**
> **As a** Compliance Officer,  
> **I want** the system to automatically flag uploaded ID documents that are expired,  
> **So that** I do not have to manually check every document date and can focus on complex cases.

**Acceptance Criteria:**
1. The system must parse the 'Expiration Date' field upon document upload.
2. If the date is strictly less than the current system date, the account status must change to "Action Required - Expired ID".
3. The system must trigger automated email template #42 to the client.

---

## Epic 2: Trade Discrepancy Reconciliation

**User Story 2.1:**
> **As a** Customer Support Agent,  
> **I want** the CRM to automatically flag discrepancies between the user's terminal buy price and the backend executed price,  
> **So that** I can quickly process refunds or adjustments without waiting for developer database checks.

**Acceptance Criteria:**
1. The CRM must compare the `Terminal_Input_Price` with the `Ledger_Execution_Price` for intraday trades.
2. If a discrepancy exists (e.g., Terminal Input was 157.60, but Ledger Execution was 157.76), the system must highlight the trade row in red on the agent's dashboard.
3. The system must calculate and display the exact price delta (e.g., 0.16) for quick reference.
   
---

## Requirement Traceability Matrix (RTM)

| Business Goal | Functional Req (User Story) | Test Case ID | Status |
| :--- | :--- | :--- | :--- |
| Reduce manual document review time | **US 1.1:** Auto-flag expired ID docs | TC-001 | Pending |
| Resolve support tickets faster | **US 2.1:** Flag trade price discrepancies | TC-002 | Pending |
