---
toc_depth: 3
---

# H-1B Documentation

## **Initiate H-1B Scenarios**

### **Case Rejected**

**Test Name**: `InitiiateH1BTest_CaseRejected_Automation`

#### Description
This test validates the workflow for initiating an H-1B petition, creating and uploading necessary packet documents, tracking, and handling a case rejection scenario. It ensures all stages are managed accurately, and the system properly cleans up after rejection.

#### Steps

   1. **Initiate H-1B Petition**
      - H-1B Classification: New H-1B Cap.
      - Petition Processing Type: General.
      - Petition Filed by: Employer.
      - Validate Employer Information and Initiate.

   1. **Create H-1B Packet**
      - Create H-1B Packet by selecting Beneficiary Documents Check boxes,RTC Documents Check boxes, Client Documents Check boxes, Petitioner Document Check boxes and Current Work Authorization Documents.

   1. **Request and Upload Multiple H-1B Supporting Documents(HR)**
      - This method handles the process of requesting and uploading multiple H-1B packet documents, such as Current Work Authorization, Beneficiary, RTC and Client Documents.
      - Validate Uploaded Data.

   1. **Upload Tracking Information**
      - Upload Tracking Information.
      - Validate Uploaded Data.

   1. **Case Rejected by USCIS**
      - Select Case Rejected and Upload Case Rejection Document.
      - Validate Uploaded Data.
      - Perform Actions(include View Document, Download Document,Share Document).

   1. **Delete H-1B Record**
      - Select Delete H-1B through main Actions.
      - Deletes the uploaded H-1B information.

   1. **Delete Employee Record**
      - Deletes the employee record once the process is complete.

---------------------------------------------------

### **H-1B Denied**

**Test Name**: `InitiateH1BTest_H1BDenied_Automation`

#### Description
This test case verifies the workflow for handling an H-1B petition that is denied. The steps include initiating the petition, creating the required packet, uploading tracking information, and managing the denial process, followed by cleanup of related data. 

#### Steps

   1. **Initiate H-1B Petition**
      - Petition Processing Type: General.
      - Petition Filed by: Employer.
      - Validate Employer Information and Initiate.

   1. **Create H-1B Packet**
      - Create H-1B Packet by selecting Beneficiary Documents Check boxes,RTC Documents Check boxes, Client Documents Check boxes, Petitioner Document Check boxes and Current Work Authorization Documents.

   1. **Upload Tracking Information**
      - Upload Tracking Information.
      - Validate Uploaded Data.

   1. **Upload Receipt Notice (I-797C)**
      - Upload Document
      - Validate Uploaded Data.
      - Perform Actions(include View Document, Download Document,Share Document).

   1. **Case Rejected by USCIS**
      - Select Case Rejected and Upload Case Rejection Document.
      - Validate Uploaded Data.
      - Perform Actions(include View Document, Download Document,Share Document).

   1. **Delete H-1B Record**
      - Select Delete H-1B through main Actions.
      - Deletes the uploaded H-1B information.

   1. **Delete Employee Record**
      - Deletes the employee record once the process is complete.

---------------------------------------------------

### **NOID**

**Test Name**: `InitiateH1BTest_NOID_Automation`

#### Description
This test case verifies the workflow for processing an H-1B petition that has received a NOID. The workflow includes initiating the petition, creating the required packet, uploading necessary documentation, and ultimately deleting the records to maintain data integrity.

#### Steps

   1. **Initiate H-1B Petition**
      - Petition Processing Type: General.
      - Petition Filed by: Employer.
      - Validate Employer Information and Initiate.

   1. **Create H-1B Packet**
      - Create H-1B Packet by selecting Beneficiary Documents Check boxes,RTC Documents Check boxes, Client Documents Check boxes, Petitioner Document Check boxes and Current Work Authorization Documents.

   1. **Request and Upload Individual H-1B Supporting Documents(HR)**
      - This method handles the process of Requesting and uploading individual H-1B Supporting documents(Current Work Authorization, Beneficiary, RTC, and Client documents)
      - Validate Uploaded Data

   1. **Actions for Supporting H-1B Documents by HR**
      - Perform Actions(include View Document, Download Document,Edit Document,Share Document) for all H-1B Supporting Documents which have submitted by HR.

   1. **Upload Tracking Information**
      - Upload Tracking Information.
      - Validate Uploaded Data.

   1. **Upload Receipt Notice (I-797C)**
      - Upload Document
      - Validate Uploaded Data.
      - Perform Actions(include View Document, Download Document,Share Document).

   1. **Upload NOID Notice**
      - Select H-1B NOID through main Actions.
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

   1. **Upload H-1B Approval Notice**
      - Select H-1B Approved through main Actions. 
      - Select H-1B Approval Type: I-797B.
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

---------------------------------------------------

### **NOIR**

**Test Name**: `InitiateH1BTest_NOIR_Automation`

#### Description
This test case verifies the complete workflow for processing an H-1B petition that has received a Notice of Intent to Revoke (NOIR). The steps encompass initiating the petition, creating the necessary packet, uploading relevant documentation, and finalizing the records by deleting any related entries.

#### Steps

   1. **Initiate H-1B Petition**
      - Petition Processing Type: General.
      - Petition Filed by: Employer.
      - Validate Employer Information and Initiate.

   1. **Create H-1B Packet**
      - Create H-1B Packet by selecting Beneficiary Documents Check boxes,RTC Documents Check boxes, Client Documents Check boxes, Petitioner Document Check boxes and Current Work Authorization Documents.

   1. **Upload All H-1B Supporting Documents (HR)**
      - Upload H-1B Supporting documents, including petitioner documents, current work authorization documents,beneficiary documents, right to control(RTC) documents, and client documents.
      - Validate Uploaded Data.

   1. **Actions for Supporting H-1B Documents (HR)**
      - Perform Actions(include View Document, Download Document,Edit Document,Share Document) for all H-1B Supporting Documents which have submitted by HR.

   1. **Upload Tracking Information**
      - Upload Tracking Information.
      - Validate Uploaded Data.

   1. **Upload Receipt Notice (I-797C)**
      - Upload Document.
      - Validate Uploaded Data.
      - Perform Actions(include View Document, Download Document,Share Document).

   1. **Upload H-1B Approval Notice**
      - Select H-1B Approved through main Actions. 
      - Select H-1B Approval Type: I-797A.
      - Uploads the H-1B Approval document.
      - Validate Uploaded Data.
      - Perform Actions(include View Document, Download Document).

   1. **Upload NOIR Notice**
      - Select H-1B NOIR through main Actions.
      - Uploads H-1B NOIR Notice.
      - Validate Uploaded Data.
      - Perform Actions(include View Document, Download Document,Share Document).

   1. **Upload NOIR Response Packet**
      - Upload Packet
      - Perform Actions(include View Document, Download Document,Share Document).

   1. **Upload NOIR Response Tracking Information**
      - Uploads tracking details for the NOID response packet.
      - Validate Uploaded Data.
      - Perform Actions(include View Document, Download Document,Share Document).

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

---------------------------------------------------

### **Port of Entry Denied**

**Test Name**: `InitiateH1BTest_PortOfEntryDenied_Automation`

#### Description
This test case verifies the complete workflow for processing an H-1B petition that has been denied following a Port of Entry (POF) review. The steps include initiating the petition, creating the necessary packet, uploading relevant documentation, and cleaning up any related entries.

#### Steps

   1. **Initiate H-1B Petition**
      - Petition Processing Type: General.
      - Petition Filed by: Employer.
      - Validate Employer Information and Initiate.

   1. **Create H-1B Packet**
      - Create H-1B Packet by selecting Beneficiary Documents Check boxes,RTC Documents Check boxes, Client Documents Check boxes, Petitioner Document Check boxes and Current Work Authorization Documents.

   1. **Upload Tracking Information**
      - Upload Tracking Information.
      - Validate Uploaded Data.

   1. **Upload Receipt Notice (I-797C)**
      - Upload Document
      - Validate Uploaded Data.
      - Perform Actions(include View Document, Download Document,Share Document).

   1. **Upload H-1B Approval Notice**
      - Select H-1B Approved through main Actions. 
      - Select H-1B Approval Type: I-797B.
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
      - Choose Port of Entry Status: Entry Denied.
      - Updates the employee's Port of Entry status.
  
   1.**Withdraw H-1B Petition**
      - Upload Withdrawal Document.
      - Validate Uploaded Data.
      - Perform Actions(include View Document, Download Document, Share Document).

   1. **Delete H-1B Record**
      - Select Delete H-1B through main Actions.
      - Deletes the uploaded H-1B information.

   1. **Delete Employee Record**
      - Deletes the employee record once the process is complete.

 ----------------------------------------------------------------

### **RFE**

**Test Name**: `InitiateH1BTest_RFE_Automation`

#### Description
This test case verifies the workflow for processing an H-1B petition that has received a RFE. The workflow includes initiating the petition, creating the required packet, uploading necessary documentation, and ultimately deleting the records to maintain data integrity.

#### Steps

   1. **Initiate H-1B Petition**
      - Petition Processing Type: General.
      - Petition Filed by: Employer.
      - Validate Employer Information and Initiate.

   1. **Create H-1B Packet**
      - Create H-1B Packet by selecting Beneficiary Documents Check boxes,RTC Documents Check boxes, Client Documents Check boxes, Petitioner Document Check boxes and Current Work Authorization Documents.

   1. **Request H-1B Petition Documents**
      - Request Documents of H-1B petition.
      - Select Documents and Enter Reviewer Details.

   1. **Complete H-1B Petition Beneficiary Info(ESS)**
      - Completes the Beneficiary Information for the H-1B petition by Employee.

   1. **Review H-1B Petition Beneficiary Information(HR)**
      - Reviews and Approve the beneficiary information by Reviewer and HR
      - Validate H-1B Packet Documents by HR which are uploaded by Employee.


   1. **Initiate Form I-129**
      - Initiate the Form I-129.
      - Download and Upload the Signed Form.
      - This [`Initiate Form I-129`](form-i129-tests.md) document clearly explains how to initiate Form I-129.      

   1. **Upload Tracking Information**
      - Upload Tracking Information.
      - Validate Uploaded Data.

   1. **Upload Receipt Notice (I-797C)**
      - Upload Document.
      - Validate Uploaded Data.
      - Perform Actions(include View Document, Download Document,Share Document).

   1. **Upload RFE Notice**
      - Select H-1B RFE through main Actions.
      - Uploads H-1B RFE Notice.
      - Validate Uploaded Data.
      - Perform Actions(include View Document, Download Document,Share Document).

   1. **Upload RFE Response Packet**
      - Upload Packet
      - Perform Actions(include View Document, Download Document,Share Document).

   1. **Upload RFE Response Tracking Information**
      - Uploads tracking details for the NOID response packet.
      - Validate Uploaded Data.
      - Perform Actions(include View Document, Download Document,Share Document).

   1. **Upload H-1B Approval Notice**
      - Select H-1B Approved through main Actions. 
      - Select H-1B Approval Type: I-797B.
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

------------------------------------------------------------------------------

### **Visa Denied**

**Test Name**: `InitiateH1BTest_VisaDenied_Automation`

#### Description
This test case covers the workflow for handling an H-1B petition that is denied after the visa interview. The process includes creating the petition, uploading necessary documentation, tracking the status, and ensuring proper cleanup in the system.

#### Steps

   1. **Initiate H-1B Petition**
      - Petition Processing Type: General.
      - Petition Filed by: Employer.
      - Validate Employer Information and Initiate.

   1. **Create H-1B Packet**
      - Create H-1B Packet by selecting Beneficiary Documents Check boxes,RTC Documents Check boxes, Client Documents Check boxes, Petitioner Document Check boxes and Current Work Authorization Documents.

   1. **Request and Upload Multiple H-1B Supporting Documents(HR)**
      - This method handles the process of requesting and uploading multiple H-1B packet documents, such as Current Work Authorization, Beneficiary, RTC and Client Documents. 

   1. **Upload Tracking Information**
      - Upload Tracking Information.
      - Validate Uploaded Data.

   1. **Upload Receipt Notice (I-797C)**
      - Upload Document.
      - Validate Uploaded Data.
      - Perform Actions(include View Document, Download Document,Share Document).

   1. **Upload H-1B Approval Notice**
      - Select H-1B Approved through main Actions. 
      - Select H-1B Approval Type: I-797A.
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
      - Choose Interview Status: Visa Denied.
      - Updates the Interview status.
      - Validate Uploaded Data.
      - Perform Actions(include View Document, Download Document, Share Document).

   1. **Delete H-1B Record**
      - Select Delete H-1B through main Actions.
      - Deletes the uploaded H-1B information.

   1. **Delete Employee Record**
      - Deletes the employee record once the process is complete.
