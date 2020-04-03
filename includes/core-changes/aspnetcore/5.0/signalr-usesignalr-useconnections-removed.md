---
ms.openlocfilehash: 329ef39c7626ecd743577f336a4c8cd4a38fb082
ms.sourcegitcommit: e48a54ebe62e874500a7043f6ee0b77a744d55b4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/26/2020
ms.locfileid: "80291644"
---
### <a name="signalr-usesignalr-and-useconnections-methods-removed"></a>SignalR: UseSignalR- und UseConnections-Methoden entfernt

In ASP.NET Core 3.0 wurde für SignalR das Endpunktrouting eingeführt. Im Rahmen dieser Änderung wurde die Methoden <xref:Microsoft.AspNetCore.Builder.SignalRAppBuilderExtensions.UseSignalR%2A> und <xref:Microsoft.AspNetCore.Builder.ConnectionsAppBuilderExtensions.UseConnections%2A> sowie einige verwandte Methoden als veraltet gekennzeichnet. In ASP.NET Core 5.0 wurden diese veralteten Methoden entfernt. Eine vollständige Liste der Methoden finden Sie unter [Betroffene APIs](#affected-apis).

Dieses Problem wird unter [dotnet/aspnetcore#20082](https://github.com/dotnet/aspnetcore/issues/20082) behandelt.

#### <a name="version-introduced"></a>Eingeführt in Version

5.0 Preview 3

#### <a name="old-behavior"></a>Altes Verhalten

SignalR-Hubs und Verbindungshandler konnten in der Middlewarepipeline über die Methoden `UseSignalR` oder `UseConnections` registriert werden.

#### <a name="new-behavior"></a>Neues Verhalten

SignalR-Hubs und Verbindungsmethoden müssen innerhalb von <xref:Microsoft.AspNetCore.Builder.EndpointRoutingApplicationBuilderExtensions.UseEndpoints%2A> mithilfe der Erweiterungsmethoden <xref:Microsoft.AspNetCore.SignalR.HubRouteBuilder.MapHub%2A> und <xref:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnectionHandler%2A> in <xref:Microsoft.AspNetCore.Routing.IEndpointRouteBuilder> registriert werden.

#### <a name="reason-for-change"></a>Grund für die Änderung

Die alten Methoden umfassten eine benutzerdefinierte Routinglogik, die keine Interaktion mit anderen Routingkomponenten in ASP.NET Core ermöglichte. In ASP.NET Core 3.0 wurde ein neues, universelles Routingsystem eingeführt, das sogenannte Endpunktrouting. Das Endpunktrouting ermöglichte SignalR eine Interaktion mit anderen Routingkomponenten. Durch den Wechsel auf dieses Modell können Benutzer alle Vorteile des Endpunktroutings nutzen. Folglich wurden die alten Methoden entfernt.

#### <a name="recommended-action"></a>Empfohlene Aktion

Entfernen Sie Code, der `UseSignalR` oder `UseConnections` aus der `Startup.Configure`-Methode Ihres Projekts aufruft. Verwenden Sie stattdessen Aufrufe von `MapHub` bzw. `MapConnectionHandler` im Text eines `UseEndpoints`-Aufrufs. Zum Beispiel:

**Alter Code:**

```csharp
app.UseSignalR(routes =>
{
    routes.MapHub<SomeHub>("/path");
});
```

**Neuer Code:**

```csharp
app.UseEndpoints(endpoints =>
{
    endpoints.MapHub<SomeHub>("/path");
});
```

Im Allgemeinen können die vorherigen `MapHub`- und `MapConnectionHandler`-Aufrufe mit minimalen oder ganz ohne Änderungen direkt vom Text von `UseSignalR` und `UseConnections` nach `UseEndpoints` übertragen werden.

#### <a name="category"></a>Kategorie

ASP.NET Core

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:Microsoft.AspNetCore.Builder.ConnectionsAppBuilderExtensions.UseConnections%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Builder.SignalRAppBuilderExtensions.UseSignalR%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnections%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnectionHandler%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SignalR.HubRouteBuilder.MapHub%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:Microsoft.AspNetCore.Builder.ConnectionsAppBuilderExtensions.UseConnections`
- `Overload:Microsoft.AspNetCore.Builder.SignalRAppBuilderExtensions.UseSignalR`
- `Overload:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnections`
- `Overload:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnectionHandler`
- `Overload:Microsoft.AspNetCore.SignalR.HubRouteBuilder.MapHub`

-->
