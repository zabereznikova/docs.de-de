---
ms.openlocfilehash: de06825f1031d05bc83183a83bae165e2f9512ff
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75901806"
---
### <a name="signalr-hubconnection-resetsendping-and-resettimeout-methods-removed"></a>SignalR: Methoden ResetSendPing und ResetTimeout wurden aus HubConnection entfernt.

Die Methoden `ResetSendPing` und `ResetTimeout` wurden aus der SignalR-API `HubConnection` entfernt. Diese Methoden waren ursprünglich nur für die interne Verwendung vorgesehen, wurden aber in ASP.NET Core 2.2 öffentlich („public“) gemacht. Diese Methoden sind ab dem Release ASP.NET Core 3.0 Preview 4 nicht mehr verfügbar. Weitere Informationen finden Sie unter [dotnet/aspnetcore#8543](https://github.com/dotnet/aspnetcore/issues/8543).

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="old-behavior"></a>Altes Verhalten

Die APIs waren verfügbar.

#### <a name="new-behavior"></a>Neues Verhalten

Die APIs wurden entfernt.

#### <a name="reason-for-change"></a>Grund für die Änderung

Diese Methoden waren ursprünglich nur für die interne Verwendung vorgesehen, wurden aber in ASP.NET Core 2.2 öffentlich („public“) gemacht.

#### <a name="recommended-action"></a>Empfohlene Aktion

Verwenden Sie diese Methoden nicht mehr.

#### <a name="category"></a>Kategorie

ASP.NET Core

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:Microsoft.AspNetCore.SignalR.Client.HubConnection.ResetSendPing?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SignalR.Client.HubConnection.ResetTimeout?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:Microsoft.AspNetCore.SignalR.Client.HubConnection.ResetSendPing`
- `M:Microsoft.AspNetCore.SignalR.Client.HubConnection.ResetTimeout`

-->
