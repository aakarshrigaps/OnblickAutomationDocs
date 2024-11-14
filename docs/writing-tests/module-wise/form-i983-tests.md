# Form I-983 (Both Electronic and Ink Methods)

## Sanity Test

### Signature method types

1. Electronic Method
    - <p id="popup-flow">Popup Flow</p> Clicks on the "Copy section email" and stores the OTP and review link on the popup. Completes the respective section.
    - <p id="mail-flow">Mail Flow</p> It will open mail from mailhog in case of demo , mailinator in case of prod( If mail domain is not one of mailinator domains then switches to popup flow ) and stores OTP. Completes the respective section through the review link in mail.
2. <p id="ink-flow">Ink Method</p>
    - HR completes the respective section, downloads the form and upload.

### Scenarios

1. <p id="sanity-first">**Initiate primary from HR and complete**:</p>
    - Initiate the primary form by giving signatory authority details and select electronic or ink signature method type.
    - Complete section 1 and 2 i.e student information from ESS.
    - Complete section 3 and 4 using [Popup](#popup-flow) or [Mail](#mail-flow) or [ink](#ink-flow) flow.
    - Verify section 5 and 6 from ESS.
    - Complete section 5 and 6 using [Popup](#popup-flow) or [Mail](#mail-flow) or [ink](#ink-flow) flow.

1. <p id="sanity-second">**Initiate material change only and complete**:</p>
    - Initiate material change only.
    - Complete section 3 and 4 using [Popup](#popup-flow) or [Mail](#mail-flow) or [ink](#ink-flow) flow.
    - Verify section 5 and 6 from ESS.
    - Complete section 5 and 6 using [Popup](#popup-flow) or [Mail](#mail-flow) or [ink](#ink-flow) flow.

1. <p id="sanity-third"> **Initiate student evaluation only and complete**:</p>
    - Initiate student evaluation only.
    - Complete student evaluation from ESS.

1. **Delete all forms**
    - Delete all forms in I983 tab from HR to start the new flow.

1. <p id="sanity-fifth"> **Initiate material change with new form and complete**:</p>
    - Initiate Material change with new form.
    - Complete section 1 and 2 i.e student information from ESS.
    - Complete section 3 and 4 using [Popup](#popup-flow) or [Mail](#mail-flow) or [ink](#ink-flow) flow.
    - Verify section 5 and 6 from ESS.
    - Complete section 5 and 6 using [Popup](#popup-flow) or [Mail](#mail-flow) or [ink](#ink-flow) flow..

1. **Delete all forms**
    - Delete all forms in I983 tab from HR to start the new flow.

1. <p id="sanity-seventh">**Initiate student evaluation with new form and complete**:</p>
    - Initiate student evaluation with new form.
    - Complete section 1 and 2 i.e student information from ESS.
    - Complete section 3 and 4 using [Popup](#popup-flow) or [Mail](#mail-flow) or [ink](#ink-flow) flow.
    - Verify section 5 and 6 from ESS.
    - Complete section 5 and 6 using [Popup](#popup-flow) or [Mail](#mail-flow) or [ink](#ink-flow) flow.
    - Complete student evaluation from ESS.

## Material Change

1. **Material Change after primary form I-983**:
    - Initiate and complete primary form (refer [1st step in sanity test](#sanity-first)).
    - Initiate material change only and complete (refer [2nd step in sanity test](#sanity-second)).

2. **Material Change with New Form I-983**:
    - Initiate material change with new form and complete (refer [5th step in sanity test](#sanity-fifth)).

## Student Evaluation

1. **Student evaluation after primary form I-983**:
    - Initiate and complete primary form (refer [1st step in sanity test](#sanity-first)).
    - Initiate student evaluation only and complete (refer [3rd step in sanity test](#sanity-third)).

2. **Student evaluation with new form I-983**:
    - Initiate material change with new form and complete (refer [7th step in sanity test](#sanity-seventh)).

---

## Supervisor Flow

1. **Initiate primary from HR and complete**:
    - Initiate and complete primary form (refer [1st step in sanity test](#sanity-first)).

2. **Initiate material change from supervisor and complete**:
    - Supervisor initiates and completes the material change.

3. **Initiate student evaluation from supervisor and complete**:
    - Supervisor initiates and completes the student evaluation.

---
