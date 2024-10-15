# Change Password from Settings Page

## Test Steps

### **Password Guidelines Tooltip**
   - **Description**: Hover over `Password Guidelines` to view password guidelines (e.g., character length, special characters).
   - **Expected Result**: Tooltip with password requirements is displayed.

### **Error on Save Without Data**
   - **Description**: Click "Save" without entering any data.
   - **Expected Result**: Error message indicating required fields.

### **Incorrect Current Password**
   - **Description**: Enter "test" as current password and try to save.
   - **Expected Result**: Error message: "Incorrect current password."

### **Old Password in New Password Field**
   - **Description**: Enter the current password in the "New Password" field.
   - **Expected Result**: Error message: "New password cannot be the same as old password."

### **Mismatched Confirm Password**
   - **Description**: Enter a valid new password but a different value in the "Confirm Password" field.
   - **Expected Result**: Error message: "Passwords do not match."

### **Save New Password**
   - **Description**: Enter the same valid new password in both fields and save.
   - **Expected Result**: Confirmation message: "Password updated successfully."

### **Login with Old Password**
   - **Description**: Attempt to log in with the old password after changing it.
   - **Expected Result**: Error message: "Incorrect password."

### **Relogin and Reset to Old Password**
   - **Description**: Log in with the new password, then reset to the old password.
   - **Expected Result**: Password is successfully reverted to the old one.
