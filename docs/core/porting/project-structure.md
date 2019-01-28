---
title: Organisieren von Projekten für .NET Framework und .NET Core
description: Dieser Artikel soll Projektbesitzern dabei helfen, Ihre eigene Lösung parallel für .NET Framework und .NET Core zu kompilieren.
author: conniey
ms.date: 04/06/2017
ms.custom: seodec18
ms.openlocfilehash: 52205a32af212dc74b000025c0e4fc8cde3ae134
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54498660"
---
# <a name="organize-your-project-to-support-both-net-framework-and-net-core"></a><span data-ttu-id="1d490-103">Organisieren Ihres Projekts zur Unterstützung von sowohl .NET Framework als auch .NET Core</span><span class="sxs-lookup"><span data-stu-id="1d490-103">Organize your project to support both .NET Framework and .NET Core</span></span>

<span data-ttu-id="1d490-104">Erfahren Sie, wie Sie eine Lösung erstellen, die .NET Framework und .NET Core parallel kompiliert.</span><span class="sxs-lookup"><span data-stu-id="1d490-104">Learn how to create a solution that compiles for both .NET Framework and .NET Core side-by-side.</span></span> <span data-ttu-id="1d490-105">Es gibt mehrere Optionen zum Organisieren von Projekten, um dieses Ziel zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="1d490-105">See several options to organize projects to help you achieve this goal.</span></span> <span data-ttu-id="1d490-106">Im Folgenden finden Sie einige Szenarios, die Sie bei der Entscheidung bedenken sollten, wie Sie Ihr Projektlayout mit .NET Core einrichten.</span><span class="sxs-lookup"><span data-stu-id="1d490-106">Here are some typical scenarios to consider when you're deciding how to setup your project layout with .NET Core.</span></span> <span data-ttu-id="1d490-107">Die Liste deckt möglicherweise nicht alle Punkte ab, die Sie benötigen. Sie können abhängig von den Anforderungen Ihrer Projekte priorisieren.</span><span class="sxs-lookup"><span data-stu-id="1d490-107">The list may not cover everything you want; prioritize based on your project's needs.</span></span>

* <span data-ttu-id="1d490-108">[**Combine existing projects and .NET Core projects into single projects**][option-csproj] (Kombinieren von vorhandenen Projekten und .NET Core-Projekten in einzelnen Projekten)</span><span class="sxs-lookup"><span data-stu-id="1d490-108">[**Combine existing projects and .NET Core projects into single projects**][option-csproj]</span></span>

  <span data-ttu-id="1d490-109">*Es dient folgenden Zwecken:*</span><span class="sxs-lookup"><span data-stu-id="1d490-109">*What this is good for:*</span></span>
  * <span data-ttu-id="1d490-110">Vereinfachen Ihres Buildprozesses durch Kompilieren eines einzelnen Projekts statt mehrerer Projekte, die alle eine andere Version von .NET Framework oder eine andere Plattform als Ziel haben.</span><span class="sxs-lookup"><span data-stu-id="1d490-110">Simplifying your build process by compiling a single project rather than compiling multiple projects, each targeting a different .NET Framework version or platform.</span></span>
  * <span data-ttu-id="1d490-111">Vereinfachen der Verwaltung von Quelldateien für mehrfachzielorientierte Projekte, da Sie eine einzelne Projektdatei verwalten müssen.</span><span class="sxs-lookup"><span data-stu-id="1d490-111">Simplifying source file management for multi-targeted projects because you must manage a single project file.</span></span> <span data-ttu-id="1d490-112">Beim Hinzufügen/Entfernen von Quelldateien müssen Sie diese bei den Alternativen manuell mit Ihren Projekten synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="1d490-112">When adding/removing source files, the alternatives require you to manually sync these with your other projects.</span></span>
  * <span data-ttu-id="1d490-113">Einfaches Generieren eines NuGet-Pakets zum Verbrauch.</span><span class="sxs-lookup"><span data-stu-id="1d490-113">Easily generating a NuGet package for consumption.</span></span>
  * <span data-ttu-id="1d490-114">Ermöglicht das Schreiben von Code für eine bestimmte .NET Framework-Version in Ihren Bibliotheken mithilfe von Compileranweisungen.</span><span class="sxs-lookup"><span data-stu-id="1d490-114">Allows you to write code for a specific .NET Framework version in your libraries through the use of compiler directives.</span></span>

  <span data-ttu-id="1d490-115">*Nicht unterstützte Szenarios:*</span><span class="sxs-lookup"><span data-stu-id="1d490-115">*Unsupported scenarios:*</span></span>
  * <span data-ttu-id="1d490-116">Entwickler benötigen Visual Studio 2017, um vorhandene Projekte zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="1d490-116">Requires developers to use Visual Studio 2017 to open existing projects.</span></span> <span data-ttu-id="1d490-117">Zur Unterstützung von älteren Versionen von Visual Studio ist es eine bessere Option, [Ihre Projektdateien in unterschiedlichen Ordnern zu speichern](#support-vs).</span><span class="sxs-lookup"><span data-stu-id="1d490-117">To support older versions of Visual Studio, [keeping your project files in different folders](#support-vs) is a better option.</span></span>

* <a name="support-vs"></a><span data-ttu-id="1d490-118">[**Trennen vorhandener und neuer .NET Core-Projekte**][option-csproj-folder]</span><span class="sxs-lookup"><span data-stu-id="1d490-118">[**Keep existing projects and new .NET Core projects separate**][option-csproj-folder]</span></span>

  <span data-ttu-id="1d490-119">*Es dient folgenden Zwecken:*</span><span class="sxs-lookup"><span data-stu-id="1d490-119">*What this is good for:*</span></span>
  * <span data-ttu-id="1d490-120">Entwicklung in bereits erstellten Projekten wird weiterhin unterstützt. Entwickler oder Mitwirkende, die eventuell nicht über Visual Studio 2017 verfügen, müssen kein Upgrade durchführen.</span><span class="sxs-lookup"><span data-stu-id="1d490-120">Continuing to support development on existing projects without having to upgrade for developers/contributors who may not have Visual Studio 2017.</span></span>
  * <span data-ttu-id="1d490-121">Minimieren der Möglichkeit, neue Probleme in vorhandenen Projekten zu erstellen, da in diesen Projekten keine Codeänderung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="1d490-121">Decreasing the possibility of creating new bugs in existing projects because no code churn is required in those projects.</span></span>

## <a name="example"></a><span data-ttu-id="1d490-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1d490-122">Example</span></span>

<span data-ttu-id="1d490-123">Betrachten Sie das folgende Repository:</span><span class="sxs-lookup"><span data-stu-id="1d490-123">Consider the repository below:</span></span>

<span data-ttu-id="1d490-124">![Vorhandenes Projekt][example-initial-project]</span><span class="sxs-lookup"><span data-stu-id="1d490-124">![Existing project][example-initial-project]</span></span>

<span data-ttu-id="1d490-125">[**Quellcode**][example-initial-project-code]</span><span class="sxs-lookup"><span data-stu-id="1d490-125">[**Source Code**][example-initial-project-code]</span></span>

<span data-ttu-id="1d490-126">Im Folgenden sind verschiedene Möglichkeiten beschrieben, Unterstützung für .NET Core für dieses Repository hinzuzufügen. Dies ist abhängig von den Einschränkungen und der Komplexität bestehender Projekte.</span><span class="sxs-lookup"><span data-stu-id="1d490-126">The following describes several ways to add support for .NET Core for this repository depending on the constraints and complexity of the existing projects.</span></span>

## <a name="replace-existing-projects-with-a-multi-targeted-net-core-project"></a><span data-ttu-id="1d490-127">Ersetzen von vorhandenen Projekten mit mehrfachzielorientierten .NET Core Projekten</span><span class="sxs-lookup"><span data-stu-id="1d490-127">Replace existing projects with a multi-targeted .NET Core project</span></span>

<span data-ttu-id="1d490-128">Organisieren Sie das Repository neu, sodass alle vorhandenen *\*.csproj*-Dateien entfernt werden, und eine einzelne *\*.csproj*-Datei erstellt wird, die mehrere Frameworks als Ziel hat.</span><span class="sxs-lookup"><span data-stu-id="1d490-128">Reorganize the repository so that any existing *\*.csproj* files are removed and a single *\*.csproj* file is created that targets multiple frameworks.</span></span> <span data-ttu-id="1d490-129">Dies ist eine hervorragende Option, da ein einzelnes Projekt für andere Frameworks kompilieren kann.</span><span class="sxs-lookup"><span data-stu-id="1d490-129">This is a great option because a single project is able to compile for different frameworks.</span></span> <span data-ttu-id="1d490-130">Außerdem kann die Option verschiedene Kompilierungsoptionen und Abhängigkeiten pro Zielframework behandeln.</span><span class="sxs-lookup"><span data-stu-id="1d490-130">It also has the power to handle different compilation options and dependencies per targeted framework.</span></span>

<span data-ttu-id="1d490-131">![Erstellen einer csproj, die mehrere Frameworks als Ziel hat][example-csproj]</span><span class="sxs-lookup"><span data-stu-id="1d490-131">![Create an csproj that targets multiple frameworks][example-csproj]</span></span>

<span data-ttu-id="1d490-132">[**Quellcode**][example-csproj-code]</span><span class="sxs-lookup"><span data-stu-id="1d490-132">[**Source Code**][example-csproj-code]</span></span>

<span data-ttu-id="1d490-133">Zu beachtende Änderungen:</span><span class="sxs-lookup"><span data-stu-id="1d490-133">Changes to note are:</span></span>

* <span data-ttu-id="1d490-134">Der Ersatz für *packages.config* und *\*.csproj* mit einer neuen [.NET Core *\*.csproj*][example-csproj-netcore].</span><span class="sxs-lookup"><span data-stu-id="1d490-134">Replacement of *packages.config* and *\*.csproj* with a new [.NET Core *\*.csproj*][example-csproj-netcore].</span></span> <span data-ttu-id="1d490-135">NuGet-Pakete werden mit `<PackageReference> ItemGroup` angegeben.</span><span class="sxs-lookup"><span data-stu-id="1d490-135">NuGet packages are specified with `<PackageReference> ItemGroup`.</span></span>

## <a name="keep-existing-projects-and-create-a-net-core-project"></a><span data-ttu-id="1d490-136">Behalten vorhandener Projekte und Erstellen eines .NET Core-Projekts</span><span class="sxs-lookup"><span data-stu-id="1d490-136">Keep existing projects and create a .NET Core project</span></span>

<span data-ttu-id="1d490-137">Wenn es vorhandene Projekte gibt, die ältere Frameworks als Ziel haben, empfiehlt es sich, diese Projekte unverändert zu lassen und ein .NET Core-Projekt zu verwenden, um kommende Frameworks als Ziel festzulegen.</span><span class="sxs-lookup"><span data-stu-id="1d490-137">If there are existing projects that target older frameworks, you may want to leave these projects untouched and use a .NET Core project to target future frameworks.</span></span>

<span data-ttu-id="1d490-138">![.NET Core-Projekt mit vorhandenem Projekt in anderem Ordner][example-csproj-different-folder]</span><span class="sxs-lookup"><span data-stu-id="1d490-138">![.NET Core project with existing project in different folder][example-csproj-different-folder]</span></span>

<span data-ttu-id="1d490-139">[**Quellcode**][example-csproj-different-code]</span><span class="sxs-lookup"><span data-stu-id="1d490-139">[**Source Code**][example-csproj-different-code]</span></span>

<span data-ttu-id="1d490-140">Zu beachtende Änderungen:</span><span class="sxs-lookup"><span data-stu-id="1d490-140">Changes to note are:</span></span>

* <span data-ttu-id="1d490-141">.NET Core-Projekte und vorhandene Projekte werden in separaten Ordnern gespeichert.</span><span class="sxs-lookup"><span data-stu-id="1d490-141">The .NET Core and existing projects are kept in separate folders.</span></span>
  * <span data-ttu-id="1d490-142">Projekte in separaten Ordnern zu speichern, vermeidet, dass Sie über Visual Studio 2017 verfügen müssen.</span><span class="sxs-lookup"><span data-stu-id="1d490-142">Keeping projects in separate folders avoids forcing you to have Visual Studio 2017.</span></span> <span data-ttu-id="1d490-143">Sie können eine separate Lösung erstellen, die nur die alten Projekte öffnet.</span><span class="sxs-lookup"><span data-stu-id="1d490-143">You can create a separate solution that only opens the old projects.</span></span>

## <a name="see-also"></a><span data-ttu-id="1d490-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1d490-144">See also</span></span>

* <span data-ttu-id="1d490-145">Weitere Anleitungen zum Migrieren zu .NET Core finden Sie in der [Dokumentation zum Portieren von .NET Core][porting-doc].</span><span class="sxs-lookup"><span data-stu-id="1d490-145">Please see the [.NET Core porting documentation][porting-doc] for more guidance on migrating to .NET Core.</span></span>

[porting-doc]: index.md
[example-initial-project]: media/project-structure/project.png "Vorhandenes Projekt"
[example-initial-project-code]: https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library/

[example-csproj]: media/project-structure/project.csproj.png "Erstellen einer csproj, die mehrere Frameworks als Ziel hat"
[example-csproj-code]: https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library-csproj/
[example-csproj-netcore]: https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library-csproj/src/Car/Car.csproj

[example-csproj-different-folder]: media/project-structure/project.csproj.different.png ".NET Core-Projekt mit vorhandener PLC in anderem Ordner"
[example-csproj-different-code]: https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library-csproj-keep-existing/

[option-csproj]: #replace-existing-projects-with-a-multi-targeted-net-core-project
[option-csproj-folder]: #keep-existing-projects-and-create-a-net-core-project
