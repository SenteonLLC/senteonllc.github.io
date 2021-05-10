# Configuring Endpoints

Once Command Center and the Senteon Agents are installed on their corresponding systems, Endpoints can be viewed through the Command Center Dashboard and Controls can be applied to them. 

## Verify status of endpoints
All endpoints with Senteon Agents installed that have an internet connection will be viewable from the managed account endpoints screen. 
To do so follow the steps below:
1) Log into Command Center with your provided administrator credentials

<img src="images/loginpage.PNG" width="750">

2)  Navigate to the `Account Manager` tab.

<img src="images/accountmanager.png" width="750">

3)  Select the relevant managed account from the list provided and choose `Manage Account`.

<img src="images/manageaccount.png" width="750">

4)  Navigate to the `Endpoints` Screen

<img src="images/navtoendpoints.png" width="750">

5)  This pages shows all endpoints associated with the managed account

<img src="images/endpoints.PNG" width="750">

6)  Under a single endpoint, select the `info` button to see fingerprinted information on the endpoint's status.

<img src="images/endpointinfo.png" width="750">
<img src="images/endpointinfopage.PNG" width="750">

7) Once the Endpoint's status has been verified, you can continue to the initialization of the endpoint and control setup.  

## Initialize the Endpoint 
1) On the `Endpoints` screen you can see the status of Senteon agents on each endpoint. All endpoints with the status `Ready to Begin Evaluation` are ready for initializing.

<img src="images/endpoints.PNG" width="750">

2)  From the `Endpoints` screen, navigate to the `Endpoint Setup` screen using the radio buttons at the top 

<img src="images/endpointsetup.png" width="750">

3)  The `Endpoint Setup` screen has a list on the bottom left indicating all endpoints ready for initialization. Select the endpoints you wish to initialize from the list and then select `Initialize Selected`. 
> **Note**: You can initialize as many endpoints at once as you would like. When the grouping feature is released, endpoints that are initialized together will be initialized into the same group and compared against the same baseline. 
 
<img src="images/evaluation.png" width="750">
<img src="images/acceptinitialization.png" width="750">

4)  After initialization, Endpoints will begin to analyze the requirements set for by Senteon and determine which controls can be safely implemented on the endpoint.
> **Note**: This initialization period is configured to take as long as the Senteon Agent needs to make determinations. With future updates this time is expected to be around 2 weeks. For the purposes of the beta, this audit period has been removed and endpoints can be setup immediately.  



5)  Changing back to the `Endpoint` screen will show that the endpoints are now in a ready for setup state. Changing back to the `Uninitialized` screen will show that this endpoint is now listed in the `Ready for Setup` list and can be setup.
> **Note**: Currently changing tabs is necessary to prompt Command Center to update with endpoint statuses from Senteon master servers. This will be available as a refresh button for individual lists upon release. 




## Endpoint Setup
Once endpoints have been initialized and audited, they can be setup for controls to be applied

1) On the `Endpoint Setup` Screen, all endpoints ready for setup with be listed in the top list.

2) Select the endpoint you would like to setup by selecting the setup button next to the relevant endpoint.
> **Note**: It is currently not possible to setup endpoints in groups due to the nature of the Senteon Agent providing unique telemetry for each endpoint resulting in differing analysis based on the endpoint's activity. Senteon will be supporting quick setup for a high volume of endpoints by providing the ability to automatically enforce the baseline of an existing endpoint onto selected endpoints as necessary. This feature will be available on release with Groups functionality. 

<img src="images/endpointfinalization.png" width="750">

3) For the purposes of the Beta, all controlsets are currently being accepted without conflicts. With proper application, questions targeted at specific controls that an endpoint is found to have issues with enabling will be posted to the client with unique telemetry to allow for an educated decision to be made by the administrator. 
> **Note**: The very first endpoint setup for a managed account will have an extended wizard used to answer managed account specific questions that will apply to all controls within a managed account organization. 

<img src="images/wizard.png" width="750">

4) Once the setup is completed, Endpoint will begin to apply controls based upon the specified configurations. Its status in the `Endpoints` page will now be listed as `Active`. 




This dashboard will allow you to view endpoints registered under that Managed Account as well as reset controls for those endpoints. More information on resetting can be found in [Resetting Systems](resetting.md).
