# Endpoint Configuration

This section describes the concepts and systems that Senteon uses to manage security-related settings on your endpoints. We highly recommend that you familiarize yourself with this section before completing Intelligent Setup and administering Senteon.

Below you can find details regarding how to complete the setup of your fleet of endpoints from start to finish, the settings/configurations Senteon manages, how a Senteon user should expect to organize and manage their fleet of endpoints, and what healthy activity looks like.

## Intelligent Setup

Senteon assists users in performing baseline security configuration (also known as system hardening) by guiding them through Senteon's "Intelligent Setup" process. 

Intelligent Setup has two phases:

1) Evaluation

2) Guided Setup
 
Senteon Agents will evaluate your Endpoints to determine what potential blocking/disruption factors there may be to enabling recommended security settings. After Evaluation, Senteon will use the results to provide a unique Guided Setup Wizard which will help you get as close to the recommendations as possible while providing actionable data on how to overcome blocking/disruption factors.

Once Command Center and the Senteon Agents are installed on their corresponding systems, Endpoints will populate in the Managed Account Console with an "Agent Status" of `Ready to Begin Evaluation`. From here you will be able to begin the Evaluation Phase of Intelligent Setup.

### Phase 1: Evaluation

During Evaluation, one or more Endpoints will be analyzed to determine which security-related settings can be safely implemented without disrupting user experience and/or network operations.

Endpoints that are ready to begin Evaluation will appear in the `Endpoint Setup` page under "Ready for Evaluation"

**Location:** `Managed Account Console > Endpoints (Endpoint Type) > Endpoint Setup (page)`
  
<img src="../images/SelectEvaluation.PNG" width="750">

---
When Endpoints are selected for Evaluation, one of the following options can be chosen:

- Create a new Group to add the Endpoint(s) and Evaluate based off of the Group's Configuration Set
- Add the Endpoint(s) to a pre-existing Group and Evaluate based off of the Group's Configuration Set
- Add the Endpoint(s) to a pre-existing Group and skip Intelligent Setup
    - *Note: The Group's Configuration Set will be immediately applied with no regard to potential blocking/disruption factors*

<img src="../images/EvaluationPrompt.PNG" width="750">

### Phase 2: Guided Setup

After a Senteon Agent/Endpoint finishes Evaluation, the Agent Status will change to `Ready for Setup` and it will appear in the `Endpoint Setup` page under "Ready for Setup"

<img src="../images/readyforsetup.PNG" width="750">

Clicking the `Finish Setup` button next to an Endpoint will launch the Guided Setup Wizard which walks you through any decisions that need to be made due to blocking/disruption factors. This can range from technical factors such as out-of-date authentication protocols to organizational/cultural factors that Senteon cannot be aware of in a vacuum.

Example Wizard Page:  
<img src="../images/wizardpage.PNG" width="750">

#### Account-wide Guided Setup Decisions

Some Wizard questions will have a warning such as **"Warning: Once this decision has been made, it will be set for all systems configured through Senteon after this"** which indicates that Senteon will only ask you to make the decision once for all Endpoints in the Managed Account. The decision can be adjusted for the setup of subsequent Endpoints in the following location:

`Managed Account Console > Settings > Account-wide Guided Setup Decisions`

More information can be found [here](settings.md#general-settings_1)

#### Guided Setup for Multiple Endpoints

Guided Setup can only be completed for one (1) endpoint at a time in this version since each Senteon Agent performs a unique evaluation of its Endpoint. If you would like to setup more than one at a time, Senteon recommends the following work-arounds: 

1) Complete the process for the first Endpoint in the Group in order to finalize the Group's Applied/Target Configuration Set

2a) (Option 1) Note down your decisions and complete the Guided Setup Wizard again for subsequent Endpoints

2b) (Option 2) Override the Setup Wizard for the subsequent Endpoints by choosing the option at the start of the Wizard to skip the questions/decisions and apply the Group's Applied/Target Configuration Set
  > *Note: Senteon cannot gurantee that this will not cause usability or networking issues for these Endpoints since warnings that would be provided in the Wizard will be bypassed.*

<img src="../images/Skip Guided Setup Wizard.png" width="750">

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
- Microsoft's Security Configuration Framework (SCF)

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

## Endpoint/Fleet Management

Senteon Users can observe and manage their fleet of Endpoints in Command Center. When Senteon Agent is installed on an Endpoint, it will register itself with Senteon Master and Command Center. Once registered, it will appear in Command Center under the relevant Managed Account and Endpoint Type (Windows 10 Standalone, Domain Member, Unknown).

The main `Endpoints` tab will display a listing of all Endpoints no matter what type they are. The sub-tabs will display a listing of all Endpoints of the specified type, and allow you to setup and modify those Endpoints.

**Location:** `Managed Account Console > Endpoints (Endpoint Type) > Endpoints (page)`

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
| Endpoint Config Status | The current status of the Endpoint's managed security settings </br></br> - `Healthy`: All settings match the Applied/Target Configuration Set value </br> - `Drifted`: One or more settings have drifted from the Applied/Target Configuration Set value |
| Configuration Set Listing | This window displays the settings/values of the Endpoint's Active/Target Configuration Set along with the current values on the endpoint. Using the radio buttons, the list can be adjusted to display only the settings that have drifted from their target values. Specific information about each control can be viewed by selecting the `View` button for the relevant setting |

  
<img src="../images/endpointinfopage.png" width="750">
 
### Agent Statuses

All of the possible statuses that Senteon Agent can report are detailed here:
  
| Status | Description |
|:-----------:|:-----------|
| Active | The Endpoint has finished Intelligent Setup and Senteon Agent is actively monitoring for drift from the associated Applied/Target Configuration Set |
| Creating Temporary Endpoint Profile | The Agent is currently in the process of installing, but has not finished yet |
| Disabling Endpoint | The Agent is in the process of reverting the Senteon-managed settings back to the state they were in prior to Senteon and disabling itself |
| Disabled | The Agent is fully disabled and is not managing/monitoring the Endpoint. Senteon-managed settings are reverted back to the state they were in prior to Senteon |
| Evaluating | The Agent is currently in the process of evaluating the Endpoint |
| Ready for Setup | The Endpoint has finished Evaluation and is ready to begin Guided Setup |
| Ready to Begin Evaluation | The Senteon Agent has been successfully installed and is ready to begin evaluating the Endpoint |
| Uninstalled | The Agent has been uninstalled from the endpoint. It is safe to remove the Endpoint from the Managed Account |



### Endpoint Actions

Depending on the current status of a Senteon Agent/Endpoint, different actions can be performed.

**Location:** `Managed Account Console > Endpoints (Endpoint Type) > Endpoints (page)`

All of the possible actions are are:

| Action | Availability (Agent Status) | Usage |
|:-----------:|:-----------:|:-----------|
| Info | Always Available | Displays info specific to the Endpoint including its current configuration status, operating system, and a list of applied configurations |
| Disable | `Active`, `Creating Temporary Endpoint Profile`, `Evaluating`, `Ready to Begin Evaluation`, or `Ready for Setup`| Disables the Agent on the Endpoint and reverts the Senteon-managed settings back to the state they were in prior to Senteon </br> *Note: This happens automatically when an Agent is uninstalled* |
| Enable | `Disabled` | Reverts the Agent/Endpoint back to its status before it was disabled |
| Edit | `Active` | Provides the ability to work with the group and configuration sets associated with the endpoint. More information can be found under [Modifying Endpoints](#modifying-endpoints) |
| Reset | `Disabled` | Resets the Agent Status back to `Ready to Begin Evaluation`|
| Remove | `Uninstalling` | Removes the Endpoint from the Managed Account |

### Modifying Endpoints

An individual Endpoint's Applied/Target Configuration Set can be modified either by changing the Group the Endpoint belongs to or by directly editing the Endpoint's target setting values. Both methods can be accessed by clicking the `Edit` button next to an Endpoint.

**Location**

`Managed Account Console > Endpoints (Endpoint Type) > Endpoints (page)`

<img src="../images/editEndpoint.png" width="750">


#### Changing an Endpoint's Group

After clicking the `Edit` button, the `Edit Groups` page will display the Endpoint's current Group as well as all other compatible Groups you can move the Endpoint to.

*Note: You can only move an Endpoint into a Group of the same Endpoint Type/Profile (e.g. Windows 10 Standalone)*

When a Group is selected, all of the target setting values that are different between it and the current Group are displayed.
  
<img src="../images/groupDiff.PNG" width="750">

**Steps**

1) Navigate to `Managed Account Console > Endpoints (Endpoint Type) > Endpoints (page)` and click the `Edit` button on the Endpoint you wish to modify

2) In the new window, select `Edit Groups`

3) Select the Group you wish to move the Endpoint into and click the `Change Group` button


#### Modifying Individual Settings
After clicking the `Edit` button, the `Edit Individual Settings` page will display the Endpoint's Applied/Target Configuration Set which is inherited from its Group.

In this page you can view security setting information by clicking `View`. You can also modify the target values of individual settings by clicking `Modify`, making a selection, and then clicking the `Apply Changes` button.

After clicking `Apply Changes`, Senteon will determine if there are any exising Groups that match the modified Applied/Target Configuration Set. If any matching Groups exist, an option will be provided to move the Endpoint into the existing Group. If there are no matching Groups, or you choose not to add the Endpoint to a matching one, a new Exception Group will be made for the Endpoint. 

<img src="../images/endpointIndivSetting.PNG" width="750">

**Steps**

1) Navigate to `Managed Account Console > Endpoints (Endpoint Type) > Endpoints (page)` and click the `Edit` button on the Endpoint you wish to modify

2) In the new window, select `Edit Individual Settings`

3) Click the `Modify` button next to each setting you wish to modify and choose new target values

4) Click the `Apply Changes` button

5) If any existing Groups match the modified Applied/Target Configuration Set, select whether you would like to move the Endpoint to one of them. Otherwise finish creating a new Exception Group

## Groups

Senteon uses Groups to organize sets of Endpoints and provide the Applied/Target Configuration Set that members of the Group inherit. Each Group can be associated with exactly one (1) Applied/Target Configuration Set, and only Endpoints with the same Endpoint Type/Profile as a Group can become a member (e.g. Windows 10 Standalone).

**Location:** `Managed Account Console > Endpoints (Endpoint Type) > Groups`

There are two (2) different types of Groups:
  
| Group Type/Tier | Description |
|:-----------:|:-----------|
| Management Group | Main type of Group that should be used for organizing different types of Endpoints |
| Exception Group | Group that should be used when one or more Endpoints in a Management Group need slight modifications/exceptions but are still logically related to the Management Group |

The `Groups` page displays the following information:

| Column | Description |
|:-----------:|:-----------|
| Group Name | The name of the Group |
| Group Parent | The name of the Group's parent Group </br> </br> *Note: Management Groups will display their Endpoint Type/Profile here* |
| Group Tier | The tier/type of the Group (Management Group or Exception Group) |
| Actions | Different actions that can be performed. Further detail can be found below |
  
### Group Info

Information about a specific Group can be accessed by selecting the `View` button next to the relevant Group.

Group info for Management Groups will display the following:

- Member Endpoints
- Applied/Target Configuration Set
- Child Exception Groups

Group info for Exception Groups will display the following:

- Member Endpoints
- Exceptions (Diff of parent Management Group's Applied/Target Configuration Set)
- Total Applied/Target Configuration Set

The Group info page also includes a `Generate Report for Group` button which generates a group-specific report. More information on Reports can be found [here](reports.md).

### Creating and Modifying Groups

Senteon Users can create new groups or modify existing ones in a number of ways depending on the Group Type.

#### Creating Management Groups

1) Navigate to `Managed Account Console > Endpoints > Groups` and click the `Create New Group` button

2) Enter a name/identifier for the Group

3) (Optional) Customize the Applied/Target Configuration Set by using the `Set` buttons next to each setting

4) (Optional) Add Endpoints to the Group if you wish to move them
  > *NOTE: NOT RECOMMENDED UNLESS YOU WISH BYPASS INTELLIGENT SETUP*

5) Click the `Create Group` button
  
<img src="../images/newGroup.PNG" width="750">  

#### Creating Exception Groups

Exception Groups can be made using the `Create Exception` button available for Management Groups. Creation of an Exception Group allows the Senteon User to select Endpoints within the Management Group to move to the Exception Group and change settings as necessary.

**Steps**

1) Navigate to `Managed Account Console > Endpoints > Groups`

2) Click the `Create Exception` button next to the Management Group you wish to make an Exception Group under

3) Enter a name/identifier for the Exception Group

4) (Optional) Select Endpoints from the Management Group that you want to add to the Exception Group

5) (Optional) Make exceptions to the parent Management Group's Applied/Target Configuration Set by using the `Modify` buttons next to each setting

6) Click the `Confirm` button
  
<img src="../images/createException.PNG" width="750">

#### Merging Exception Groups

When an Exception Group is no longer necessary, Senteon Users can merge it back into its parent Management Group and return the Endpoints back to the Management Group. 

**Steps**

1) Navigate to `Managed Account Console > Endpoints > Groups`

2) Click the `Modify Group` button next to the parent Management Group

3) Select the `Merge Child Groups` page

4) Select one or more Exception Groups and click the `Merge Group(s)` button

<img src="../images/groupMergeChildren.PNG" width="750">


#### Converting Exception Groups
In some situations, Senteon Users may decide they want to convert an Exception Group into a standalone Management Group. This is done using the `Convert to Mgmt Grp` button available for Exception Groups. This will turn the Exception Group into a Management Group and maintain its member Endpoints and the Applied/Target Configuration Set.

<img src="../images/groupMergeChildren.PNG" width="750">

**Steps**

1) Navigate to `Managed Account Console > Endpoints > Groups`

2) Click the `Convert to Mgmt Grp` button next to the Exception Group

3) Enter a name/identifier for the Group

4) Click the `Confirm` button


#### Modifying Individual Settings

Specific settings/target values can be modified for a whole Group.

**Management Group**

For Management Groups, the Applied/Target Configuration Set can be directly modified and saved.

1) Navigate to `Managed Account Console > Endpoints > Groups`

2) Click the `Modify Group` button next to the Management Group

3) Select the `Edit Individual Settings` page

4) Edit the Applied/Target Configuration Set by using the `Modify` buttons next to each setting

5) Click the `Apply Changes` button

<img src="../images/groupModifyIndividual.PNG" width="750">

  
**Exception Group**

For Exception Groups, settings associated with the Exception Group (exceptions) can be directly modified and saved. Other settings can be added to the Exception Group and modified using the `Add Settings` button. Exception settings can also be removed from the Exception Group using the `Remove Selected Setting from Exception` button. 

1) Navigate to `Managed Account Console > Endpoints > Groups`

2) Click the `Modify Group` button next to the Exception Group

3) Select the `Edit Individual Settings` page

4) Edit the Applied/Target Configuration Set by using the `Modify` buttons next to each setting

5) (Optional) Remove exceptions from the Applied/Target Configuration Set by selecting one or more settings and clicking  the `Remove Selected Setting from Exception` button

6) (Optional) Add exceptions to the Applied/Target Configuration Set by clicking the `Add Settings` button

  6a) Select one or more settings, and then click the `Save` Button
  
  6b) (Optional) Edit the new settings/exceptions by using the `Modify` buttons next to each setting

7) Click the `Apply Changes` button

<img src="../images/groupModifyIndividualException.PNG" width="750">

#### Moving Endpoints

**Move Endpoints From a Group to Another Group**

1) Navigate to `Managed Account Console > Endpoints > Groups`

2) Click the `Modify Group` button next to the Group

3) Select the `Edit Endpoints` page

4) Select one or more Endpoints from the `Endpoints within Group` column and click the `Move selected Endpoints to different Group` button

5) Select a Group from the list of Available Groups and click the `Move to selected Group` button
  
**Move Endpoints To a Group From Another Group**

1) Navigate to `Managed Account Console > Endpoints > Groups`

2) Click the `Modify Group` button next to the Group

3) Select the `Edit Endpoints` page

4) Select one or more Endpoints from the `Endpoints outside Group` column and click the `Add Endpoints to Group` button

<img src="../images/modifyGroupEndpoint.PNG" width="750">
