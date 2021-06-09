# Senteon Technical Details

This section describes technical details about Senteon.

## Supported Operating Systems

**Senteon Command Center**

- Windows 10 Version 2004+
  - Pro and Enterprise (Not Home)
- Windows Server 2016 Version 2004+
- Windows Server 2019 Version 1809+

**Senteon Agent**

- Windows 10 Version 2004+
  - Pro and Enterprise (Not Home)


## Resource Usage

**Senteon Command Center Size**

- Required Disk Space: 29.2 MB
- Avg. Memory Usage: 50-70 MB


**Senteon Agent**

- Required Disk Space: 12.3 MB
- Avg. Memory Usage: 15-25 MB
- Maximum Audit Log size increase from best-practice configurations:
    - Windows 10 - 244 MB


## Networking and Security

### Networking

Senteon Command Center and Senteon Agent require access to Senteon's Master Communications server as well as the Update server.

**Senteon Master Communications Server**

  - DNS Hostname: `master.senteon.co`
  - Required Destination Protocol/Port(s): `TCP 5555`


**Senteon Update Server**

  - DNS Hostname: `updates.senteon.co`
  - Required Destination Protocol/Port(s): `TCP 80 & 443`

### Security

#### Data-in-Transit

Senteon Command Center and Senteon Agent encrypt authentication data in transit using RSA 2048 and AES256. 

#### Data-at-Rest

Senteon hashes and encrypts all credentials and sensitive data at rest.
