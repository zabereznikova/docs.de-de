---
ms.openlocfilehash: 0c88d40e34d2d6458bb463a09d716dea42b711fe
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901850"
---
### <a name="authorization-iallowanonymous-removed-from-authorizationfiltercontextfilters"></a><span data-ttu-id="d8881-101">Autorisierung: IAllowAnonymous aus AuthorizationFilterContext.Filters entfernt</span><span class="sxs-lookup"><span data-stu-id="d8881-101">Authorization: IAllowAnonymous removed from AuthorizationFilterContext.Filters</span></span>

<span data-ttu-id="d8881-102">Ab ASP.NET Core 3.0 fügt MVC keine [AllowAnonymousFilters](xref:Microsoft.AspNetCore.Mvc.Authorization.AllowAnonymousFilter) für [[AllowAnonymous]](xref:Microsoft.AspNetCore.Authorization.AllowAnonymousAttribute)-Attribute hinzu, die für Controller und Aktionsmethoden ermittelt wurden.</span><span class="sxs-lookup"><span data-stu-id="d8881-102">As of ASP.NET Core 3.0, MVC doesn't add [AllowAnonymousFilters](xref:Microsoft.AspNetCore.Mvc.Authorization.AllowAnonymousFilter) for [[AllowAnonymous]](xref:Microsoft.AspNetCore.Authorization.AllowAnonymousAttribute) attributes that were discovered on controllers and action methods.</span></span> <span data-ttu-id="d8881-103">Diese Änderung wird lokal für Ableitungen von <xref:Microsoft.AspNetCore.Authorization.AuthorizeAttribute>behandelt, ist aber ein Breaking Change für <xref:Microsoft.AspNetCore.Mvc.Filters.IAsyncAuthorizationFilter>- und <xref:Microsoft.AspNetCore.Mvc.Filters.IAuthorizationFilter>-Implementierungen.</span><span class="sxs-lookup"><span data-stu-id="d8881-103">This change is addressed locally for derivatives of <xref:Microsoft.AspNetCore.Authorization.AuthorizeAttribute>, but it's a breaking change for <xref:Microsoft.AspNetCore.Mvc.Filters.IAsyncAuthorizationFilter> and <xref:Microsoft.AspNetCore.Mvc.Filters.IAuthorizationFilter> implementations.</span></span> <span data-ttu-id="d8881-104">Solche Implementierungen, die ein [[TypeFilter]](xref:Microsoft.AspNetCore.Mvc.TypeFilterAttribute)-Attribut als Wrapper verwenden, sind eine [gängige](https://stackoverflow.com/a/41348219/608220) und unterstützte Möglichkeit, um eine stark typisierte, attributbasierte Autorisierung zu erreichen, wenn sowohl Konfiguration als auch Abhängigkeitsinjektion (Dependency Injection, DI) erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="d8881-104">Such implementations wrapped in a [[TypeFilter]](xref:Microsoft.AspNetCore.Mvc.TypeFilterAttribute) attribute are a [popular](https://stackoverflow.com/a/41348219/608220) and supported way to achieve strongly-typed, attribute-based authorization when both configuration and dependency injection are required.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="d8881-105">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="d8881-105">Version introduced</span></span>

<span data-ttu-id="d8881-106">3.0</span><span class="sxs-lookup"><span data-stu-id="d8881-106">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="d8881-107">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="d8881-107">Old behavior</span></span>

<span data-ttu-id="d8881-108"><xref:Microsoft.AspNetCore.Authorization.IAllowAnonymous> war in der [AuthorizationFilterContext.Filters](xref:Microsoft.AspNetCore.Mvc.Filters.FilterContext.Filters%2A)-Sammlung enthalten.</span><span class="sxs-lookup"><span data-stu-id="d8881-108"><xref:Microsoft.AspNetCore.Authorization.IAllowAnonymous> appeared in the [AuthorizationFilterContext.Filters](xref:Microsoft.AspNetCore.Mvc.Filters.FilterContext.Filters%2A) collection.</span></span> <span data-ttu-id="d8881-109">Das Testen auf das Vorhandensein der Schnittstelle war ein gültiger Ansatz, um den Filter für einzelne Controllermethoden zu überschreiben oder zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="d8881-109">Testing for the interface's presence was a valid approach to override or disable the filter on individual controller methods.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="d8881-110">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="d8881-110">New behavior</span></span>

<span data-ttu-id="d8881-111">`IAllowAnonymous` ist nicht mehr in der `AuthorizationFilterContext.Filters`-Sammlung enthalten.</span><span class="sxs-lookup"><span data-stu-id="d8881-111">`IAllowAnonymous` no longer appears in the `AuthorizationFilterContext.Filters` collection.</span></span> <span data-ttu-id="d8881-112">`IAsyncAuthorizationFilter`-Implementierungen, die vom alten Verhalten abhängig sind, verursachen in der Regel vorübergehende HTTP 401- (Nicht autorisiert) oder HTTP 403-Antworten (Unzulässig).</span><span class="sxs-lookup"><span data-stu-id="d8881-112">`IAsyncAuthorizationFilter` implementations that are dependent on the old behavior typically cause intermittent HTTP 401 Unauthorized or HTTP 403 Forbidden responses.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="d8881-113">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="d8881-113">Reason for change</span></span>

<span data-ttu-id="d8881-114">In ASP.NET Core 3.0 wurde eine neue Endpunktroutingstrategie eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d8881-114">A new endpoint routing strategy was introduced in ASP.NET Core 3.0.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="d8881-115">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="d8881-115">Recommended action</span></span>

<span data-ttu-id="d8881-116">Suchen Sie nach den Endpunktmetadaten für `IAllowAnonymous`.</span><span class="sxs-lookup"><span data-stu-id="d8881-116">Search the endpoint metadata for `IAllowAnonymous`.</span></span> <span data-ttu-id="d8881-117">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d8881-117">For example:</span></span>

```csharp
var endpoint = context.HttpContext.GetEndpoint();
if (endpoint?.Metadata?.GetMetadata<IAllowAnonymous>() != null)
{
}
```

<span data-ttu-id="d8881-118">Ein Beispiel für diese Technik finden Sie in [dieser HasAllowAnonymous-Methode](https://github.com/dotnet/aspnetcore/blob/bd65275148abc9b07a3b59797a88d485341152bf/src/Mvc/Mvc.Core/src/Authorization/AuthorizeFilter.cs#L236).</span><span class="sxs-lookup"><span data-stu-id="d8881-118">An example of this technique is seen in [this HasAllowAnonymous method](https://github.com/dotnet/aspnetcore/blob/bd65275148abc9b07a3b59797a88d485341152bf/src/Mvc/Mvc.Core/src/Authorization/AuthorizeFilter.cs#L236).</span></span>

#### <a name="category"></a><span data-ttu-id="d8881-119">Kategorie</span><span class="sxs-lookup"><span data-stu-id="d8881-119">Category</span></span>

<span data-ttu-id="d8881-120">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="d8881-120">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="d8881-121">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="d8881-121">Affected APIs</span></span>

<span data-ttu-id="d8881-122">Keine</span><span class="sxs-lookup"><span data-stu-id="d8881-122">None</span></span>

<!--

#### Affected APIs

Not detectable via API analysis

-->
