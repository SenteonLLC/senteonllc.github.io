# Getting Started 
## Beta Build

On this page you can find instructions for installing and logging into the beta build of Senteon Fortify

Instructions for utilizing available features can be found here:
  - [Setting up Controls](controls.md)
  - [Resetting Systems](resetting.md)
  - [Generating Reports](reports.md)

### Terminology

`Senteon Command Center` - The central administrator console

`Senteon Agent` - A small program installed on each endpoint that performs actions and communicates back to Command Center

`Managed Account` - An account that agents/endpoints are registered to and managed from

### Supported Operating Systems

**Senteon Command Center**
- Windows 10 Version 2004+
- Windows Server 2016 Version 2004+
- Windows Server 2019 Version 1809+

**Senteon Agent**
- Windows 10 Version 2004+

# Installation

## Please note there are two installs that need to be done to support the Senteon Infrastructure. Please first follow the steps for installed Command Center followed by the steps to install the Senteon Agent.
### The Command Center allows for remote management and administering of the system, but the Senteon Agent is necessary to apply the controls and changes pushed by command center.
For the purposes of the beta, Senteon has provided you with:
- Installer for Senteon Command Center
- Credentials for Senteon Command Center
- Credentials for Managed Account

> **Note**: In full release, you will be able to create new Managed Accounts through Command Center. 

Senteon installation is divided into two separate sets with different installers. The provided installer is the Command Center installer, where customers can manage their controls and accounts. After installing Command Center, the agent installer must be deployed on systems that controls should be applied on. Documentation for setting both up can be found below.

Please be aware that Senteon does not currently support Command Center and Agent installations on the same system. It is highly recommended to keep the services separate to reduce to possibility of operational conflicts with their databases.

# Command Center Installation Steps

1) Load up `SenteonCommandCenter.msi` onto the machine that is intended to be used as the central console and execute (double-click). 

<img src="images/startInstall.png" width="750">

2) Accept the Senteon End-User License Agreement and select `Next`.

<img src="images/eula.png" width="550">

3) Accept the UAC prompt that appears in the taskbar.

<img src="images/uac.png" width="250">

**Post-Install**

After Command Center has finished installing, it can be accessed by searching "Senteon Command Center" in Windows Search or directly at `C:\Program Files\Senteon\CommandCenter\SenteonCommandCenter.exe`.

# Senteon Agent Installation Steps

Inside the Command Center install directory (`C:\Program Files\Senteon\CommandCenter\` by default), there will be an additional .msi installer for the Senteon Agent called `SenteonAgent.msi`. This installer should be distributed and installed onto all systems that you intend to manage. 

<img src="images/agentlocation.png" width="750">


**To install you will need:**

- `Account ID` - ID/Name of Managed Account you wish to register the agent/endpoint to

- `Account Password` - Password for Managed Account

**Steps**

1) Load up `SenteonAgentInstaller.msi` onto the endpoint you want to manage and execute (double-click). 

<img src="images/senteonAgent.png" width="750">

2) Accept the Senteon End-User License Agreement and select `Next`.

<img src="images/eulaAgent.png" width="550">

3) Choose the folder where you want to install (`C:\Program Files\Senteon\SenteonAgent` by default)

4) Enter the credentials for your Managed Account registered in Command Center

<img src="images/acctIDPass.png" width="550">

5) Accept the UAC prompt that appears in the taskbar.

<img src="images/uac.png" width="250">

**Post-Install**

After the installation is complete, the "Senteon Agent" service will be running on the endpoint. This service is configured to automatically restart if the computer is rebooted.

## Next Steps

In order to configure Senteon Agents to implement and manage your hardened settings, follow the instructions in [Setting up Controls](controls.md).
