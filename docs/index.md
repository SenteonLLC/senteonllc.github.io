# Senteon Overview
Welcome to the documentation for Senteon's Security Configuration Management solution. Basic terminology and operating system support details are listed below.

Senteon recommends reading the sections below for key concepts and install instructions if it is your first time using the solution. 


## Before You Begin

### Terminology

| Term | Description |
|:--------------:|:-----------|
| Senteon Command Center | Senteon's central, self-hosted administrative console |
| Senteon Agent | A small program installed on each endpoint that performs actions and communicates back to Command Center |
| Senteon Master | Senteon's back-end private cloud services which do the following: </br></br> - Communications facilitation between Command Center and Agent(s) </br> - Authentication services </br> - ML assistance for endpoint evaluation |
| Master Account | The primary account that you signed up for Senteon with. This account acts as a container for all of your users, data, and resources |
| Managed Account | A "sub-account" within the Master Account that you set up for each organization you wish to manage. Agents/endpoints are registered to Managed Accounts for administration |
| Command Center User | A local user within a Master Account with permissions to login and perform actions in Command Center based off of the user's role |

### Supported Operating Systems

**Senteon Command Center**

- Windows 10 Version 2004+
    - Pro and Enterprise Editions (Not Home)
- Windows Server 2016 Version 2004+
- Windows Server 2019 Version 1809+

**Senteon Agent**

- Windows 10 Version 2004+
    - Pro and Enterprise Editions (Not Home)

---

## Installation

### Prerequisites

Senteon has provided you with:

- Installer for Senteon Command Center
- Master Account credentials for Senteon Command Center

Senteon installation is divided into two separate stages that use different installers. The provided installer is for Command Center, the administrator console. 

After installing Command Center on the computer you intend to use for Senteon administration, the Senteon Agent installer will be created for you to deploy on your endpoints. Documentation for both can be found below.

### Step 1: Install Command Center

*Note: Senteon recommends that you use an account with Administrator privileges to install Senteon Command Center*

1) Transfer `SenteonCommandCenter.msi` onto the computer that is intended to be used as the central console and execute (double-click). 

 <img src="images/startInstall.png" width="750">

2) Review and Accept the Senteon End-User License Agreement, then select `Next`.

<img src="images/eula.png" width="550">

3) Accept the UAC prompt that appears in the taskbar.

<img src="images/uac.png" width="250">

**Post-Install**

After Command Center has finished installing, it can be accessed by searching "Senteon Command Center" in Windows Search or directly at:

 `C:\Program Files\Senteon\CommandCenter\SenteonCommandCenter.exe`

### Step 2: Create a Managed Account for the Organization

1) Login to Command Center using your Master Account User

2) Navigate to the "Account Manager" tab and click `Create Account`

3) Enter a name for the Managed Account in the `Account Identifier` box

4) Copy the Registration Code and save it in a password vault or secure location.
  > *Note: This will be used for installing Senteon Agents*
 
5) Click `Create Managed Account`

### Step 3: Install Senteon Agent(s)


Inside the Command Center install directory (`C:\Program Files\Senteon\CommandCenter\` by default), there will be an additional .msi installer for the Senteon Agent called `SenteonAgent.msi`. This installer should be distributed and installed onto all systems that you intend to manage. 

<img src="images/agentlocation.png" width="750">

---

**To install you will need:**

- `Managed Account ID` - ID/Name of Managed Account you wish to register the agent/endpoint to

- `Registration Code` - Registration code for Managed Account

*Note: You **MUST** use an account with Administrator privileges on the endpoint to install Senteon Agent*

#### Senteon Agent GUI/Desktop Install

1) Transfer `SenteonAgentInstaller.msi` onto the endpoint you want to manage and execute (double-click). 

<img src="images/senteonAgent.png" width="750">

2) Review and Accept the Senteon End-User License Agreement, then select `Next`.

<img src="images/eulaAgent.png" width="550">

3) Choose the folder where you want to install (`C:\Program Files\Senteon\SenteonAgent` by default)

4) Enter the requested details for the Managed Account you wish to register the endpoint to.

<img src="images/acctIDPass.png" width="550">

5) Accept the UAC prompt that appears in the taskbar.

<img src="images/uac.png" width="250">

**Post-Install**

After the installation is complete, the "Senteon Agent" service will be running on the endpoint. This service is configured to automatically restart if the computer is rebooted.

#### Senteon Agent Command-line Install
Senteon Agent can be installed using Msiexec. All additional non-Senteon specific flags can be found in MsiExec's documentation. The Senteon recommended install command flags can be found below.

**Install Flags**

| Flag | Description |
|:-------:|:-------:|
| /i   | Install with the following msi file   |
| /quiet   | Silent install without the GUI. Recommended for installs using RMM tools or SCCM   |
| ACCOUNTID=   | Specifies the Managed Account the Agent will belong to   |
| INSTALLCODE=   | Specifies the Registration Code of the Managed Account being used   |
| ACCEPTALL=   | Accepts the EULA   |
| /l*v  | Sets the output file for installation logs   |

---

**Steps**

1) Transfer `SenteonAgentInstaller.msi` onto the endpoint you want to manage. 

<img src="images/senteonAgent.png" width="750">

2) Using Administrator PowerShell or a Remote CLI session with a user that has Administrator privileges, run the following install command:


```  
msiexec /i "<path>\SenteonAgent.msi" /quiet ACCOUNTID="<Managed Account>" INSTALLCODE="<Registration Code>" ACCEPTALL=YES /l*v "SenteonInstall.log"  
```  

**Post-Install**

After the installation is complete, the "Senteon Agent" service will be running on the endpoint. This service is configured to automatically restart if the computer is rebooted.

## Next Steps

In order to configure Senteon Agents to implement and manage your hardened settings, follow the instructions in [Endpoint Configuration](endpointconfiguration.md).
