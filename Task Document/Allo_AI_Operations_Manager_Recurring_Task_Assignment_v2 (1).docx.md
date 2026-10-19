                                                         **ALLO INNOWARE**

# **AI Operations Manager Assignment Test**

**Recurring Task Tracking, Pending Reports & Escalation Automation**

# **1\. Business Problem**

Allo Innoware has recurring operational tasks assigned to approximately 3–4 team members. Different tasks repeat at different frequencies such as Daily, every 7 days, every 15 days and every 30 days.

Some recurring tasks require the employee to create or update a ticket on an external/internal portal. Daily tasks may instead require an operational action such as sharing an update in a WhatsApp group.

We need a Google Sheets-based system that tells each employee what is currently pending, captures completion with minimum duplicate work, alerts the manager when work is not completed on time, and eventually escalates unresolved items to leadership.

# **2\. Assignment Objective**

Create a working prototype of this recurring-task system using Google Sheets as the primary operating interface. You may use Google Apps Script, formulas and ChatGPT where required.

The objective is to demonstrate the complete flow from task becoming due → employee action → completion update → pending detection → manager alert → leadership escalation.

# **3\. Minimum Scenario to Build**

| Dummy Task | Assigned To | Frequency | Expected Completion | Proof / Update |
| :---- | :---- | :---- | :---- | :---- |
| Daily Operations Update | Employee A | Daily | Required each working day | Candidate to propose method |
| Portal Task A | Employee B | Every 7 days | Complete task and update ticket | Ticket ID |
| Portal Task B | Employee C | Every 15 days | Complete task and update ticket | Ticket ID |
| Portal Task C | Employee D | Every 30 days | Complete task and update ticket | Ticket ID |

You may create additional dummy task cases if required to prove that your logic works correctly.

# **4\. Core Requirements**

**Recurring cycle logic:** Every task must become due again automatically after its configured cycle period is completed. For example, a 7-day task should enter the next cycle after the current cycle is completed and become due according to the configured 7-day recurrence logic. The employee should not manually calculate the next due date.

**Employee pending report:** Each employee must have a clear report showing the tasks currently requiring action, including the task, due date/cycle, status and required completion proof.

**Single-point updating / no duplication of effort:** The employee should update completion information only once. Preferably, the same report from which the employee sees the pending task should allow the employee to enter the Ticket ID or other completion information. The employee should not have to update the same task in multiple sheets.

**Ticket-based task completion:** For recurring tasks that require a portal ticket, the employee should be able to enter the Ticket ID against that task. The system should use this update as part of the completion logic.

**Daily-task completion method:** Daily tasks may not have a Ticket ID. You must propose the most practical way to capture whether a daily task, such as sharing an update in a WhatsApp group, has actually been completed. Explain what the employee needs to do and how the system will record completion with minimum manual effort.

**Completion tracking:** The system must capture who completed the task, when it was completed and the relevant Ticket ID/proof/update. The completion should close the current cycle and allow the next cycle to be tracked automatically.

**Manager visibility:** The manager must be able to see which team members have pending or overdue recurring tasks without manually checking each employee separately.

**Manager acknowledgement:** Where the manager is required to review a pending-task report or escalation, the system should capture that the manager has reviewed/acknowledged it.

# **5\. Expected Google Sheet**

Create the Google Sheet structure required to operate the above system. At minimum, it should contain a recurring task master, a usable employee pending-task report/view, and the information required for manager monitoring and escalation.

You are expected to decide the exact sheets, columns, formulas and automation structure. Keep the employee-facing process simple. The employee should primarily work from one place rather than moving between multiple sheets.

# **6\. Automation & Escalation Logic to Demonstrate**

This is the most important part of the assignment. Build working test cases and demonstrate how your proposed system behaves.

**Test 1 — Recurring cycle**  
Complete a dummy 7-day, 15-day or 30-day task and demonstrate how the system closes that cycle and prepares/tracks the next cycle automatically.

**Test 2 — Single-point completion**  
Demonstrate that an employee can see a pending task and update its Ticket ID/completion from one operating location without repeating the same update elsewhere.

**Test 3 — Daily task**  
Demonstrate your proposed method for recording completion of a daily task that does not naturally generate a Ticket ID. The design of this method is part of the test.

**Test 4 — Same-day manager alert**  
Create a test case where an employee does not complete a task by the required time. The manager should automatically receive an email on the same day informing them which employee/task is still pending.

**Test 5 — Manager action / acknowledgement**  
Define what the manager is expected to do after receiving the pending-task email. The system should be able to determine whether the manager has reviewed/acknowledged the issue and whether the underlying task was subsequently completed.

**Test 6 — Leadership escalation**  
Create a test case where the pending task remains unresolved beyond a defined time, or the required manager action/review does not happen. The system should then automatically escalate the issue to the leadership team.

**Test 7 — Escalation timing logic**  
You must propose the actual timing/SLA logic for manager alerts and leadership escalation. For example: when should the first manager email go, how long should the manager/employee get to resolve it, when should leadership be informed, and how should the system avoid unnecessary repeated emails? Explain the reasoning behind your design.

**Test 8 — No duplicate alerts or work**  
Run the automation more than once and demonstrate that it does not create duplicate task cycles, duplicate completion entries or unnecessary duplicate escalation emails.

# **7\. What You Need to Submit**

* Working Google Sheet prototype.  
* Google Apps Script / automation used, if applicable.  
* Daily Task Completion Tracking  
* Manager Alerts & Leadership Escalation (SLA)  
* Working Demonstration / Test Cases

**We are evaluating whether you can convert a real operational requirement into a simple, reliable and automated working system.**

### **Submission**

Kindly share your completed assignment, work portfolio, and contact details at [hr.ops.allo@gmail.com](mailto:hr.ops.allo@gmail.com)

Please ensure that Editor access is provided to the submitted Google Sheet so we can test and verify the working automation.

