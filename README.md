# Allo Innoware - AI Operations Manager Assignment Solution
**Recurring Task Tracking, Pending Reports & Escalation Automation**

Welcome to the complete, production-grade prototype for the **Allo Innoware AI Operations Manager Assignment**. This solution converts real-world recurring task management and SLA escalations into an automated, zero-friction operating system using Google Sheets and Google Apps Script.

---

## 📂 Repository Structure

```text
├── Allo_AI_Operations_Manager_Recurring_Task_Assignment_v2 (1).docx.md  # Original assignment requirements
├── SUBMISSION_REPORT.md             # Complete submission document covering architecture, SLAs, and all 8 tests
├── GOOGLE_SHEET_SETUP_GUIDE.md      # Step-by-step 2-minute deployment guide
├── test_simulation.py               # Standalone Python verification suite for Tests 1-8
├── google-apps-script/
│   ├── Code.js                      # Core Apps Script code (1-click sheet builder, triggers, SLA audit)
│   ├── ManagerAckDialog.html        # Manager Acknowledgement UI modal dialog
│   └── appsscript.json              # Apps Script manifest and OAuth scopes
└── README.md                        # Project overview and quickstart
```

---

## 🚀 Key Features

1. **Single-Point Employee Interface (`02_Employee_Pending_Tasks`):**
   - Team members view pending tasks, enter Ticket ID or WhatsApp update proof in Column I, and check Column K (`Mark Complete`).
   - The system handles the rest: saves the completion audit log, increments the cycle, and rolls forward to the next due date. Zero duplicate effort.
2. **Automatic Recurrence Engine (`03_Task_Master`):**
   - Configurable recurrence intervals (Daily, 7 days, 15 days, 30 days).
   - Weekend-skipping intelligence for working-day tasks (Monday-Friday).
3. **Daily Task Completion Method:**
   - Detailed proposal and working prototype for tracking daily WhatsApp group updates with zero ticket overhead.
   - Includes support for an inbound WhatsApp webhook (`doPost(e)`).
4. **Intelligent Escalation Engine (`05_Escalation_Log`):**
   - **T0:** Cutoff time (17:00 IST for Daily, 18:00 IST for Portal tasks).
   - **T1:** Level 1 Same-Day Manager Alert email.
   - **T2:** 18-hour manager grace window.
   - **T3:** Level 2 Leadership Escalation email at 14:00 IST next business day if still unresolved.
5. **Manager Acknowledgement & Dashboard (`01_Manager_Dashboard`):**
   - Live KPI cards, team compliance rates, and 1-click acknowledgement with review comments.
6. **Strict De-duplication (Idempotency):**
   - Deterministic composite keys (`TaskId_Cycle_Level`) ensure running repeated audits never generates duplicate emails, duplicate rows, or duplicate cycles.

---

## ⚡ Quickstart

### 1. Run the Python Simulation Suite
Verify all 8 test cases locally:
```bash
python test_simulation.py
```

### 2. Deploy into Google Sheets
Follow the instructions in [`GOOGLE_SHEET_SETUP_GUIDE.md`](./GOOGLE_SHEET_SETUP_GUIDE.md):
1. Open a blank Google Sheet at [sheets.new](https://sheets.new).
2. Go to **Extensions** > **Apps Script**.
3. Paste [`google-apps-script/Code.js`](./google-apps-script/Code.js) and [`google-apps-script/ManagerAckDialog.html`](./google-apps-script/ManagerAckDialog.html).
4. Run `setupAlloSystem()` to auto-generate all 6 sheets with formulas, formatting, validations, and test data in 5 seconds!

---

## 📄 Submission Details
- **Submission Document:** Read the full [`SUBMISSION_REPORT.md`](./SUBMISSION_REPORT.md).
- **Recipient:** [hr.ops.allo@gmail.com](mailto:hr.ops.allo@gmail.com)
- **Permissions:** Provide **Editor** access to the deployed Google Sheet prototype.
