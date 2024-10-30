---
toc_depth: 3
---

# Timesheets

## **Filters Validation**

### **Purpose**
To validate the functionality of filters in both the **Calendar View** and **List View** of the timesheet module by applying, clearing, and verifying results across different filter sets.

### **Test Steps**

1. **Navigate to Timesheets**:
    - Access the Timesheets section via the appropriate URL.

2. **Switch Views**:
    - Toggle between **Calendar View** and **List View** for testing filter functionality in each respective view.

3. **Apply Filters**:
    - Select and apply various filters, including both single-selection and multi-selection scenarios, across **Calendar View** and **List View**.
    - The filters may include parameters such as employee, project, date range, and more.

4. **Validate Filters**:
    - Confirm that the correct timesheet entries are displayed based on the applied filters in both views.
    - Ensure the filters accurately reflect timesheet entries and return appropriate results.

5. **Repeat for All Filter Sets**:
    - Iterate through multiple filter sets in both views, testing individual and combined filter options to ensure comprehensive coverage.

## Automation Script Scenarios

### Scenario 1

#### Timesheets

1. **Add a timesheet (ESS)**:
    - Type: TimesheetsOnly
    - Date Range: Previous month (up to 3 days)
    - Project: None
    - Task: Any task

2. **Send for approval**:
    - Sign out of ESS and sign in as HR.
    - Reject the timesheet.

3. **Add another timesheet (HR)**:
    - Same date range but with different details.

4. **Submit and approve**.

5. **Delete timesheets** (HR).

6. **Delete candidate** (HR).

---

#### Expenses

1. **Add an expense (ESS)**:
    - Type: ExpensesOnly
    - Date Range: Previous month (up to 3 days)
    - Project: None
    - Task: Any task

2. **Send for approval**:
    - Sign out of ESS and sign in as HR.
    - Reject the expense.

3. **Add another expense (HR)**:
    - Same date range but with different details.

4. **Submit and approve**.

5. **Delete expenses** (HR).

6. **Delete candidate** (HR).

---

#### Timesheets and Expenses

1. **Add a timesheet and expense (ESS)**:
   - Type: TimesheetsAndExpenses
   - Date Range: Previous month (up to 3 days)
   - Project: None
   - Task: Any task

2. **Send for approval**:
   - Sign out of ESS and sign in as HR.
   - Approve the timesheet and reject the expense.

3. **Resubmit expenses** (ESS).

4. **Approve expenses** (HR).

5. **Delete timesheets and expenses** (HR).

6. **Delete candidate** (HR).

### Scenario 2

#### Timesheets

1. **Add a project (HR)**:
    - Project type: OvertimeApplicable.

2. **Add a timesheet (HR)**:
    - Type: TimesheetsOnly
    - Date Range: Any future month (up to 5 days).
    - Include the project from step 1.
    - No task but include overtime hours.

3. **Submit and approve**.

4. **Request for edit** (ESS).

5. **Approve edit request** (HR).

6. **Update and send for approval** (ESS).

7. **Approve timesheet** (HR).

8. **Delete timesheet** (HR).

9. **Delete candidate** (HR).

10. **Delete project** (HR).

---

#### Expenses

1. **Add a project (HR)**:
    - Project type: OvertimeApplicable.

2. **Add an expense (HR)**:
    - Type: ExpensesOnly
    - Date Range: Any future month (up to 5 days).
    - Include the project from step 1.

3. **Submit and approve**.

4. **Request for edit** (ESS).

5. **Approve edit request** (HR).

6. **Update and send for approval** (ESS).

7. **Approve expense** (HR).

8. **Delete expense** (HR).

9. **Delete candidate** (HR).

10. **Delete project** (HR).

---

#### Timesheets and Expenses

1. **Add a project (HR)**.

2. **Add a timesheet (HR)**:
    - Type: TimesheetsAndExpenses
    - Date Range: Future month (up to 5 days).
    - Include the project from step 1.
    - No task.

3. **Submit and approve**.

4. **Request for edit** (ESS):
    - Edit both timesheets and expenses.

5. **Approve and reject edit requests** (HR):
    - Approve edit request for timesheet.
    - Reject edit request for expenses.

6. **Update and send for approval** (ESS).

7. **Approve timesheet** (HR).

8. **Delete timesheets and expenses** (HR).

9. **Delete candidate** (HR).

### Scenario 3

#### Timesheets

1. **Onboard another candidate (HR)**:
    - Make this candidate a supervisor for the first candidate.

2. **Enable ESS and login as supervisor**:
    - Reset the password and login as the supervisor.

3. **Add a timesheet (Supervisor)**:
    - Type: TimesheetsOnly
    - Date Range: Any dates in the current month (future or past).
    - No project, no task.

4. **Save**.

5. **Approve the timesheet** (Supervisor).

6. **Request for re-submit** (HR).

7. **Resubmit the timesheet** (ESS).

8. **Approve as HR** (not the supervisor).

9. **Delete both candidates** (HR).

---

#### Expenses

1. **Onboard another candidate (HR)**:
    - Make this candidate a supervisor for the first candidate.

2. **Enable ESS and login as supervisor**:
    - Reset the password and login as the supervisor.

3. **Add an expense (Supervisor)**:
    - Type: ExpensesOnly
    - Date Range: Any dates in the current month (future or past).
    - No project, no task.

4. **Save**.

5. **Approve the expense** (Supervisor).

6. **Request for re-submit** (HR).

7. **Resubmit the expense** (ESS).

8. **Approve as HR** (not the supervisor).

9. **Delete both candidates** (HR).

---

#### Timesheets and Expenses

1. **Onboard another candidate (HR)**:
    - Make this candidate a supervisor for the first candidate.

2. **Enable ESS and login as supervisor**:
    - Reset the password and login as the supervisor.

3. **Add a timesheet (Supervisor)**:
    - Type: TimesheetsAndExpenses
    - Date Range: Any dates in the current month (future or past).
    - No project, no task.

4. **Save**.

5. **Approve timesheets and reject/delete expenses** (Supervisor).

6. **Request for re-submit** (Supervisor):
    - Follow all 3 steps above.

7. **Resubmit the timesheet** (ESS).

8. **Approve as HR** (not the supervisor).

9. **Delete timesheets and both candidates** (HR).

### Scenario 4

#### Timesheets

1. **Add a timesheet (ESS)**:
    - Type: TimesheetsOnly
    - Date Range: Previous month (up to 3 days).
    - Project: Include a project with **ThirdPartyApproval** (add approver name and email).
    - Task: Any task.

2. **Send for approval**:
    - Sign out of ESS and sign in as HR.

3. **Approve as third party**.

4. **Request for re-submit** (HR).

5. **Re-submit** (ESS).

6. **Approve again** (HR).

7. **Delete timesheet** (HR).

8. **Delete candidate** (HR).

---

#### Expenses

1. **Add an expense (ESS)**:
    - Type: ExpensesOnly
    - Date Range: Previous month (up to 3 days).
    - Project: Include a project with **ThirdPartyApproval** (add approver name and email).
    - Task: Any task.

2. **Send for approval**:
    - Sign out of ESS and sign in as HR.

3. **Approve as third party**.

4. **Request for re-submit** (HR).

5. **Re-submit** (ESS).

6. **Approve again** (HR).

7. **Delete expense** (HR).

8. **Delete candidate** (HR).

---

#### Timesheets and Expenses

1. **Add a timesheet and expense (ESS)**:
    - Type: TimesheetsAndExpenses
    - Date Range: Previous month (up to 3 days).
    - Project: Include a project with **ThirdPartyApproval** (add approver name and email).
    - Task: Any task.

2. **Send for approval**:
    - Sign out of ESS and sign in as HR.

3. **Approve as third party**.

4. **Request for re-submit** (HR).

5. **Re-submit** (ESS).

6. **Approve again** (HR).

7. **Delete timesheet and expense** (HR).

8. **Delete candidate** (HR).
