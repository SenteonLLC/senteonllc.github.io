# Senteon Technical Details

- [Supported Operating Systems](TechnicalDetails.md#supported-operating-systems)
- [Resource Usage](TechnicalDetails.md#resource-usage)
- [Networking and Security](TechnicalDetails.md#networking-and-security)

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
- Avg. Memory Usage: 60-70 MB


**Senteon Agent**
- Required Disk Space: 12.3 MB
- Avg. Memory Usage: 20-25 MB
- Maximum Audit Log Size Increase from Best-Practice Configurations:
    - Windows 10 - 244 MB


## Networking and Security

### Networking

Senteon Command Center and Senteon Agent require access to Senteon's Master Communications server as well as the Updates server.

**Senteon Master Communications Server**
  - DNS Hostname: `master.senteon.co`
  - Required Protocol/Port(s): `TCP 5555`


**Senteon Update Server**
  - DNS Hostname: `updates.senteon.co`
  - Required Protocol/Port(s): `TCP 80 & 443`

### Security

**Data-in-Transit**

Senteon Command Center and Senteon Agent encrypt authentication data in transit using RSA 2048 and AES256. 

**Data-at-Rest**

Senteon hashes and encrypts all credentials and sensitive data at rest.
