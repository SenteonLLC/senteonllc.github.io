# Senteon Installation Instructions
Senteon installation is split into two distinct steps: command center installation & core agent installation.  
The command center console provides centralized management to all agents under your purview and should be installed on the system being used to manage endpoints.  
The core agent performs actions and analysis on client endpoints and reports back to its parent command center.

## Command Center Installer
Command Center installation should be performed with the installer provided specifically to you by Senteon  
To install command center:  
- Run the installer on the management system of choice (current support for Windows systems only)
- Accept the Senteon EULA & choose an install location
- Allow Senteon Command Center to finish its install on your systems 
- Senteon Command Center can now be accessed on the management system.
- Initial admin login information should be provided directly by Senteon and can be changed after first log in.

## Core Agent Installer
Core Agent installer should be used to install agents on any endpoint that you are looking to manage.  
Senteon bills based on agents installed and any unused system should have Senteon uninstalled first or you may be billed an extra cycle for an inactive system.  
The Core Agent installer can be found in the Command Center instal directory and can be copied for deployment as necessary.
To install the core agent through GUI:  
- First ensure that you have the relevant subaccount ID and Password from Command Center
  - If you're unsure what this is, plesae refer here: [subaccounts]()
- Move the installer to the relevant endpoint you're looking to run Senteon on
- Execute the installer and accept the Senteon EULA & choose and install location
- When prompted for accountID and password, input the relevant subaccountID and password retaind from step 1
- Allow Core Agent to finish its install on the system.
- Once installed agent will automatically connect to master and be ready for administration through Command Center. 
