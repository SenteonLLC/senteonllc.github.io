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
| Alert | Reasoning |
|:--------|:-------:|
| Configuration  Drift   | Configuration drift alerts indicate that an endpoint has had a control setting change from the current expected value. Depending on the Managed Account's current settings, this will just be a notification that it was found and corrected or there will be an option on the alert to correct the drift.  |
| Endpoint Ready For Setup   |  This alert indicates that an endpoint on a managed account has completed evaluation and is now ready to be finalized either through the guided setup wizard or just directly finalized into the group.  |
| Endpoint Uninstalling   |  This alert indicates that an endpoint has been set to uninstall by a user on the system it is installed on and is currently going through the process of resetting controls and disabling.  |
| Endpoint Uninstall Failure   |  This alert indicates that an endpoint has been attempting to uninstall but hit an issue that caused it to fail.  |
| Command Center Order  | Command Center Order alerts indicate that an instruction was sent to a Senteon Agent to perform. Instructions include manual configuration drift correction.   |
| Command Center Order Complete  |  Command Center Order has successfully completed.  |
| Command Center Order Failed  |  Command Center Order failed  |
| Command Center Order Version Mismatch  |  agent version is too outdated to handle the order given to it  |
| New Managed Account Created  |  Managed Account Created alert indicates that a new managed account has been created and will detail the user and time it was done.  |
| Endpoint Disabled  |  Endpoint Disabled alerts trigger when an endpoint is disabled and will indicate which endpoint was disabled, who it was disabled by, and when it was disabled.  |
| Endpoint Re-Enabled  |  Endpoint Re-Enabled alerts trigger when an endpoint is re-enabled and will indicate which endpoint was re-enabled, who it was re-enabled by, and when it was re-enabled.  |
| Endpoint Reset  |  Endpoint Reset alerts trigger when an endpoint is reset and will indicate which endpoint was reset, who it was reset by, and when it was reset.  |

# Configuration Drift Management

Configuration drift is automatically fixed by Senteon when detected, but this setting can be changed in the managed account settings. The alternative options are to request IT team approval before correcting drift and not allowing correction at all. In the case that drift is set to be manually corrected, the option to do so will be provided on the alert relevant to the drifted control. Unless a specific situation calls for it, Senteon recommends allowing automatic drift enforcement and the creation of exception sets to account for changes where necessary.
