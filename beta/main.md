# Getting Started 
## Beta Build

On this page you can find instructions for installing and logging into the beta build of Senteon Fortify
Instructions for utilizing available features can be found here:
  - [Setting up Controls](controls.md)
  - [Resetting Systems](resetting.md)
  - [Generating Reports](reports.md)

## Installation
Senteon Beta Command Center installer is distributed directly by Senteon. 

Simply load up the msi onto the machine that is intended to be used as the command console and execute. 
Accept the Senteon End User License Agreement and select an install location. (Senteon recommends leaving it in the default `C:\Program Files\` directory)
Once the install finishes, the command console can now be accessed from this machine. 

Inside the command center install directory (`C:\Program Files\Senteon\CommandCenter\` by default), there will be an additional .msi installer for the Senteon core agent called SenteonCoreInstaller. This installer should be distributed and installed onto all systems that you intend to keep secured by Senteon controls. 

This installer requires the entry of an accountID and password for successful installation. This accountID and password refer to the specific client that the agent is intended to be serving. For the cases of the beta, this accountID and password will be provided to you. 
In proper release, new accounts can be created from the command center. 


## Logging in
Once Command Center installation has completed, the command console can be accessed from the local machine that it was installed on. 
The username and password will be provided to the client and is different from the one used to install core agents on client systems. This username and password combination provide full privileged access into the CommandCenter admin console from which all client accounts can be accessed and managed through. 