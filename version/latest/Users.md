# Overview
Command Center gives you the ability to create and manage users in addition to your Master Account user.

  - [Roles and Permissions](Users.md#roles-and-permissions)
  - [Creating Users](Users.md#creating-users)
  - [Modifying Users](Users.md#modifying-users)
      - [Change Password For Current User](Users.md#change-password-for-current-user)
  - [Deleting Users](Users.md#deleting-users)

# Roles and Permissions

The Master Account user is automatically assigned the "Owner" role. This is the highest privileged role, and no other users can be assigned this role.

Senteon provides 3 additional roles to meet your different use-cases.

**Auditor**
  * Report Generation
  * Read-Only access to Managed Account Consoles
 
**Manager**
  * All Auditor Permissions
  * Endpoint, Group, Control Editing, Config Set Creation
  * Alert Visibility and Response

 **Administrator**
   * All Manager Permissions 
   * Endpoint Deactivation
   * Managed Account Creation and Deactivation
   * Read-Only access to Users

**Owner**
  * All Administrator Permissions
  * User Creation, Deletion, & Password Changes
  * Managed Account Settings

# Creating Users

You can create additional users through the Master Account Console in Command Center. 
> Note: In order to create, modify, or delete users you must be logged in with a user that has the `Owner` or `Administrator` role.

**Steps**
1) Log into Command Center and navigate to the Users tab
2) Click the `Add User` button
<img src="images/Navigate to User tab.png" width="750">

3) Enter a username and the role of the user, then click `Create User`
<img src="images/Create User.png" width="750">

4) Senteon will generate a password for the user and copy it to your clipboard.
> Note: Make sure you save this password to a secure location or share it with the intended user in a timely and secure fashion.

<img src="images/Create User - password generated.png" width="250">

---
**Post-Creation**

When logging into a user account for the first time, you will be prompted to create a new password.

<img src="images/User First Login.png" width="550">

# Modifying Users

## Change Password For Current User
You can change the password for your current user no matter what role they are assigned.

**Steps**
1) Log into Command Center as the user and navigate to the Settings tab
2) Navigate to General Settings and click `Change Password`

<img src="images/Change User Password.png" width="750">

## Change Password For Another User
**Steps**
1) Log into Command Center and navigate to the Users tab
2) Select the user you wish to modify the role of and click `Change Password`

<img src="images/Modify User.png" width="750">

## Modify Role
**Steps**
1) Log into Command Center and navigate to the Users tab
2) Select the user you wish to modify the role of and click `Edit User`
3) Select the role you wish the user to assign the user and click `Save Changes`

<img src="images/Modify User.png" width="750">
<img src="images/Modify User Permissions.png" width="750">

# Deleting Users
**Steps**
1) Log into Command Center and navigate to the Users tab
2) Select the user you wish to delete and click the `Delete User` button.
3) Confirm that you wish to delete the user.

<img src="images/Delete User.png" width="750">
