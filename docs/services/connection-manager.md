---
layout: default
title: ConnectionManagerService
parent: Sonos UPNP
---
# ConnectionManagerService
{: .no_toc }

The ConnectionManagerService is available on these models: `v1-S1` `v1-S5` `v1-S9` .

1. TOC
{:toc}

---


## Service data
{: .no_toc }

| name | value |
|:-----|:------|
| **Control URL** | `http://192.168.x.x:1400/MediaRenderer/ConnectionManager/Control` |
| **Event subscription URL** | `http://192.168.x.x:1400/MediaRenderer/ConnectionManager/Event` |
| **Discovery url** | `http://192.168.x.x:1400/xml/ConnectionManager1.xml` |
| **Service ID** | `urn:upnp-org:serviceId:ConnectionManager` |
| **Service type** | `urn:schemas-upnp-org:service:ConnectionManager:1` |

### Sample request
{: .no_toc }

```http
POST /MediaRenderer/ConnectionManager/Control
Host: 192.168.x.x:1400
SOAP-Action: "urn:schemas-upnp-org:service:ConnectionManager:1#{ActionName}"
Content-Type: text/xml; charset=utf8

<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/" s:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/">
  <s:Body>
    {ActionBodyHere}
  </s:Body>
</s:Envelope>
```

---

## Available actions

### GetProtocolInfo

Action body:

```xml
<u:GetProtocolInfo xmlns:u="urn:schemas-upnp-org:service:ConnectionManager:1">
</u:GetProtocolInfo>
```


No input arguments

Outputs:

| parameter | type | description |
|:----------|:-----|:------------|
| **Source** | `string` |  |
| **Sink** | `string` |  |

### GetCurrentConnectionIDs

Action body:

```xml
<u:GetCurrentConnectionIDs xmlns:u="urn:schemas-upnp-org:service:ConnectionManager:1">
</u:GetCurrentConnectionIDs>
```


No input arguments

Outputs:

| parameter | type | description |
|:----------|:-----|:------------|
| **ConnectionIDs** | `string` |  |

### GetCurrentConnectionInfo

Action body:

```xml
<u:GetCurrentConnectionInfo xmlns:u="urn:schemas-upnp-org:service:ConnectionManager:1">
  <ConnectionID>i4</ConnectionID>
</u:GetCurrentConnectionInfo>
```


Inputs:

| parameter | type | description |
|:----------|:-----|:------------|
| **ConnectionID** | `i4` |  |

Outputs:

| parameter | type | description |
|:----------|:-----|:------------|
| **RcsID** | `i4` |  |
| **AVTransportID** | `i4` |  |
| **ProtocolInfo** | `string` |  |
| **PeerConnectionManager** | `string` |  |
| **PeerConnectionID** | `i4` |  |
| **Direction** | `string` |  Possible values: `Input` / `Output` |
| **Status** | `string` |  Possible values: `OK` / `ContentFormatMismatch` / `InsufficientBandwidth` / `UnreliableChannel` / `Unknown` |


This file is automatically generated with [@svrooij/sonos-docs](https://github.com/svrooij/sonos-api-docs/tree/main/generator/sonos-docs), do not edit manually.