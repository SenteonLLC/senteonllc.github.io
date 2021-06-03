# Senteon Technical Details

- [Resource Usage](TechnicalDetails.md#resource-usage)
- [Networking & Security](TechnicalDetails.md#networking-and-security)


## Resource Usage

**Senteon Agent**
- Required Disk Space: 12.3 MB
- Avg. Memory Usage: 20-25 MB

**Senteon Command Center Size**
- Required Disk Space: 29.2 MB
- Avg. Memory Usage: 60-70 MB


## Networking and Security

### Networking

Senteon Command Center and Senteon Agent require access to Senteon's Master Communications server as well as the Updates server

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
