---
ms.openlocfilehash: 09fd95ba5f3aee59f2abdfbb4e64eb6202e2b873
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2019
ms.locfileid: "72393942"
---
### <a name="mvc-pubternal-types-changed-to-internal"></a><span data-ttu-id="a4bc8-101">MVC: „pubternal“-Typen in „internal“-Typen geändert</span><span class="sxs-lookup"><span data-stu-id="a4bc8-101">MVC: "Pubternal" types changed to internal</span></span>

<span data-ttu-id="a4bc8-102">In ASP.NET Core 3.0 wurden alle „pubternal“-Typen in MVC je nach Anwendungsfall in `public` in einem unterstützten Namespace oder in `internal` geändert.</span><span class="sxs-lookup"><span data-stu-id="a4bc8-102">In ASP.NET Core 3.0, all "pubternal" types in MVC were updated to either be `public` in a supported namespace or `internal` as appropriate.</span></span>

#### <a name="change-description"></a><span data-ttu-id="a4bc8-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="a4bc8-103">Change description</span></span>

<span data-ttu-id="a4bc8-104">In ASP.NET Core werden „pubternal“-Typen als `public` deklariert, befinden sich jedoch in einem Namespace mit dem Suffix `.Internal`.</span><span class="sxs-lookup"><span data-stu-id="a4bc8-104">In ASP.NET Core, "pubternal" types are declared as `public` but reside in a `.Internal`-suffixed namespace.</span></span> <span data-ttu-id="a4bc8-105">Diese Typen sind zwar `public`, sie verfügen jedoch nicht über eine Unterstützungsrichtlinie und können daher Breaking Changes unterliegen.</span><span class="sxs-lookup"><span data-stu-id="a4bc8-105">While these types are `public`, they have no support policy and are subject to breaking changes.</span></span> <span data-ttu-id="a4bc8-106">Da diese Typen leider relativ häufig versehentlich verwendet werden, können an diesen Projekten Breaking Changes auftreten, und die Fähigkeit zum Verwalten des Frameworks kann eingeschränkt werden.</span><span class="sxs-lookup"><span data-stu-id="a4bc8-106">Unfortunately, accidental use of these types has been common, resulting in breaking changes to these projects and limiting the ability to maintain the framework.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="a4bc8-107">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="a4bc8-107">Version introduced</span></span>

<span data-ttu-id="a4bc8-108">3.0</span><span class="sxs-lookup"><span data-stu-id="a4bc8-108">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="a4bc8-109">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="a4bc8-109">Old behavior</span></span>

<span data-ttu-id="a4bc8-110">Einige Typen in MVC waren `public` – aber in einem `.Internal`-Namespace.</span><span class="sxs-lookup"><span data-stu-id="a4bc8-110">Some types in MVC were `public` but in a `.Internal` namespace.</span></span> <span data-ttu-id="a4bc8-111">Diese Typen verfügten nicht über eine Unterstützungsrichtlinie und konnten daher Breaking Changes unterliegen.</span><span class="sxs-lookup"><span data-stu-id="a4bc8-111">These types had no support policy and were subject to breaking changes.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="a4bc8-112">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="a4bc8-112">New behavior</span></span>

<span data-ttu-id="a4bc8-113">Alle diese Typen wurden entweder als `public` in einem unterstützten Namespace oder als `internal` gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="a4bc8-113">All such types are updated either to be `public` in a supported namespace or marked as `internal`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="a4bc8-114">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="a4bc8-114">Reason for change</span></span>

<span data-ttu-id="a4bc8-115">Da die „pubternal“-Typen relativ häufig versehentlich verwendet wurden, konnten an diesen Projekten Breaking Changes auftreten, und die Fähigkeit zum Verwalten des Frameworks konnte eingeschränkt werden.</span><span class="sxs-lookup"><span data-stu-id="a4bc8-115">Accidental use of the "pubternal" types has been common, resulting in breaking changes to these projects and limiting the ability to maintain the framework.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="a4bc8-116">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="a4bc8-116">Recommended action</span></span>

<span data-ttu-id="a4bc8-117">Wenn Sie Typen verwenden, die tatsächlich `public` waren und in einen neuen, unterstützten Namespace verschoben wurden, aktualisieren Sie Ihre Verweise entsprechend den neuen Namespaces.</span><span class="sxs-lookup"><span data-stu-id="a4bc8-117">If you're using types that have become truly `public` and have been moved into a new, supported namespace, update your references to match the new namespaces.</span></span>

<span data-ttu-id="a4bc8-118">Wenn Sie Typen verwenden, die als `internal` gekennzeichnet wurden, müssen Sie eine Alternative suchen.</span><span class="sxs-lookup"><span data-stu-id="a4bc8-118">If you're using types that have become marked as `internal`, you'll need to find an alternative.</span></span> <span data-ttu-id="a4bc8-119">Die zuvor als „pubternal“ deklarierten Typen waren nie für die öffentliche Verwendung vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="a4bc8-119">The previously "pubternal" types were never supported for public use.</span></span> <span data-ttu-id="a4bc8-120">Wenn diese Namespaces bestimmte Typen enthalten, die für Ihre Apps wichtig sind, melden Sie ein Problem bei [aspnet/AspNetCore](https://github.com/aspnet/AspNetCore/issues).</span><span class="sxs-lookup"><span data-stu-id="a4bc8-120">If there are specific types in these namespaces that are critical to your apps, file an issue at [aspnet/AspNetCore](https://github.com/aspnet/AspNetCore/issues).</span></span> <span data-ttu-id="a4bc8-121">Es ist eventuell möglich, die angeforderten Typen `public` zu machen.</span><span class="sxs-lookup"><span data-stu-id="a4bc8-121">Considerations may be made for making the requested types `public`.</span></span>

#### <a name="category"></a><span data-ttu-id="a4bc8-122">Kategorie</span><span class="sxs-lookup"><span data-stu-id="a4bc8-122">Category</span></span>

<span data-ttu-id="a4bc8-123">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="a4bc8-123">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="a4bc8-124">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="a4bc8-124">Affected APIs</span></span>

<span data-ttu-id="a4bc8-125">Diese Änderung umfasst Typen in den folgenden Namespaces:</span><span class="sxs-lookup"><span data-stu-id="a4bc8-125">This change includes types in the following namespaces:</span></span>

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

<!--

#### Affected APIs

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

-->
