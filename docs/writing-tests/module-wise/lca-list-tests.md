---
toc_depth: 3
---

# LCA List Documentation

## **Initiate LCA**

**Test Name**: `LCA List: Initiate LCA`

#### Description
This test case outlines the workflow for initiating a Labor Condition Application (LCA) for an employee. It includes steps for onboarding the employee, managing LCA numbers, linking projects, validating data, handling documents, and cleanup processes.

#### Steps


   1. **Onboard Employee**
      - Onboard the Employee.
      - Navigate to the LCA List.
 
   1. **Check LCA Number Availability**
      - Search the LCA number whether it is available or not in the system.
      - If it is already available, create an another LCA number for further processing.
   
   1. **Initiate LCA**
      - **Select Project**: Randomly choose between:
        - Linking existing project (if selected, add New Project from the candidate's profile).
        - Enter new project details manually.
      - choose Suggest a Code option.
      - Validate the linked project in LCA page.
      - Link the candidate with the LCA and validate their details.
      - Upload In-Progress/Certified LCA document.
      - Validate Place of Employment details.
      - Validate LCA Summary
   
   1. **Upload Manually uploaded PAF Documents**
      - Upload Complete PAF File (Scanned Version).
      - Upload Other Documents
   
   1. **Perform Actions for All PAF Documents**
      - Perform Actions for In-Progress/Certified LCA document, Manually uploaded PAF documents and system generated PAF documents.
      - Actions include View Document, Download Document and Update Document.

   1. **Perform Actions for LCA**
      - **Share PAF**: Share the PAF document to Recipient.
      - **Add a Note**: Add and Validate Note.
   
   1. **Update LCA**
      - Select Update LCA through main Actions.
      - Modify details in the LCA as needed and Validate changes.
      - Validate LCA Pill
   
   1. **Delete LCA**
      - Remove the LCA record if no longer required.
   
   1. **Delete Project**
      - Delete the linked project if it is no longer associated with any LCA.
   
   1. **Delete Employee**
      - Remove the employee record after all associated data has been handled.

     
 ----------------------------------------------------------------------


## **Fill LCA Information**

**Test Name**: `LCA List: Fill LCA`

#### Description
This test case outlines the workflow for filling in Labor Condition Application (LCA) information. It includes onboarding the employee, managing LCA numbers, validating linked data, handling documents, and performing actions related to the LCA process.

#### Steps

   1. **Onboard Employee**
      - Onboard the Employee.
      - Navigate to the LCA List.

   1. **Add Project**
      - Add Project for the Onboarded Employee from their profile.  
   
   1. **Check LCA Number Availability**
      - Search the LCA number whether it is available or not in the system.
      - If it is already available, create an another LCA number for further processing.
   
   1. **Upload LCA > Fill LCA Information**
      - Click on Upload button and Fill LCA Information.
      - Fill LCA Details, Save and go to that LCA page.
      - Validate the linked project in LCA page.
      - Link the candidate with the LCA and Validate their details.
      - Validate Place of Employment details.
      - Validate LCA Summary
   
   1. **Upload Manually uploaded PAF Documents**
      - Upload Complete PAF File (Scanned Version).
      - Upload Other Documents

   1. **Share LCA**
      - Click on Share LCA Button
      - Share and Validate the document which received Mail.
      - Validate the 
   
   1. **Perform Actions for All PAF Documents**
      - Perform Actions for In-Progress/Certified LCA document, Manually uploaded PAF documents and system generated PAF documents.
      - Actions include View Document, Download Document and Update Document.
   
   1. **Update LCA**
      - Select Update LCA through main Actions.
      - Modify details in the LCA as needed and Validate changes.
      - Validate LCA Pill
   
   1. **Perform Actions for LCA**
      - **Share PAF**: Share the PAF document to Recipient.
      - **Add a Note**: Add and Validate Note.
   
   1. **Delete LCA**
      - Remove the LCA record if no longer required.
   
   1. **Delete Project**
      - Delete the linked project if it is no longer associated with any LCA.
   
   1. **Delete Employee**
       - Remove the employee record after all associated data has been handled.

---------------------------------------------------------------------------------------

## **Parse LCA Document**

**Test Name**: `LCA List: Parse LCA`

#### Description
This test case outlines the workflow for uploading and parsing a Labor Condition Application (LCA). It includes onboarding the employee, managing LCA numbers, validating parsed data, handling documents, and performing actions related to the LCA process.

#### Steps

   1. **Onboard Employee**
      - Onboard the Employee.
      - Navigate to the LCA List.
   
   1. **Check LCA Number Availability**
      - Search the LCA number whether it is available or not in the system.
      - If it is already available, create an another LCA number for further processing.
   
   1. **Upload LCA > Parse LCA Document**
      - Click on Upload button and choose Parse LCA Document
      - Randomly select from the following options: 'Save' or 'Save & Auto Generate'.
      - Validate the parsed LCA details in the active LCAs section.
      - Validate LCA Summary
      - **Auto Generate PAF**: If "Save" is chosen,click on Auto Generate PAF button and ensure the Public Access File (PAF) is generated automatically.
      - Validate the linked project in LCA page.
      - Link the candidate with the LCA and Validate their details.
      - Validate Place of Employment details.
   
   1. **Perform Actions for All PAF Documents**
      - Perform Actions for In-Progress/Certified LCA document and system generated PAF documents.
      - Actions include View Document, Download Document and Update Document.
   
   1. **Perform Actions for LCA**
      - **Share PAF**: Share the PAF document to Recipient.
      - **Add a Note**: Add and Validate Note.
   
   1. **Delete LCA**
      - Remove the LCA record if no longer required.
   
   1. **Delete Project**
      - Delete the linked project if it is no longer associated with any LCA.
   
   1. **Delete Employee**
       - Remove the employee record after all associated data has been handled.



