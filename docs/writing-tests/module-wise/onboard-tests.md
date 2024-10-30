# Onboard

## Single Onboard

- **Description**: The Single Onboard process allows the onboarding of individual users through manual input. It ensures that user-specific data is correctly entered and validated before being stored in the system. This process is crucial for scenarios where a single user needs to be added to the system to access the platform's features.
- **Scenarios**: The Single Onboard process is typically tested with both positive and negative cases to verify the system's ability to handle complete and incomplete data submissions.

### Positive Case – With All Mandatory Fields { data-toc-label="Positive Case" }

- **Description**: This test involves onboarding a single user.
- **Steps**:
    1. Navigate to the onboarding page.
    2. Fill in the required fields (e.g., name, email, designation).
    3. Submit the form.
    4. Verify that the user appears in the system with the correct details.
- **Included in almost every test**: This scenario is a fundamental part of the onboarding process and is included in most test cases to ensure basic functionality.

### Negative Case – Missing Mandatory Fields { data-toc-label="Negative Case" }

- **Description**: This test checks how the system handles errors when mandatory fields are missing during onboarding.

- **Steps**:
    1. Navigate to the onboarding page.
    2. Click on Submit button without filling in any mandatory fields.
    3. Verify that the system provides appropriate error messages.
    4. Fill in mandatory details one by one and check the validation messages.
    5. Fill in only mandatory fields and submit the form.
    6. Verify that the user is not onboarded if the form is incomplete.

## Bulk Onboard
- **Description**: This test involves onboarding multiple candidates at once using a CSV file.
- **Steps**:
    1. Prepare a CSV file with the required fields (e.g., name, email, designation).
    2. Navigate to the bulk onboarding page.
    3. Upload the CSV file.
    4. Submit the form.
    5. Verify that all candidates appear in the system with the correct details.

### Positive Case – Without Any Missing Fields { data-toc-label="Positive Case" }
- **Description**: This test ensures that the bulk onboarding process works correctly when all required fields are present in the CSV file.
- **Steps**:
    1. Prepare a CSV file with complete data for all required fields.
    2. Follow the bulk onboarding steps.
    3. Verify that all candidates are onboarded successfully.
    4. Check that there are no errors or warnings.

### Negative Case – Missing Mandatory Fields in the CSV { data-toc-label="Negative Case" }
- **Description**: This test checks how the system handles errors when mandatory fields are missing in the CSV file.
- **Steps**:
    1. Prepare a CSV file with some missing mandatory fields (e.g., missing email or designation).
    2. Follow the bulk onboarding steps.
    3. Verify that the system provides appropriate error messages.
    4. Ensure that no candidates are onboarded if the CSV file is incomplete.
    5. Check that the system logs the errors for further analysis.
