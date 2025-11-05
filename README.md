# Automated Engineering Change Request (ECR) Workflow

This project is a complete, end-to-end automated workflow for managing Engineering Change Requests (ECRs) or Non-Conformance Reports (NCRs) in an engineering or manufacturing environment. It was built using the Microsoft Power Platform to demonstrate low-code process automation skills.

**Live Demo Asset:**

<img width="693" height="1200" alt="Screenshot 2025-11-05 101434" src="https://github.com/user-attachments/assets/4b1b50bd-5452-4cc3-b31e-034c14b68d54" />


---

## 🎯 The Problem

In many industrial and engineering settings, critical processes like ECRs or NCRs are still managed manually through emails and spreadsheets. This leads to several problems:

* **Slow Turnaround:** Approvals get lost in inboxes, delaying critical changes.
* **No Visibility:** It's difficult to track the current status of a request.
* **Data Entry Errors:** Manually transferring data from an email to a logbook is error-prone.
* **Lack of Audit Trail:** There is no standardized, auditable record of who approved what, and when.

## Solution

This automated workflow solves these problems by creating a "single source of truth" that requires zero manual data entry after the initial submission.

### ⚙️ How It Works

The workflow logic is as follows:

1.  **Intake:** An engineer or operator submits a request using a simple **Microsoft Form**.
2.  **Logging:** **Power Automate** instantly triggers, capturing the form response and creating a new row in an **Excel Online** logbook. The request's `Status` is automatically set to `Pending Approval`.
3.  **Approval:** An adaptive card or email is immediately sent to the designated approver (e.g., Engineering Manager) via **Outlook/Teams**. The flow then *pauses* and waits for a response.
4.  **Condition (The Logic):**
    * **If Approved:** The flow captures the approver's comments, updates the Excel row `Status` to `Approved`, and sends a confirmation email to the original submitter.
    * **If Rejected:** The flow captures the rejection reason, updates the Excel row `Status` to `Rejected`, and sends a notification email to the original submitter.

### 🛠️ Tools Used

* **Microsoft Power Automate:** (The central "brain" for the workflow logic).
* **Microsoft Forms:** (The user-facing data intake portal).
* **Excel Online:** (Used as a simple, cloud-based database/logbook).
* **Outlook / Teams:** (For handling notifications and the approval/reject actions).

## 📈 Business Impact

This system provides clear, measurable value for any operational team:

* **Standardizes** the ECR intake process across the entire organization.
* **Reduces administrative overhead** by 100% by eliminating manual data entry.
* **Creates an automated, auditable log** for quality control and process analysis.
* **Decreases approval turnaround time** from days to minutes by providing instant notifications and mobile-friendly approval options.
