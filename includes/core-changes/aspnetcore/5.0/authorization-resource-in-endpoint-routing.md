---
ms.openlocfilehash: 2b88ab7cfdd7a0a0a770b305ecd0200afd9a9b4b
ms.sourcegitcommit: 2543a78be6e246aa010a01decf58889de53d1636
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/17/2020
ms.locfileid: "86441548"
---
### <a name="authorization-resource-in-endpoint-routing-is-httpcontext"></a><span data-ttu-id="0d947-101">Autorisierung: Die Ressource im Endpunktrouting ist HttpContext</span><span class="sxs-lookup"><span data-stu-id="0d947-101">Authorization: Resource in endpoint routing is HttpContext</span></span>

<span data-ttu-id="0d947-102">Bei der Verwendung des Endpunktroutings in ASP.NET Core 3.1 ist die für die Autorisierung verwendete Ressource der Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="0d947-102">When using endpoint routing in ASP.NET Core 3.1, the resource used for authorization is the endpoint.</span></span> <span data-ttu-id="0d947-103">Dieser Ansatz war nicht ausreichend, um Zugriff auf die Routendaten (<xref:Microsoft.AspNetCore.Routing.RouteData>) zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="0d947-103">This approach was insufficient for gaining access to the route data (<xref:Microsoft.AspNetCore.Routing.RouteData>).</span></span> <span data-ttu-id="0d947-104">Bisher wurde in MVC eine <xref:Microsoft.AspNetCore.Http.HttpContext>-Ressource übergeben, die sowohl den Zugriff auf den Endpunkt (<xref:Microsoft.AspNetCore.Http.Endpoint>) als auch auf die Routendaten ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="0d947-104">Previously in MVC, an <xref:Microsoft.AspNetCore.Http.HttpContext> resource was passed in, which allows access to both the endpoint (<xref:Microsoft.AspNetCore.Http.Endpoint>) and the route data.</span></span> <span data-ttu-id="0d947-105">Diese Änderung sorgt dafür, dass die für die Autorisierung übergebene Ressource immer `HttpContext` ist.</span><span class="sxs-lookup"><span data-stu-id="0d947-105">This change ensures that the resource passed to authorization is always the `HttpContext`.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="0d947-106">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="0d947-106">Version introduced</span></span>

<span data-ttu-id="0d947-107">5.0 Preview 7</span><span class="sxs-lookup"><span data-stu-id="0d947-107">5.0 Preview 7</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="0d947-108">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="0d947-108">Old behavior</span></span>

<span data-ttu-id="0d947-109">Wenn Endpunktrouting und die Autorisierungsmiddleware (<xref:Microsoft.AspNetCore.Authorization.AuthorizationMiddleware>) oder [[Authorize]](xref:Microsoft.AspNetCore.Authorization.AuthorizeAttribute)-Attribute verwendet werden, ist die für die Autorisierung übergebene Ressource der übereinstimmende Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="0d947-109">When using endpoint routing and the authorization middleware (<xref:Microsoft.AspNetCore.Authorization.AuthorizationMiddleware>) or [[Authorize]](xref:Microsoft.AspNetCore.Authorization.AuthorizeAttribute) attributes, the resource passed to authorization is the matching endpoint.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="0d947-110">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="0d947-110">New behavior</span></span>

<span data-ttu-id="0d947-111">Beim Endpunktrouting wird `HttpContext` für die Autorisierung übergeben.</span><span class="sxs-lookup"><span data-stu-id="0d947-111">Endpoint routing passes the `HttpContext` to authorization.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="0d947-112">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="0d947-112">Reason for change</span></span>

<span data-ttu-id="0d947-113">Der Endpunkt kann über `HttpContext` erreicht werden.</span><span class="sxs-lookup"><span data-stu-id="0d947-113">You can get to the endpoint from the `HttpContext`.</span></span> <span data-ttu-id="0d947-114">Es bestand jedoch keine Möglichkeit, vom Endpunkt beispielsweise zu den Routendaten zu gelangen.</span><span class="sxs-lookup"><span data-stu-id="0d947-114">However, there was no way to get from the endpoint to things like the route data.</span></span> <span data-ttu-id="0d947-115">Beim Nicht-Endpunkt-Routing führte das also zu einer eingeschränkten Funktionalität.</span><span class="sxs-lookup"><span data-stu-id="0d947-115">There was a loss in functionality from non-endpoint routing.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="0d947-116">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="0d947-116">Recommended action</span></span>

<span data-ttu-id="0d947-117">Wenn Ihre App die Endpunktressource verwendet, rufen Sie <xref:Microsoft.AspNetCore.Http.EndpointHttpContextExtensions.GetEndpoint%2A> in `HttpContext` auf, um das Zugreifen auf den Endpunkt fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="0d947-117">If your app uses the endpoint resource, call <xref:Microsoft.AspNetCore.Http.EndpointHttpContextExtensions.GetEndpoint%2A> on the `HttpContext` to continue accessing the endpoint.</span></span>

<span data-ttu-id="0d947-118">In ASP.NET Core 5.0 Preview 8 und höher können Sie das alte Verhalten mit <xref:System.AppContext.SetSwitch%2A> wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="0d947-118">In ASP.NET Core 5.0 Preview 8 and later, you can revert to the old behavior with <xref:System.AppContext.SetSwitch%2A>.</span></span> <span data-ttu-id="0d947-119">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="0d947-119">For example:</span></span>

```csharp
AppContext.SetSwitch(
    "Microsoft.AspNetCore.Authorization.SuppressUseHttpContextAsAuthorizationResource",
    isEnabled: true);
```

#### <a name="category"></a><span data-ttu-id="0d947-120">Kategorie</span><span class="sxs-lookup"><span data-stu-id="0d947-120">Category</span></span>

<span data-ttu-id="0d947-121">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="0d947-121">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="0d947-122">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="0d947-122">Affected APIs</span></span>

<span data-ttu-id="0d947-123">Keine</span><span class="sxs-lookup"><span data-stu-id="0d947-123">None</span></span>

<!--

#### Affected APIs

Not detectable via API analysis

-->
