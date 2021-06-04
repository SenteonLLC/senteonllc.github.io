# Command Center Settings - Master Account Console

## General Settings

**Change Password**

Currently the only available setting in the Master Account Console is the ability for a logged in user to change their password. This functionality is available to all users except for the Master Account/Owner user.

# Command Center Settings - Managed Account Console

## General Settings

**Configuration Drift Management**

This setting indicates the current response Senteon has for configuration drift alerts on all endpoints underneath the managed account. There are currently three available settings to choose from:

* Automatically Enforce (Default)
  * Senteon will automatically return controls to their specified baseline when the agent detects that they have drifted and provide an alert to the user that it has happened.
* Alert and Require Approval
  * Senteon will alert the administrator that a control monitored by Senteon has drifted. The administrator then has the option of choosing whether or not he/she wants to return the control to its baseline.
* Alert Only
  * Senteon will alert the administrator that a control monitored by Senteon has drifted. No action can be taken from the dashboard to rectify the drift. 
