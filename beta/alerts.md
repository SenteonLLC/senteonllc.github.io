## Alerts
This page details alerts that a client may see in Senteon Command Center alongside instructions on how to handle actions relevant to the alert (if it has any).

* Audit Complete
  * This alert triggers when an endpoint has completed initialization and is ready to be setup
* Configuration Drift Detected
  * This alert triggers when a Senteon Agent detects that an endpoint has had a control mis-aligned from the Senteon determined setting
  * If the Managed Account setting is set to `Alert & Require Approval`, the client can choose to enforce the alignment of the control here and set the control back to the configured. Otherwise there will be no actionable data here.
* Endpoint Uninstalling
  * This alert triggers when a Senteon Agent has been uninstalled. The agent will need to be manually reinstalled if this was unintentional 
* Endpoing Uninstall Failed
  * This alert triggers when a Senteon Agent has been asked to uninstall but runs into an issue during the uninstall process. At this point it is likely that the client will need to manually access the endpoint to rectify any issues stopping the agent from uninstalling properly.  
