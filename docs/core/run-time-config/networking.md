---
title: Netzwerkkonfigurationseinstellungen
description: Erfahren Sie mehr über Laufzeiteinstellungen, die das Netzwerk für .NET Core-Apps konfigurieren.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 622c4afbd36d3d9004edbd9219145fa9e5d326ae
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/04/2019
ms.locfileid: "74998834"
---
# <a name="run-time-configuration-options-for-networking"></a>Laufzeitkonfigurationsoptionen für Netzwerke

## <a name="http2-protocol"></a>HTTP/2-Protokoll

- Konfiguriert, ob der Support für das HTTP/2-Protokoll aktiviert ist
- Standard: Deaktiviert (`false`)
- Eingeführt in .NET Core 3.0

| | Einstellungsname | Werte |
| - | - |
| **runtimeconfig.json** | `System.Net.Http.SocketsHttpHandler.Http2Support` | `false` – deaktiviert<br/>`true` – aktiviert |
| **Umgebungsvariable** | `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2SUPPORT` | `0` – deaktiviert<br/>`1` – aktiviert |

## <a name="sockets-http-handler"></a>Socket-HTTP-Handler

- Konfiguriert, ob allgemeine Netzwerk-APIs, wie z. B. <xref:System.Net.Http.HttpClient>, <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> oder die Implementierung von <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> verwenden, die auf [libcurl](https://curl.haxx.se/libcurl/) basiert
- Standard: Verwenden von <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> (`true`)
- Sie können diese Einstellung programmgesteuert konfigurieren, indem Sie die <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType>-Methode aufrufen.

| | Einstellungsname | Werte |
| - | - | - |
| **runtimeconfig.json** | `System.Net.Http.UseSocketsHttpHandler` | `true` – aktiviert die Verwendung von <xref:System.Net.Http.SocketsHttpHandler><br/>`false` – aktiviert die Verwendung von <xref:System.Net.Http.HttpClientHandler> |
| **Umgebungsvariable** | `DOTNET_SYSTEM_NET_HTTP_USESOCKETSHTTPHANDLER` | `1` – aktiviert die Verwendung von <xref:System.Net.Http.SocketsHttpHandler><br/>`0` – aktiviert die Verwendung von <xref:System.Net.Http.HttpClientHandler> |
