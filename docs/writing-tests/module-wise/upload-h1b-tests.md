---
toc_depth: 3
---

# H-1B Documentation

## **Upload H-1B Scenarios**

### **Approval (I-797A/B) Received**

**Test Name**: `H1BTest_ApprovalReceived_Automation`

#### Description
This test validates the workflow for uploading an H-1B approval for an onboarded employee. It ensures that the process from HR login, candidate onboarding, and H-1B upload to employee record deletion is functioning as expected.

#### Steps

   1. **Upload H-1B**
      - Petition Processing Type: General.
      - Petition Filed by: Employer.
      - Petition Status type: H-1B Approval (I-797A/B) Received.
      - Select H-1B Approval Type: I-797A.
      - Uploads the H-1B Approval document.
      - Perform Actions(include View Document, Download Document).

   1. **Port of Entry**
      - Select Port of Entry through main Actions. 
      - Select radio option for "Does this candidate have a valid H-1B visa?" as No.
      - Completes the Port of Entry process.
      - Validate Uploaded Data.

   1. **Update Interview Status**
      - Select Update Interview Status through main Actions.
      - Choose Interview Status: Visa Stamped.
      - Updates the Interview status.
      - Validate Uploaded Data.
      - Perform Actions(include View Document, Download Document, Share Document).

   1. **Port of Entry Information**
      - Select Port of Entry Information through main Actions.
      - Completes the port of entry information.
      - Validate Uploaded Data.

   1. **Update Port of Entry Status**
      - Select Update Port of Entry Status through main Actions.
      - Choose Port of Entry Status: Entry Approved.
      - Updates the employee's Port of Entry status.
      - Validate Uploaded Data.
      - Perform Actions(include View Document, Download Document, Share Document).

   1. **Port of Exit**
      - Select Update Port of Exit through main Actions.
      - Select radio option for "Does this candidate have a valid H-1B visa?" as Yes.
      - Completes the Port of Exit process.
      - Validate Uploaded Data.
      - Perform Actions(include View Document, Download Document, Share Document).

   1. **Delete H-1B Record**
      - Select Delete H-1B through main Actions.
      - Deletes the uploaded H-1B information.

   1. **Delete Employee Record**
      - Deletes the employee record once the process is complete.

----------------------------------------------------------------------------------------

### **Denial Received**

**Test Name**: `H1BTest_DenialReceived_Automation`

#### Description
This test validates the workflow for uploading an H-1B denial for an onboarded employee. It covers the process from HR login, candidate onboarding, and H-1B denial upload to employee record deletion.

#### Steps

   1. **Upload H-1B**
      - Petition Processing Type: General.
      - Petition Filed by: Employer.
      - Petition Status type: H-1B Denial Received.
      - Uploads the Denial Notice.
      - Select Further Action:End Employment.
      - Select Radio button: Employee Terminated.
      - Upload termination letter and Save.
      - Validate Uploaded Data.
      - Perform Actions(include View Document, Download Document).

   1. **Delete H-1B Record**
      - Select Delete H-1B through main Actions.
      - Deletes the uploaded H-1B information.

   1. **Delete Employee Record**
      - Deletes the employee record once the process is complete.

----------------------------------------------------------------------------------------

### **Receipt Notice(I-797C) Received**

**Test Name**: `H1BTest_I797CReceived_Automation`

#### Description
This test simulates the workflow for handling the H-1B petition process, including uploading the I-797C notice, requesting H-1B petition documents, updating employee details, and completing the process for approval or denial.

#### Steps
   1. **Upload H-1B**
      - Petition Processing Type: General.
      - Petition Filed by: Employer.
      - Petition Status type: H-1B Receipt Notice(I-797C) Received.
      - Uploads the Receipt Notice(I-797C).
      - Validate Uploaded Data.
      - Perform Actions(include View Document, Download Document,Share Document).

   1. **Request H-1B Petition Documents**
      - Request Documents of H-1B petition.
      - Select Documents and Enter Reviewer Details.

   1. **Complete H-1B Petition Beneficiary Info(ESS)**
      - Completes the Beneficiary Information for the H-1B petition by Employee.

   1. **Review H-1B Petition Beneficiary Information(HR)**
      - Reviews and Approve the beneficiary information by Reviewer and HR.
      - Validate H-1B Packet Documents by HR which are uploaded by Employee.

   1. **Initiate Form I-129**
      - 

   1. **Upload H-1B Approval Notice**
      - Select H-1B Approved through main Actions. 
      - Select H-1B Approval Type: I-797B
      - Uploads the H-1B Approval document.
      - Validate Uploaded Data.
      - Perform Actions(include View Document, Download Document).

   1. **Port of Entry**
      - Select Port of Entry through main Actions. 
      - Select radio option for "Does this candidate have a valid H-1B visa?" as No.
      - Completes the Port of Entry process.
      - Validate Uploaded Data.

   1. **Update Interview Status**
      - Select Update Interview Status through main Actions.
      - Choose Interview Status: Visa Stamped.
      - Updates the Interview status.
      - Validate Uploaded Data.
      - Perform Actions(include View Document, Download Document, Share Document).

   1. **Port of Entry Information**
      - Select Port of Entry Information through main Actions.
      - Completes the port of entry information.
      - Validate Uploaded Data.

   1. **Update Port of Entry Status**
      - Select Update Port of Entry Status through main Actions.
      - Choose Port of Entry Status: Entry Approved.
      - Updates the employee's Port of Entry status.
      - Validate Uploaded Data.
      - Perform Actions(include View Document, Download Document, Share Document).

   1. **Port of Exit**
      - Select Update Port of Exit through main Actions.
      - Select radio option for "Does this candidate have a valid H-1B visa?" as Yes.
      - Completes the Port of Exit process.
      - Validate Uploaded Data.
      - Perform Actions(include View Document, Download Document, Share Document).

   1. **Delete H-1B Record**
      - Select Delete H-1B through main Actions.
      - Deletes the uploaded H-1B information.

   1. **Delete Employee Record**
      - Deletes the employee record once the process is complete.

----------------------------------------------------------------------------------------

### **NOID Received**

**Test Name**: `H1BTest_NOIDReceived_Automation`

#### Description
This test validates the process of handling a NOID for an H-1B petition. It includes steps to upload the NOID, respond to it, and approve the petition.

#### Steps
   1. **Upload H-1B**
      - Petition Processing Type: General.
      - Petition Filed by: Employer.
      - Petition Status type: H-1B NOID Received.
      - Uploads H-1B NOID Notice.
      - Validate Uploaded Data.
      - Perform Actions(include View Document, Download Document,Share Document).

   1. **Upload NOID Response Packet**
      - Upload Packet.
      - Perform Actions(include View Document, Download Document,Share Document).

   1. **Upload NOID Response Tracking Information**
      - Uploads tracking details for the NOID response packet.
      - Validate Uploaded Data.
      - Perform Actions(include View Document, Download Document,Share Document).

   1. **Request and Upload Individual H-1B Supporting Documents**
      - This method handles the process of Requesting and uploading individual H-1B Supporting documents(Current Work Authorization, Beneficiary, RTC, and Client documents).
      - Validate Uploaded Data.

   1. **Actions for Supporting H-1B Documents**
      - Perform Actions(include View Document, Download Document,Edit Document,Share Document) for all H-1B Supporting documents submitted by HR.

   1. **Upload H-1B Approval Notice**
      - Select H-1B Approved through main Actions. 
      - Select H-1B Approval Type: I-797A
      - Uploads the H-1B Approval document.
      - Validate Uploaded Data.
      - Perform Actions(include View Document, Download Document).

   1. **Port of Entry**
      - Select Port of Entry through main Actions. 
      - Select radio option for "Does this candidate have a valid H-1B visa?" as Yes.
      - Completes the Port of Entry process.
      - Validate Uploaded Data.

   1. **Update Port of Entry Status**
      - Select Update Port of Entry Status through main Actions.
      - Choose Port of Entry Status: Entry Approved.
      - Updates the employee's Port of Entry status.
      - Validate Uploaded Data.
      - Perform Actions(include View Document, Download Document, Share Document).

   1. **Port of Exit**
      - Select Update Port of Exit through main Actions.
      - Select radio option for "Does this candidate have a valid H-1B visa?" as Yes.
      - Completes the Port of Exit process.
      - Validate Uploaded Data.
      - Perform Actions(include View Document, Download Document, Share Document).

   1. **Delete H-1B Record**
      - Select Delete H-1B through main Actions.
      - Deletes the uploaded H-1B information.

   1. **Delete Employee Record**
      - Deletes the employee record once the process is complete.

----------------------------------------------------------------------------------------

### **NOIR Received**

**Test Name**: `H1BTest_NOIRReceived_Automation`

#### Description
This test validates the process of handling a NOIR for an H-1B petition. It includes steps to upload the NOIR, respond to it, and approve.

#### Steps
   1. **Upload H-1B**
      - Petition Processing Type: General.
      - Petition Filed by: Employer.
      - Petition Status type: H-1B NOIR Received.
      - Uploads H-1B NOID Notice along with Approved H-1B (I-797A/B) for which you received NOIR status from USCIS.
      - Validate Uploaded Data.
      - Perform Actions(include View Document, Download Document,Share Document).

   1. **Upload NOIR Response Packet**
      - Upload Packet.
      - Perform Actions(include View Document, Download Document,Share Document).

   1. **Upload NOIR Response Tracking Information**
      - Uploads tracking details for the NOID response packet.
      - Validate Uploaded Data.
      - Perform Actions(include View Document, Download Document,Share Document).

   1. **Request and Upload Multiple H-1B Supporting Documents**
      - This method handles the process of requesting and uploading multiple H-1B packet documents, such as Current Work Authorization, Beneficiary, RTC and Client Documents. 
      - Validate Uploaded Data.
      
   1. **Upload H-1B Approval Notice**
      - Select H-1B Approved through main Actions. 
      - Select H-1B Approval Type: I-797A.
      - Uploads the H-1B Approval document.
      - Validate Uploaded Data.
      - Perform Actions(include View Document, Download Document).

   1. **Port of Entry**
      - Select Port of Entry through main Actions. 
      - Select radio option for "Does this candidate have a valid H-1B visa?" as Yes.
      - Completes the Port of Entry process.
      - Validate Uploaded Data.

   1. **Update Port of Entry Status**
      - Select Update Port of Entry Status through main Actions.
      - Choose Port of Entry Status: Entry Approved.
      - Updates the employee's Port of Entry status.
      - Validate Uploaded Data.
      - Perform Actions(include View Document, Download Document, Share Document).

   1. **Port of Exit**
      - Select Update Port of Exit through main Actions.
      - Select radio option for "Does this candidate have a valid H-1B visa?" as Yes.
      - Completes the Port of Exit process.
      - Validate Uploaded Data.
      - Perform Actions(include View Document, Download Document, Share Document).

   1. **Delete H-1B Record**
      - Select Delete H-1B through main Actions.
      - Deletes the uploaded H-1B information.

   1. **Delete Employee Record**
      - Deletes the employee record once the process is complete.

----------------------------------------------------------------------------------------

### **Petition Sent to USCIS**

**Test Name**: `H1BTest_PetitionSentToUSCIS`

#### Description
This test validates the process for managing H-1B petition documents required by USCIS, handling the potential for case rejection, and ensuring the correct documentation is uploaded and reviewed.
#### Steps
   1. **Upload H-1B**
      - Petition Processing Type: General.
      - Petition Filed by: Employer.
      - Petition Status type: H-1B petition sent to USCIS.
      - Upload Tracking Information.
      - Validate Uploaded Data.

   1. **Upload All H-1B Supporting Documents (HR)**
      - Upload H-1B Supporting documents, including petitioner documents, current work authorization documents,beneficiary documents, right to control(RTC) documents, and client documents.
      - Validate Uploaded Data.

   1. **Actions for Supporting H-1B Documents (HR)**
      - Perform Actions(include View Document, Download Document,Edit Document,Share Document) for all H-1B Supporting documents submitted by HR.

   1. **Case Rejected by USCIS**
      - Select Case Rejected and Upload Case Rejection Document.
      - Validate Uploaded Data.

   1. **Delete H-1B Record**
      - Select Delete H-1B through main Actions.
      - Deletes the uploaded H-1B information.

   1. **Delete Employee Record**
      - Deletes the employee record once the process is complete.

----------------------------------------------------------------------------------------

### **RFE Received**

**Test Name**: `H1BTest_RFEReceived_Automation`

#### Description
This test validates the process of handling a RFE for an H-1B petition. It includes steps to upload the RFE, respond to it, and approve the petition.

#### Steps
   1. **Upload H-1B**
      - Petition Processing Type: General.
      - Petition Filed by: Employer
      - Petition Status type: H-1B RFE Received.
      - Uploads H-1B RFE Notice.
      - Validate Uploaded Data.
      - Perform Actions(include View Document, Download Document,Share Document).

   1. **Upload RFE Response Packet**
      - Upload Packet
      - Perform Actions(include View Document, Download Document,Share Document).

   1. **Upload RFE Response Tracking Information**
      - Uploads tracking details for the RFE response packet.
      - Validate Uploaded Data.
      - Perform Actions(include View Document, Download Document,Share Document).

   1. **Upload H-1B Approval Notice**
      - Select H-1B Approved through main Actions. 
      - Select H-1B Approval Type: I-797A
      - Uploads the H-1B Approval document.
      - Validate Uploaded Data.
      - Perform Actions(include View Document, Download Document).

   1. **Port of Entry**
      - Select Port of Entry through main Actions. 
      - Select radio option for "Does this candidate have a valid H-1B visa?" as Yes.
      - Completes the Port of Entry process.
      - Validate Uploaded Data.

   1. **Update Port of Entry Status**
      - Select Update Port of Entry Status through main Actions.
      - Choose Port of Entry Status: Entry Approved.
      - Updates the employee's Port of Entry status.
      - Validate Uploaded Data.
      - Perform Actions(include View Document, Download Document, Share Document).

   1. **Port of Exit**
      - Select Update Port of Exit through main Actions.
      - Select radio option for "Does this candidate have a valid H-1B visa?" as Yes.
      - Completes the Port of Exit process.
      - Validate Uploaded Data. 
      - Perform Actions(include View Document, Download Document, Share Document).

   1. **Delete H-1B Record**
      - Select Delete H-1B through main Actions.
      - Deletes the uploaded H-1B information.

   1. **Delete Employee Record**
      - Deletes the employee record once the process is complete.

----------------------------------------------------------------------------------------

### **Withdrawn/Revoked**

**Test Name**: `H1BTest_Withdrawn`

#### Description
This test verifies the workflow for withdrawing H-1B. 

#### Steps

   1. **Upload H-1B**
      - Petition Processing Type: General.
      - Petition Filed by: Employer
      - Petition Status type: H-1B Withdrawn/Revoked.
      - Upload Withdrawal Document.
      - Validate Uploaded Data.
      - Perform Actions(include View Document, Download Document, Share Document).

   1. **Delete H-1B Record**
      - Select Delete H-1B through main Actions.
      - Deletes the uploaded H-1B information.

   1. **Delete Employee Record**
      - Deletes the employee record once the process is complete.

