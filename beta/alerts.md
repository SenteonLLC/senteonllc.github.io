## Alerts
This page describes alerts that a Senteon User may see in Command Center alongside guidance on how to respond, and potential actions relevant to the alert (if applicable).

**Audit Complete**
* Description: This alert triggers when an endpoint has completed the Evaluation Phase of the Intelligent Setup process and is ready for Guided Setup.

**Configuration Drift Detected**
* Description: This alert triggers for an endpoint when the Senteon Agent detects that one of the managed settings has been modified without approval.
* [Action Condition] The Managed Account's `Configuration Drift Response` setting is set to "Alert & Require Approval"
  * [Options] The Senteon User can choose to enforce realignment of the setting to the Active Policy Set baseline, or ignore the alert.
 
**Endpoint Uninstalling**
* Descrption: This alert triggers when a Senteon Agent has been uninstalled. 
* Guidance: The agent will need to be manually reinstalled if this was unintentional.

**Endpoint Uninstall Failed**
* Description: This alert triggers when a Senteon Agent has been signalled to uninstall but runs into an issue during the uninstall process. 
* Guidance: At this point it is likely that the client will need to manually access the endpoint to rectify any issues stopping the Agent from uninstalling properly.  
