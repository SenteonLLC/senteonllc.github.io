# Endpoint Configuration

This section describes the concepts and systems that Senteon uses to manage security-related settings on your endpoints. We highly recommend that you familiarize yourself with this section before completing Intelligent Setup and administering Senteon.

Below you can find details regarding how to complete the setup of your fleet of endpoints from start to finish, the settings/configurations Senteon manages, how a Senteon user should expect to organize and manage their fleet of endpoints, and what healthy activity looks like.

## Intelligent Setup
When endpoints have a Senteon Agent installed, the Senteon Agent will register itself with Command Center so that it can be evaluated and finalized. Starting Evaluation will allow the Senteon Agent to audit all of the settings related to that endpoint type and determine the ideal baseline for the endpoint. After evaluation is complete, the endpoint can be setup with the wizard. The Setup wizard contains questions relating to settings that the Agent could not make determinations for due to organizational/cultural restrictions. Specific choices that can be made during evaluation and setup are detailed below. 

### Evaluation
Evaluation can be started on one or more endpoints simultaneously through the Endpoint Setup page. 
  
<img src="../images/SelectEvaluation.PNG" width="750">
  
When endpoints are selected for evaluation, one of three options can be chosen. Endpoints can either be placed into a new group and evaluated, placed into a pre-existing group and evaluated, or evaluation and set up can be skipped entirely and an existing configuration set will be immediately applied. 
  
<img src="../images/EvaluationPrompt.PNG" width="750">
  
Adding the Endpoint to an existing group will utilize the group's pre-existing configuration set as a baseline and ignore settings that are already not configured for the group. 

### Guided Setup
Setup must be done for endpoints one at a time. When the setup wizard begins, the Senteon User can choose to skip the wizard and immediately setup the wizard with the configuration set of its current group regardless of the conflicts found in the wizard. Otherwise, the wizard will run through a set of questions that detail specific issues related to settings and provide endpoint specific data for settings that have findings. Senteon also provides an explanation as to the importance and potential impact caused by these settings to help Senteon Users make clear informed decisions. Some settings decisions are considered to be organization wide, and will only be queried once. Once a decision as been made, these settings will be accessible for the Managed Account settings for modification. 
  
<img src="../images/readyforsetup.PNG" width="750">
  

Example Wizard Page:  
<img src="../images/wizardpage.PNG" width="750">

## Configuration Sets

Configuration Sets are groups of settings and their recommended values defined by Senteon as relevant to ensuring a strong security posture. Without Senteon, these settings would typically be managed and controlled using local/Domain Group Policy or the Windows Registry.

There are two (2) types of Configuration Sets:

| Type | Description |
|:------------------:|:-----------|
| Recommended Configuration Set | A set of recommended security-related settings/values based on industry best-practice guidelines for a type of endpoint |
| Applied/Target Configuration Set | A baseline of settings/values that Senteon actually uses for implementation and monitoring/alerting purposes. It is derived from a Recommended Configuration Set and is the result of any modifications/exceptions. Groups/Endpoints are associated with exactly one (1) |

Recommended Configuration Sets are derived from various industry-recognized benchmarks such as:

- Center for Internet Security (CIS) Benchmarks
- Defense Information Systems Agency's Security Technical Implementation Guides (DISA STIGs)
- Microsoft's Security Configuration Framework (SCF).

Senteon provides a Recommended Configuration Set for each type of supported "Endpoint Profile":

- Windows 10 Standalone
- Windows 10 Domain Member


### Setting Information

Senteon provides a variety of information about the Senteon-supported settings to help educate and inform Senteon Users. Each setting can be viewed to see the following:


| Data | Description |
|:----:|:-----------|
| GPO Path | The path of the setting in Windows local Group Policy |
| Details | Description of the setting and any additional information |
| Registry Data | The Windows Registry Path and Value associated with the setting |
| GPO Recommendations | The default and recommended Group Policy values for the setting |
 
 *Note: Settings derived from CIS and STIGs benchmarks have aditional information provided in "Details" such as Rationale, Impact, and Default Behavior*
 
<img src="../images/configurationInfoPanel.png" width="750">
  

/* DELETE THIS

### Changing Configurations
Changing setting configurations with a configuration set can be done through multiple methods detailed under the endpoints and groups sections below. It is, however, worth noting that regardless of how configurations are changed and adjusted. they are always associated with groups and not with endpoints directly. As a result, when settings are changed on an endpoint, users will be prompted to move the endpoint into another group with a matching configuration set or create a new exception group with the intended condfiguration set. 

Configuration settings are always changed using a modify window that will display the setting as well as its preferred value and any alternate acceptable values it has. Any place where configurations can be edited will have access to the modify window.

*/
  

## Endpoint/Fleet Management

Senteon Users can observe and manage their fleet of Endpoints in Command Center. When Senteon Agent is installed on an Endpoint, it will register itself with Senteon Master and Command Center. Once registered, it will appear in Command Center under the relevant Managed Account.

**Location**

`Managed Account Console > Endpoints (tab) > Endpoints (page)`

<img src="../images/endpoints.PNG" width="750">


The main `Endpoints` page displays the following information:
  
| Column | Description |
|:-----------:|:-----------|
| Hostname | The hostname of the Endpoint |
| Endpoint ID | A unique identifier generated by Senteon to ensure every Endpoint can be referenced even if hostnames are not unique |
| Group | The current group that the endpoint belongs to and is deriving its Applied/Target Configuration Set from |
| Agent Status | The current status of the Senteon Agent on the Endpoint. Information about the different statuses can be found [here](#agent-statuses) |
| Actions | Depending on the current status of the Senteon Agent/Endpoint, different actions can be performed. Further detail can be found [here](#modifying-endpoints) |
  

### Endpoint Information

On the main `Endpoints` page, the `Info` button next to each Endpoint can be clicked to display in-depth information.

<img src="../images/endpointinfo.png" width="750">  


A window will open and display the following set of information specific to the Endpoint:  
  
| Field | Description |
|:-----------:|:-----------|
| Hostname | The hostname of the Endpoint |
| Operating System | The operating system of the Endpoint|
| OS Version | The OS Version of the Endpoint |
| Connection Status | Displays whether the Endpoint is online or offline based on the last time it checked in |
| Last Check in Time | The last time the endpoint checked in with Senteon Master/Command Center. A long period without a check-in may be an indicator that the Endpoint is currently experiencing issues |
| Install Date | The date/time when the Senteon Agent was installed |
| Agent Version | The current version of the installed Senteon Agent. Agents should automatically update themselves, so an outdated Agent may be an indicator of an issue with the endpoint |
| Group | The current group that the endpoint is in |
| Endpoint Config Status | The current status of the Endpoint's managed security settings </br> - `Healthy` - All settings match the Applied/Target Configuration Set value </br> - `Drifted` - One or more settings have drifted from the Applied/Target Configuration Set value |
| Configuration Set Listing | This window displays the settings/values of the Endpoint's Active/Target Configuration Set along with the current values on the endpoint. Using the radio buttons, the list can be adjusted to display only the settings that have drifted from their target values. Specific information about each control can be viewed by selecting the `View` button for the relevant setting |

  
<img src="../images/endpointinfopage.png" width="750">
 
### Agent Statuses

All of the possible states that Senteon Agent can be in are detailed here:
  
| State | Description |
|:-----------:|:-----------|
| Active | The Endpoint has finished Intelligent Setup and Senteon Agent is actively monitoring for drift from the associated Applied/Target Configuration Set |
| Creating Temporary Endpoint Profile | The Agent is currently in the process of installing, but has not finished yet |
| Disabling Endpoint | The Agent is in the process of reverting the Senteon-managed settings back to the state they were in prior to Senteon and disabling itself |
| Disabled | The Agent is fully disabled and is not managing/monitoring the Endpoint. Senteon-managed settings are reverted back to the state they were in prior to Senteon |
| Evaluating | The Agent is currently in the process of evaluating the Endpoint |
| Ready for Setup | The Endpoint has finished Evaluation and is ready to begin Guided Setup |
| Ready to Begin Evaluation | The Senteon Agent has been successfully installed and is ready to begin evaluating the Endpoint |
| Uninstalling | The Agent has been uninstalled from the endpoint. It is safe to remove the Endpoint from the Managed Account |



### Endpoint Actions

Depending on the current status of a Senteon Agent/Endpoint, different actions can be performed.

**Location**

`Managed Account Console > Endpoints (tab) > Endpoints (page)`

All of the possible actions are are:

| Action | Availability (Agent Status) | Usage |
|:-----------:|:-----------:|:-----------:|
| Info | Always Available | Displays info specific to the Endpoint including its current configuration status, operating system, and a list of applied configurations |
| Disable | `Active`, `Creating Temporary Endpoint Profile`, `Evaluating`, `Ready to Begin Evaluation`, or `Ready for Setup`| Disables the Agent on the Endpoint and reverts the Senteon-managed settings back to the state they were in prior to Senteon </br> *Note: This happens automatically when an Agent is uninstalled* |
| Enable | `Disabled` | Reverts the Agent/Endpoint back to its status before it was disabled |
| Edit | `Active` | Provides the ability to work with the group and configuration sets associated with the endpoint. More information can be found under [Modifying Endpoint Configurations](#modifying-endpoint-configurations) |
| Reset | `Disabled` | Resets the Agent Status back to `Ready to Begin Evaluation`|
| Remove | `Uninstalling` | Removes the Endpoint from the Managed Account |

### Modifying an Endpoint's Applied/Target Configuration Set

An individual Endpoint's Applied/Target Configuration Set can be modified either by changing the Group the Endpoint belongs to or by directly editing the Endpoint's target setting values. Both methods can be accessed by clicking the `Edit` button next to an Endpoint.

**Location**

`Managed Account Console > Endpoints (tab) > Endpoints (page)`

<img src="../images/editEndpoint.png" width="750">


#### Changing an Endpoint's Group

After clicking the `Edit` button, the `Edit Groups` page will display the Endpoint's current Group as well as all other compatible Groups you can move the Endpoint to.

*Note: You can only move an Endpoint into a Group of the same Endpoint Type/Profile (e.g. Windows 10 Standalone)*

When a Group is selected, all of the target setting values that are different between it and the current Group are displayed.
  
<img src="../images/groupDiff.PNG" width="750">

**Steps**

1) Navigate to `Managed Account Console > Endpoints (tab) > Endpoints (page)` and click the `Edit` button on the Endpoint you wish to modify

2) In the new window, select `Edit Groups`

3) Select the Group you wish to move the Endpoint into and click the `Change Group` button


#### Modifying Individual Settings
After clicking the `Edit` button, the `Edit Individual Settings` page will display the Endpoint's Applied/Target Configuration Set which is inherited from its Group.

In this page you can view Setting information by clicking `View`. You can also modify individual target settings/values by clicking `Modify`, making a selection, and then clicking the`Save Settings` button.

After clicking `Save Settings`, Senteon will determine if there are any Groups with an Applied/Target Configuration Set that matches the modifications. If any matching Groups exist, an option will be provided to move the Endpoint into the existing Group. If there are no matching Groups, or you choose not to add the Endpoint to a matching one, a new Exception Group will be made for the Endpoint. 

  
<img src="../images/endpointIndivSetting.PNG" width="750">

## Groups
Groups are utilized to keep endpoints consistent with the same baseline. Each group has a configuration set associated with it that is used by all endpoints within the group. Groups must have endpoints of the same types within them. Endpoint types are defined by Senteon when they have different full configuration sets. Examples include `Windows 10 Standalone`, `Windows 10 Domain Joined`, and `Server 2016 Non-DC`. This endpoint type is determined when the Agent is installed and will be listed as the endpoint's group until it is placed in a created group during evaluation. There are two different types of groups available for creation:
  
| Group Type | Description |
|:-----------:|:-----------:|
| Management Group | Management Groups have all settings available for the endpoint type and should be used for general baselines that include the majority of endpoints |
| Exception Group | Exception Groups are created underneath a management group and only have the settings that are configured to be different from its parent management group. These groups should be used when Endpoints have configuration sets that are slightly different from the management group. |
  
### Group Info
Info for a specific group can be accessed by selecting the `view` button next to the relevant group.
Group info for Management Groups will display the current endpoints that belong to the role, the current configuration set for the role, and the exception groups underneath that management group. 
Group info for an Exception Group will display the current endpoints that belong to the role, the current configurations set that are different from the management group, and its entire effective configuration set with the management group's controls included. 

The Group info page also includes a button used to generate a report specific to the group. To learn more about reports, please reference the [reports page](reports.md)

### Group Modification
There is a multitude of ways to affect a group and its configuration sets that are dependent on the type of group. The different types of methods to change group configurations are detailed below. 

### Creating Management Groups
Management Groups can be created from the Groups page. When doing so, the group's name and configuration set can be defined and endpoints can be moved into the group as it is created through the Group Creation Form.
  
<img src="../images/newGroup.PNG" width="750">  

#### Creating Exception Groups
Exception Groups can be made using the `Create Exception` button available to Management Groups. Creation of an Exception Group allows the Senteon User to select endpoints within the Management Group to move to the Exception Group and change settings are necessary.

  
<img src="../images/createException.PNG" width="750">

#### Merging Exception Groups
When an Exception Group is no longer necessary, Senteon Users can merge the Exception Group back into its Parent Management Group and return the endpoints back to the Management Group. This is done through the `Edit Groups` Window when accessed for a Management Group. 

  
<img src="../images/groupMergeChildren.PNG" width="750">
  

#### Converting Exception Groups
In some situations, Senteon Users may decide they want to convert an Exception Group into a standalone Management Group. This is done using the `Convert to Mgmt Grp` button available to Exception Groups. Doing so will turn the Exception Group into a Management Group with the same name, effective configuration set (its former parent Management Group's configuration set + the groups own differences), and all endpoints previously part of the Exception Group. 


#### Modifying Individual Settings
To modify specific settings for a group, access the individual setting tab in the `Edit Groups` window. For Management Groups, settings can be directly modified and saved here. For Exception Groups, Settings associated with the exception group can be directly modified here. Other settings can be added to the exception group and modified here as well using the `Add Settings` button. Settings can also be removed from the Exception set using the `Remove Selected Setting from Exception` button. 
  
Management Group:  
<img src="../images/groupModifyIndividual.PNG" width="750">
  
Exception Group:  
<img src="../images/groupModifyIndividualException.PNG" width="750">

#### Moving Endpoints
Endpoints can be directly moved between groups through the `Edit Groups` window. Groups will list all endpoints within the group and all endpoints outside the group. An endpoint can be moved into a group and out of a group from any group window. 
  
<img src="../images/modifyGroupEndpoint.PNG" width="750">
