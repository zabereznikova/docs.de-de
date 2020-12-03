---
title: 'Breaking Change: Autorisierung: Die Ressource im Endpunktrouting ist HttpContext'
description: 'Hier erfahren Sie mehr über den Breaking Change in ASP.NET Core 5.0 mit dem Titel „Autorisierung: Die Ressource im Endpunktrouting ist HttpContext'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: 7c5a77cb8999c60a7780b9b4f7ad2a1c79fd8310
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759544"
---
# <a name="authorization-resource-in-endpoint-routing-is-httpcontext"></a><span data-ttu-id="33777-103">Autorisierung: Die Ressource im Endpunktrouting ist HttpContext</span><span class="sxs-lookup"><span data-stu-id="33777-103">Authorization: Resource in endpoint routing is HttpContext</span></span>

<span data-ttu-id="33777-104">Bei der Verwendung des Endpunktroutings in ASP.NET Core 3.1 ist die für die Autorisierung verwendete Ressource der Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="33777-104">When using endpoint routing in ASP.NET Core 3.1, the resource used for authorization is the endpoint.</span></span> <span data-ttu-id="33777-105">Dieser Ansatz war nicht ausreichend, um Zugriff auf die Routendaten (<xref:Microsoft.AspNetCore.Routing.RouteData>) zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="33777-105">This approach was insufficient for gaining access to the route data (<xref:Microsoft.AspNetCore.Routing.RouteData>).</span></span> <span data-ttu-id="33777-106">Bisher wurde in MVC eine <xref:Microsoft.AspNetCore.Http.HttpContext>-Ressource übergeben, die sowohl den Zugriff auf den Endpunkt (<xref:Microsoft.AspNetCore.Http.Endpoint>) als auch auf die Routendaten ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="33777-106">Previously in MVC, an <xref:Microsoft.AspNetCore.Http.HttpContext> resource was passed in, which allows access to both the endpoint (<xref:Microsoft.AspNetCore.Http.Endpoint>) and the route data.</span></span> <span data-ttu-id="33777-107">Diese Änderung sorgt dafür, dass die für die Autorisierung übergebene Ressource immer `HttpContext` ist.</span><span class="sxs-lookup"><span data-stu-id="33777-107">This change ensures that the resource passed to authorization is always the `HttpContext`.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="33777-108">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="33777-108">Version introduced</span></span>

<span data-ttu-id="33777-109">5.0 Preview 7</span><span class="sxs-lookup"><span data-stu-id="33777-109">5.0 Preview 7</span></span>

## <a name="old-behavior"></a><span data-ttu-id="33777-110">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="33777-110">Old behavior</span></span>

<span data-ttu-id="33777-111">Wenn Endpunktrouting und die Autorisierungsmiddleware (<xref:Microsoft.AspNetCore.Authorization.AuthorizationMiddleware>) oder [[Authorize]](xref:Microsoft.AspNetCore.Authorization.AuthorizeAttribute)-Attribute verwendet werden, ist die für die Autorisierung übergebene Ressource der übereinstimmende Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="33777-111">When using endpoint routing and the authorization middleware (<xref:Microsoft.AspNetCore.Authorization.AuthorizationMiddleware>) or [[Authorize]](xref:Microsoft.AspNetCore.Authorization.AuthorizeAttribute) attributes, the resource passed to authorization is the matching endpoint.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="33777-112">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="33777-112">New behavior</span></span>

<span data-ttu-id="33777-113">Beim Endpunktrouting wird `HttpContext` für die Autorisierung übergeben.</span><span class="sxs-lookup"><span data-stu-id="33777-113">Endpoint routing passes the `HttpContext` to authorization.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="33777-114">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="33777-114">Reason for change</span></span>

<span data-ttu-id="33777-115">Der Endpunkt kann über `HttpContext` erreicht werden.</span><span class="sxs-lookup"><span data-stu-id="33777-115">You can get to the endpoint from the `HttpContext`.</span></span> <span data-ttu-id="33777-116">Es bestand jedoch keine Möglichkeit, vom Endpunkt beispielsweise zu den Routendaten zu gelangen.</span><span class="sxs-lookup"><span data-stu-id="33777-116">However, there was no way to get from the endpoint to things like the route data.</span></span> <span data-ttu-id="33777-117">Beim Nicht-Endpunkt-Routing führte das also zu einer eingeschränkten Funktionalität.</span><span class="sxs-lookup"><span data-stu-id="33777-117">There was a loss in functionality from non-endpoint routing.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="33777-118">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="33777-118">Recommended action</span></span>

<span data-ttu-id="33777-119">Wenn Ihre App die Endpunktressource verwendet, rufen Sie <xref:Microsoft.AspNetCore.Http.EndpointHttpContextExtensions.GetEndpoint%2A> in `HttpContext` auf, um das Zugreifen auf den Endpunkt fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="33777-119">If your app uses the endpoint resource, call <xref:Microsoft.AspNetCore.Http.EndpointHttpContextExtensions.GetEndpoint%2A> on the `HttpContext` to continue accessing the endpoint.</span></span>

<span data-ttu-id="33777-120">In ASP.NET Core 5.0 Preview 8 und höher können Sie das alte Verhalten mit <xref:System.AppContext.SetSwitch%2A> wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="33777-120">In ASP.NET Core 5.0 Preview 8 and later, you can revert to the old behavior with <xref:System.AppContext.SetSwitch%2A>.</span></span> <span data-ttu-id="33777-121">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="33777-121">For example:</span></span>

```csharp
AppContext.SetSwitch(
    "Microsoft.AspNetCore.Authorization.SuppressUseHttpContextAsAuthorizationResource",
    isEnabled: true);
```

## <a name="affected-apis"></a><span data-ttu-id="33777-122">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="33777-122">Affected APIs</span></span>

<span data-ttu-id="33777-123">Keine</span><span class="sxs-lookup"><span data-stu-id="33777-123">None</span></span>

<!--

### Category

ASP.NET Core

### Affected APIs

Not detectable via API analysis

-->
