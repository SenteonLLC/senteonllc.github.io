# Users and Permissions
This section describes Senteon's User and Role-Based Permissions Systems. Command Center gives you the ability to create and manage users in addition to your Master Account User.

## Roles and Permissions

The Master Account User is automatically assigned the "Owner" role. This is the highest privileged role, and no other users can be assigned this role.

Senteon provides additional user roles to meet your different use-cases:

|   Role    | Permissions |
|:---------:|:-----------|
| Auditor | - Report Generation </br> - Read-Only access to Managed Account Consoles |
| Manager | - All Auditor Permissions </br> - Endpoint, Group, Configuration Set Creation and Modification </br> - Alert Visibility and Response |
| Administrator | - All Manager Permissions </br> - Endpoint Deactivation </br> - Managed Account Creation and Deactivation </br> - Read-Only access to Users |
| Owner | - All Administrator Permissions </br> - User Creation, Deletion, & Password Changes</br> - Managed Account Creation and Deactivation </br> - Managed Account Settings |

## Creating Users

You can create additional users through the Master Account Console in Command Center. 

In order to create, modify, or delete users you must be logged in with a user that has the `Owner` or `Administrator` role.

**Steps**

1) Log into Command Center and navigate to the "Users" tab

2) Click the `Add User` button

<img src="../images/Navigate to User tab.png" width="750">

3) Enter a username and the role of the user, then click `Create User`

<img src="../images/Create User.png" width="750">

4) Senteon will generate a password for the user and copy it to your clipboard.
> *Note: Make sure you save this password to a secure location or share it with the intended user in a timely and secure fashion.*

<img src="../images/Create User - password generated.png" width="250">

---
**Post-Creation**

When logging in as user for the first time, you will be prompted to create a new password.

<img src="../images/User First Login.png" width="550">

## Modifying Users

### Changing Password for Current User

*Note: You can change the password for your current user no matter what role they are assigned.*

1) Log into Command Center as the user and navigate to the Settings tab

2) Navigate to General Settings and click `Change Password`

<img src="../images/Change User Password.png" width="750">

### Changing Password for Another User

1) Log into Command Center and navigate to the "Users" tab

2) Select the user you wish to modify the role of and click `Change Password`

<img src="../images/Modify User.png" width="750">

### Modifying a User's Role

1) Log into Command Center and navigate to the "Users"tab

2) Select the user you wish to modify the role of and click `Edit User`

3) Select the role you wish the user to assign the user and click `Save Changes`

<img src="../images/Modify User.png" width="750">

<img src="../images/Modify User Permissions.png" width="750">

### Enabling MFA for Current User

1) Log into Command Center as the user and navigate to the "Settings" tab

2) Navigate to General Settings and click `Enable MFA`

3) Open your Authenticator App and scan the QR code, then close the window

> *Alternatively you can enter the secret key manually.*

4) Enter the 6 digit TOTP from the Authenticator App and click the `Submit` button to verify and complete MFA setup

<img src="../images/EnableMFA.png" width="750">

### Disabling MFA for Current User

1) Log into Command Center as the user and navigate to the "Settings" tab

2) Navigate to General Settings and click `Disable MFA`

3) Enter the 6 digit TOTP from the Authenticator App and click the `Submit` button to verify and disable MFA

<img src="../images/DisableMFA.png" width="750">

## Deleting Users

1) Log into Command Center and navigate to the "Users" tab

2) Select the user you wish to delete and click the `Delete User` button.

3) Confirm that you wish to delete the user

<img src="../images/Delete User.png" width="750">

