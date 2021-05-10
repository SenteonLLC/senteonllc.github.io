# Configuring/Setting Up Endpoints

Once Command Center and the Senteon Agents are installed on their corresponding systems, endpoints for the Managed Account will populate in Command Center. From here you will be able to begin the Intelligent Setup process to apply policies to your endpoint fleet.

## Verify Status of Endpoints
Endpoints will be appear in the Managed Account Dashboard under the `Endpoints` tab once they have had the Senteon Agent installed and registered to the Managed Account.
> **Note**: If an endpoint doesn't appear in the list, verify that the Senteon Agent has been installed and registered to the proper Managed Account. If you have verified that installation was done properly, see [# Troubleshooting] for more guidance.

### Steps ###
1) Log into Command Center with your provided `Owner` user credentials.

<img src="images/loginpage.png" width="750">

2) Navigate to the `Account Manager` tab.

<img src="images/accountmanager.png" width="750">

3) Select the relevant Managed Account from the list provided and choose `Manage Account` to open a Managed Account Dashboard.

<img src="images/manageaccount.png" width="750">

4) Navigate to the `Endpoints` tab

<img src="images/navtoendpoints.png" width="750">

5) The main `Endpoints` page shows all endpoints registered to the Managed Account

<img src="images/endpoints.PNG" width="750">

Once an endpoint's `System Status` is "Ready To Begin Evaluation", you are ready to continue.

## Intelligent Setup: Evaluation Phase
### Steps ###
1) Navigate to the `Endpoint Setup` page.

<img src="images/endpointsetup.png" width="750">

2) The `Endpoint Setup` page has a section on the bottom left labeled `Ready For Evaluation` indicating all endpoints ready for to begin the Intelligent Setup process. Select the endpoints you wish to initialize from the list and then click the `Initialize Selected` button. This will begin the Evaluation Phase.
> **Note**: You can initialize as many endpoints at once as you would like. When the grouping feature is released, endpoints that are initialized together will be added to the same group and evaluated against the same baseline.
 
<img src="images/evaluation.png" width="750">
<img src="images/acceptinitialization.png" width="750">

 During the Evaluation Phase, endpoints will be analyzed to determine which controls can be safely implemented without disrupting user experience and network operations.
 > **Note**: For the purposes of this Beta, The Evaluation Phase will complete immediately. In the Full Release, evaluation will take around 2 weeks maximum  to gather relevant data and make a decision depending on prior configuration of an endpoint.

3) Once an endpoint completes the Evaluation Phase, its `System Status` becomes "Ready For Setup". Changing pages or clicking the `refresh` icon will pull the latest status. Once an endpoint's `System Status` is "Ready For Setup", you are ready to continue.

## Intelligent Setup: Guided Setup Phase
### Steps ###
1) On the `Endpoint Setup` page, all endpoints that have completed the Evaluation Phase will appear under the section labled `Ready For Setup`.

2) Select the endpoint you would like to setup by clicking the `Finish Setup` button next to it.
 > **Note**: It is currently not possible to perform Guided Setup for batches of endpoints. We plan to add this functionality for the Full Release.

<img src="images/endpointfinalization.png" width="750">

3) For the purposes of the Beta, all settings/values suggested in the default Senteon Recommended Policy Set are accepted without conflicts.
 > **Note**: It is currently not possible to perform Guided Setup for batches of endpoints. We plan to add this functionality for the Full Release.

<img src="images/wizard.png" width="750">

Once Guided Setup is completed, the Senteon Agent on the endpoint will apply the configurations of the finalized Policy Set (also referred to as the Active Policy Set). The endpoint's `System Status` will be updated to "Active"
