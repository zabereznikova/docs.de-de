---
ms.openlocfilehash: 224cd3c7897c64ef05baba7d3d31dbe5ac0dd610
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606757"
---
### <a name="pubternal-apis-removed"></a><span data-ttu-id="0d051-101">„Pubternal“-APIs entfernt</span><span class="sxs-lookup"><span data-stu-id="0d051-101">"Pubternal" APIs removed</span></span>

<span data-ttu-id="0d051-102">Um die öffentliche API-Oberfläche von ASP.NET Core besser zu verwalten, sind die meisten Typen in `*.Internal`-Namespaces (als :::no-loc text="\"pubternal\"":::-APIs bezeichnet) wirklich intern geworden.</span><span class="sxs-lookup"><span data-stu-id="0d051-102">To better maintain the public API surface of ASP.NET Core, most of the types in `*.Internal` namespaces (referred to as :::no-loc text="\"pubternal\""::: APIs) have become truly internal.</span></span> <span data-ttu-id="0d051-103">Member in diesen Namespaces sollten nie als öffentlich ausgerichtete APIs unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="0d051-103">Members in these namespaces were never meant to be supported as public-facing APIs.</span></span> <span data-ttu-id="0d051-104">Bei den APIs konnten in Nebenversionen Fehler auftreten, was auch häufig der Fall war.</span><span class="sxs-lookup"><span data-stu-id="0d051-104">The APIs could break in minor releases and often did.</span></span> <span data-ttu-id="0d051-105">Bei Code, der von diesen APIs abhängig ist, treten beim Aktualisieren auf ASP.Net Core 3.0 Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="0d051-105">Code that depends on these APIs breaks when updating to ASP.NET Core 3.0.</span></span>

<span data-ttu-id="0d051-106">Weitere Informationen finden Sie unter [dotnet/aspnetcore#4932](https://github.com/dotnet/aspnetcore/issues/4932) und [dotnet/aspnetcore#11312](https://github.com/dotnet/aspnetcore/issues/11312).</span><span class="sxs-lookup"><span data-stu-id="0d051-106">For more information, see [dotnet/aspnetcore#4932](https://github.com/dotnet/aspnetcore/issues/4932) and [dotnet/aspnetcore#11312](https://github.com/dotnet/aspnetcore/issues/11312).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="0d051-107">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="0d051-107">Version introduced</span></span>

<span data-ttu-id="0d051-108">3.0</span><span class="sxs-lookup"><span data-stu-id="0d051-108">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="0d051-109">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="0d051-109">Old behavior</span></span>

<span data-ttu-id="0d051-110">Die betroffenen APIs werden mit dem `public`-Zugriffsmodifizierer gekennzeichnet und sind in `*.Internal`-Namespaces vorhanden.</span><span class="sxs-lookup"><span data-stu-id="0d051-110">The affected APIs are marked with the `public` access modifier and exist in `*.Internal` namespaces.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="0d051-111">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="0d051-111">New behavior</span></span>

<span data-ttu-id="0d051-112">Die betroffenen APIs sind mit dem [internal](../../../../docs/csharp/language-reference/keywords/internal.md)-Zugriffsmodifizierer gekennzeichnet und können nicht mehr von Code außerhalb dieser Assembly verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0d051-112">The affected APIs are marked with the [internal](../../../../docs/csharp/language-reference/keywords/internal.md) access modifier and can no longer be used by code outside that assembly.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="0d051-113">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="0d051-113">Reason for change</span></span>

<span data-ttu-id="0d051-114">Die Richtlinie für diese :::no-loc text="\"pubternal\"":::-APIs war:</span><span class="sxs-lookup"><span data-stu-id="0d051-114">The guidance for these :::no-loc text="\"pubternal\""::: APIs was that they:</span></span>

* <span data-ttu-id="0d051-115">Sie konnten ohne vorherige Ankündigung geändert werden.</span><span class="sxs-lookup"><span data-stu-id="0d051-115">Could change without notice.</span></span>
* <span data-ttu-id="0d051-116">Sie unterlagen nicht den .NET-Richtlinien zum Verhindern von Breaking Changes.</span><span class="sxs-lookup"><span data-stu-id="0d051-116">Weren't subject to .NET policies to prevent breaking changes.</span></span>

<span data-ttu-id="0d051-117">Die APIs `public` zu lassen (selbst in den `*.Internal`-Namespaces), war für Kunden verwirrend.</span><span class="sxs-lookup"><span data-stu-id="0d051-117">Leaving the APIs `public` (even in the `*.Internal` namespaces) was confusing to customers.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="0d051-118">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="0d051-118">Recommended action</span></span>

<span data-ttu-id="0d051-119">Verwenden Sie diese :::no-loc text="\"pubternal\"":::-APIs nicht mehr.</span><span class="sxs-lookup"><span data-stu-id="0d051-119">Stop using these :::no-loc text="\"pubternal\""::: APIs.</span></span> <span data-ttu-id="0d051-120">Wenn Sie Fragen zu alternativen APIs haben, öffnen Sie ein Issue im [dotnet/aspnetcore](https://github.com/dotnet/aspnetcore/issues)-Repository.</span><span class="sxs-lookup"><span data-stu-id="0d051-120">If you have questions about alternate APIs, open an issue in the [dotnet/aspnetcore](https://github.com/dotnet/aspnetcore/issues) repository.</span></span>

<span data-ttu-id="0d051-121">Sehen Sie sich beispielsweise den folgenden HTTP-Anforderungspuffercode in einem ASP.NET Core 2.2-Projekt an.</span><span class="sxs-lookup"><span data-stu-id="0d051-121">For example, consider the following HTTP request buffering code in an ASP.NET Core 2.2 project.</span></span> <span data-ttu-id="0d051-122">Die `EnableRewind`-Erweiterungsmethode ist im `Microsoft.AspNetCore.Http.Internal`-Namespace vorhanden.</span><span class="sxs-lookup"><span data-stu-id="0d051-122">The `EnableRewind` extension method exists in the `Microsoft.AspNetCore.Http.Internal` namespace.</span></span>

```csharp
HttpContext.Request.EnableRewind();
```

<span data-ttu-id="0d051-123">Ersetzen Sie den `EnableRewind`-Aufruf in einem ASP.NET Core 3.0-Projekt durch einen Aufruf der `EnableBuffering`-Erweiterungsmethode.</span><span class="sxs-lookup"><span data-stu-id="0d051-123">In an ASP.NET Core 3.0 project, replace the `EnableRewind` call with a call to the `EnableBuffering` extension method.</span></span> <span data-ttu-id="0d051-124">Das Feature für die Anforderungspufferung funktioniert wie bisher.</span><span class="sxs-lookup"><span data-stu-id="0d051-124">The request buffering feature works as it did in the past.</span></span> <span data-ttu-id="0d051-125">`EnableBuffering` ruft die jetzige `internal`-API auf.</span><span class="sxs-lookup"><span data-stu-id="0d051-125">`EnableBuffering` calls the now `internal` API.</span></span>

```csharp
HttpContext.Request.EnableBuffering();
```

#### <a name="category"></a><span data-ttu-id="0d051-126">Kategorie</span><span class="sxs-lookup"><span data-stu-id="0d051-126">Category</span></span>

<span data-ttu-id="0d051-127">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="0d051-127">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="0d051-128">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="0d051-128">Affected APIs</span></span>

<span data-ttu-id="0d051-129">Alle APIs in den `Microsoft.AspNetCore.*`-und `Microsoft.Extensions.*`-Namespaces mit einem `Internal`-Segment im Namespacenamen.</span><span class="sxs-lookup"><span data-stu-id="0d051-129">All APIs in the `Microsoft.AspNetCore.*` and `Microsoft.Extensions.*` namespaces that have an `Internal` segment in the namespace name.</span></span> <span data-ttu-id="0d051-130">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="0d051-130">For example:</span></span>

- `Microsoft.AspNetCore.Authentication.Internal`
- `Microsoft.AspNetCore.Builder.Internal`
- `Microsoft.AspNetCore.DataProtection.Cng.Internal`
- `Microsoft.AspNetCore.DataProtection.Internal`
- `Microsoft.AspNetCore.Hosting.Internal`
- `Microsoft.AspNetCore.Http.Internal`
- `Microsoft.AspNetCore.Mvc.Core.Infrastructure`
- `Microsoft.AspNetCore.Mvc.Core.Internal`
- `Microsoft.AspNetCore.Mvc.Cors.Internal`
- `Microsoft.AspNetCore.Mvc.DataAnnotations.Internal`
- `Microsoft.AspNetCore.Mvc.Formatters.Internal`
- `Microsoft.AspNetCore.Mvc.Formatters.Json.Internal`
- `Microsoft.AspNetCore.Mvc.Formatters.Xml.Internal`
- `Microsoft.AspNetCore.Mvc.Internal`
- `Microsoft.AspNetCore.Mvc.ModelBinding.Internal`
- `Microsoft.AspNetCore.Mvc.Razor.Internal`
- `Microsoft.AspNetCore.Mvc.RazorPages.Internal`
- `Microsoft.AspNetCore.Mvc.TagHelpers.Internal`
- `Microsoft.AspNetCore.Mvc.ViewFeatures.Internal`
- `Microsoft.AspNetCore.Rewrite.Internal`
- `Microsoft.AspNetCore.Routing.Internal`
- `Microsoft.AspNetCore.Server.Kestrel.Core.Adapter.Internal`
- `Microsoft.AspNetCore.Server.Kestrel.Core.Internal.Http`
- `Microsoft.AspNetCore.Server.Kestrel.Core.Internal.Infrastructure`
- `Microsoft.AspNetCore.Server.Kestrel.Https.Internal`

<!--

#### Affected APIs

- `N:Microsoft.AspNetCore.Authentication.Internal`
- `N:Microsoft.AspNetCore.Builder.Internal`
- `N:Microsoft.AspNetCore.DataProtection.Cng.Internal`
- `N:Microsoft.AspNetCore.DataProtection.Internal`
- `N:Microsoft.AspNetCore.Hosting.Internal`
- `N:Microsoft.AspNetCore.Http.Internal`
- `N:Microsoft.AspNetCore.Mvc.Core.Infrastructure`
- `N:Microsoft.AspNetCore.Mvc.Core.Internal`
- `N:Microsoft.AspNetCore.Mvc.Cors.Internal`
- `N:Microsoft.AspNetCore.Mvc.DataAnnotations.Internal`
- `N:Microsoft.AspNetCore.Mvc.Formatters.Internal`
- `N:Microsoft.AspNetCore.Mvc.Formatters.Json.Internal`
- `N:Microsoft.AspNetCore.Mvc.Formatters.Xml.Internal`
- `N:Microsoft.AspNetCore.Mvc.Internal`
- `N:Microsoft.AspNetCore.Mvc.ModelBinding.Internal`
- `N:Microsoft.AspNetCore.Mvc.Razor.Internal`
- `N:Microsoft.AspNetCore.Mvc.RazorPages.Internal`
- `N:Microsoft.AspNetCore.Mvc.TagHelpers.Internal`
- `N:Microsoft.AspNetCore.Mvc.ViewFeatures.Internal`
- `N:Microsoft.AspNetCore.Rewrite.Internal`
- `N:Microsoft.AspNetCore.Routing.Internal`
- `N:Microsoft.AspNetCore.Server.Kestrel.Core.Adapter.Internal`
- `N:Microsoft.AspNetCore.Server.Kestrel.Core.Internal.Http`
- `N:Microsoft.AspNetCore.Server.Kestrel.Core.Internal.Infrastructure`
- `N:Microsoft.AspNetCore.Server.Kestrel.Https.Internal`

-->
