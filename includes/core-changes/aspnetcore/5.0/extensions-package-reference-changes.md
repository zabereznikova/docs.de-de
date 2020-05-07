---
ms.openlocfilehash: d7a93cb539baee6a70f75d3afe52fd7546ac2399
ms.sourcegitcommit: 1cb64b53eb1f253e6a3f53ca9510ef0be1fd06fe
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/29/2020
ms.locfileid: "82507081"
---
### <a name="extensions-package-reference-changes-affecting-some-nuget-packages"></a><span data-ttu-id="999e8-101">Erweiterungen: Paketverweisänderungen beeinträchtigen einige NuGet-Pakete</span><span class="sxs-lookup"><span data-stu-id="999e8-101">Extensions: Package reference changes affecting some NuGet packages</span></span>

<span data-ttu-id="999e8-102">Bei der Migration einiger `Microsoft.Extensions.*`-NuGet-Pakete vom Repository [dotnet/extensions](https://github.com/dotnet/extensions) zu [dotnet/runtime](https://github.com/dotnet/runtime) ([aspnet/Announcements#411](https://github.com/aspnet/Announcements/issues/411)) werden Paketänderungen auf einige der migrierten Pakete angewendet.</span><span class="sxs-lookup"><span data-stu-id="999e8-102">With the migration of some `Microsoft.Extensions.*` NuGet packages from the [dotnet/extensions](https://github.com/dotnet/extensions) repository to [dotnet/runtime](https://github.com/dotnet/runtime), as described in [aspnet/Announcements#411](https://github.com/aspnet/Announcements/issues/411), packaging changes are being applied to some of the migrated packages.</span></span> <span data-ttu-id="999e8-103">Dieses Problem wird unter [dotnet/aspnetcore#21033](https://github.com/dotnet/aspnetcore/issues/21033) behandelt.</span><span class="sxs-lookup"><span data-stu-id="999e8-103">For discussion on this issue, see [dotnet/aspnetcore#21033](https://github.com/dotnet/aspnetcore/issues/21033).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="999e8-104">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="999e8-104">Version introduced</span></span>

<span data-ttu-id="999e8-105">5.0 Preview 4</span><span class="sxs-lookup"><span data-stu-id="999e8-105">5.0 Preview 4</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="999e8-106">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="999e8-106">Old behavior</span></span>

<span data-ttu-id="999e8-107">Einige `Microsoft.Extensions.*`-Pakete enthielten Paketverweise für APIs, auf die Ihre App angewiesen war.</span><span class="sxs-lookup"><span data-stu-id="999e8-107">Some `Microsoft.Extensions.*` packages included package references for APIs on which your app relied.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="999e8-108">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="999e8-108">New behavior</span></span>

<span data-ttu-id="999e8-109">Möglicherweise müssen Sie Ihrer App `Microsoft.Extensions.*`-Paketabhängigkeiten hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="999e8-109">Your app may have to add `Microsoft.Extensions.*` package dependencies.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="999e8-110">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="999e8-110">Reason for change</span></span>

<span data-ttu-id="999e8-111">Die Paketrichtlinien wurden besser auf das Repository *dotnet/runtime* abgestimmt.</span><span class="sxs-lookup"><span data-stu-id="999e8-111">Packaging policies were updated to better align with the *dotnet/runtime* repository.</span></span> <span data-ttu-id="999e8-112">Unter der neuen Richtlinie werden nicht verwendete Paketverweise während der Paketerstellung aus *NUPKG*-Dateien entfernt.</span><span class="sxs-lookup"><span data-stu-id="999e8-112">Under the new policy, unused package references are removed from *.nupkg* files during packaging.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="999e8-113">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="999e8-113">Recommended action</span></span>

<span data-ttu-id="999e8-114">Benutzer der betroffenen Pakete sollten eine direkte Abhängigkeit von der entfernten Paketabhängigkeit zu ihrem Projekt hinzufügen, wenn APIs der entfernten Paketabhängigkeit verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="999e8-114">Consumers of the affected packages should add a direct dependency on the removed package dependency in their project if APIs from removed package dependency are used.</span></span> <span data-ttu-id="999e8-115">In der folgenden Tabelle werden die betroffenen Pakete und die zugehörigen Änderungen aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="999e8-115">The following table lists the affected packages and the corresponding changes.</span></span>

|<span data-ttu-id="999e8-116">Paketname</span><span class="sxs-lookup"><span data-stu-id="999e8-116">Package name</span></span>|<span data-ttu-id="999e8-117">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="999e8-117">Change description</span></span>|
|------------|------------------|
|[<span data-ttu-id="999e8-118">Microsoft.Extensions.Configuration.Binder</span><span class="sxs-lookup"><span data-stu-id="999e8-118">Microsoft.Extensions.Configuration.Binder</span></span>](https://nuget.org/packages/Microsoft.Extensions.Configuration.Binder)|<span data-ttu-id="999e8-119">Verweis auf `Microsoft.Extensions.Configuration` entfernt</span><span class="sxs-lookup"><span data-stu-id="999e8-119">Removed reference to `Microsoft.Extensions.Configuration`</span></span>|
|[<span data-ttu-id="999e8-120">Microsoft.Extensions.Configuration.Json</span><span class="sxs-lookup"><span data-stu-id="999e8-120">Microsoft.Extensions.Configuration.Json</span></span>](https://nuget.org/packages/Microsoft.Extensions.Configuration.Json)    |<span data-ttu-id="999e8-121">Verweis auf `System.Threading.Tasks.Extensions` entfernt</span><span class="sxs-lookup"><span data-stu-id="999e8-121">Removed reference to `System.Threading.Tasks.Extensions`</span></span>|
|[<span data-ttu-id="999e8-122">Microsoft.Extensions.Hosting.Abstractions</span><span class="sxs-lookup"><span data-stu-id="999e8-122">Microsoft.Extensions.Hosting.Abstractions</span></span>](https://nuget.org/packages/Microsoft.Extensions.Hosting.Abstractions)|<span data-ttu-id="999e8-123">Verweis auf `Microsoft.Extensions.Logging.Abstractions` entfernt</span><span class="sxs-lookup"><span data-stu-id="999e8-123">Removed reference to `Microsoft.Extensions.Logging.Abstractions`</span></span>|
|[<span data-ttu-id="999e8-124">Microsoft.Extensions.Logging</span><span class="sxs-lookup"><span data-stu-id="999e8-124">Microsoft.Extensions.Logging</span></span>](https://nuget.org/packages/Microsoft.Extensions.Logging)                          |<span data-ttu-id="999e8-125">Verweis auf `Microsoft.Extensions.Configuration.Binder` entfernt</span><span class="sxs-lookup"><span data-stu-id="999e8-125">Removed reference to `Microsoft.Extensions.Configuration.Binder`</span></span>|
|[<span data-ttu-id="999e8-126">Microsoft.Extensions.Logging.Console</span><span class="sxs-lookup"><span data-stu-id="999e8-126">Microsoft.Extensions.Logging.Console</span></span>](https://nuget.org/packages/Microsoft.Extensions.Logging.Console)          |<span data-ttu-id="999e8-127">Verweis auf `Microsoft.Extensions.Configuration.Abstractions` entfernt</span><span class="sxs-lookup"><span data-stu-id="999e8-127">Removed reference to `Microsoft.Extensions.Configuration.Abstractions`</span></span>|
|[<span data-ttu-id="999e8-128">Microsoft.Extensions.Logging.EventLog</span><span class="sxs-lookup"><span data-stu-id="999e8-128">Microsoft.Extensions.Logging.EventLog</span></span>](https://nuget.org/packages/Microsoft.Extensions.Logging.EventLog)        |<span data-ttu-id="999e8-129">Verweis auf `System.Diagnostics.EventLog` für den .NET Framework 4.6.1-Zielframeworkmoniker entfernt</span><span class="sxs-lookup"><span data-stu-id="999e8-129">Removed reference to `System.Diagnostics.EventLog` for the .NET Framework 4.6.1 target framework moniker</span></span>|
|[<span data-ttu-id="999e8-130">Microsoft.Extensions.Logging.EventSource</span><span class="sxs-lookup"><span data-stu-id="999e8-130">Microsoft.Extensions.Logging.EventSource</span></span>](https://nuget.org/packages/Microsoft.Extensions.Logging.EventSource)  |<span data-ttu-id="999e8-131">Verweis auf `System.Threading.Tasks.Extensions` entfernt</span><span class="sxs-lookup"><span data-stu-id="999e8-131">Removed reference to `System.Threading.Tasks.Extensions`</span></span>|
|[<span data-ttu-id="999e8-132">Microsoft.Extensions.Options</span><span class="sxs-lookup"><span data-stu-id="999e8-132">Microsoft.Extensions.Options</span></span>](https://nuget.org/packages/Microsoft.Extensions.Options)                          |<span data-ttu-id="999e8-133">Verweis auf `System.ComponentModel.Annotations` entfernt</span><span class="sxs-lookup"><span data-stu-id="999e8-133">Removed reference to `System.ComponentModel.Annotations`</span></span>|

<span data-ttu-id="999e8-134">Beispielsweise wurde der Paketverweis auf `Microsoft.Extensions.Configuration` aus `Microsoft.Extensions.Configuration.Binder`entfernt.</span><span class="sxs-lookup"><span data-stu-id="999e8-134">For example, the package reference to `Microsoft.Extensions.Configuration` was removed from `Microsoft.Extensions.Configuration.Binder`.</span></span> <span data-ttu-id="999e8-135">Im Paket wurde keine API der Abhängigkeit verwendet.</span><span class="sxs-lookup"><span data-stu-id="999e8-135">No API from the dependency was used in the package.</span></span> <span data-ttu-id="999e8-136">Benutzer von `Microsoft.Extensions.Configuration.Binder`, die von `Microsoft.Extensions.Configuration`-APIs abhängig sind, sollten Ihrem Projekt einen direkten Verweis auf diese hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="999e8-136">Users of `Microsoft.Extensions.Configuration.Binder` who depend on APIs from `Microsoft.Extensions.Configuration` should add a direct reference to it in their project.</span></span>

#### <a name="category"></a><span data-ttu-id="999e8-137">Kategorie</span><span class="sxs-lookup"><span data-stu-id="999e8-137">Category</span></span>

<span data-ttu-id="999e8-138">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="999e8-138">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="999e8-139">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="999e8-139">Affected APIs</span></span>

<span data-ttu-id="999e8-140">Keine</span><span class="sxs-lookup"><span data-stu-id="999e8-140">None</span></span>

<!--

#### Affected APIs

Not detectable via API analysis

-->
