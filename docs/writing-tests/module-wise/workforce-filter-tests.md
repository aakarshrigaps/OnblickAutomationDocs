# Workforce Filters Documentation

## Overview

This document provides detailed information regarding the implementation of the filters present in the workforce (active, new hires, terminated) tabs.

---

## Workforce Filters Execution

**Test Name**: `WorkforceFiltersValidation`

1. **Login as HR**:

   -  Access the HR portal to begin the work force filters process.

1. **Complete Workforce filter**

   -  For each filter type, such as dropdowns, multiple select, and checkboxes, various combinations of filter parameters are created and tested.

   2. **Apply Filters**

      Based on the different **filter types** present in the workforce tab, such as radio buttons, text entry, etc., various filters are applied accordingly.

      1. **Radio Button**

         When a radio button is selected, any one filter parameter can be chosen, and then the filters are applied.

         - **Filter Names**: Billing Status, Employee Type, Benefits, Supervisory Status, Employment Start Date
         - **Filter Parameters**: For filter parameters, refer to the table [Filter Parameters](#filter-parameters).

      1. **Text Entry**

         In text entry, the date is provided, and then the filters are applied.

         - **Filter Names**: Employment Start Date Range, Current Project Start Date Range, Termination Date Range
         - **Filter Parameters**: For filter parameters, refer to the table [Filter Parameters](#filter-parameters).

      1. **Check Box**

         Multiple filter parameters can be selected, and then the filters are applied.

         - **Filter Names**: Tax Terms, Employment Type
         - **Filter Parameters**: For filter parameters, refer to the table [Filter Parameters](#filter-parameters).

      1. **Dropdown**

         Retrieve department names from the settings, select a random department name, and then filter is applied.

         - **Filter Names**: Department

      1. **Multiple Select**

         First, different work authorizations are added, followed by their selection and the application of filters.

         - **Filter Names**: Work Authorization Type

   3. **Validate Filters**

      After applying the filters different filters are validated in different ways.

      1. Validation is performed based on the value present in the resultant applied filters table. Some of the filters include Billing Status, Tax Terms, Employment Type, Benefits, etc.

      1. In some conditions, validation occurs by going into the profile of the candidate, and then the applied filters are validated. Some of the filters include Supervisory Status, Employee Type, etc.

      1. For the date entry filters, the resultant dates are validated based on the conditions specified in the "From" and "To" dates, respectively. Some of the filters include Employment Start Date Range, Termination Date Range, Current Project Start Date Range, etc.

## Filter Parameters

| Filter Name                      | Filter Parameters                                                                              |
| -------------------------------- | ---------------------------------------------------------------------------------------------- |
| Billing Status                   | `Billing`, `Non-Billing`                                                                       |
| Employee Type                    | `All`, `Trainees`, `Supervisors`                                                               |
| Benefits                         | `Applicable`,  `Not Applicable`                                                                |
| Supervisory Status               | `Assigned`, `Unassigned`                                                                       |
| Employment Start Date            | `Available`, `Not Available`                                                                   |
| Employment Start Date Range      | `From`, `To`                                                                                   |
| Current Project Start Date Range | `From`, `To`                                                                                   |
| Termination Date Range           | `From`, `To`                                                                                   |
| Tax Terms                        | `All`, `C2C`, `W2`, `1099`, `Not Available`                                                    |
| Employment Type                  | `Full-time`, `Part-time`, `Intern`, `Temporary`, `Contractor`, `Freelance`                     |
| Work Authorization Type          | `H1B`, `NewH1BCAP`, `H1BExtension`, `H1BTransfer`, `H1BAmendment`, `NewH1BCAPExempt`, `H1BAmendmentExtension`, `H1BConcurrent`, `L1Visa`, `E3Visa`, `TNVisa`, `GreenCard`, `USCitizen`, `CPT`, `EADOTHERS`, `OPTEAD`, `STEMOPT` |

