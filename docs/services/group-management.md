---
layout: default
title: GroupManagement
parent: Sonos Services
---
# GroupManagement service
{: .no_toc }

Services related to groups

The GroupManagement service is available on these models: `Sonos Play:1 (S1) S2` / `Sonos One (S13) S2` / `Sonos Beam (S14) S2` / `Sonos Amp (S16) S2` / `Sonos One (S18) S2` / `SYMFONISK Bookshelf (S21) S2` / `Sonos Roam (S27) S2` / `Sonos Play:3 (S3) S2` / `SYMFONISK Bookshelf (S33) S2` / `Sonos One SL (S38) S2` / `Sonos Era 100 (S39) S2` / `Sonos Play:5 (S6) S2` / `Sonos Playbar (S9) S2` / `Sonos Sub (Sub) S2`.

1. TOC
{:toc}

---

## Service data
{: .no_toc }

| name | value |
|:-----|:------|
| **Control URL** | `http://192.168.x.x:1400/GroupManagement/Control` |
| **Event subscription URL** | `http://192.168.x.x:1400/GroupManagement/Event` |
| **Discovery URL** | `http://192.168.x.x:1400/xml/GroupManagement1.xml` |
| **Service ID** | `urn:upnp-org:serviceId:GroupManagement` |
| **Service type** | `urn:schemas-upnp-org:service:GroupManagement:1` |

### Sample request
{: .no_toc }

```text
POST /GroupManagement/Control
Host: 192.168.x.x:1400
soapaction: "urn:schemas-upnp-org:service:GroupManagement:1#{ActionName}"
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

### AddMember

Action body:

```xml
<u:AddMember xmlns:u="urn:schemas-upnp-org:service:GroupManagement:1">
  <MemberID>string</MemberID>
  <BootSeq>ui4</BootSeq>
</u:AddMember>
```

Inputs:

| parameter | type | description |
|:----------|:-----|:------------|
| **MemberID** | `string` |  |
| **BootSeq** | `ui4` |  |

Outputs:

| parameter | type | description |
|:----------|:-----|:------------|
| **CurrentTransportSettings** | `string` |  |
| **CurrentURI** | `string` |  |
| **GroupUUIDJoined** | `string` |  |
| **ResetVolumeAfter** | `boolean` |  `1` for true and `0` for false  |
| **VolumeAVTransportURI** | `string` |  |

### RemoveMember

Action body:

```xml
<u:RemoveMember xmlns:u="urn:schemas-upnp-org:service:GroupManagement:1">
  <MemberID>string</MemberID>
</u:RemoveMember>
```

Inputs:

| parameter | type | description |
|:----------|:-----|:------------|
| **MemberID** | `string` |  |

### ReportTrackBufferingResult

Action body:

```xml
<u:ReportTrackBufferingResult xmlns:u="urn:schemas-upnp-org:service:GroupManagement:1">
  <MemberID>string</MemberID>
  <ResultCode>i4</ResultCode>
</u:ReportTrackBufferingResult>
```

Inputs:

| parameter | type | description |
|:----------|:-----|:------------|
| **MemberID** | `string` |  |
| **ResultCode** | `i4` |  |

### SetSourceAreaIds

Action body:

```xml
<u:SetSourceAreaIds xmlns:u="urn:schemas-upnp-org:service:GroupManagement:1">
  <DesiredSourceAreaIds>string</DesiredSourceAreaIds>
</u:SetSourceAreaIds>
```

Inputs:

| parameter | type | description |
|:----------|:-----|:------------|
| **DesiredSourceAreaIds** | `string` |  |

## Events

The GroupManagementService has variables that might be emitted if you subscribe to events.

### Subscribe to events

```text
SUBSCRIBE /GroupManagement/Event
Host: 192.168.x.x:1400
callback: <http://...>
NT: upnp:event
Timeout: Second-3600
```

### Event variables

| Variable | Sends events* | type | possible values |
|:---------|:-------------|:-----|:----------------|
| GroupCoordinatorIsLocal | ✔ | `boolean` |  `1` for true and `0` for false  |
| LocalGroupUUID | ✔ | `string` |  |
| ResetVolumeAfter | ✔ | `boolean` |  `1` for true and `0` for false  |
| SourceAreaIds |  | `string` |  |
| VirtualLineInGroupID | ✔ | `string` |  |
| VolumeAVTransportURI | ✔ | `string` |  |

If the variable has a `✔` in the Sends events column, the service discovery specifies this variable emits events. Other properties might be send as a part of `LastChange`

---

This file is automatically generated with [@svrooij/sonos-docs](https://github.com/svrooij/sonos-api-docs/tree/main/generator/sonos-docs), do not edit manually.

| Device | Software generation | Software version | Discovery date |
|:-------|:--------------------|:-----------------|:---------------|
| `Sonos Play:1 (S1)` | S2 | 77.4-49290 | 2024-02-13T15:56:06.184Z |
| `Sonos One (S13)` | S2 | 63.2-90210 | 2021-07-21T23:31:19.273Z |
| `Sonos Beam (S14)` | S2 | 64.3-19080 | 2021-08-18T06:04:08.308Z |
| `Sonos Amp (S16)` | S2 | 79.1-53290 | 2024-11-09T18:45:16.539Z |
| `Sonos One (S18)` | S2 | 77.4-49290 | 2024-02-13T15:55:36.464Z |
| `SYMFONISK Bookshelf (S21)` | S2 | 66.4-23300 | 2022-01-01T11:41:01.361Z |
| `Sonos Roam (S27)` | S2 | 63.2-90210 | 2021-07-21T23:31:31.207Z |
| `Sonos Play:3 (S3)` | S2 | 64.3-19080 | 2021-08-18T06:09:36.692Z |
| `SYMFONISK Bookshelf (S33)` | S2 | 77.4-49290 | 2024-02-13T15:55:24.423Z |
| `Sonos One SL (S38)` | S2 | 72.2-40060 | 2023-05-22T16:39:25.503Z |
| `Sonos Era 100 (S39)` | S2 | 79.1-53290 | 2024-11-09T18:45:10.792Z |
| `Sonos Play:5 (S6)` | S2 | 64.3-19080 | 2021-08-18T06:06:35.970Z |
| `Sonos Playbar (S9)` | S2 | 77.4-49290 | 2024-02-13T15:55:46.307Z |
| `Sonos Sub (Sub)` | S2 | 63.2-90210 | 2021-07-21T23:31:40.304Z |
