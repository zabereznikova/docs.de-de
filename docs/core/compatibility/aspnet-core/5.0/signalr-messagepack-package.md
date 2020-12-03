---
title: 'Breaking Change: SignalR: MessagePack-Hubprotokoll in MessagePack 2.x-Paket verschoben'
description: 'Hier erfahren Sie mehr über den Breaking Change in ASP.NET Core 5.0 mit dem Titel „SignalR: MessagePack-Hubprotokoll in MessagePack 2.x-Paket verschoben'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: 1e666c40d7046233c9fb06af819b901fd1251b06
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759549"
---
# <a name="signalr-messagepack-hub-protocol-moved-to-messagepack-2x-package"></a>SignalR: MessagePack-Hubprotokoll in MessagePack 2.x-Paket verschoben

Das [MessagePack-Hubprotokoll](/aspnet/core/signalr/messagepackhubprotocol) von ASP.NET Core SignalR verwendet das [NuGet-Paket „MessagePack“](https://www.nuget.org/packages/MessagePack) für die MessagePack-Serialisierung. In ASP.NET Core 5.0 wird das Paket von Version 1.x auf die neueste Paketversion 2.x aktualisiert.

Dieses Problem wird unter [dotnet/aspnetcore#18692](https://github.com/dotnet/aspnetcore/issues/18692) behandelt.

## <a name="version-introduced"></a>Eingeführt in Version

5.0 Preview 1

## <a name="old-behavior"></a>Altes Verhalten

ASP.NET Core SignalR verwendete das MessagePack 1.x-Paket zum Serialisieren und Deserialisieren von MessagePack-Nachrichten.

## <a name="new-behavior"></a>Neues Verhalten

ASP.NET Core SignalR verwendete das MessagePack 2.x-Paket zum Serialisieren und Deserialisieren von MessagePack-Nachrichten.

## <a name="reason-for-change"></a>Grund für die Änderung

Mit den neuesten Verbesserungen im MessagePack 2.x-Paket wird nützliche Funktionalität hinzugefügt.

## <a name="recommended-action"></a>Empfohlene Aktion

Dieser Breaking Change gilt in folgenden Fällen:

* Sie konfigurieren oder legen Werte für <xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions> fest.
* Direkte Verwendung der MessagePack-APIs und Verwendung des MessagePack-Hubprotokolls von ASP.NET Core SignalR im selben Projekt. Anstelle der vorherigen Version wird die neuere Version geladen.

Hinweise der Paketautoren zur Migration finden Sie unter [Migrieren von MessagePack v1.x zu MessagePack v2.x](https://github.com/neuecc/MessagePack-CSharp/blob/master/doc/migration.md). Die Änderung wirkt sich auf einige Aspekte der Nachrichtenserialisierung und -deserialisierung aus. Insbesondere kommt es [Verhaltensänderungen in Bezug auf die Serialisierung von DateTime-Werten](https://github.com/neuecc/MessagePack-CSharp/blob/master/doc/migration.md#behavioral-changes).

## <a name="affected-apis"></a>Betroffene APIs

<xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

`T:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions`

-->
