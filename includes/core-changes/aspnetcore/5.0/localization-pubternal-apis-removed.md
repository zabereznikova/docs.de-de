---
ms.openlocfilehash: 62a5f56bb7fffc453623a2c3202f288a19110158
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90539476"
---
### <a name="localization-pubternal-apis-removed"></a><span data-ttu-id="1ecdb-101">Lokalisierung: „Pubternal“-APIs entfernt</span><span class="sxs-lookup"><span data-stu-id="1ecdb-101">Localization: "Pubternal" APIs removed</span></span>

<span data-ttu-id="1ecdb-102">Einige :::no-loc text="\"pubternal\"":::-Lokalisierungs-APIs wurden entfernt, um die öffentliche API-Oberfläche von ASP.NET Core besser verwalten zu können.</span><span class="sxs-lookup"><span data-stu-id="1ecdb-102">To better maintain the public API surface of ASP.NET Core, some :::no-loc text="\"pubternal\""::: localization APIs were removed.</span></span> <span data-ttu-id="1ecdb-103">Eine :::no-loc text="\"pubternal\"":::-API verfügt über einen `public`-Zugriffsmodifizierer und wird in einem Namespace definiert, der eine [internal](../../../../docs/csharp/language-reference/keywords/internal.md)-Absicht impliziert.</span><span class="sxs-lookup"><span data-stu-id="1ecdb-103">A :::no-loc text="\"pubternal\""::: API has a `public` access modifier and is defined in a namespace that implies an [internal](../../../../docs/csharp/language-reference/keywords/internal.md) intent.</span></span>

<span data-ttu-id="1ecdb-104">Weitere Informationen finden Sie unter [dotnet/aspnetcore#22291](https://github.com/dotnet/aspnetcore/issues/22291).</span><span class="sxs-lookup"><span data-stu-id="1ecdb-104">For discussion, see [dotnet/aspnetcore#22291](https://github.com/dotnet/aspnetcore/issues/22291).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="1ecdb-105">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="1ecdb-105">Version introduced</span></span>

<span data-ttu-id="1ecdb-106">Version 5.0 Vorschau 6</span><span class="sxs-lookup"><span data-stu-id="1ecdb-106">5.0 Preview 6</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="1ecdb-107">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="1ecdb-107">Old behavior</span></span>

<span data-ttu-id="1ecdb-108">Die folgenden APIs waren `public`:</span><span class="sxs-lookup"><span data-stu-id="1ecdb-108">The following APIs were `public`:</span></span>

- `Microsoft.Extensions.Localization.Internal.AssemblyWrapper`
- `Microsoft.Extensions.Localization.Internal.IResourceStringProvider`
- <span data-ttu-id="1ecdb-109">`Microsoft.Extensions.Localization.ResourceManagerStringLocalizer`-Konstruktorüberladungen, die einen der folgenden Parametertypen akzeptieren:</span><span class="sxs-lookup"><span data-stu-id="1ecdb-109">`Microsoft.Extensions.Localization.ResourceManagerStringLocalizer` constructor overloads accepting either of the following parameter types:</span></span>
  - `AssemblyWrapper`
  - `IResourceStringProvider`

#### <a name="new-behavior"></a><span data-ttu-id="1ecdb-110">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="1ecdb-110">New behavior</span></span>

<span data-ttu-id="1ecdb-111">In der folgenden Liste werden die Änderungen erläutert:</span><span class="sxs-lookup"><span data-stu-id="1ecdb-111">The following list outlines the changes:</span></span>

- <span data-ttu-id="1ecdb-112">`Microsoft.Extensions.Localization.Internal.AssemblyWrapper` wurde `Microsoft.Extensions.Localization.AssemblyWrapper` und ist jetzt `internal`.</span><span class="sxs-lookup"><span data-stu-id="1ecdb-112">`Microsoft.Extensions.Localization.Internal.AssemblyWrapper` became `Microsoft.Extensions.Localization.AssemblyWrapper` and is now `internal`.</span></span>
- <span data-ttu-id="1ecdb-113">`Microsoft.Extensions.Localization.Internal.IResourceStringProvider` wurde `Microsoft.Extensions.Localization.Internal.IResourceStringProvider` und ist jetzt `internal`.</span><span class="sxs-lookup"><span data-stu-id="1ecdb-113">`Microsoft.Extensions.Localization.Internal.IResourceStringProvider` became `Microsoft.Extensions.Localization.Internal.IResourceStringProvider` and is now `internal`.</span></span>
- <span data-ttu-id="1ecdb-114">`Microsoft.Extensions.Localization.ResourceManagerStringLocalizer`-Konstruktorüberladungen, die einen der folgenden Parametertypen akzeptieren, sind jetzt `internal`:</span><span class="sxs-lookup"><span data-stu-id="1ecdb-114">`Microsoft.Extensions.Localization.ResourceManagerStringLocalizer` constructor overloads accepting either of the following parameter types are now `internal`:</span></span>
  - `AssemblyWrapper`
  - `IResourceStringProvider`

#### <a name="reason-for-change"></a><span data-ttu-id="1ecdb-115">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="1ecdb-115">Reason for change</span></span>

<span data-ttu-id="1ecdb-116">Die :::no-loc text="\"pubternal\"":::-Typen wurden aus der `public`-API-Oberfläche entfernt. Ausführlichere Informationen finden Sie unter [aspnet/Announcements#377](https://github.com/aspnet/Announcements/issues/377#issue-473651882).</span><span class="sxs-lookup"><span data-stu-id="1ecdb-116">Explained more thoroughly at [aspnet/Announcements#377](https://github.com/aspnet/Announcements/issues/377#issue-473651882), :::no-loc text="\"pubternal\""::: types were removed from the `public` API surface.</span></span> <span data-ttu-id="1ecdb-117">Mit diesen Änderungen werden mehr Klassen an diese Entwurfsentscheidung angepasst.</span><span class="sxs-lookup"><span data-stu-id="1ecdb-117">These changes adapt more classes to that design decision.</span></span> <span data-ttu-id="1ecdb-118">Die betroffenen Klassen waren als Erweiterungspunkte für die internen Tests des Teams vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="1ecdb-118">The classes in question were intended as extension points for the team's internal testing.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="1ecdb-119">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="1ecdb-119">Recommended action</span></span>

<span data-ttu-id="1ecdb-120">Obwohl es unwahrscheinlich ist, können einige Apps absichtlich oder unabsichtlich von den :::no-loc text="\"pubternal\"":::-Typen abhängen.</span><span class="sxs-lookup"><span data-stu-id="1ecdb-120">Although it's unlikely, some apps may intentionally or accidentally depend upon the :::no-loc text="\"pubternal\""::: types.</span></span> <span data-ttu-id="1ecdb-121">Lesen Sie den Abschnitt [Neues Verhalten](#new-behavior) durch, um sich über die Migration weg von diesen Typen zu informieren.</span><span class="sxs-lookup"><span data-stu-id="1ecdb-121">See the [New behavior](#new-behavior) sections to determine how to migrate away from the types.</span></span>

<span data-ttu-id="1ecdb-122">In einem Szenario, in dem die öffentliche API vor dieser Änderung zulässig war, nun aber nicht mehr ist, melden Sie ein Issue auf [dotnet/aspnetcore](https://github.com/dotnet/aspnetcore/issues).</span><span class="sxs-lookup"><span data-stu-id="1ecdb-122">If you've identified a scenario which the public API allowed before this change but doesn't now, file an issue at [dotnet/aspnetcore](https://github.com/dotnet/aspnetcore/issues).</span></span>

#### <a name="category"></a><span data-ttu-id="1ecdb-123">Kategorie</span><span class="sxs-lookup"><span data-stu-id="1ecdb-123">Category</span></span>

<span data-ttu-id="1ecdb-124">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="1ecdb-124">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="1ecdb-125">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="1ecdb-125">Affected APIs</span></span>

- `Microsoft.Extensions.Localization.Internal.AssemblyWrapper`
- `Microsoft.Extensions.Localization.Internal.IResourceStringProvider`
- <xref:Microsoft.Extensions.Localization.ResourceManagerStringLocalizer.%23ctor%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:Microsoft.Extensions.Localization.Internal.AssemblyWrapper`
- `T:Microsoft.Extensions.Localization.Internal.IResourceStringProvider`
- `Overload:Microsoft.Extensions.Localization.ResourceManagerStringLocalizer.#ctor`

-->
