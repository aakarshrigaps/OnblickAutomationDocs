# Leave Management
## Purpose
- This test adds the time off code and then </br> apply and approve the leave from HR or </br> apply from the ESS and then aprroves from HR. </br> Then HR updates the leave by changing the leave date to next working day.
### Scenario
1. **HR Login**
1. **Onboard Employee**
1. **Turn on the time off toggle**
    - Opens leave management settings page and turns on the time off toggle if it is off.
1. **Get Week Days and Holiday List**
    - It gets the list of days that are selected to avail time off in settings page and holidays list from holidays list tab.
1. **Add Time Off Code** 
    - It adds the time off code witn its name, opening balance.
1. **HR Flow**
    - First it stores the leave count of taken, pending, balance then clicks on the "Add Leave" button.Then checks whether given leave day is in the weekdays(selected days to avail time off) and not in the holiday list, if not take following date and fill in leave date input.
    - Select time off code and enter leave reason and clicks "Apply and approve" button.
    - Then check if leave taken count is increased by one and leave balance is decreased by one.
1. **ESS Flow**
    - Set Password and Login ESS
    - Stores the leave count of taken, pending, balance then clicks on the "Apply Leave" button.Then checks whether given leave day is in the weekdays(selected days to avail time off) and not in the holiday list, if not take following date and fill in leave date input.
    - Select time off code and enter leave reason and apply leave.
    - Then check if leave pending count is increased by one and leave balance is decreased by one.
    - Login into HR and approve the leave

1. **Update the leave**
    - Update the leave by changing the leave date to next day of previous leave date.    