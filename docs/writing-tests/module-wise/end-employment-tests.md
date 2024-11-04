# End Employment

## Test Scenarios

### **Current Date and Validations in HR and ESS**
   - **Description**: End an employee's employment with the current date and verify system responses in both HR and ESS.
   - **Steps**:
     1. Navigate to the HR portal and search for the employee.
     2. Set the end date to today’s date.
     3. Save the changes.
     4. Validate that the employee is "Active" in the HR system until the end of the day.
     5. Attempt to log in to ESS with the employee's credentials.
     6. Verify that ESS login remains active until the end of the day.
   - **Expected Result**: 
     - The employee's status should remain "Active" until the end of the day.
     - ESS login should be available until the end of the day, after which status changes to "Terminated" and access is denied.

### **Future Date and Validations in HR and ESS**
   - **Description**: Set a future date for termination and verify behavior in HR and ESS.
   - **Steps**:
     1. Set the end date to a future date.
     2. Save the changes.
     3. Validate that the employee remains "Active" in HR.
     4. Ensure the employee can log in to ESS until the future termination date.
   - **Expected Result**: 
     - Status remains "Active" until the future date.
     - ESS login and services are accessible until the termination date, after which access is disabled.

### **Past Date and Validations in HR and ESS**
   - **Description**: End employment with a past date and validate that ESS access is restricted.
   - **Steps**:
     1. Set the end date to a past date.
     2. Save the changes.
     3. Confirm the employee’s status is immediately changed to "Terminated."
     4. Attempt to log in to ESS and verify login is disabled.
   - **Expected Result**:
     - Status changes to "Terminated" immediately.
     - ESS login is disabled, and appropriate error messages are displayed.
