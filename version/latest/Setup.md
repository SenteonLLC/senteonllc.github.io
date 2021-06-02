# Senteon Command Center Installation
The Senteon Command Center installer is directly distributed for use by the Senteon team. 

**Steps**

1) Transfer `SenteonCommandCenter.msi` onto the computer that is intended to be used as the central console and execute (double-click). 

<img src="images/startInstall.png" width="750">

2) Review and Accept the Senteon End-User License Agreement, then select `Next`.

<img src="images/eula.png" width="550">

3) Accept the UAC prompt that appears in the taskbar.

<img src="images/uac.png" width="250">

**Post-Install**

After Command Center has finished installing, it can be accessed by searching "Senteon Command Center" in Windows Search or directly at `C:\Program Files\Senteon\CommandCenter\SenteonCommandCenter.exe`.


# Managed Accounts
Managed accounts are created using the Command Center console. Managed accounts are used to differentiate different clients under the parent company for multi tenant support. When a managed account is created, Senteon generates a registration code along side it that is used to verify the authenticity of the install. Users should retain this information in a password vault or other secure storage. 

# Senteon Agent Installation
Inside the Command Center install directory (`C:\Program Files\Senteon\CommandCenter\` by default), there will be an additional .msi installer for the Senteon Agent called `SenteonAgent.msi`. This installer should be distributed and installed onto all systems that you intend to manage. 

<img src="images/agentlocation.png" width="750">

**To install you will need:**

- `Managed Account ID` - ID/Name of Managed Account you wish to register the agent/endpoint to

- `Registration Code` - Registration code for Managed Account

**Steps**

The Agent can be installed by either double-clicking the installer file or via the commandline. Senteon recommends using the msiexec commandline tool as shown below if you are using SCCM or an RMM tool to distribute the agent: 

~~~~~~~~~~
msiexec /i "<path on target endpoint\>SenteonAgent.msi" /quiet ACCOUNTID="<Managed Account ID>" INSTALLCODE="<Registration Code>" ACCEPTALL=YES /l*v "SenteonInstall.log"
~~~~~~~~~~


If you instead wish to utilize the Windows GUI, follow these steps:

1) Transfer `SenteonAgentInstaller.msi` onto the endpoint you want to manage and execute (double-click). 

<img src="images/senteonAgent.png" width="750">

2) Review and Accept the Senteon End-User License Agreement, then select `Next`.

<img src="images/eulaAgent.png" width="550">

3) Choose the folder where you want to install (`C:\Program Files\Senteon\SenteonAgent` by default)

4) Enter the requested details for the Managed Account you wish to register the endpoint to.

<img src="images/acctIDPass.png" width="550">

5) Accept the UAC prompt that appears in the taskbar.

<img src="images/uac.png" width="250">


# Install Flags
Senteon Agent installer is run using the Msiexec and has a multitude of flags that can be utilized during the installation process. All available flags can be found in the MsiExec documentation. The Senteon recommended install command flags can be found below.

| Flag | Usage |
|:--------|:-------:|
| /i   | specifies MsiExec to run a standard install with the following msi file   |
| /quiet   | specifies a silent install without the GUI. Recommended for installs using RMM tools or SCCM   |
| ACCOUNTID=   | Specifies the managed account this agent belongs to   |
| INSTALLCODE=   | Specifies the registration code the managed account being used   |
| ACCEPTALL=   | Accepts the EULA   |
| /l*v  | sets up a file for logging information from the install   |


