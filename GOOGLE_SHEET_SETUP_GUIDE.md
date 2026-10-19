# Allo Innoware - Google Sheet Setup & Deployment Guide
**Recurring Task Tracking, Pending Reports & Escalation Automation Prototype**

This guide outlines how to deploy and operate the Allo Innoware Recurring Task Prototype in Google Sheets with complete automation in under 2 minutes.

---

## ⚡ Option 1: 1-Click Automated Deployment (Recommended)

You can generate the entire system (all 6 sheets, formulas, color formatting, column widths, data validations, and dummy data) automatically using the built-in setup script.

### Step 1: Create a Blank Google Sheet
1. Open Google Sheets ([sheets.new](https://sheets.new)).
2. Name the spreadsheet: `Allo Innoware - Recurring Operations System`.

### Step 2: Open Google Apps Script Editor
1. In the Google Sheets menu, click **Extensions** > **Apps Script**.
2. Rename the project to `Allo_Operations_Automation`.

### Step 3: Copy Code into Apps Script
1. Delete any boilerplate code inside `Code.gs`.
2. Copy the entire contents of [`google-apps-script/Code.js`](file:///e:/GitHub/Allo%20Innoware%20Assignment/google-apps-script/Code.js) and paste it into `Code.gs`.
3. Click the `+` icon next to **Files** > Select **HTML** > Name the file `ManagerAckDialog`.
4. Copy the entire contents of [`google-apps-script/ManagerAckDialog.html`](file:///e:/GitHub/Allo%20Innoware%20Assignment/google-apps-script/ManagerAckDialog.html) and paste it into `ManagerAckDialog.html`.
5. Click **Save** (💾 icon or `Ctrl + S`).

### Step 4: Run the 1-Click Initialization
1. In the Apps Script toolbar function dropdown, select **`setupAlloSystem`**.
2. Click **Run** (▶️).
3. Google will prompt for permissions:
   - Click **Review permissions** > Choose your account > Click **Advanced** > Click **Go to Allo_Operations_Automation (unsafe)** > Click **Allow**.
4. The script will create and format all 6 sheets with headers, formulas, and dummy data within 5 seconds.
5. Return to your Google Sheet tab and refresh the page (`F5`).
6. You will see the custom menu: **`🚀 Allo Innoware Ops`** in the top menu bar!

---

## 📋 Sheet Structure Overview

The system creates 6 dedicated sheets:

| Sheet Tab Name | Purpose & Audience | Key Features |
| :--- | :--- | :--- |
| **`01_Manager_Dashboard`** | Manager & Leadership Overview | Real-time KPI summary cards, employee compliance rates, active escalations |
| **`02_Employee_Pending_Tasks`** | **Primary Operating Interface** for Team Members | Single-point task list, proof entry (Col I), 1-click completion checkbox (Col K) |
| **`03_Task_Master`** | System Configuration & State | Master registry of tasks, frequencies (1, 7, 15, 30 days), cutoffs, current active cycle |
| **`04_Completion_Log`** | Immutable Audit Trail | Historical record of every completed cycle, timestamp, proof submitted, on-time status |
| **`05_Escalation_Log`** | SLA & Incident Management | Tracks Level 1 Manager Alerts, Manager Ack status & notes, Level 2 Leadership Escalations |
| **`06_System_Config`** | Environment Variables | Manager email, Leadership email, SLA cutoff hours, grace period, simulation mode |

---

## ⚙️ Trigger Setup (For Full Production Automation)

To run the system in fully automated production mode without manual button clicks:

### 1. Simple Trigger (Already Active)
- **`onEdit(e)`**: Automatically executes whenever an employee checks the **Mark Complete** box in `02_Employee_Pending_Tasks`. This operates in real time with zero configuration.

### 2. Time-Driven Automated Audit Trigger
To automatically scan for overdue tasks and fire Manager Alerts & Leadership Escalations:
1. In Apps Script, click the **Triggers** icon (clock icon ⏰ on the left sidebar).
2. Click **+ Add Trigger** (bottom right).
3. Configure the trigger:
   - **Choose which function to run**: `runAuditWorkflow`
   - **Choose which deployment should run**: `Head`
   - **Select event source**: `Time-driven`
   - **Select type of time based trigger**: `Hour timer`
   - **Select hour interval**: `Every hour` (or `Day timer` between `18:00 to 19:00`)
4. Click **Save**.

---

## 🧪 Running Test Cases in Google Sheets

You can verify all 8 requirements directly from the spreadsheet menu:

1. Click **`🚀 Allo Innoware Ops`** in the Google Sheets menu.
2. Under **Automated Test Suite**, you can run any individual test:
   - `Run Test 1: Recurring Cycle (7/15/30 Day)`
   - `Run Test 2: Single-Point Task Completion`
   - `Run Test 3: Daily Task Completion (WhatsApp)`
   - `Run Test 4: Same-Day Manager Alert`
   - `Run Test 5: Manager Action & Acknowledgement`
   - `Run Test 6: Leadership Escalation (SLA Breach)`
   - `Run Test 7: Verify SLA & Timing Logic`
   - `Run Test 8: De-duplication & Idempotency Check`
3. Or click **`⚡ Run Full Test Suite (Tests 1 - 8)`** to execute all 8 tests sequentially.
4. Alerts and logs will confirm test execution and display the before/after state transitions.

---

## 📬 Sharing & Submission Checklist
- Ensure the Google Sheet sharing permissions are set to:
  - **`hr.ops.allo@gmail.com`** added as **Editor**.
- Confirm that the `06_System_Config` sheet contains the correct operational emails.
