---
title: 'Breaking Change: Socket.LocalEndPoint wird nach dem Aufruf von SendToAsync aktualisiert'
description: Hier erfahren Sie mehr über den Breaking Change in .NET 5.0, durch den SendToAsync jetzt den Wert der lokalen Endpunkteigenschaft auf die lokale Adresse des Sockets aktualisiert.
ms.date: 10/18/2020
ms.openlocfilehash: 53d7da350eac6e65832012331044427fd90fe796
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759390"
---
# <a name="socketlocalendpoint-is-updated-after-calling-sendtoasync"></a>Socket.LocalEndPoint wird nach dem Aufruf von SendToAsync aktualisiert

<xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=nameWithType> aktualisiert jetzt den Wert der <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType>-Eigenschaft auf die lokale Adresse des Sockets.

## <a name="version-introduced"></a>Eingeführt in Version

5.0

## <a name="change-description"></a>Änderungsbeschreibung

In früheren .NET-Versionen wird der Wert der <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType>-Eigenschaft der Socketinstanz nicht durch <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=nameWithType> geändert. Ab .NET 5.0 ist der Wert von <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)> die lokale Adresse des implizit gebundenen Sockets, wenn <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> erfolgreich abgeschlossen wurde. Dieses neue Verhalten ist mit dem von <xref:System.Net.Sockets.Socket.SendTo(System.Byte[],System.Net.EndPoint)> und <xref:System.Net.Sockets.Socket.BeginSendTo(System.Byte[],System.Int32,System.Int32,System.Net.Sockets.SocketFlags,System.Net.EndPoint,System.AsyncCallback,System.Object)>/<xref:System.Net.Sockets.Socket.EndSendTo(System.IAsyncResult)> konsistent.

## <a name="reason-for-change"></a>Grund für die Änderung

Diese Änderung [korrigiert einen Fehler](https://github.com/dotnet/runtime/issues/915) und bewirkt, dass das Verhalten von `SendTo`-Varianten konsistent ist.

## <a name="recommended-action"></a>Empfohlene Maßnahme

Ändern Sie jeglichen Code, der annimmt, dass <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)> den Wert von <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> nicht ändert.

## <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=fullName>

<!--

### Affected APIs

- `M:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)`

### Category

Networking

-->
