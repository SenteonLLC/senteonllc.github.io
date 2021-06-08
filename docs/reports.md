# Reports Overview
This section describes the reporting functionality of Senteon.

- [Generating Reports](reports.md#generating-reports)
  - [Managed Account Reports](reports.md#managed-account-reports)
  - [Group Reports](reports.md#group-reports)

# Generating Reports
Senteon Command Center allows you to generate PDF-based reports. These reports can be generated for an entire fleet of endpoints in a Managed Account or for a specific Group. 

**Output Location**

By default, reports are saved to the Windows "Documents" folder. When a report is generated, it will automatically be opened with the default PDF viewing application.


## Managed Account Reports

Managed Account Reports can be generated in the following location: `Managed Account Console > Dashboard`


### Report Options

You can choose from the following options depending on the data you wish to include in a report:

| Option | Description |
|:--------------:|:-----------:|
| Endpoints | Dislays a listing of all Endpoints within the Managed Account organized by Group with their current compliance percentages |
| Security Configurations | Displays a listing of all Senteon-supported Security Configurations in the form of "Configuration Sets" with descriptions and Senteon preferred values |
| Alerts | Displays a listing of all Alerts generated for the Managed Account in the last month |

- `Endpoints` - Dislays a listing of all Endpoints within the Managed Account organized by Group with their current compliance percentages
- `Security Configurations` - Displays a listing of all Senteon-supported Security Configurations in the form of "Configuration Sets" with descriptions and Senteon preferred values
- `Alerts` - Displays a listing of all Alerts generated for the Managed Account in the last month

## Group Reports

Group Reports can be generated in the following location: `Managed Account Console > Endpoints > Groups`

1) Click the `View` button on the group you wish to generate a report for
2) Click the `Generate Report` button

### Report Options

Group Reports will display all of the Endpoints, Security Configurations, and Alerts specific to the Group and all Endpoints within that Group. 
