---
title: "Portieren auf .NET Core – Analysieren der Abhängigkeiten von Drittanbietern"
description: "Portieren auf .NET Core – Analysieren der Abhängigkeiten von Drittanbietern"
keywords: .NET, .NET Core
author: cartermp
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: b446e9e0-72f6-48f6-92c6-70ad0ce3f86a
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a074978f2817abafa7b8a9fefe7c67c9c52195b3
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---

# <a name="porting-to-net-core---analyzing-your-third-party-party-dependencies"></a><span data-ttu-id="dfd32-104">Portieren auf .NET Core – Analysieren der Abhängigkeiten von Drittanbietern</span><span class="sxs-lookup"><span data-stu-id="dfd32-104">Porting to .NET Core - Analyzing your Third-Party Party Dependencies</span></span>

<span data-ttu-id="dfd32-105">Der erste Schritt bei der Portierung besteht darin, die Abhängigkeiten von Drittanbietern zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="dfd32-105">The first step in the porting process is to understand your third party dependencies.</span></span>  <span data-ttu-id="dfd32-106">Sie müssen herausfinden, welche gegebenenfalls noch nicht unter .NET Core ausgeführt werden und für diese einen Notfallplan entwickeln.</span><span class="sxs-lookup"><span data-stu-id="dfd32-106">You need to figure out which of them, if any, don't yet run on .NET Core, and develop a contingency plan for those which don't run on .NET Core.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="dfd32-107">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="dfd32-107">Prerequisites</span></span>

<span data-ttu-id="dfd32-108">In diesem Artikel wird davon ausgegangen, dass Sie Windows und Visual Studio sowie Code verwenden, der derzeit auf .NET Framework ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="dfd32-108">This article will assume you are using Windows and Visual Studio, and that you have code which runs on the .NET Framework today.</span></span>

## <a name="analyzing-nuget-packages"></a><span data-ttu-id="dfd32-109">Analysieren von NuGet-Paketen</span><span class="sxs-lookup"><span data-stu-id="dfd32-109">Analyzing NuGet Packages</span></span>

<span data-ttu-id="dfd32-110">Die Analyse von NuGet-Paketen für Portabilität ist sehr einfach.</span><span class="sxs-lookup"><span data-stu-id="dfd32-110">Analyzing NuGet packages for portability is very easy.</span></span>  <span data-ttu-id="dfd32-111">Da ein NuGet-Paket selbst eine Reihe von Ordnern darstellt, die plattformspezifische Assemblys enthalten, müssen Sie lediglich überprüfen, ob ein Ordner mit einer .NET Core-Assembly vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="dfd32-111">Because a NuGet package is itself a set of folders which contain platform-specific assemblies, all you have to do is check to see if there is a folder which contains a .NET Core assembly.</span></span>

<span data-ttu-id="dfd32-112">Am einfachsten überprüfen Sie die NuGet-Paket-Ordner mit dem Tool [NuGet-Paket-Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer).</span><span class="sxs-lookup"><span data-stu-id="dfd32-112">Inspecting NuGet Package folders is easiest with the [NuGet Package Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer) tool.</span></span>  <span data-ttu-id="dfd32-113">Und so gehen Sie dabei vor.</span><span class="sxs-lookup"><span data-stu-id="dfd32-113">Here's how to do it.</span></span>

1. <span data-ttu-id="dfd32-114">Laden Sie den NuGet-Paket-Explorer herunter, und öffnen Sie ihn.</span><span class="sxs-lookup"><span data-stu-id="dfd32-114">Download and open the NuGet Package Explorer.</span></span>
2. <span data-ttu-id="dfd32-115">Klicken Sie auf „Open package from online feed“ (Paket im Online-Feed öffnen).</span><span class="sxs-lookup"><span data-stu-id="dfd32-115">Click "Open package from online feed".</span></span>
3. <span data-ttu-id="dfd32-116">Suchen Sie nach dem Namen des Pakets.</span><span class="sxs-lookup"><span data-stu-id="dfd32-116">Search for the name of the package.</span></span>
4. <span data-ttu-id="dfd32-117">Erweitern Sie den Ordner „Lib“ auf der rechten Seite, und suchen Sie in den Ordnernamen.</span><span class="sxs-lookup"><span data-stu-id="dfd32-117">Expand the "lib" folder on the right-hand side and look at folder names.</span></span>

<span data-ttu-id="dfd32-118">Unter [nuget.org](https://www.nuget.org/) können Sie im Abschnitt **Dependencies** (Abhängigkeiten) der Seite für dieses Paket auch sehen, was von einem Paket unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="dfd32-118">You can also see what a package supports on [nuget.org](https://www.nuget.org/) under the **Dependencies** section of the page for that package.</span></span>

<span data-ttu-id="dfd32-119">In beiden Fällen müssen Sie unter [nuget.org](https://www.nuget.org/) nach einem Ordner oder Eintrag mit einem der folgenden Namen suchen:</span><span class="sxs-lookup"><span data-stu-id="dfd32-119">In either case, you'll need to look for a folder or entry on [nuget.org](https://www.nuget.org/) with any of the following names:</span></span>

```
netstandard1.0
netstandard1.1
netstandard1.2
netstandard1.3
netstandard1.4
netstandard1.5
netstandard1.6
netcoreapp1.0
portable-net45-win8
portable-win8-wpa8
portable-net451-win81
portable-net45-win8-wpa8-wpa81
```

<span data-ttu-id="dfd32-120">Hierbei handelt es sich um Target Framework Moniker (TFM), die den Versionen von [.NET-Standard](../../standard/net-standard.md) und den herkömmlichen PCL-Profilen (Portable Class Library) zugeordnet sind, die mit .NET Core kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="dfd32-120">These are the Target Framework Monikers (TFM) which map to versions of the [.NET Standard](../../standard/net-standard.md) and traditional Portable Class Library (PCL) profiles which are compatible with .NET Core.</span></span>  <span data-ttu-id="dfd32-121">Beachten Sie, dass `netcoreapp1.0` zwar kompatibel ist, jedoch nicht für Bibliotheken, sondern für Anwendungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="dfd32-121">Note that `netcoreapp1.0`, while compatible, is for applications and not libraries.</span></span>  <span data-ttu-id="dfd32-122">Sie können zwar eine `netcoreapp1.0`-basierte Bibliothek verwenden, diese wird jedoch von anderen `netcoreapp1.0`-Anwendungen möglicherweise für nichts *anderes* als für den Verbrauch verwendet.</span><span class="sxs-lookup"><span data-stu-id="dfd32-122">Although there's nothing wrong with using a library which is `netcoreapp1.0`-based, that library may not be intended for anything *other* than consumption by other `netcoreapp1.0` applications.</span></span>

<span data-ttu-id="dfd32-123">Es gibt auch einige ältere TFMs, die in Vorabversionen von .NET Core verwendet wurden, die möglicherweise ebenfalls kompatibel sind:</span><span class="sxs-lookup"><span data-stu-id="dfd32-123">There are also some legacy TFMs used in pre-release versions of .NET Core that may also be compatible:</span></span>

```
dnxcore50
dotnet5.0
dotnet5.1
dotnet5.2
dotnet5.3
dotnet5.4
dotnet5.5
```

<span data-ttu-id="dfd32-124">**Die Wahrscheinlichkeit ist hoch, dass diese mit Ihrem Code funktionieren, eine Garantie für die Kompatibilität besteht jedoch nicht**.</span><span class="sxs-lookup"><span data-stu-id="dfd32-124">**While these will likely work with your code, there is no guarantee of compatibility**.</span></span>  <span data-ttu-id="dfd32-125">Pakete mit diesen TFMs wurden mit der Vorabversion von .NET Core-Paketen erstellt.</span><span class="sxs-lookup"><span data-stu-id="dfd32-125">Packages with these TFMs were built with pre-release .NET Core packages.</span></span>  <span data-ttu-id="dfd32-126">Achten Sie darauf, wann (oder ob) Pakete wie dieses so aktualisiert werden, dass sie auf `netstandard` basieren.</span><span class="sxs-lookup"><span data-stu-id="dfd32-126">Take note of when (or if) packages like this are updated to be `netstandard`-based.</span></span>

> [!NOTE]
> <span data-ttu-id="dfd32-127">Wenn Sie ein Paket auf eine herkömmliche PCL oder Vorabversion von .NET Core ausrichten möchten, müssen Sie die `imports`-Anweisung in Ihrer `project.json`-Datei verwenden.</span><span class="sxs-lookup"><span data-stu-id="dfd32-127">To use a package targeting a traditional PCL or pre-release .NET Core target, you must use the `imports` directive in your `project.json` file.</span></span>

### <a name="what-to-do-when-your-nuget-package-dependency-doesnt-run-on-net-core"></a><span data-ttu-id="dfd32-128">Vorgehensweise, wenn die NuGet-Paket-Abhängigkeit unter .NET Core nicht ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="dfd32-128">What to do when your NuGet package dependency doesn't run on .NET Core</span></span>

<span data-ttu-id="dfd32-129">Es gibt einige Dinge, die Sie tun können, wenn ein NuGet-Paket, auf das Sie angewiesen sind, unter .NET Core nicht ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="dfd32-129">There are a few things you can do if a NuGet package you depend on won't run on .NET Core.</span></span>

1. <span data-ttu-id="dfd32-130">Wenn es sich um ein Open Source-Projekt handelt, das beispielsweise von GitHub gehostet wird, können Sie sich direkt an den oder die Entwickler wenden.</span><span class="sxs-lookup"><span data-stu-id="dfd32-130">If the project is open source and hosted somewhere like GitHub, you can engage the developer(s) directly.</span></span>
2. <span data-ttu-id="dfd32-131">Über [nuget.org](https://www.nuget.org/) können Sie sich direkt an den Entwickler wenden, indem Sie nach dem Paket suchen und links auf der Seite des Pakets auf „Contact Owners“ (An Besitzer wenden) klicken.</span><span class="sxs-lookup"><span data-stu-id="dfd32-131">You can contact the author directly on [nuget.org](https://www.nuget.org/) by searching for the package and clicking "Contact Owners" on the left hand side of the package's page.</span></span>
3. <span data-ttu-id="dfd32-132">Sie können nach einem anderen Paket suchen, das unter .NET Core ausgeführt wird und denselben Zweck erfüllt wie das Paket, das Sie bisher verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="dfd32-132">You can look for another package that runs on .NET Core which accomplishes the same task as the package you were using.</span></span>
4. <span data-ttu-id="dfd32-133">Sie können den vom Paket ausgeführten Code selbst schreiben.</span><span class="sxs-lookup"><span data-stu-id="dfd32-133">You can attempt to write the code the package was doing yourself.</span></span>
5. <span data-ttu-id="dfd32-134">Sie können die Abhängigkeit für das Paket eliminieren, indem Sie die Funktionalität Ihrer Anwendung ändern, zumindest bis eine kompatible Version des Pakets verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="dfd32-134">You could eliminate the dependency on the package by changing the functionality of your app, at least until a compatible version of the package becomes available.</span></span>

<span data-ttu-id="dfd32-135">Denken Sie daran, dass Betreiber von Open Source-Projekten und Herausgeber von NuGet-Paketen häufig ehrenamtlich tätig sind, sich kostenlos um einen bestimmten Bereich kümmern, und ansonsten einer anderen Tätigkeit nachgehen.</span><span class="sxs-lookup"><span data-stu-id="dfd32-135">Please remember that open source project maintainers and NuGet package publishers are often volunteers who contribute because they care about a given domain, do it for free, and often have a different daytime job.</span></span> <span data-ttu-id="dfd32-136">Wenn Sie bei ihnen anfragen, sollten Sie mit einer positiven Äußerung zu der Bibliothek beginnen, bevor Sie um Unterstützung bei .NET Core bitten.</span><span class="sxs-lookup"><span data-stu-id="dfd32-136">If you do reach out, you might start with a positive statement about the library before asking about .NET Core support.</span></span>

<span data-ttu-id="dfd32-137">Wenn es Ihnen mit den genannten Vorschlägen nicht gelingt, Ihr Problem zu beheben, müssen Sie sich mit dem Portieren auf .NET Core noch etwas gedulden.</span><span class="sxs-lookup"><span data-stu-id="dfd32-137">If you're unable to resolve your issue with any of the above, you may have to port to .NET Core at a later date.</span></span>

<span data-ttu-id="dfd32-138">Das .NET-Team würde gerne wissen, welche Bibliotheken als Nächstes von .NET Core unterstützt werden sollten.</span><span class="sxs-lookup"><span data-stu-id="dfd32-138">The .NET Team would like to know which libraries are the most important to support next with .NET Core.</span></span> <span data-ttu-id="dfd32-139">Sie können uns gerne per E-Mail an dotnet@microsoft.com mitteilen, welche Bibliotheken Sie gerne verwenden würden.</span><span class="sxs-lookup"><span data-stu-id="dfd32-139">You can also send us mail at dotnet@microsoft.com about the libraries you'd like to use.</span></span>

## <a name="analyzing-dependencies-which-arent-nuget-packages"></a><span data-ttu-id="dfd32-140">Analysieren von Abhängigkeiten, bei denen es sich nicht um NuGet-Pakete handelt</span><span class="sxs-lookup"><span data-stu-id="dfd32-140">Analyzing Dependencies which aren't NuGet Packages</span></span>

<span data-ttu-id="dfd32-141">Möglicherweise verfügen Sie über eine Abhängigkeit, bei der es sich nicht um ein NuGet-Paket, sondern beispielsweise um eine DLL im Dateisystem handelt.</span><span class="sxs-lookup"><span data-stu-id="dfd32-141">You may have a dependency that isn't a NuGet package, such as a DLL in the filesystem.</span></span>  <span data-ttu-id="dfd32-142">Wenn Sie feststellen möchten, ob diese Abhängigkeit portiert werden kann, haben Sie nur die Möglichkeit, das Tool [ApiPort](https://github.com/Microsoft/dotnet-apiport/blob/master/docs/HowTo/) auszuführen.</span><span class="sxs-lookup"><span data-stu-id="dfd32-142">The only way to determine the portability of that dependency is to run the [ApiPort tool](https://github.com/Microsoft/dotnet-apiport/blob/master/docs/HowTo/).</span></span>

## <a name="next-steps"></a><span data-ttu-id="dfd32-143">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="dfd32-143">Next steps</span></span>

<span data-ttu-id="dfd32-144">Wenn Sie eine Bibliothek portieren, lesen Sie [Portieren von Bibliotheken](libraries.md).</span><span class="sxs-lookup"><span data-stu-id="dfd32-144">If you're porting a library, check out [Porting your Libraries](libraries.md).</span></span>

