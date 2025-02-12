---
layout: default
title: VirtualLineInService
parent: Sonos UPNP
---
# VirtualLineInService
{: .no_toc }

The VirtualLineInService is available on these models: `v1-S1` / `v1-S5` / `v1-S9`.

1. TOC
{:toc}

---

## Service data
{: .no_toc }

| name | value |
|:-----|:------|
| **Control URL** | `http://192.168.x.x:1400/MediaRenderer/VirtualLineIn/Control` |
| **Event subscription URL** | `http://192.168.x.x:1400/MediaRenderer/VirtualLineIn/Event` |
| **Discovery url** | `http://192.168.x.x:1400/xml/VirtualLineIn1.xml` |
| **Service ID** | `urn:upnp-org:serviceId:VirtualLineIn` |
| **Service type** | `urn:schemas-upnp-org:service:VirtualLineIn:1` |

### Sample request
{: .no_toc }

```http
POST /MediaRenderer/VirtualLineIn/Control
Host: 192.168.x.x:1400
soapaction: "urn:schemas-upnp-org:service:VirtualLineIn:1#{ActionName}"
Content-Type: text/xml; charset="utf-8"

<?xml version="1.0" encoding="utf-8"?>
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/" s:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/">
  <s:Body>
    {ActionBodyHere}
  </s:Body>
</s:Envelope>
```

---

## Available actions

### Next

Action body:

```xml
<u:Next xmlns:u="urn:schemas-upnp-org:service:VirtualLineIn:1">
  <InstanceID>ui4</InstanceID>
</u:Next>
```

Inputs:

| parameter | type | description |
|:----------|:-----|:------------|
| **InstanceID** | `ui4` |  |

### Pause

Action body:

```xml
<u:Pause xmlns:u="urn:schemas-upnp-org:service:VirtualLineIn:1">
  <InstanceID>ui4</InstanceID>
</u:Pause>
```

Inputs:

| parameter | type | description |
|:----------|:-----|:------------|
| **InstanceID** | `ui4` |  |

### Play

Action body:

```xml
<u:Play xmlns:u="urn:schemas-upnp-org:service:VirtualLineIn:1">
  <InstanceID>ui4</InstanceID>
  <Speed>string</Speed>
</u:Play>
```

Inputs:

| parameter | type | description |
|:----------|:-----|:------------|
| **InstanceID** | `ui4` |  |
| **Speed** | `string` |  |

### Previous

Action body:

```xml
<u:Previous xmlns:u="urn:schemas-upnp-org:service:VirtualLineIn:1">
  <InstanceID>ui4</InstanceID>
</u:Previous>
```

Inputs:

| parameter | type | description |
|:----------|:-----|:------------|
| **InstanceID** | `ui4` |  |

### SetVolume

Action body:

```xml
<u:SetVolume xmlns:u="urn:schemas-upnp-org:service:VirtualLineIn:1">
  <InstanceID>ui4</InstanceID>
  <DesiredVolume>ui2</DesiredVolume>
</u:SetVolume>
```

Inputs:

| parameter | type | description |
|:----------|:-----|:------------|
| **InstanceID** | `ui4` |  |
| **DesiredVolume** | `ui2` |  |

### StartTransmission

Action body:

```xml
<u:StartTransmission xmlns:u="urn:schemas-upnp-org:service:VirtualLineIn:1">
  <InstanceID>ui4</InstanceID>
  <CoordinatorID>string</CoordinatorID>
</u:StartTransmission>
```

Inputs:

| parameter | type | description |
|:----------|:-----|:------------|
| **InstanceID** | `ui4` |  |
| **CoordinatorID** | `string` |  |

Outputs:

| parameter | type | description |
|:----------|:-----|:------------|
| **CurrentTransportSettings** | `string` |  |

### Stop

Action body:

```xml
<u:Stop xmlns:u="urn:schemas-upnp-org:service:VirtualLineIn:1">
  <InstanceID>ui4</InstanceID>
</u:Stop>
```

Inputs:

| parameter | type | description |
|:----------|:-----|:------------|
| **InstanceID** | `ui4` |  |

### StopTransmission

Action body:

```xml
<u:StopTransmission xmlns:u="urn:schemas-upnp-org:service:VirtualLineIn:1">
  <InstanceID>ui4</InstanceID>
  <CoordinatorID>string</CoordinatorID>
</u:StopTransmission>
```

Inputs:

| parameter | type | description |
|:----------|:-----|:------------|
| **InstanceID** | `ui4` |  |
| **CoordinatorID** | `string` |  |

## Events

The VirtualLineInService has variables that might be emitted if you subscribe to events.

### Subscribe to events

```http
SUBSCRIBE /MediaRenderer/VirtualLineIn/Event
Host: 192.168.x.x:1400
callback: <http://...>
NT: upnp:event
Timeout: Second-3600
```

### Event variables

| Variable | Sends events* | type | possible values |
|:---------|:-------------|:-----|:----------------|
| AVTransportURIMetaData | ❌ | `string` |  |
| CurrentTrackMetaData | ❌ | `string` |  |
| CurrentTransportActions | ❌ | `string` |  |
| EnqueuedTransportURIMetaData | ❌ | `string` |  |
| LastChange | ✔ | `string` |  |

If the variable has a `✔` in the Sends events column, the service discovery specifies this variable emits events. A `❌` doesn't mean that is won't emit events.

---

This file is automatically generated with [@svrooij/sonos-docs](https://github.com/svrooij/sonos-api-docs/tree/main/generator/sonos-docs), do not edit manually.
