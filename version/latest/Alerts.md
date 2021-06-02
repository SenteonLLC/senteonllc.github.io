# Alerts
Senteon generates alerts for a variety of different actions that Command Center and Senteon Agent can take. Alerts are divided into three priority levels:
* **Critical**
  * Critical alerts involve events that require immediate attention or action from the managing team.
* **Important**
  * Important alerts have middling severity level that typically indicates that there may not be action needed, but the team should be aware that the event has occurred.
* **Informational**
  * Informational alerts provide details to the activities and events occurring on the agents 

# Alert Types
| Alert | Reasoning |
|:--------|:-------:|
| Configuration  Drift   | Configuration drift alerts indicate that an endpoint has had a control setting change from the current expected value. Depending on the Managed Account's current settings, this will just be a notification that it was found and corrected or there will be an option on the alert to correct the drift.  |
| Endpoint Ready For Setup   |  This alert indicates that an endpoint on a managed account has completed evaluation and is now ready to be finalized either through the guided setup wizard or just directly finalized into the group.  |
| Endpoint Uninstalling   |  This alert indicates that an endpoint has been set to uninstall by a user on the system it is installed on and is currently going through the process of resetting controls and disabling.  |
| Endpoint Uninstall Failure   |  This alert indicates that an endpoint has been attempting to uninstall but hit an issue that caused it to fail.  |
| Command Center Order  | Command Center Order alerts indicate that an instruction was sent to a Senteon Agent to perform. Instructions include manual configuration drift correction.   |
| Command Center Order Complete  |    |
| Command Center Order Failed  |    |
| Command Center Order Version Mismatch  |    |
| New Managed Account Created  |    |
| Endpoint Disabled  |    |
| Endpoint Re-Enabled  |    |
| Endpoint Reset  |    |
# Configuration Drift Management
