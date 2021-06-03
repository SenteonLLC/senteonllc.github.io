# Alerts
Senteon generates alerts for a variety of different actions that Command Center and Senteon Agent can take. Alerts are divided into three priority levels:
* **Critical**
  * Critical alerts involve events that require immediate attention or action from the managing team.
* **Important**
  * Important alerts have middling severity level that typically indicates that there may not be action needed, but the team should be aware that the event has occurred.
* **Informational**
  * Informational alerts provide details to the activities and events occurring on the agents 

Senteon Command Center has two locations to view alerts. The first is in the main window for Command Center and the second is within the Managed Account. Command Center view displays all alerts underneath every managed account the command center has access to as well as command center specific alerts. The managed account alerts only display alerts specific to the related account. 

# Alert Types
| Alert | Description |
|:--------|:-------:|
| Configuration  Drift   | Indicates that an endpoint has had a Senteon-managed setting change from the expected value. Depending on the Managed Account's current settings, this will just be a notification that it was found and corrected or there will be an option on the alert to correct the drift.  |
| Endpoint Ready For Setup   |  Indicates that an endpoint in a Managed Account has completed the Evaluation Phase and is now ready to be finalized either through the Guided Setup Wizard or just directly finalized into the group.  |
| Endpoint Uninstalling   |  Indicates that a Senteon Agent has been signaled to uninstall by a user on the system it is installed on and is currently going through the process of reverting settings and disabling itself.  |
| Endpoint Uninstall Failure   |  Indicates that a Senteon Agent has been attempting to uninstall but hit an issue that caused it to fail.  |
| Command Center Order  | Indicates that an instruction was sent to a Senteon Agent to perform. Instructions include manual configuration drift correction.   |
| Command Center Order Complete  |  Indicates that a Command Center Order has successfully completed.  |
| Command Center Order Failed  |  Indicates that a Command Center Order failed.  |
| Command Center Order Version Mismatch  |  Indicates that a Seneon Agent's version is too outdated to handle the order given to it  |
| New Managed Account Created  |  Indicates that a new Managed Account has been created as well as providing the user and time it when the action was performed.  |
| Endpoint Disabled  |  Indicates that a Senteon Agent has been disabled as well as providing which endpoint the Agent is on, who it was disabled by, and when it was disabled.  |
| Endpoint Re-Enabled  |  Indicates that a Senteon Agent has been re-enabled as well as providing which endpoint the Agent is on, who it was re-enabled by, and when it was re-enabled.  |
| Endpoint Reset  |  Endpoint Reset alerts trigger when an endpoint is reset and will indicate which endpoint was reset, who it was reset by, and when it was reset.  |

# Configuration Drift Management

Configuration drift is automatically fixed by Senteon when detected, but this setting can be changed in the managed account settings. The alternative options are to request IT team approval before correcting drift and not allowing correction at all. In the case that drift is set to be manually corrected, the option to do so will be provided on the alert relevant to the drifted control. Unless a specific situation calls for it, Senteon recommends allowing automatic drift enforcement and the creation of exception sets to account for changes where necessary.
