# Configuration Sets
Configuration sets are groups of settings defined by Senteon as required or important for endpoints to have enabled or managed to ensure a strong security posture. Without Senteon, these settings would typically be managed and controlled through the local Group Policy console on the endpoint. Senteon utilitizes these defined configuration sets by associating them with groups to ensure that all endpoints within a group all remain consistent with each other. 

## Setting Information
Every setting within a configuration set can be viewed to see the setting's GPO path as well as its underlying value (registry, auditpol, secpol, etc). Information panels also include descriptions that have an explanation of the setting, rationale for why it should be configured, the impact of configuring the control, and its default and preferred configuration values. Finally, any compliance or severity value will also be listed here. 

## Changing Configurations
Changing setting configurations with a configuration set can be done through multiple methods detailed under the endpoints and groups sections below. It is, however, worth noting that regardless of how configurations are changed and adjusted. they are always associated with groups and not with endpoints directly. As a result, when settings are changed on an endpoint, users will be prompted to move the endpoint into another group with a matching configuration set or create a new exception group with the intended condfiguration set. 

# Endpoints
Once a Senteon Agent is installed, it will fingerprint the system it is installed on and register itself with the Senteon Servers and display an entry on the endpoint listing for the managed account. 
## Endpoint Listing
## Endpoint Information
## Modifying Endpoints
### Changing Groups
### Changing Controls
## Endpoint States

# Groups
## Group Info
## Group Modification
### Moving Endpoints
### Making Exception Groups
### Merging Exception Groups
### Converting Exception Groups
### Individual Control Modification
### New Management Group Creation

# Setup
## Evaluation
## Finalization Wizard
