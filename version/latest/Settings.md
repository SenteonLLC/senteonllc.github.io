# Senteon Settings Overview

This section describes the settings available to Senteon Users.

- [Command Center - Master Account Settings](Settings.md#command-center---master-account-settings)
- [Command Center - Managed Account Settings](Settings.md#command-center---managed-account-settings)

# Command Center - Master Account Settings

Master Account Settings affect Senteon functionality and are scoped to the entire Master Account.

Location: `Master Account Console > Settings`

## General Settings

**Change Password**

Currently the only available setting in the Master Account Console is the ability for a logged in user to change their password. This functionality is available to all users except for the Master Account/Owner user.

# Command Center - Managed Account Settings

Managed Account Settings affect Senteon functionality, but only affect resources within that specific Managed Account.

Location: `Managed Account Console > Settings`

## General Settings

**Configuration Drift Management**

This setting defines Senteon's reponse to configuration drift on all Endpoints registered to the Managed Account.

|   Option    | Description |
|:-----------:|:-----------:|
| Automatically Enforce (Default) | Senteon will generate an alert and automatically return the setting back to its target baseline value. |
| Alert and Require Approval | Senteon will generate an alert. In the "Alerts" tab, Senteon users with `Manager` role or higher will have the option to choose whether or not they want to return the setting back to its target baseline value. |
| Alert Only | Senteon will generate an alert and no further action will be taken by Senteon. |


* Automatically Enforce (Default)
  * Senteon will generate an alert and automatically return the setting back to its target baseline value.
* Alert and Require Approval
  * Senteon will generate an alert. In the "Alerts" tab, Senteon users with `Manager` role or higher will have the option to choose whether or not they want to return the setting back to its target baseline value.
* Alert Only
  * Senteon will generate an alert and no further action will be taken by Senteon.


**Account-wide Guided Setup Decisions**

This category displays the chosen values for security configurations that are reliant on an understanding of organizational/company culture. These values are the result of decisions made during Guided Setup. Once the decisions have been made for the first time, Senteon will use the decisions during the setup of all subsequent endpoints within the Managed Account instead of asking the Senteon User every time. 

The target values can be modified here if one wishes to change a decision. After adjustment, Senteon will use the updated target values during the setup of all subsequent endpoints, but it will not affect any active endpoints that have been setup previously.
