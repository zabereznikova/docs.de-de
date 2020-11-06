---
title: Netzwerkkonfigurationseinstellungen
description: Erfahren Sie mehr über Laufzeiteinstellungen, die das Netzwerk für .NET Core-Apps konfigurieren.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: bda608e83bb1b093d7d9b860de9607f6734720aa
ms.sourcegitcommit: 7588b1f16b7608bc6833c05f91ae670c22ef56f8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2020
ms.locfileid: "93188301"
---
# <a name="run-time-configuration-options-for-networking"></a>Laufzeitkonfigurationsoptionen für Netzwerke

## <a name="http2-protocol"></a>HTTP/2-Protokoll

- Konfiguriert, ob der Support für das HTTP/2-Protokoll aktiviert ist

- Eingeführt in .NET Core 3.0

- Nur .NET Core 3.0: Wenn Sie diese Einstellung weglassen, ist die Unterstützung für das HTTP/2-Protokoll deaktiviert. Dies entspricht der Einstellung des Werts auf `false`.

- .NET Core 3.1 und .NET 5 und höher: Wenn Sie diese Einstellung weglassen, ist die Unterstützung für das HTTP/2-Protokoll aktiviert. Dies entspricht der Einstellung des Werts auf `true`.

| | Einstellungsname | Werte |
| - | - | - |
| **runtimeconfig.json** | `System.Net.Http.SocketsHttpHandler.Http2Support` | `false` – deaktiviert<br/>`true` – aktiviert |
| **Umgebungsvariable** | `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2SUPPORT` | `0` – deaktiviert<br/>`1` – aktiviert |

## <a name="usesocketshttphandler"></a>UseSocketsHttpHandler

- Mit dieser Einstellung wird konfiguriert, ob <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> die <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType>-Klasse oder ältere HTTP-Protokollstapel verwendet (<xref:System.Net.Http.WinHttpHandler> unter Windows und `CurlHandler`, eine interne auf Grundlage von [libcurl](https://curl.haxx.se/libcurl/) implementierte Klasse, unter Linux).

  > [!NOTE]
  > Möglicherweise verwenden Sie allgemeine Netzwerk-APIs, anstatt die <xref:System.Net.Http.HttpClientHandler>-Klasse direkt zu instanziieren. Diese Einstellung wirkt sich auch darauf aus, welcher HTTP-Protokollstapel von allgemeinen Netzwerk-APIs verwendet wird, einschließlich <xref:System.Net.Http.HttpClient> und [HttpClientFactory](/previous-versions/aspnet/hh995280(v=vs.118)).

- Wenn Sie diese Einstellung weglassen, verwendet <xref:System.Net.Http.HttpClientHandler> <xref:System.Net.Http.SocketsHttpHandler>. Dies entspricht der Einstellung des Werts auf `true`.

- Sie können diese Einstellung programmgesteuert konfigurieren, indem Sie die <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType>-Methode aufrufen.

| | Einstellungsname | Werte |
| - | - | - |
| **runtimeconfig.json** | `System.Net.Http.UseSocketsHttpHandler` | `true` – aktiviert die Verwendung von <xref:System.Net.Http.SocketsHttpHandler><br/>`false`: ermöglicht die Verwendung von <xref:System.Net.Http.WinHttpHandler> unter Windows oder [libcurl](https://curl.haxx.se/libcurl/) unter Linux |
| **Umgebungsvariable** | `DOTNET_SYSTEM_NET_HTTP_USESOCKETSHTTPHANDLER` | `1` – aktiviert die Verwendung von <xref:System.Net.Http.SocketsHttpHandler><br/>`0`: ermöglicht die Verwendung von <xref:System.Net.Http.WinHttpHandler> unter Windows oder [libcurl](https://curl.haxx.se/libcurl/) unter Linux |

> [!NOTE]
> Ab .NET 5 ist die Einstellung `System.Net.Http.UseSocketsHttpHandler` nicht mehr verfügbar.

## <a name="latin1-headers-net-core-31-only"></a>Latin1-Header (nur .NET Core 3.1)

- Durch diese Umstellung kann die Überprüfung des HTTP-Headers gelockert werden, wodurch <xref:System.Net.Http.SocketsHttpHandler> ISO-8859-1-codierte (Latin-1-codierte) Zeichen in Headern senden kann.

- Wenn Sie diese Einstellung weglassen, wird beim Versuch, ein Nicht-ASCII-Zeichen zu senden, <xref:System.Net.Http.HttpRequestException> zurückgegeben. Dies entspricht der Einstellung des Werts auf `false`.

| | Einstellungsname | Werte |
| - | - | - |
| **runtimeconfig.json** | `System.Net.Http.SocketsHttpHandler.AllowLatin1Headers` | `false` – deaktiviert<br/>`true` – aktiviert |
| **Umgebungsvariable** | `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_ALLOWLATIN1HEADERS` | `0` – deaktiviert<br/>`1` – aktiviert |

> [!NOTE]
> Diese Option ist nur in .NET Core 3.1 ab Version 3.1.9 und nicht in früheren oder neueren Versionen verfügbar. Bei .NET 5 empfiehlt sich die Verwendung von <xref:System.Net.Http.SocketsHttpHandler.RequestHeaderEncodingSelector>.
