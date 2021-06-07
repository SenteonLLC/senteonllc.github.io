# Alerts Overview

This section decribes Senteon's event-logging and alerting system.

- [Viewing Alerts](Alerts.md#viweing-alerts)
- [Alert Priority Levels](Alerts.md#alert-priority-levels)
- [Alert Types](Alerts.md#alert-types)

# Viewing Alerts

Alerts can be viewed in two locations:

- `Master Account Console > Alerts` - Displays aggregated Alerts for all Managed Accounts within the Master Account
- `Managed Account Console > Alerts` - Displays Alerts for only that specific Managed Account



# Alert Priority Levels

| Priority Level | Description |
|:--------------:|:-----------:|
| Critical | Indicates an event that requires immediate attention or action. |
| Important | Indicates that there may not be action needed, but the team should be aware that the event has occurred. |
| Informational | Indicates that a typical event has occured and provides details surrounding the event. |


- **Critical**
  * Indicates an event that requires immediate attention or action. 
- **Important**
  * Indicates that there may not be action needed, but the team should be aware that the event has occurred.
- **Informational**
  * Indicates that a typical event has occured and provides details surrounding the event.

# Alert Types
|    Alert    | Description |
|:-----------:|:-----------:|
|  Configuration  Drift  | Indicates that an Endpoint has had a Senteon-managed setting change from the expected value. Depending on the Managed Account's current settings, this will just be a notification that it was found and corrected or there will be an option on the alert to correct the drift  |
|  Endpoint Ready For Setup   |  Indicates that an Endpoint in a Managed Account has completed the Evaluation Phase and is now ready to be finalized either through the Guided Setup Wizard or just directly finalized into the group  |
|  Endpoint Uninstalling   |  Indicates that a Senteon Agent has been signaled to uninstall by a user on the system it is installed on and is currently going through the process of reverting settings and disabling itself  |
|  Endpoint Uninstall Failure   |  Indicates that a Senteon Agent has been attempting to uninstall but hit an issue that caused it to fail  |
|  Command Center Order  | Indicates that an instruction was sent to a Senteon Agent to perform. Instructions include manual configuration drift correction   |
|  Command Center Order Complete  |  Indicates that a Command Center Order successfully completed  |
|  Command Center Order Failed  |  Indicates that a Command Center Order failed  |
|  Command Center Order Version Mismatch  |  Indicates that a Senteon Agent's version is too outdated to handle the order given to it  |
|  New Managed Account Created  |  Indicates that a new Managed Account has been created as well as providing the user and time when the action was performed  |
|  Endpoint Disabled  |  Indicates that a Senteon Agent has been disabled as well as providing which Endpoint the Agent is on, who it was disabled by, and when it was disabled.  |
|  Endpoint Re-Enabled  |  Indicates that a Senteon Agent has been re-enabled as well as providing which Endpoint the Agent is on, who it was re-enabled by, and when it was re-enabled.  |
|  Endpoint Reset  |  Indicates that a Senteon Agent has been reset  as well as providing which Endpoint the Agent is on, who it was reset by, and when it was reset.  |

## Example Alert:
<img src="../images/exampleAlert.PNG" width="750">
