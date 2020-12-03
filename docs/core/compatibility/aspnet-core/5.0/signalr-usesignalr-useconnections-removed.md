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
# <a name="signalr-usesignalr-and-useconnections-methods-removed"></a><span data-ttu-id="ea128-103">SignalR: UseSignalR- und UseConnections-Methoden entfernt</span><span class="sxs-lookup"><span data-stu-id="ea128-103">SignalR: UseSignalR and UseConnections methods removed</span></span>

<span data-ttu-id="ea128-104">In ASP.NET Core 3.0 wurde für SignalR das Endpunktrouting eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ea128-104">In ASP.NET Core 3.0, SignalR adopted endpoint routing.</span></span> <span data-ttu-id="ea128-105">Im Rahmen dieser Änderung wurde die Methoden <xref:Microsoft.AspNetCore.Builder.SignalRAppBuilderExtensions.UseSignalR%2A> und <xref:Microsoft.AspNetCore.Builder.ConnectionsAppBuilderExtensions.UseConnections%2A> sowie einige verwandte Methoden als veraltet gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="ea128-105">As part of that change, the <xref:Microsoft.AspNetCore.Builder.SignalRAppBuilderExtensions.UseSignalR%2A>, <xref:Microsoft.AspNetCore.Builder.ConnectionsAppBuilderExtensions.UseConnections%2A>, and some related methods were marked as obsolete.</span></span> <span data-ttu-id="ea128-106">In ASP.NET Core 5.0 wurden diese veralteten Methoden entfernt.</span><span class="sxs-lookup"><span data-stu-id="ea128-106">In ASP.NET Core 5.0, those obsolete methods were removed.</span></span> <span data-ttu-id="ea128-107">Eine vollständige Liste der Methoden finden Sie unter [Betroffene APIs](#affected-apis).</span><span class="sxs-lookup"><span data-stu-id="ea128-107">For the full list of methods, see [Affected APIs](#affected-apis).</span></span>

<span data-ttu-id="ea128-108">Dieses Problem wird unter [dotnet/aspnetcore#20082](https://github.com/dotnet/aspnetcore/issues/20082) behandelt.</span><span class="sxs-lookup"><span data-stu-id="ea128-108">For discussion on this issue, see [dotnet/aspnetcore#20082](https://github.com/dotnet/aspnetcore/issues/20082).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="ea128-109">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="ea128-109">Version introduced</span></span>

<span data-ttu-id="ea128-110">5.0 Preview 3</span><span class="sxs-lookup"><span data-stu-id="ea128-110">5.0 Preview 3</span></span>

## <a name="old-behavior"></a><span data-ttu-id="ea128-111">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="ea128-111">Old behavior</span></span>

<span data-ttu-id="ea128-112">SignalR-Hubs und Verbindungshandler konnten in der Middlewarepipeline über die Methoden `UseSignalR` oder `UseConnections` registriert werden.</span><span class="sxs-lookup"><span data-stu-id="ea128-112">SignalR hubs and connection handlers could be registered in the middleware pipeline using the `UseSignalR` or `UseConnections` methods.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="ea128-113">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="ea128-113">New behavior</span></span>

<span data-ttu-id="ea128-114">SignalR-Hubs und Verbindungsmethoden müssen innerhalb von <xref:Microsoft.AspNetCore.Builder.EndpointRoutingApplicationBuilderExtensions.UseEndpoints%2A> mithilfe der Erweiterungsmethoden <xref:Microsoft.AspNetCore.SignalR.HubRouteBuilder.MapHub%2A> und <xref:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnectionHandler%2A> in <xref:Microsoft.AspNetCore.Routing.IEndpointRouteBuilder> registriert werden.</span><span class="sxs-lookup"><span data-stu-id="ea128-114">SignalR hubs and connection handlers should be registered within <xref:Microsoft.AspNetCore.Builder.EndpointRoutingApplicationBuilderExtensions.UseEndpoints%2A> using the <xref:Microsoft.AspNetCore.SignalR.HubRouteBuilder.MapHub%2A> and <xref:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnectionHandler%2A> extension methods on <xref:Microsoft.AspNetCore.Routing.IEndpointRouteBuilder>.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="ea128-115">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="ea128-115">Reason for change</span></span>

<span data-ttu-id="ea128-116">Die alten Methoden umfassten eine benutzerdefinierte Routinglogik, die keine Interaktion mit anderen Routingkomponenten in ASP.NET Core ermöglichte.</span><span class="sxs-lookup"><span data-stu-id="ea128-116">The old methods had custom routing logic that didn't interact with other routing components in ASP.NET Core.</span></span> <span data-ttu-id="ea128-117">In ASP.NET Core 3.0 wurde ein neues, universelles Routingsystem eingeführt, das sogenannte Endpunktrouting.</span><span class="sxs-lookup"><span data-stu-id="ea128-117">In ASP.NET Core 3.0, a new general-purpose routing system, called endpoint routing, was introduced.</span></span> <span data-ttu-id="ea128-118">Das Endpunktrouting ermöglichte SignalR eine Interaktion mit anderen Routingkomponenten.</span><span class="sxs-lookup"><span data-stu-id="ea128-118">Endpoint routing enabled SignalR to interact with other routing components.</span></span> <span data-ttu-id="ea128-119">Durch den Wechsel auf dieses Modell können Benutzer alle Vorteile des Endpunktroutings nutzen.</span><span class="sxs-lookup"><span data-stu-id="ea128-119">Switching to this model allows users to realize the full benefits of endpoint routing.</span></span> <span data-ttu-id="ea128-120">Folglich wurden die alten Methoden entfernt.</span><span class="sxs-lookup"><span data-stu-id="ea128-120">Consequently, the old methods have been removed.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="ea128-121">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="ea128-121">Recommended action</span></span>

<span data-ttu-id="ea128-122">Entfernen Sie Code, der `UseSignalR` oder `UseConnections` aus der `Startup.Configure`-Methode Ihres Projekts aufruft.</span><span class="sxs-lookup"><span data-stu-id="ea128-122">Remove code that calls `UseSignalR` or `UseConnections` from your project's `Startup.Configure` method.</span></span> <span data-ttu-id="ea128-123">Verwenden Sie stattdessen Aufrufe von `MapHub` bzw. `MapConnectionHandler` im Text eines `UseEndpoints`-Aufrufs.</span><span class="sxs-lookup"><span data-stu-id="ea128-123">Replace it with calls to `MapHub` or `MapConnectionHandler`, respectively, within the body of a call to `UseEndpoints`.</span></span> <span data-ttu-id="ea128-124">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ea128-124">For example:</span></span>

<span data-ttu-id="ea128-125">**Alter Code:**</span><span class="sxs-lookup"><span data-stu-id="ea128-125">**Old code:**</span></span>

```csharp
app.UseSignalR(routes =>
{
    routes.MapHub<SomeHub>("/path");
});
```

<span data-ttu-id="ea128-126">**Neuer Code:**</span><span class="sxs-lookup"><span data-stu-id="ea128-126">**New code:**</span></span>

```csharp
app.UseEndpoints(endpoints =>
{
    endpoints.MapHub<SomeHub>("/path");
});
```

<span data-ttu-id="ea128-127">Im Allgemeinen können die vorherigen `MapHub`- und `MapConnectionHandler`-Aufrufe mit minimalen oder ganz ohne Änderungen direkt vom Text von `UseSignalR` und `UseConnections` nach `UseEndpoints` übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="ea128-127">In general, your previous `MapHub` and `MapConnectionHandler` calls can be transferred directly from the body of `UseSignalR` and `UseConnections` to `UseEndpoints` with little-to-no change needed.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="ea128-128">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="ea128-128">Affected APIs</span></span>

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
