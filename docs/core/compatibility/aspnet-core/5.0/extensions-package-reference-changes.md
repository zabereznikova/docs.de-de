---
title: 'Breaking Change: Erweiterungen: Paketverweisänderungen beeinträchtigen einige NuGet-Pakete'
description: 'Hier erfahren Sie mehr über den Breaking Change in ASP.NET Core 5.0 mit dem Titel „Erweiterungen: Paketverweisänderungen beeinträchtigen einige NuGet-Pakete'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: 4a525d9f7aad4409fd507fcf80c00968ff4b63d4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759422"
---
# <a name="extensions-package-reference-changes-affecting-some-nuget-packages"></a><span data-ttu-id="5dff3-103">Erweiterungen: Paketverweisänderungen beeinträchtigen einige NuGet-Pakete</span><span class="sxs-lookup"><span data-stu-id="5dff3-103">Extensions: Package reference changes affecting some NuGet packages</span></span>

<span data-ttu-id="5dff3-104">Bei der Migration einiger `Microsoft.Extensions.*`-NuGet-Pakete vom Repository [dotnet/extensions](https://github.com/dotnet/extensions) zu [dotnet/runtime](https://github.com/dotnet/runtime) ([aspnet/Announcements#411](https://github.com/aspnet/Announcements/issues/411)) werden Paketänderungen auf einige der migrierten Pakete angewendet.</span><span class="sxs-lookup"><span data-stu-id="5dff3-104">With the migration of some `Microsoft.Extensions.*` NuGet packages from the [dotnet/extensions](https://github.com/dotnet/extensions) repository to [dotnet/runtime](https://github.com/dotnet/runtime), as described in [aspnet/Announcements#411](https://github.com/aspnet/Announcements/issues/411), packaging changes are being applied to some of the migrated packages.</span></span> <span data-ttu-id="5dff3-105">Dieses Problem wird unter [dotnet/aspnetcore#21033](https://github.com/dotnet/aspnetcore/issues/21033) behandelt.</span><span class="sxs-lookup"><span data-stu-id="5dff3-105">For discussion on this issue, see [dotnet/aspnetcore#21033](https://github.com/dotnet/aspnetcore/issues/21033).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="5dff3-106">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="5dff3-106">Version introduced</span></span>

<span data-ttu-id="5dff3-107">5.0 Preview 4</span><span class="sxs-lookup"><span data-stu-id="5dff3-107">5.0 Preview 4</span></span>

## <a name="old-behavior"></a><span data-ttu-id="5dff3-108">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="5dff3-108">Old behavior</span></span>

<span data-ttu-id="5dff3-109">Einige `Microsoft.Extensions.*`-Pakete enthielten Paketverweise für APIs, auf die Ihre App angewiesen war.</span><span class="sxs-lookup"><span data-stu-id="5dff3-109">Some `Microsoft.Extensions.*` packages included package references for APIs on which your app relied.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="5dff3-110">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="5dff3-110">New behavior</span></span>

<span data-ttu-id="5dff3-111">Möglicherweise müssen Sie Ihrer App `Microsoft.Extensions.*`-Paketabhängigkeiten hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="5dff3-111">Your app may have to add `Microsoft.Extensions.*` package dependencies.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="5dff3-112">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="5dff3-112">Reason for change</span></span>

<span data-ttu-id="5dff3-113">Die Paketrichtlinien wurden besser auf das Repository *dotnet/runtime* abgestimmt.</span><span class="sxs-lookup"><span data-stu-id="5dff3-113">Packaging policies were updated to better align with the *dotnet/runtime* repository.</span></span> <span data-ttu-id="5dff3-114">Unter der neuen Richtlinie werden nicht verwendete Paketverweise während der Paketerstellung aus *NUPKG*-Dateien entfernt.</span><span class="sxs-lookup"><span data-stu-id="5dff3-114">Under the new policy, unused package references are removed from *.nupkg* files during packaging.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="5dff3-115">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="5dff3-115">Recommended action</span></span>

<span data-ttu-id="5dff3-116">Benutzer der betroffenen Pakete sollten eine direkte Abhängigkeit von der entfernten Paketabhängigkeit zu ihrem Projekt hinzufügen, wenn APIs der entfernten Paketabhängigkeit verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5dff3-116">Consumers of the affected packages should add a direct dependency on the removed package dependency in their project if APIs from removed package dependency are used.</span></span> <span data-ttu-id="5dff3-117">In der folgenden Tabelle werden die betroffenen Pakete und die zugehörigen Änderungen aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="5dff3-117">The following table lists the affected packages and the corresponding changes.</span></span>

|<span data-ttu-id="5dff3-118">Paketname</span><span class="sxs-lookup"><span data-stu-id="5dff3-118">Package name</span></span>|<span data-ttu-id="5dff3-119">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="5dff3-119">Change description</span></span>|
|------------|------------------|
|[<span data-ttu-id="5dff3-120">Microsoft.Extensions.Configuration.Binder</span><span class="sxs-lookup"><span data-stu-id="5dff3-120">Microsoft.Extensions.Configuration.Binder</span></span>](https://nuget.org/packages/Microsoft.Extensions.Configuration.Binder)|<span data-ttu-id="5dff3-121">Verweis auf `Microsoft.Extensions.Configuration` entfernt</span><span class="sxs-lookup"><span data-stu-id="5dff3-121">Removed reference to `Microsoft.Extensions.Configuration`</span></span>|
|[<span data-ttu-id="5dff3-122">Microsoft.Extensions.Configuration.Json</span><span class="sxs-lookup"><span data-stu-id="5dff3-122">Microsoft.Extensions.Configuration.Json</span></span>](https://nuget.org/packages/Microsoft.Extensions.Configuration.Json)    |<span data-ttu-id="5dff3-123">Verweis auf `System.Threading.Tasks.Extensions` entfernt</span><span class="sxs-lookup"><span data-stu-id="5dff3-123">Removed reference to `System.Threading.Tasks.Extensions`</span></span>|
|[<span data-ttu-id="5dff3-124">Microsoft.Extensions.Hosting.Abstractions</span><span class="sxs-lookup"><span data-stu-id="5dff3-124">Microsoft.Extensions.Hosting.Abstractions</span></span>](https://nuget.org/packages/Microsoft.Extensions.Hosting.Abstractions)|<span data-ttu-id="5dff3-125">Verweis auf `Microsoft.Extensions.Logging.Abstractions` entfernt</span><span class="sxs-lookup"><span data-stu-id="5dff3-125">Removed reference to `Microsoft.Extensions.Logging.Abstractions`</span></span>|
|[<span data-ttu-id="5dff3-126">Microsoft.Extensions.Logging</span><span class="sxs-lookup"><span data-stu-id="5dff3-126">Microsoft.Extensions.Logging</span></span>](https://nuget.org/packages/Microsoft.Extensions.Logging)                          |<span data-ttu-id="5dff3-127">Verweis auf `Microsoft.Extensions.Configuration.Binder` entfernt</span><span class="sxs-lookup"><span data-stu-id="5dff3-127">Removed reference to `Microsoft.Extensions.Configuration.Binder`</span></span>|
|[<span data-ttu-id="5dff3-128">Microsoft.Extensions.Logging.Console</span><span class="sxs-lookup"><span data-stu-id="5dff3-128">Microsoft.Extensions.Logging.Console</span></span>](https://nuget.org/packages/Microsoft.Extensions.Logging.Console)          |<span data-ttu-id="5dff3-129">Verweis auf `Microsoft.Extensions.Configuration.Abstractions` entfernt</span><span class="sxs-lookup"><span data-stu-id="5dff3-129">Removed reference to `Microsoft.Extensions.Configuration.Abstractions`</span></span>|
|[<span data-ttu-id="5dff3-130">Microsoft.Extensions.Logging.EventLog</span><span class="sxs-lookup"><span data-stu-id="5dff3-130">Microsoft.Extensions.Logging.EventLog</span></span>](https://nuget.org/packages/Microsoft.Extensions.Logging.EventLog)        |<span data-ttu-id="5dff3-131">Verweis auf `System.Diagnostics.EventLog` für den .NET Framework 4.6.1-Zielframeworkmoniker entfernt</span><span class="sxs-lookup"><span data-stu-id="5dff3-131">Removed reference to `System.Diagnostics.EventLog` for the .NET Framework 4.6.1 target framework moniker</span></span>|
|[<span data-ttu-id="5dff3-132">Microsoft.Extensions.Logging.EventSource</span><span class="sxs-lookup"><span data-stu-id="5dff3-132">Microsoft.Extensions.Logging.EventSource</span></span>](https://nuget.org/packages/Microsoft.Extensions.Logging.EventSource)  |<span data-ttu-id="5dff3-133">Verweis auf `System.Threading.Tasks.Extensions` entfernt</span><span class="sxs-lookup"><span data-stu-id="5dff3-133">Removed reference to `System.Threading.Tasks.Extensions`</span></span>|
|[<span data-ttu-id="5dff3-134">Microsoft.Extensions.Options</span><span class="sxs-lookup"><span data-stu-id="5dff3-134">Microsoft.Extensions.Options</span></span>](https://nuget.org/packages/Microsoft.Extensions.Options)                          |<span data-ttu-id="5dff3-135">Verweis auf `System.ComponentModel.Annotations` entfernt</span><span class="sxs-lookup"><span data-stu-id="5dff3-135">Removed reference to `System.ComponentModel.Annotations`</span></span>|

<span data-ttu-id="5dff3-136">Beispielsweise wurde der Paketverweis auf `Microsoft.Extensions.Configuration` aus `Microsoft.Extensions.Configuration.Binder`entfernt.</span><span class="sxs-lookup"><span data-stu-id="5dff3-136">For example, the package reference to `Microsoft.Extensions.Configuration` was removed from `Microsoft.Extensions.Configuration.Binder`.</span></span> <span data-ttu-id="5dff3-137">Im Paket wurde keine API der Abhängigkeit verwendet.</span><span class="sxs-lookup"><span data-stu-id="5dff3-137">No API from the dependency was used in the package.</span></span> <span data-ttu-id="5dff3-138">Benutzer von `Microsoft.Extensions.Configuration.Binder`, die von `Microsoft.Extensions.Configuration`-APIs abhängig sind, sollten Ihrem Projekt einen direkten Verweis auf diese hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="5dff3-138">Users of `Microsoft.Extensions.Configuration.Binder` who depend on APIs from `Microsoft.Extensions.Configuration` should add a direct reference to it in their project.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="5dff3-139">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="5dff3-139">Affected APIs</span></span>

<span data-ttu-id="5dff3-140">Keine</span><span class="sxs-lookup"><span data-stu-id="5dff3-140">None</span></span>

<!--

### Category

ASP.NET Core

### Affected APIs

Not detectable via API analysis

-->
