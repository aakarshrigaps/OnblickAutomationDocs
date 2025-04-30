---
toc_depth: 3
---

# I-9 Linkage Documentation

## Overview
This document provides detailed guidance on managing I-9 Linkage flows, including retrieving settings, initiation, and various flows through different work authorizations. It covers all flows, including first uploading work authorization and then completing I-9, and vice versa.

---

### H1BLinkageFlow
#### Description
This test validates the workflow for completing an H-1B petition, creating and uploading the necessary packet documents for the approval scenario. It ensures that all stages are managed accurately. This test plan includes all H-1B work authorizations and all H-1B Linkage scenarios.

#### Steps  

1. **Login as HR**  
    - Access the HR portal.  

2. **Delete Employee**  
        - Delete the record of the employee if the email is already used during onboarding.  

3. **Navigate to the I-9 Settings**  
    - Go to **Settings** section.  
    - Click on **I-9/E-Verify**.  

4. **Upload Approval Copy**  
    - Upload the H-1B approval copy based on the given input (797A/797B).  

5. **Complete Section-1 Linkage**  
    - Section 1 is completed based on the work authorization in the onboarding details, with validation occurring at this stage.  

6. **Complete Section-2**  
    - Section 2 is completed based on the work authorization in the onboarding details, with validation occurring at this stage.  

7. **Go To Work Auth Tab**  
    - Navigate to the corresponding work authorization in the Employee Profile tab using the onboarding details.  

8. **Upload H1B In Work Auth**  
    - Upload the H-1B work authorization document in the Work Auth tab based on onboarding details, either before or after completing I-9. 

9. **Validate Work Auth Details**  
    - Validate all the details in the pill generated after completing the linkage flow.  

10. **Delete Employee Record**  
    - Deletes the employee record once the process is complete.  

---

### LinkageFlow
#### Description
This test validates the workflow for completing a work authorization other than visa types (H-1B, L-1, E-3, and TN), creating and uploading the necessary packet documents for the approval scenario. It ensures that all stages are managed accurately. This test plan includes all non-H-1B work authorizations and all H-1B Linkage scenarios.

#### Steps  

1. **Login as HR**  
    - Access the HR portal.  

2. **Delete Employee**  
    - Delete the record of the employee if the email is already used during onboarding.  

3. **Navigate to the I-9 Settings**  
    - Go to **Settings** section.  
    - Click on **I-9/E-Verify**.  

4. **Upload Approval Copy**  
    - Upload the Work Auth approval copy based on the given input.  

5. **Complete Section-1 Linkage**  
    - Section 1 is completed based on the work authorization in the onboarding details, with validation occurring at this stage.  

6. **Complete Section-2**  
    - Section 2 is completed based on the work authorization in the onboarding details, with validation occurring at this stage.  

7. **Go To Work Auth Tab**  
    - Navigate to the corresponding work authorization in the Employee Profile tab using the onboarding details.  

8. **Upload Work Authorization**  
    - Upload the work authorization document in the Work Auth tab based on onboarding details, either before or after completing I-9. 

9. **Validate Work Auth Details**  
    - Validate all the details in the pill generated after completing the linkage flow.  

10. **Delete Employee Record**  
    - Deletes the employee record once the process is complete.  

---

### VisaTypeLinkageFlow
#### Description
This test validates the workflow for completing a visa type (L-1, E-3, and TN), creating and uploading the necessary packet documents for the approval scenario. It ensures that all stages are managed accurately and that the system properly cleans up after rejection. This test plan includes all L-1, E-3, and TN work authorizations, as well as all H-1B Linkage scenarios.

#### Steps  

1. **Login as HR**  
    - Access the HR portal.  

2. **Delete Employee**  
    - Delete the record of the employee if the email is already used during onboarding.  

3. **Navigate to the I-9 Settings**  
    - Go to **Settings** section.  
    - Click on **I-9/E-Verify**.  

4. **Upload Approval Copy**  
    - Upload the approval copy of the visa type based on the given input preference.  

5. **Complete Section-1 Linkage**  
    - Section 1 is completed based on the work authorization in the onboarding details, with validation occurring at this stage.  

6. **Complete Section-2**  
    - Section 2 is completed based on the work authorization in the onboarding details, with validation occurring at this stage.  

7. **Go To Work Auth Tab**  
    - Navigate to the corresponding work authorization in the Employee Profile tab using the onboarding details.  

8. **Upload Visa Type In Work Auth**  
    - Upload the Visa type work authorization document in the Work Auth tab based on onboarding details, either before or after completing I-9. 

9. **Validate Work Auth Details**  
    - Validate all the details in the pill generated after completing the linkage flow.  

10. **Delete Employee Record**  
    - Deletes the employee record once the process is complete.  
