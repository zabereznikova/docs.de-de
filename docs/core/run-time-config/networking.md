---
title: Netzwerkkonfigurationseinstellungen
description: Erfahren Sie mehr über Laufzeiteinstellungen, die das Netzwerk für .NET Core-Apps konfigurieren.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 8d02087ad7260cc78c096090bf3b06a716d34678
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2020
ms.locfileid: "80989102"
---
# <a name="run-time-configuration-options-for-networking"></a>Laufzeitkonfigurationsoptionen für Netzwerke

## <a name="http2-protocol"></a>HTTP/2-Protokoll

- Konfiguriert, ob der Support für das HTTP/2-Protokoll aktiviert ist

- Standard: Deaktiviert (`false`)

- Eingeführt in .NET Core 3.0

| | Einstellungsname | Werte |
| - | - | - |
| **runtimeconfig.json** | `System.Net.Http.SocketsHttpHandler.Http2Support` | `false` – deaktiviert<br/>`true` – aktiviert |
| **Umgebungsvariable** | `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2SUPPORT` | `0` – deaktiviert<br/>`1` – aktiviert |

## <a name="usesocketshttphandler"></a>UseSocketsHttpHandler

- Mit dieser Einstellung wird konfiguriert, ob <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> die <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType>-Klasse oder ältere HTTP-Protokollstapel verwendet (<xref:System.Net.Http.WinHttpHandler> unter Windows und `CurlHandler`, eine interne auf Grundlage von [libcurl](https://curl.haxx.se/libcurl/) implementierte Klasse, unter Linux).

  > [!NOTE]
  > Möglicherweise verwenden Sie allgemeine Netzwerk-APIs, anstatt die <xref:System.Net.Http.HttpClientHandler>-Klasse direkt zu instanziieren. Diese Einstellung wirkt sich auch darauf aus, welcher HTTP-Protokollstapel von allgemeinen Netzwerk-APIs verwendet wird, einschließlich <xref:System.Net.Http.HttpClient> und [HttpClientFactory](https://docs.microsoft.com/previous-versions/aspnet/hh995280(v%3dvs.118)).

- Standard: Verwenden von <xref:System.Net.Http.SocketsHttpHandler> (`true`)

- Sie können diese Einstellung programmgesteuert konfigurieren, indem Sie die <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType>-Methode aufrufen.

| | Einstellungsname | Werte |
| - | - | - |
| **runtimeconfig.json** | `System.Net.Http.UseSocketsHttpHandler` | `true` – aktiviert die Verwendung von <xref:System.Net.Http.SocketsHttpHandler><br/>`false`: ermöglicht die Verwendung von <xref:System.Net.Http.WinHttpHandler> unter Windows oder [libcurl](https://curl.haxx.se/libcurl/) unter Linux |
| **Umgebungsvariable** | `DOTNET_SYSTEM_NET_HTTP_USESOCKETSHTTPHANDLER` | `1` – aktiviert die Verwendung von <xref:System.Net.Http.SocketsHttpHandler><br/>`0`: ermöglicht die Verwendung von <xref:System.Net.Http.WinHttpHandler> unter Windows oder [libcurl](https://curl.haxx.se/libcurl/) unter Linux |

> [!NOTE]
> Ab .NET 5 ist die Einstellung `System.Net.Http.UseSocketsHttpHandler` nicht mehr verfügbar.
