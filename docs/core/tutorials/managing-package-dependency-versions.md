---
title: "So verwalten Sie Paketabhängigkeitsversionen für .NET Core 1.0"
description: "Erfahren Sie mehr zur Versionsverwaltung der Paketabhängigkeit für Ihre .NET Core-Bibliotheken und Apps."
keywords: .NET, .NET Core
author: cartermp
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 4424a947-bdf9-4775-8d48-dc350a4e0aee
ms.workload: dotnetcore
ms.openlocfilehash: 2bb55f3bcd6678a127f099afbb9461cafe1a9c94
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-manage-package-dependency-versions-for-net-core-10"></a><span data-ttu-id="c7826-104">So verwalten Sie Paketabhängigkeitsversionen für .NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="c7826-104">How to Manage Package Dependency Versions for .NET Core 1.0</span></span>

<span data-ttu-id="c7826-105">Dieser Artikel beschreibt, was Sie über Paketversionen für Ihre .NET Core-Bibliotheken und Apps wissen müssen.</span><span class="sxs-lookup"><span data-stu-id="c7826-105">This article covers what you need to know about package versions for your .NET Core libraries and apps.</span></span>

## <a name="glossary"></a><span data-ttu-id="c7826-106">Glossar</span><span class="sxs-lookup"><span data-stu-id="c7826-106">Glossary</span></span>

<span data-ttu-id="c7826-107">**Korrigieren** – Das Korrigieren von Abhängigkeiten bedeutet, dass Sie dieselbe Paket-„Familie“ verwenden, die auf NuGet für .NET Core 1.0 erschienen ist.</span><span class="sxs-lookup"><span data-stu-id="c7826-107">**Fix** - Fixing dependencies means you are using the same "family" of packages released on NuGet for .NET Core 1.0.</span></span>

<span data-ttu-id="c7826-108">**Metapaket** – ein NuGet-Paket, dass eine Reihe NuGet-Pakete darstellt.</span><span class="sxs-lookup"><span data-stu-id="c7826-108">**Metapackage** - A NuGet package that represents a set of NuGet packages.</span></span>

<span data-ttu-id="c7826-109">**Trimmen** – Entfernen der Pakete, von denen Sie nicht von einem Metapaket abhängig sind.</span><span class="sxs-lookup"><span data-stu-id="c7826-109">**Trimming** - The act of removing the packages you do not depend on from a metapackage.</span></span>  <span data-ttu-id="c7826-110">Dies ist nur für Autoren von NuGet-Paketen relevant.</span><span class="sxs-lookup"><span data-stu-id="c7826-110">This is something relevant for NuGet package authors.</span></span>  <span data-ttu-id="c7826-111">Weitere Informationen finden Sie unter [Reducing Package Dependencies with project.json (Reduzieren von Paketabhängigkeiten mit project.json)](../deploying/reducing-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="c7826-111">See [Reducing Package Dependencies with project.json](../deploying/reducing-dependencies.md) for more information.</span></span> 

## <a name="fix-your-dependencies-to-net-core-10"></a><span data-ttu-id="c7826-112">Korrigieren Ihrer Abhängigkeiten zu .NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="c7826-112">Fix your dependencies to .NET Core 1.0</span></span>

<span data-ttu-id="c7826-113">Um zuverlässig Pakete wiederherzustellen und zuverlässigen Code zu schreiben, ist es wichtig, dass Sie Ihre Abhängigkeiten zu der Paketversionen korrigieren, die zusammen mit .NET Core 1.0 versendet werden.</span><span class="sxs-lookup"><span data-stu-id="c7826-113">To reliably restore packages and write reliable code, it's important that you fix your dependencies to the versions of packages shipping alongside .NET Core 1.0.</span></span>  <span data-ttu-id="c7826-114">Dies bedeutet, dass jedes Paket über eine einzelne Version ohne zusätzlichen Qualifizierer verfügen muss.</span><span class="sxs-lookup"><span data-stu-id="c7826-114">This means every package should have a single version with no additional qualifiers.</span></span>

<span data-ttu-id="c7826-115">**Beispiele für Pakete, die zu 1.0 korrigiert wurden**</span><span class="sxs-lookup"><span data-stu-id="c7826-115">**Examples of packages fixed to 1.0**</span></span>

`"System.Collections":"4.0.11"`

`"NETStandard.Library":"1.6.0"`

`"Microsoft.NETCore.App":"1.0.0"`

<span data-ttu-id="c7826-116">**Beispiele für Pakete, die NICHT zu 1.0 korrigiert wurden**</span><span class="sxs-lookup"><span data-stu-id="c7826-116">**Examples of packages that are NOT fixed to 1.0**</span></span>

`"Microsoft.NETCore.App":"1.0.0-rc4-00454-00"`

`"System.Net.Http":"4.1.0-*"`

`"System.Text.RegularExpressions":"4.0.10-rc3-24021-00"`

### <a name="why-does-this-matter"></a><span data-ttu-id="c7826-117">Warum ist das wichtig?</span><span class="sxs-lookup"><span data-stu-id="c7826-117">Why does this matter?</span></span>

<span data-ttu-id="c7826-118">Wir garantieren, dass alle Pakete zusammen funktionieren, wenn Sie Ihre Abhängigkeiten auf das korrigiert haben, was zusammen mit .NET Core 1.0 versendet wird.</span><span class="sxs-lookup"><span data-stu-id="c7826-118">We guarantee that if you fix your dependencies to what ships alongside .NET Core 1.0, those packages will all work together.</span></span> <span data-ttu-id="c7826-119">Diese Garantie verfällt, wenn Sie Pakete verwenden, die nicht auf diese Weise korrigiert wurden.</span><span class="sxs-lookup"><span data-stu-id="c7826-119">There is no such guarantee if you use packages which aren't fixed in this way.</span></span>

### <a name="scenarios"></a><span data-ttu-id="c7826-120">Szenarien</span><span class="sxs-lookup"><span data-stu-id="c7826-120">Scenarios</span></span>

<span data-ttu-id="c7826-121">Es gibt zwar eine umfangreiche Liste aller Pakete und deren Versionen, die mit .NET Core 1.0 veröffentlicht wurden, jedoch müssen Sie diese möglicherweise nicht durchgehen, wenn Ihr Code unter bestimmte Szenarios fällt.</span><span class="sxs-lookup"><span data-stu-id="c7826-121">Although there is a big list of all packages and their versions released with .NET Core 1.0, you may not have to look through it if your code falls under certain scenarios.</span></span>

<span data-ttu-id="c7826-122">**Sind Sie ausschließlich von** `NETStandard.Library` **abhängig?**</span><span class="sxs-lookup"><span data-stu-id="c7826-122">**Are you depending only on** `NETStandard.Library`**?**</span></span>

<span data-ttu-id="c7826-123">Wenn ja, dann sollten Sie Ihr `NETStandard.Library`-Paket zu Version `1.6` korrigieren.</span><span class="sxs-lookup"><span data-stu-id="c7826-123">If so, you should fix your `NETStandard.Library` package to version `1.6`.</span></span>  <span data-ttu-id="c7826-124">Da es sich um ein geordnetes Metapaket handelt, wird dessen Paketabschluss ebenso auf 1.0 festgelegt.</span><span class="sxs-lookup"><span data-stu-id="c7826-124">Because this is a curated metapackage, its package closure is also fixed to 1.0.</span></span>

<span data-ttu-id="c7826-125">**Sind Sie ausschließlich von** `Microsoft.NETCore.App` **abhängig?**</span><span class="sxs-lookup"><span data-stu-id="c7826-125">**Are you depending only on** `Microsoft.NETCore.App`**?**</span></span>

<span data-ttu-id="c7826-126">Wenn ja, dann sollten Sie Ihr `Microsoft.NETCore.App`-Paket zu Version `1.0.0` korrigieren.</span><span class="sxs-lookup"><span data-stu-id="c7826-126">If so, you should fix your `Microsoft.NETCore.App` package to version `1.0.0`.</span></span>  <span data-ttu-id="c7826-127">Da es sich um ein geordnetes Metapaket handelt, wird dessen Paketabschluss ebenso auf 1.0 festgelegt.</span><span class="sxs-lookup"><span data-stu-id="c7826-127">Because this is a curated metapackage, its package closure is also fixed to 1.0.</span></span>

<span data-ttu-id="c7826-128">**[Trimmen](../deploying/reducing-dependencies.md) Sie Ihre** `NETStandard.Library` **oder** `Microsoft.NETCore.App` **-Metapaketabhängigkeiten?**</span><span class="sxs-lookup"><span data-stu-id="c7826-128">**Are you [trimming](../deploying/reducing-dependencies.md) your** `NETStandard.Library` **or** `Microsoft.NETCore.App` **metapackage dependencies?**</span></span>

<span data-ttu-id="c7826-129">Wenn dies der Fall ist, gehen Sie sicher, dass das Metapaket, mit dem Sie beginnen, zu 1.0 korrigiert wurde.</span><span class="sxs-lookup"><span data-stu-id="c7826-129">If so, you should ensure that the metapackage you start with is fixed to 1.0.</span></span>  <span data-ttu-id="c7826-130">Die einzelnen Pakete, von denen Sie nach dem Trimmen abhängig sind, werden auch zu 1.0 korrigiert.</span><span class="sxs-lookup"><span data-stu-id="c7826-130">The individual packages you depend on after trimming are also fixed to 1.0.</span></span>

<span data-ttu-id="c7826-131">**Sind Sie von Paketen außerhalb der** `NETStandard.Library` **oder** `Microsoft.NETCore.App` **-Metapakete abhängig?**</span><span class="sxs-lookup"><span data-stu-id="c7826-131">**Are you depending on packages outside the** `NETStandard.Library` **or** `Microsoft.NETCore.App` **metapackages?**</span></span>

<span data-ttu-id="c7826-132">Wenn dies der Fall ist, müssen Sie Ihre anderen Abhängigkeiten zu 1.0 korrigieren.</span><span class="sxs-lookup"><span data-stu-id="c7826-132">If so, you need to fix your other dependencies to 1.0.</span></span>  <span data-ttu-id="c7826-133">Sehen Sie sich die richtigen Paketversionen und Buildnummern am Ende dieses Artikels an.</span><span class="sxs-lookup"><span data-stu-id="c7826-133">See the correct package versions and build numbers at the end of this article.</span></span>

### <a name="a-note-on-using-a-splat-string--when-versioning"></a><span data-ttu-id="c7826-134">Hinweis zur Verwendung einer Splat-Zeichenfolge (\\*) bei der Versionskontrolle</span><span class="sxs-lookup"><span data-stu-id="c7826-134">A note on using a splat string (\\*) when versioning</span></span>

<span data-ttu-id="c7826-135">Sie haben womöglich ein Muster bei der Versionskontrolle übernommen, bei dem eine Splat-Zeichenfolge (\*) wie etwa die folgende verwendet wird: `"System.Collections":"4.0.11-*"`.</span><span class="sxs-lookup"><span data-stu-id="c7826-135">You may have adopted a versioning pattern which uses a splat (\*) string like this: `"System.Collections":"4.0.11-*"`.</span></span>

<span data-ttu-id="c7826-136">**Dies sollten Sie nicht tun**.</span><span class="sxs-lookup"><span data-stu-id="c7826-136">**You should not do this**.</span></span>  <span data-ttu-id="c7826-137">Die Verwendung einer Splat-Zeichenfolge könnte zum Wiederherstellen von Paketen aus verschiedenen Builds führen. Einige davon gehen dann möglicherweise über .NET Core 1.0 hinaus.</span><span class="sxs-lookup"><span data-stu-id="c7826-137">Using the splat string could result in restoring packages from different builds, some of which may be further along than .NET Core 1.0.</span></span>  <span data-ttu-id="c7826-138">Dies kann dazu führen, dass einige Pakete inkompatibel werden.</span><span class="sxs-lookup"><span data-stu-id="c7826-138">This could then result in some packages being incompatible.</span></span>

## <a name="packages-and-version-numbers-organized-by-metapackage"></a><span data-ttu-id="c7826-139">Von Metapaketen organisierte Pakete und Versionsnummern</span><span class="sxs-lookup"><span data-stu-id="c7826-139">Packages and Version Numbers organized by Metapackage</span></span>

<span data-ttu-id="c7826-140">[List of all .NET Standard packages and their versions for 1.0 (Liste aller Pakete von .NET Standard und deren Versionen für 1.0)](https://github.com/dotnet/versions/blob/master/build-info/dotnet/corefx/release/1.0.0/Latest_Packages.txt).</span><span class="sxs-lookup"><span data-stu-id="c7826-140">[List of all .NET Standard packages and their versions for 1.0](https://github.com/dotnet/versions/blob/master/build-info/dotnet/corefx/release/1.0.0/Latest_Packages.txt).</span></span>

<span data-ttu-id="c7826-141">[Liste aller Laufzeitpakete und deren Versionen für 1.0](https://github.com/dotnet/versions/blob/master/build-info/dotnet/coreclr/release/1.0.0/LKG_Packages.txt).</span><span class="sxs-lookup"><span data-stu-id="c7826-141">[List of all runtime packages and their versions for 1.0](https://github.com/dotnet/versions/blob/master/build-info/dotnet/coreclr/release/1.0.0/LKG_Packages.txt).</span></span>

<span data-ttu-id="c7826-142">[Liste aller .NET Core-Anwendungspakete und deren Versionen für 1.0](https://github.com/dotnet/versions/blob/master/build-info/dotnet/core-setup/release/1.0.0/Latest_Packages.txt).</span><span class="sxs-lookup"><span data-stu-id="c7826-142">[List of all .NET Core application packages and their versions for 1.0](https://github.com/dotnet/versions/blob/master/build-info/dotnet/core-setup/release/1.0.0/Latest_Packages.txt).</span></span>
