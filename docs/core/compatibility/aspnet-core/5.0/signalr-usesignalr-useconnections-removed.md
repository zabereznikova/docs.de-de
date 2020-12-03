---
title: 'Breaking Change: SignalR: UseSignalR- und UseConnections-Methoden entfernt'
description: 'Hier erfahren Sie mehr über den Breaking Change in ASP.NET Core 5.0 mit dem Titel „SignalR: UseSignalR- und UseConnections-Methoden entfernt'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: 1b1fce04518e69927cdc1650cc1e19107cc81e3b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759230"
---
# <a name="signalr-usesignalr-and-useconnections-methods-removed"></a>SignalR: UseSignalR- und UseConnections-Methoden entfernt

In ASP.NET Core 3.0 wurde für SignalR das Endpunktrouting eingeführt. Im Rahmen dieser Änderung wurde die Methoden <xref:Microsoft.AspNetCore.Builder.SignalRAppBuilderExtensions.UseSignalR%2A> und <xref:Microsoft.AspNetCore.Builder.ConnectionsAppBuilderExtensions.UseConnections%2A> sowie einige verwandte Methoden als veraltet gekennzeichnet. In ASP.NET Core 5.0 wurden diese veralteten Methoden entfernt. Eine vollständige Liste der Methoden finden Sie unter [Betroffene APIs](#affected-apis).

Dieses Problem wird unter [dotnet/aspnetcore#20082](https://github.com/dotnet/aspnetcore/issues/20082) behandelt.

## <a name="version-introduced"></a>Eingeführt in Version

5.0 Preview 3

## <a name="old-behavior"></a>Altes Verhalten

SignalR-Hubs und Verbindungshandler konnten in der Middlewarepipeline über die Methoden `UseSignalR` oder `UseConnections` registriert werden.

## <a name="new-behavior"></a>Neues Verhalten

SignalR-Hubs und Verbindungsmethoden müssen innerhalb von <xref:Microsoft.AspNetCore.Builder.EndpointRoutingApplicationBuilderExtensions.UseEndpoints%2A> mithilfe der Erweiterungsmethoden <xref:Microsoft.AspNetCore.SignalR.HubRouteBuilder.MapHub%2A> und <xref:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnectionHandler%2A> in <xref:Microsoft.AspNetCore.Routing.IEndpointRouteBuilder> registriert werden.

## <a name="reason-for-change"></a>Grund für die Änderung

Die alten Methoden umfassten eine benutzerdefinierte Routinglogik, die keine Interaktion mit anderen Routingkomponenten in ASP.NET Core ermöglichte. In ASP.NET Core 3.0 wurde ein neues, universelles Routingsystem eingeführt, das sogenannte Endpunktrouting. Das Endpunktrouting ermöglichte SignalR eine Interaktion mit anderen Routingkomponenten. Durch den Wechsel auf dieses Modell können Benutzer alle Vorteile des Endpunktroutings nutzen. Folglich wurden die alten Methoden entfernt.

## <a name="recommended-action"></a>Empfohlene Aktion

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

## <a name="affected-apis"></a>Betroffene APIs

- <xref:Microsoft.AspNetCore.Builder.ConnectionsAppBuilderExtensions.UseConnections%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Builder.SignalRAppBuilderExtensions.UseSignalR%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnections%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnectionHandler%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SignalR.HubRouteBuilder.MapHub%2A?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

- `Overload:Microsoft.AspNetCore.Builder.ConnectionsAppBuilderExtensions.UseConnections`
- `Overload:Microsoft.AspNetCore.Builder.SignalRAppBuilderExtensions.UseSignalR`
- `Overload:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnections`
- `Overload:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnectionHandler`
- `Overload:Microsoft.AspNetCore.SignalR.HubRouteBuilder.MapHub`

-->
