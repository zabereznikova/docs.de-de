---
ms.openlocfilehash: 2094da7ec94028c112d6683620ac1146a1544dab
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2020
ms.locfileid: "84446970"
---
### <a name="localization-pubternal-apis-removed"></a><span data-ttu-id="00d9b-101">Lokalisierung: „Pubternal“-APIs entfernt</span><span class="sxs-lookup"><span data-stu-id="00d9b-101">Localization: "Pubternal" APIs removed</span></span>

<span data-ttu-id="00d9b-102">Einige :::no-loc text="\"pubternal\"":::-Lokalisierungs-APIs wurden entfernt, um die öffentliche API-Oberfläche von ASP.NET Core besser verwalten zu können.</span><span class="sxs-lookup"><span data-stu-id="00d9b-102">To better maintain the public API surface of ASP.NET Core, some :::no-loc text="\"pubternal\""::: localization APIs were removed.</span></span> <span data-ttu-id="00d9b-103">Eine :::no-loc text="\"pubternal\"":::-API verfügt über einen `public`-Zugriffsmodifizierer und wird in einem Namespace definiert, der eine [internal](/dotnet/csharp/language-reference/keywords/internal)-Absicht impliziert.</span><span class="sxs-lookup"><span data-stu-id="00d9b-103">A :::no-loc text="\"pubternal\""::: API has a `public` access modifier and is defined in a namespace that implies an [internal](/dotnet/csharp/language-reference/keywords/internal) intent.</span></span>

<span data-ttu-id="00d9b-104">Weitere Informationen finden Sie unter [dotnet/aspnetcore#22291](https://github.com/dotnet/aspnetcore/issues/22291).</span><span class="sxs-lookup"><span data-stu-id="00d9b-104">For discussion, see [dotnet/aspnetcore#22291](https://github.com/dotnet/aspnetcore/issues/22291).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="00d9b-105">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="00d9b-105">Version introduced</span></span>

<span data-ttu-id="00d9b-106">Version 5.0 Vorschau 6</span><span class="sxs-lookup"><span data-stu-id="00d9b-106">5.0 Preview 6</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="00d9b-107">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="00d9b-107">Old behavior</span></span>

<span data-ttu-id="00d9b-108">Die folgenden APIs waren `public`:</span><span class="sxs-lookup"><span data-stu-id="00d9b-108">The following APIs were `public`:</span></span>

- `Microsoft.Extensions.Localization.Internal.AssemblyWrapper`
- `Microsoft.Extensions.Localization.Internal.IResourceStringProvider`
- <span data-ttu-id="00d9b-109">`Microsoft.Extensions.Localization.ResourceManagerStringLocalizer`-Konstruktorüberladungen, die einen der folgenden Parametertypen akzeptieren:</span><span class="sxs-lookup"><span data-stu-id="00d9b-109">`Microsoft.Extensions.Localization.ResourceManagerStringLocalizer` constructor overloads accepting either of the following parameter types:</span></span>
  - `AssemblyWrapper`
  - `IResourceStringProvider`

#### <a name="new-behavior"></a><span data-ttu-id="00d9b-110">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="00d9b-110">New behavior</span></span>

<span data-ttu-id="00d9b-111">In der folgenden Liste werden die Änderungen erläutert:</span><span class="sxs-lookup"><span data-stu-id="00d9b-111">The following list outlines the changes:</span></span>

- <span data-ttu-id="00d9b-112">`Microsoft.Extensions.Localization.Internal.AssemblyWrapper` wurde `Microsoft.Extensions.Localization.AssemblyWrapper` und ist jetzt `internal`.</span><span class="sxs-lookup"><span data-stu-id="00d9b-112">`Microsoft.Extensions.Localization.Internal.AssemblyWrapper` became `Microsoft.Extensions.Localization.AssemblyWrapper` and is now `internal`.</span></span>
- <span data-ttu-id="00d9b-113">`Microsoft.Extensions.Localization.Internal.IResourceStringProvider` wurde `Microsoft.Extensions.Localization.Internal.IResourceStringProvider` und ist jetzt `internal`.</span><span class="sxs-lookup"><span data-stu-id="00d9b-113">`Microsoft.Extensions.Localization.Internal.IResourceStringProvider` became `Microsoft.Extensions.Localization.Internal.IResourceStringProvider` and is now `internal`.</span></span>
- <span data-ttu-id="00d9b-114">`Microsoft.Extensions.Localization.ResourceManagerStringLocalizer`-Konstruktorüberladungen, die einen der folgenden Parametertypen akzeptieren, sind jetzt `internal`:</span><span class="sxs-lookup"><span data-stu-id="00d9b-114">`Microsoft.Extensions.Localization.ResourceManagerStringLocalizer` constructor overloads accepting either of the following parameter types are now `internal`:</span></span>
  - `AssemblyWrapper`
  - `IResourceStringProvider`

#### <a name="reason-for-change"></a><span data-ttu-id="00d9b-115">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="00d9b-115">Reason for change</span></span>

<span data-ttu-id="00d9b-116">Die :::no-loc text="\"pubternal\"":::-Typen wurden aus der `public`-API-Oberfläche entfernt. Ausführlichere Informationen finden Sie unter [aspnet/Announcements#377](https://github.com/aspnet/Announcements/issues/377#issue-473651882).</span><span class="sxs-lookup"><span data-stu-id="00d9b-116">Explained more thoroughly at [aspnet/Announcements#377](https://github.com/aspnet/Announcements/issues/377#issue-473651882), :::no-loc text="\"pubternal\""::: types were removed from the `public` API surface.</span></span> <span data-ttu-id="00d9b-117">Mit diesen Änderungen werden mehr Klassen an diese Entwurfsentscheidung angepasst.</span><span class="sxs-lookup"><span data-stu-id="00d9b-117">These changes adapt more classes to that design decision.</span></span> <span data-ttu-id="00d9b-118">Die betroffenen Klassen waren als Erweiterungspunkte für die internen Tests des Teams vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="00d9b-118">The classes in question were intended as extension points for the team's internal testing.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="00d9b-119">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="00d9b-119">Recommended action</span></span>

<span data-ttu-id="00d9b-120">Obwohl es unwahrscheinlich ist, können einige Apps absichtlich oder unabsichtlich von den :::no-loc text="\"pubternal\"":::-Typen abhängen.</span><span class="sxs-lookup"><span data-stu-id="00d9b-120">Although it's unlikely, some apps may intentionally or accidentally depend upon the :::no-loc text="\"pubternal\""::: types.</span></span> <span data-ttu-id="00d9b-121">Lesen Sie den Abschnitt [Neues Verhalten](#new-behavior) durch, um sich über die Migration weg von diesen Typen zu informieren.</span><span class="sxs-lookup"><span data-stu-id="00d9b-121">See the [New behavior](#new-behavior) sections to determine how to migrate away from the types.</span></span>

<span data-ttu-id="00d9b-122">In einem Szenario, in dem die öffentliche API vor dieser Änderung zulässig war, nun aber nicht mehr ist, melden Sie ein Issue auf [dotnet/aspnetcore](https://github.com/dotnet/aspnetcore/issues).</span><span class="sxs-lookup"><span data-stu-id="00d9b-122">If you've identified a scenario which the public API allowed before this change but doesn't now, file an issue at [dotnet/aspnetcore](https://github.com/dotnet/aspnetcore/issues).</span></span>

#### <a name="category"></a><span data-ttu-id="00d9b-123">Kategorie</span><span class="sxs-lookup"><span data-stu-id="00d9b-123">Category</span></span>

<span data-ttu-id="00d9b-124">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="00d9b-124">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="00d9b-125">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="00d9b-125">Affected APIs</span></span>

- `Microsoft.Extensions.Localization.Internal.AssemblyWrapper`
- `Microsoft.Extensions.Localization.Internal.IResourceStringProvider`
- <xref:Microsoft.Extensions.Localization.ResourceManagerStringLocalizer.%23ctor%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:Microsoft.Extensions.Localization.Internal.AssemblyWrapper`
- `T:Microsoft.Extensions.Localization.Internal.IResourceStringProvider`
- `Overload:Microsoft.Extensions.Localization.ResourceManagerStringLocalizer.#ctor`

-->
