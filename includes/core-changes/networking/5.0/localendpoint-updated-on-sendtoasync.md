---
ms.openlocfilehash: 8de70b0c445aa48fc4c3249ccfc8c095890fb14c
ms.sourcegitcommit: 39b1d5f2978be15409c189a66ab30781d9082cd8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/14/2020
ms.locfileid: "92050518"
---
### <a name="socketlocalendpoint-is-updated-after-calling-sendtoasync"></a>Socket.LocalEndPoint wird nach dem Aufruf von SendToAsync aktualisiert

<xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=nameWithType> aktualisiert jetzt den Wert der <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType>-Eigenschaft auf die lokale Adresse des Sockets.

#### <a name="version-introduced"></a>Eingeführt in Version

5.0 RC1

#### <a name="change-description"></a>Änderungsbeschreibung

In früheren .NET-Versionen wird der Wert der <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType>-Eigenschaft der Socketinstanz nicht durch <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=nameWithType> geändert. Ab .NET 5.0 ist der Wert von <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)> die lokale Adresse des implizit gebundenen Sockets, wenn <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> erfolgreich abgeschlossen wurde. Dieses neue Verhalten ist mit dem von <xref:System.Net.Sockets.Socket.SendTo(System.Byte[],System.Net.EndPoint)> und <xref:System.Net.Sockets.Socket.BeginSendTo(System.Byte[],System.Int32,System.Int32,System.Net.Sockets.SocketFlags,System.Net.EndPoint,System.AsyncCallback,System.Object)>/<xref:System.Net.Sockets.Socket.EndSendTo(System.IAsyncResult)> konsistent.

#### <a name="reason-for-change"></a>Grund für die Änderung

Diese Änderung [korrigiert einen Fehler](https://github.com/dotnet/runtime/issues/915) und bewirkt, dass das Verhalten von `SendTo`-Varianten konsistent ist.

#### <a name="recommended-action"></a>Empfohlene Maßnahme

Ändern Sie jeglichen Code, der annimmt, dass <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)> den Wert von <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> nicht ändert.

#### <a name="category"></a>Kategorie

Netzwerk

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)`

-->
