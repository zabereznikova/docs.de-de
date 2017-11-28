---
title: "Organisieren Ihres Projekts zur Unterstützung von .NET Framework und .NET Core"
description: "Dieser Artikel soll Projektbesitzern dabei helfen, Ihre eigene Lösung parallel für .NET Framework und .NET Core zu kompilieren."
keywords: .NET, .NET Core, .NET Framework, Projektlayout, mehrere Frameworks
author: conniey
ms.author: mairaw
ms.date: 04/06/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 3af62252-1dfa-4336-8d2f-5cfdb57d7724
ms.openlocfilehash: 93bec65e3bbee93855d6f5bce5e2d6cea8bb9f3d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="organizing-your-project-to-support-net-framework-and-net-core"></a><span data-ttu-id="a21fe-104">Organisieren Ihres Projekts zur Unterstützung von .NET Framework und .NET Core</span><span class="sxs-lookup"><span data-stu-id="a21fe-104">Organizing your project to support .NET Framework and .NET Core</span></span>

<span data-ttu-id="a21fe-105">Dieser Artikel hilft Projektbesitzern, Ihre eigene Lösung parallel für .NET Framework und .NET Core zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="a21fe-105">This article helps project owners who want to compile their solution against .NET Framework and .NET Core side-by-side.</span></span> <span data-ttu-id="a21fe-106">Es werden mehrere Optionen zum Organisieren von Projekten behandelt, die Entwickler beim Erreichen dieses Ziels unterstützen sollen.</span><span class="sxs-lookup"><span data-stu-id="a21fe-106">It provides several options to organize projects to help developers achieve this goal.</span></span> <span data-ttu-id="a21fe-107">Im Folgenden finden Sie eine Liste mit typischen Szenarios, die Sie bei der Entscheidung bedenken sollten, wie Sie Ihr Projektlayout mit .NET Core einrichten.</span><span class="sxs-lookup"><span data-stu-id="a21fe-107">The following list provides some typical scenarios to consider when you're deciding how to setup your project layout with .NET Core.</span></span> <span data-ttu-id="a21fe-108">Die Liste deckt möglicherweise nicht alle Punkte ab, die Sie benötigen. Sie können abhängig von den Anforderungen Ihrer Projekte priorisieren.</span><span class="sxs-lookup"><span data-stu-id="a21fe-108">The list may not cover everything you want; prioritize based on your project's needs.</span></span>

* <span data-ttu-id="a21fe-109">[**Combine existing projects and .NET Core projects into single projects**][option-csproj] (Kombinieren von vorhandenen Projekten und .NET Core-Projekten in einzelnen Projekten)</span><span class="sxs-lookup"><span data-stu-id="a21fe-109">[**Combine existing projects and .NET Core projects into single projects**][option-csproj]</span></span>

  <span data-ttu-id="a21fe-110">*Es dient folgenden Zwecken:*</span><span class="sxs-lookup"><span data-stu-id="a21fe-110">*What this is good for:*</span></span>
  * <span data-ttu-id="a21fe-111">Vereinfachen Ihres Buildprozesses durch Kompilieren eines einzelnen Projekts statt mehrerer Projekte, die alle eine andere Version von .NET Framework oder eine andere Plattform als Ziel haben.</span><span class="sxs-lookup"><span data-stu-id="a21fe-111">Simplifying your build process by compiling a single project rather than compiling multiple projects, each targeting a different .NET Framework version or platform.</span></span>
  * <span data-ttu-id="a21fe-112">Vereinfachen der Verwaltung von Quelldateien für mehrfachzielorientierte Projekte, da Sie eine einzelne Projektdatei verwalten müssen.</span><span class="sxs-lookup"><span data-stu-id="a21fe-112">Simplifying source file management for multi-targeted projects because you must manage a single project file.</span></span> <span data-ttu-id="a21fe-113">Beim Hinzufügen/Entfernen von Quelldateien müssen Sie diese bei den Alternativen manuell mit Ihren Projekten synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="a21fe-113">When adding/removing source files, the alternatives require you to manually sync these with your other projects.</span></span>
  * <span data-ttu-id="a21fe-114">Einfaches Generieren eines NuGet-Pakets zum Verbrauch.</span><span class="sxs-lookup"><span data-stu-id="a21fe-114">Easily generating a NuGet package for consumption.</span></span>
  * <span data-ttu-id="a21fe-115">Ermöglicht das Schreiben von Code für eine bestimmte .NET Framework-Version in Ihren Bibliotheken mithilfe von Compileranweisungen.</span><span class="sxs-lookup"><span data-stu-id="a21fe-115">Allows you to write code for a specific .NET Framework version in your libraries through the use of compiler directives.</span></span>

  <span data-ttu-id="a21fe-116">*Nicht unterstützte Szenarios:*</span><span class="sxs-lookup"><span data-stu-id="a21fe-116">*Unsupported scenarios:*</span></span>
  * <span data-ttu-id="a21fe-117">Entwickler benötigen Visual Studio 2017, um vorhandene Projekte zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="a21fe-117">Requires developers to use Visual Studio 2017 to open existing projects.</span></span> <span data-ttu-id="a21fe-118">Zur Unterstützung von älteren Versionen von Visual Studio ist es eine bessere Option, [Ihre Projektdateien in unterschiedlichen Ordnern zu speichern](#support-vs).</span><span class="sxs-lookup"><span data-stu-id="a21fe-118">To support older versions of Visual Studio, [keeping your project files in different folders](#support-vs) is a better option.</span></span>

* <span data-ttu-id="a21fe-119"><a name="support-vs"></a>[**Trennen vorhandener und neuer .NET Core-Projekte**][option-csproj-folder]</span><span class="sxs-lookup"><span data-stu-id="a21fe-119"><a name="support-vs"></a>[**Keep existing projects and new .NET Core projects separate**][option-csproj-folder]</span></span>

  <span data-ttu-id="a21fe-120">*Es dient folgenden Zwecken:*</span><span class="sxs-lookup"><span data-stu-id="a21fe-120">*What this is good for:*</span></span>
  * <span data-ttu-id="a21fe-121">Entwicklung in bereits erstellten Projekten wird weiterhin unterstützt. Entwickler oder Mitwirkende, die eventuell nicht über Visual Studio 2017 verfügen, müssen kein Upgrade durchführen.</span><span class="sxs-lookup"><span data-stu-id="a21fe-121">Continuing to support development on existing projects without having to upgrade for developers/contributors who may not have Visual Studio 2017.</span></span>
  * <span data-ttu-id="a21fe-122">Minimieren der Möglichkeit, neue Probleme in vorhandenen Projekten zu erstellen, da in diesen Projekten keine Codeänderung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="a21fe-122">Decreasing the possibility of creating new bugs in existing projects because no code churn is required in those projects.</span></span>

## <a name="example"></a><span data-ttu-id="a21fe-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a21fe-123">Example</span></span>

<span data-ttu-id="a21fe-124">Betrachten Sie das folgende Repository:</span><span class="sxs-lookup"><span data-stu-id="a21fe-124">Consider the repository below:</span></span>

<span data-ttu-id="a21fe-125">![Vorhandenes Projekt][example-initial-project]</span><span class="sxs-lookup"><span data-stu-id="a21fe-125">![Existing project][example-initial-project]</span></span>

<span data-ttu-id="a21fe-126">[**Quellcode**][example-initial-project-code]</span><span class="sxs-lookup"><span data-stu-id="a21fe-126">[**Source Code**][example-initial-project-code]</span></span>

<span data-ttu-id="a21fe-127">Im Folgenden sind verschiedene Möglichkeiten beschrieben, Unterstützung für .NET Core für dieses Repository hinzuzufügen. Dies ist abhängig von den Einschränkungen und der Komplexität bestehender Projekte.</span><span class="sxs-lookup"><span data-stu-id="a21fe-127">The following describes several ways to add support for .NET Core for this repository depending on the constraints and complexity of the existing projects.</span></span>

## <a name="replace-existing-projects-with-a-multi-targeted-net-core-project"></a><span data-ttu-id="a21fe-128">Ersetzen von vorhandenen Projekten mit mehrfachzielorientierten .NET Core Projekten</span><span class="sxs-lookup"><span data-stu-id="a21fe-128">Replace existing projects with a multi-targeted .NET Core project</span></span>

<span data-ttu-id="a21fe-129">Organisieren Sie das Repository neu, sodass alle vorhandenen *\*.csproj*-Dateien entfernt werden, und eine einzelne *\*.csproj*-Datei erstellt wird, die mehrere Frameworks als Ziel hat.</span><span class="sxs-lookup"><span data-stu-id="a21fe-129">Reorganize the repository so that any existing *\*.csproj* files are removed and a single *\*.csproj* file is created that targets multiple frameworks.</span></span> <span data-ttu-id="a21fe-130">Dies ist eine hervorragende Option, da ein einzelnes Projekt für andere Frameworks kompilieren kann.</span><span class="sxs-lookup"><span data-stu-id="a21fe-130">This is a great option because a single project is able to compile for different frameworks.</span></span> <span data-ttu-id="a21fe-131">Außerdem kann die Option verschiedene Kompilierungsoptionen und Abhängigkeiten pro Zielframework behandeln.</span><span class="sxs-lookup"><span data-stu-id="a21fe-131">It also has the power to handle different compilation options and dependencies per targeted framework.</span></span>

<span data-ttu-id="a21fe-132">![Erstellen einer csproj, die mehrere Frameworks als Ziel hat][example-csproj]</span><span class="sxs-lookup"><span data-stu-id="a21fe-132">![Create an csproj that targets multiple frameworks][example-csproj]</span></span>

<span data-ttu-id="a21fe-133">[**Quellcode**][example-csproj-code]</span><span class="sxs-lookup"><span data-stu-id="a21fe-133">[**Source Code**][example-csproj-code]</span></span>

<span data-ttu-id="a21fe-134">Zu beachtende Änderungen:</span><span class="sxs-lookup"><span data-stu-id="a21fe-134">Changes to note are:</span></span>
* <span data-ttu-id="a21fe-135">Der Ersatz für *packages.config* und *\*.csproj* mit einer neuen [.NET Core *\*.csproj*][example-csproj-netcore].</span><span class="sxs-lookup"><span data-stu-id="a21fe-135">Replacement of *packages.config* and *\*.csproj* with a new [.NET Core *\*.csproj*][example-csproj-netcore].</span></span> <span data-ttu-id="a21fe-136">NuGet-Pakete werden mit `<PackageReference> ItemGroup` angegeben.</span><span class="sxs-lookup"><span data-stu-id="a21fe-136">NuGet packages are specified with `<PackageReference> ItemGroup`.</span></span>

## <a name="keep-existing-projects-and-create-a-net-core-project"></a><span data-ttu-id="a21fe-137">Behalten vorhandener Projekte und Erstellen eines .NET Core-Projekts</span><span class="sxs-lookup"><span data-stu-id="a21fe-137">Keep existing projects and create a .NET Core project</span></span>

<span data-ttu-id="a21fe-138">Wenn es vorhandene Projekte gibt, die ältere Frameworks als Ziel haben, empfiehlt es sich, diese Projekte unverändert zu lassen und ein .NET Core-Projekt zu verwenden, um kommende Frameworks als Ziel festzulegen.</span><span class="sxs-lookup"><span data-stu-id="a21fe-138">If there are existing projects that target older frameworks, you may want to leave these projects untouched and use a .NET Core project to target future frameworks.</span></span>

<span data-ttu-id="a21fe-139">![.NET Core-Projekt mit vorhandenem Projekt in anderem Ordner][example-csproj-different-folder]</span><span class="sxs-lookup"><span data-stu-id="a21fe-139">![.NET Core project with existing project in different folder][example-csproj-different-folder]</span></span>

<span data-ttu-id="a21fe-140">[**Quellcode**][example-csproj-different-code]</span><span class="sxs-lookup"><span data-stu-id="a21fe-140">[**Source Code**][example-csproj-different-code]</span></span>

<span data-ttu-id="a21fe-141">Zu beachtende Änderungen:</span><span class="sxs-lookup"><span data-stu-id="a21fe-141">Changes to note are:</span></span>
* <span data-ttu-id="a21fe-142">.NET Core-Projekte und vorhandene Projekte werden in separaten Ordnern gespeichert.</span><span class="sxs-lookup"><span data-stu-id="a21fe-142">The .NET Core and existing projects are kept in separate folders.</span></span>
    * <span data-ttu-id="a21fe-143">Projekte in separaten Ordnern zu speichern, vermeidet, dass Sie über Visual Studio 2017 verfügen müssen.</span><span class="sxs-lookup"><span data-stu-id="a21fe-143">Keeping projects in separate folders avoids forcing you to have Visual Studio 2017.</span></span> <span data-ttu-id="a21fe-144">Sie können eine separate Lösung erstellen, die nur die alten Projekte öffnet.</span><span class="sxs-lookup"><span data-stu-id="a21fe-144">You can create a separate solution that only opens the old projects.</span></span>

## <a name="see-also"></a><span data-ttu-id="a21fe-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a21fe-145">See Also</span></span>

<span data-ttu-id="a21fe-146">Weitere Anleitungen zum Migrieren zu .NET Core finden Sie in der [Dokumentation zum Portieren von .NET Core][porting-doc].</span><span class="sxs-lookup"><span data-stu-id="a21fe-146">Please see the [.NET Core porting documentation][porting-doc] for more guidance on migrating to .NET Core.</span></span>

[porting-doc]: index.md
[example-initial-project]: media/project-structure/project.png "Vorhandenes Projekt"
[example-initial-project-code]: https://github.com/dotnet/docs/tree/master/samples/framework/libraries/migrate-library/

[example-csproj]: media/project-structure/project.csproj.png "Erstellen einer csproj, die mehrere Frameworks als Ziel hat"
[example-csproj-code]: https://github.com/dotnet/docs/tree/master/samples/framework/libraries/migrate-library-csproj/
[example-csproj-netcore]: https://github.com/dotnet/docs/tree/master/samples/framework/libraries/migrate-library-csproj/src/Car/Car.csproj

[example-csproj-different-folder]: media/project-structure/project.csproj.different.png ".NET Core-Projekt mit vorhandener PLC in anderem Ordner"
[example-csproj-different-code]: https://github.com/dotnet/docs/tree/master/samples/framework/libraries/migrate-library-csproj-keep-existing/

[option-csproj]: #replace-existing-projects-with-a-multi-targeted-net-core-project
[option-csproj-folder]: #keep-existing-projects-and-create-a-net-core-project
