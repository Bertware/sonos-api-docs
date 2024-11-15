---
layout: default
title: ConnectionManager
parent: Sonos Services
---
# ConnectionManager service
{: .no_toc }

Services related to connections and protocols

The ConnectionManager service is available on these models: `Sonos Play:1 (S1) S2` / `Sonos One (S13) S2` / `Sonos Beam (S14) S2` / `Sonos Amp (S16) S2` / `Sonos One (S18) S2` / `SYMFONISK Bookshelf (S21) S2` / `Sonos Roam (S27) S2` / `Sonos Play:3 (S3) S2` / `SYMFONISK Bookshelf (S33) S2` / `Sonos One SL (S38) S2` / `Sonos Era 100 (S39) S2` / `Sonos Play:5 (S6) S2` / `Sonos Playbar (S9) S2` / `Sonos Sub (Sub) S2`.

1. TOC
{:toc}

---

## Service data
{: .no_toc }

| name | value |
|:-----|:------|
| **Control URL** | `http://192.168.x.x:1400/MediaRenderer/ConnectionManager/Control` |
| **Event subscription URL** | `http://192.168.x.x:1400/MediaRenderer/ConnectionManager/Event` |
| **Discovery URL** | `http://192.168.x.x:1400/xml/ConnectionManager1.xml` |
| **Service ID** | `urn:upnp-org:serviceId:ConnectionManager` |
| **Service type** | `urn:schemas-upnp-org:service:ConnectionManager:1` |

### Sample request
{: .no_toc }

```text
POST /MediaRenderer/ConnectionManager/Control
Host: 192.168.x.x:1400
soapaction: "urn:schemas-upnp-org:service:ConnectionManager:1#{ActionName}"
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

## Events

The ConnectionManagerService has variables that might be emitted if you subscribe to events.

### Subscribe to events

```text
SUBSCRIBE /MediaRenderer/ConnectionManager/Event
Host: 192.168.x.x:1400
callback: <http://...>
NT: upnp:event
Timeout: Second-3600
```

### Event variables

| Variable | Sends events* | type | possible values |
|:---------|:-------------|:-----|:----------------|
| CurrentConnectionIDs | ✔ | `string` |  |
| SinkProtocolInfo | ✔ | `string` |  |
| SourceProtocolInfo | ✔ | `string` |  |

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
