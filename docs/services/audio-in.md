---
layout: default
title: AudioInService
parent: Sonos UPNP
---
# AudioInService
{: .no_toc }

The AudioInService is available on these models: `v1-S5`.

1. TOC
{:toc}

---

## Service data
{: .no_toc }

| name | value |
|:-----|:------|
| **Control URL** | `http://192.168.x.x:1400/AudioIn/Control` |
| **Event subscription URL** | `http://192.168.x.x:1400/AudioIn/Event` |
| **Discovery url** | `http://192.168.x.x:1400/xml/AudioIn1.xml` |
| **Service ID** | `urn:upnp-org:serviceId:AudioIn` |
| **Service type** | `urn:schemas-upnp-org:service:AudioIn:1` |

### Sample request
{: .no_toc }

```http
POST /AudioIn/Control
Host: 192.168.x.x:1400
soapaction: "urn:schemas-upnp-org:service:AudioIn:1#{ActionName}"
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

### GetAudioInputAttributes

Action body:

```xml
<u:GetAudioInputAttributes xmlns:u="urn:schemas-upnp-org:service:AudioIn:1">
</u:GetAudioInputAttributes>
```

No input arguments

Outputs:

| parameter | type | description |
|:----------|:-----|:------------|
| **CurrentName** | `string` |  |
| **CurrentIcon** | `string` |  |

### GetLineInLevel

Action body:

```xml
<u:GetLineInLevel xmlns:u="urn:schemas-upnp-org:service:AudioIn:1">
</u:GetLineInLevel>
```

No input arguments

Outputs:

| parameter | type | description |
|:----------|:-----|:------------|
| **CurrentLeftLineInLevel** | `i4` |  |
| **CurrentRightLineInLevel** | `i4` |  |

### SelectAudio

Action body:

```xml
<u:SelectAudio xmlns:u="urn:schemas-upnp-org:service:AudioIn:1">
  <ObjectID>string</ObjectID>
</u:SelectAudio>
```

Inputs:

| parameter | type | description |
|:----------|:-----|:------------|
| **ObjectID** | `string` |  |

### SetAudioInputAttributes

Action body:

```xml
<u:SetAudioInputAttributes xmlns:u="urn:schemas-upnp-org:service:AudioIn:1">
  <DesiredName>string</DesiredName>
  <DesiredIcon>string</DesiredIcon>
</u:SetAudioInputAttributes>
```

Inputs:

| parameter | type | description |
|:----------|:-----|:------------|
| **DesiredName** | `string` |  |
| **DesiredIcon** | `string` |  |

### SetLineInLevel

Action body:

```xml
<u:SetLineInLevel xmlns:u="urn:schemas-upnp-org:service:AudioIn:1">
  <DesiredLeftLineInLevel>i4</DesiredLeftLineInLevel>
  <DesiredRightLineInLevel>i4</DesiredRightLineInLevel>
</u:SetLineInLevel>
```

Inputs:

| parameter | type | description |
|:----------|:-----|:------------|
| **DesiredLeftLineInLevel** | `i4` |  |
| **DesiredRightLineInLevel** | `i4` |  |

### StartTransmissionToGroup

Action body:

```xml
<u:StartTransmissionToGroup xmlns:u="urn:schemas-upnp-org:service:AudioIn:1">
  <CoordinatorID>string</CoordinatorID>
</u:StartTransmissionToGroup>
```

Inputs:

| parameter | type | description |
|:----------|:-----|:------------|
| **CoordinatorID** | `string` |  |

Outputs:

| parameter | type | description |
|:----------|:-----|:------------|
| **CurrentTransportSettings** | `string` |  |

### StopTransmissionToGroup

Action body:

```xml
<u:StopTransmissionToGroup xmlns:u="urn:schemas-upnp-org:service:AudioIn:1">
  <CoordinatorID>string</CoordinatorID>
</u:StopTransmissionToGroup>
```

Inputs:

| parameter | type | description |
|:----------|:-----|:------------|
| **CoordinatorID** | `string` |  |

## Events

The AudioInService has variables that might be emitted if you subscribe to events.

### Subscribe to events

```http
SUBSCRIBE /AudioIn/Event
Host: 192.168.x.x:1400
callback: <http://...>
NT: upnp:event
Timeout: Second-3600
```

### Event variables

| Variable | Sends events* | type | possible values |
|:---------|:-------------|:-----|:----------------|
| AudioInputName | ✔ | `string` |  |
| Icon | ✔ | `string` |  |
| LeftLineInLevel | ✔ | `i4` |  |
| LineInConnected | ✔ | `boolean` |  |
| Playing | ✔ | `boolean` |  |
| RightLineInLevel | ✔ | `i4` |  |

If the variable has a `✔` in the Sends events column, the service discovery specifies this variable emits events. A `❌` doesn't mean that is won't emit events.

---

This file is automatically generated with [@svrooij/sonos-docs](https://github.com/svrooij/sonos-api-docs/tree/main/generator/sonos-docs), do not edit manually.
