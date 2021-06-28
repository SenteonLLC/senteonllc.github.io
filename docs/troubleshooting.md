# Toubleshooting

In the event that you run into an issue during the operation of Senteon. There are basic troubleshooting steps that you can follow that may help solve your problem.

## Senteon Agent

### Restart Senteon Agent Service

If an Agent/Endpoint is not responding as expected, often times restarting the `Senteon Agent` service using Windows' Services.msc tool will force resyncronization and solve the problem.

### Senteon Agent Event Logs

Event Logs for Senteon Agent can be found in Windows Event Viewer under:

`Applications and Services Logs > Senteon`

<img src="../images/SenteonAgentEventLog.png" width="250">

## Senteon Command Center

### Reset Local Account Databases

If Command Center is not working as expected, often times resetting a Managed Account's database will force a resyncronization and solve the problem.

1. In the Master Account Console, navigate to `Settings > Account Settings`

2. Select the Managed Account that is having issues and click the `Reset Database` button

<img src="../images/CCResetLocalAccountDB.png" width="750">


### Senteon Command Center Event Logs

Event Logs for Senteon Command Center can be found in Windows Event Viewer under:

`Windows Logs > Application`

<img src="../images/SenteonCCEventLog.png" width="250">