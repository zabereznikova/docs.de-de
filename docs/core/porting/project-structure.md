---
title: Organisieren von Projekten für .NET Framework und .NET Core
description: Dieser Artikel soll Projektbesitzern dabei helfen, Ihre eigene Lösung parallel für .NET Framework und .NET Core zu kompilieren.
author: conniey
ms.date: 12/07/2018
ms.custom: seodec18
ms.openlocfilehash: 789f50ffb61b80f590a24bc45693df895b3424f7
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/04/2019
ms.locfileid: "74801928"
---
# <a name="organize-your-project-to-support-both-net-framework-and-net-core"></a><span data-ttu-id="ada9a-103">Organisieren Ihres Projekts zur Unterstützung von sowohl .NET Framework als auch .NET Core</span><span class="sxs-lookup"><span data-stu-id="ada9a-103">Organize your project to support both .NET Framework and .NET Core</span></span>

<span data-ttu-id="ada9a-104">Erfahren Sie, wie Sie eine Lösung erstellen, die .NET Framework und .NET Core parallel kompiliert.</span><span class="sxs-lookup"><span data-stu-id="ada9a-104">Learn how to create a solution that compiles for both .NET Framework and .NET Core side-by-side.</span></span> <span data-ttu-id="ada9a-105">Es gibt mehrere Optionen zum Organisieren von Projekten, um dieses Ziel zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="ada9a-105">See several options to organize projects to help you achieve this goal.</span></span> <span data-ttu-id="ada9a-106">Im Folgenden finden Sie einige Szenarios, die Sie bei der Entscheidung bedenken sollten, wie Sie Ihr Projektlayout mit .NET Core einrichten.</span><span class="sxs-lookup"><span data-stu-id="ada9a-106">Here are some typical scenarios to consider when you're deciding how to setup your project layout with .NET Core.</span></span> <span data-ttu-id="ada9a-107">Die Liste deckt möglicherweise nicht alle Punkte ab, die Sie benötigen. Sie können abhängig von den Anforderungen Ihrer Projekte priorisieren.</span><span class="sxs-lookup"><span data-stu-id="ada9a-107">The list may not cover everything you want; prioritize based on your project's needs.</span></span>

- [<span data-ttu-id="ada9a-108">**Kombinieren von vorhandenen Projekten und .NET Core-Projekten in einzelnen Projekten**</span><span class="sxs-lookup"><span data-stu-id="ada9a-108">**Combine existing projects and .NET Core projects into single projects**</span></span>](#replace-existing-projects-with-a-multi-targeted-net-core-project)

  <span data-ttu-id="ada9a-109">*Es dient folgenden Zwecken:*</span><span class="sxs-lookup"><span data-stu-id="ada9a-109">*What this is good for:*</span></span>
  - <span data-ttu-id="ada9a-110">Vereinfachen Ihres Buildprozesses durch Kompilieren eines einzelnen Projekts statt mehrerer Projekte, die alle eine andere Version von .NET Framework oder eine andere Plattform als Ziel haben.</span><span class="sxs-lookup"><span data-stu-id="ada9a-110">Simplifying your build process by compiling a single project rather than compiling multiple projects, each targeting a different .NET Framework version or platform.</span></span>
  - <span data-ttu-id="ada9a-111">Vereinfachen der Verwaltung von Quelldateien für mehrfachzielorientierte Projekte, da Sie eine einzelne Projektdatei verwalten müssen.</span><span class="sxs-lookup"><span data-stu-id="ada9a-111">Simplifying source file management for multi-targeted projects because you must manage a single project file.</span></span> <span data-ttu-id="ada9a-112">Beim Hinzufügen/Entfernen von Quelldateien müssen Sie diese bei den Alternativen manuell mit Ihren Projekten synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="ada9a-112">When adding/removing source files, the alternatives require you to manually sync these with your other projects.</span></span>
  - <span data-ttu-id="ada9a-113">Einfaches Generieren eines NuGet-Pakets zum Verbrauch.</span><span class="sxs-lookup"><span data-stu-id="ada9a-113">Easily generating a NuGet package for consumption.</span></span>
  - <span data-ttu-id="ada9a-114">Ermöglicht das Schreiben von Code für eine bestimmte .NET Framework-Version in Ihren Bibliotheken mithilfe von Compileranweisungen.</span><span class="sxs-lookup"><span data-stu-id="ada9a-114">Allows you to write code for a specific .NET Framework version in your libraries through the use of compiler directives.</span></span>

  <span data-ttu-id="ada9a-115">*Nicht unterstützte Szenarios:*</span><span class="sxs-lookup"><span data-stu-id="ada9a-115">*Unsupported scenarios:*</span></span>
  - <span data-ttu-id="ada9a-116">Entwickler benötigen Visual Studio 2017 oder höher, um vorhandene Projekte zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="ada9a-116">Requires developers to use Visual Studio 2017 or a later version to open existing projects.</span></span> <span data-ttu-id="ada9a-117">Zur Unterstützung von älteren Versionen von Visual Studio ist es eine bessere Option, [Ihre Projektdateien in unterschiedlichen Ordnern zu speichern](#support-vs).</span><span class="sxs-lookup"><span data-stu-id="ada9a-117">To support older versions of Visual Studio, [keeping your project files in different folders](#support-vs) is a better option.</span></span>

- <a name="support-vs"></a><span data-ttu-id="ada9a-118">[**Trennen vorhandener und neuer .NET Core-Projekte**](#keep-existing-projects-and-create-a-net-core-project)</span><span class="sxs-lookup"><span data-stu-id="ada9a-118">[**Keep existing projects and new .NET Core projects separate**](#keep-existing-projects-and-create-a-net-core-project)</span></span>

  <span data-ttu-id="ada9a-119">*Es dient folgenden Zwecken:*</span><span class="sxs-lookup"><span data-stu-id="ada9a-119">*What this is good for:*</span></span>
  - <span data-ttu-id="ada9a-120">Unterstützung der Entwicklung in bestehenden Projekten für Entwickler und Mitwirkende, die möglicherweise nicht über Visual Studio 2017 oder eine höhere Version verfügen.</span><span class="sxs-lookup"><span data-stu-id="ada9a-120">Supporting development on existing projects for developers and contributors who may not have Visual Studio 2017 or a later version.</span></span>
  - <span data-ttu-id="ada9a-121">Minimieren der Möglichkeit, neue Probleme in vorhandenen Projekten zu erstellen, da in diesen Projekten keine Codeänderung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="ada9a-121">Decreasing the possibility of creating new bugs in existing projects because no code churn is required in those projects.</span></span>

## <a name="example"></a><span data-ttu-id="ada9a-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ada9a-122">Example</span></span>

<span data-ttu-id="ada9a-123">Betrachten Sie das folgende Repository:</span><span class="sxs-lookup"><span data-stu-id="ada9a-123">Consider the repository below:</span></span>

![Vorhandenes Projekt](./media/project-structure/existing-project-structure.png)

[<span data-ttu-id="ada9a-125">**Quellcode**</span><span class="sxs-lookup"><span data-stu-id="ada9a-125">**Source Code**</span></span>](https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library/)

<span data-ttu-id="ada9a-126">Im Folgenden sind verschiedene Möglichkeiten beschrieben, Unterstützung für .NET Core für dieses Repository hinzuzufügen. Dies ist abhängig von den Einschränkungen und der Komplexität bestehender Projekte.</span><span class="sxs-lookup"><span data-stu-id="ada9a-126">The following describes several ways to add support for .NET Core for this repository depending on the constraints and complexity of the existing projects.</span></span>

## <a name="replace-existing-projects-with-a-multi-targeted-net-core-project"></a><span data-ttu-id="ada9a-127">Ersetzen von vorhandenen Projekten mit mehrfachzielorientierten .NET Core Projekten</span><span class="sxs-lookup"><span data-stu-id="ada9a-127">Replace existing projects with a multi-targeted .NET Core project</span></span>

<span data-ttu-id="ada9a-128">Organisieren Sie das Repository neu, sodass alle vorhandenen *\*.csproj*-Dateien entfernt werden, und eine einzelne *\*.csproj*-Datei erstellt wird, die mehrere Frameworks als Ziel hat.</span><span class="sxs-lookup"><span data-stu-id="ada9a-128">Reorganize the repository so that any existing *\*.csproj* files are removed and a single *\*.csproj* file is created that targets multiple frameworks.</span></span> <span data-ttu-id="ada9a-129">Dies ist eine hervorragende Option, da ein einzelnes Projekt für andere Frameworks kompilieren kann.</span><span class="sxs-lookup"><span data-stu-id="ada9a-129">This is a great option because a single project is able to compile for different frameworks.</span></span> <span data-ttu-id="ada9a-130">Außerdem kann die Option verschiedene Kompilierungsoptionen und Abhängigkeiten pro Zielframework behandeln.</span><span class="sxs-lookup"><span data-stu-id="ada9a-130">It also has the power to handle different compilation options and dependencies per targeted framework.</span></span>

![CSPROJ-Datei für mehrere Zielframeworks erstellen](./media/project-structure/multi-targeted-project.png)

[<span data-ttu-id="ada9a-132">**Quellcode**</span><span class="sxs-lookup"><span data-stu-id="ada9a-132">**Source Code**</span></span>](https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library-csproj/)

<span data-ttu-id="ada9a-133">Zu beachtende Änderungen:</span><span class="sxs-lookup"><span data-stu-id="ada9a-133">Changes to note are:</span></span>

- <span data-ttu-id="ada9a-134">Der Ersatz für *packages.config* und *\*.csproj* mit einer neuen [.NET Core *\*.csproj*](https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library-csproj/src/Car/Car.csproj).</span><span class="sxs-lookup"><span data-stu-id="ada9a-134">Replacement of *packages.config* and *\*.csproj* with a new [.NET Core *\*.csproj*](https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library-csproj/src/Car/Car.csproj).</span></span> <span data-ttu-id="ada9a-135">NuGet-Pakete werden mit `<PackageReference> ItemGroup` angegeben.</span><span class="sxs-lookup"><span data-stu-id="ada9a-135">NuGet packages are specified with `<PackageReference> ItemGroup`.</span></span>

## <a name="keep-existing-projects-and-create-a-net-core-project"></a><span data-ttu-id="ada9a-136">Behalten vorhandener Projekte und Erstellen eines .NET Core-Projekts</span><span class="sxs-lookup"><span data-stu-id="ada9a-136">Keep existing projects and create a .NET Core project</span></span>

<span data-ttu-id="ada9a-137">Wenn es vorhandene Projekte gibt, die ältere Frameworks als Ziel haben, empfiehlt es sich, diese Projekte unverändert zu lassen und ein .NET Core-Projekt zu verwenden, um kommende Frameworks als Ziel festzulegen.</span><span class="sxs-lookup"><span data-stu-id="ada9a-137">If there are existing projects that target older frameworks, you may want to leave these projects untouched and use a .NET Core project to target future frameworks.</span></span>

![.NET Core-Projekt mit vorhandenem Projekt in anderem Ordner](./media/project-structure/separate-projects-same-source.png)

[<span data-ttu-id="ada9a-139">**Quellcode**</span><span class="sxs-lookup"><span data-stu-id="ada9a-139">**Source Code**</span></span>](https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library-csproj-keep-existing/)

<span data-ttu-id="ada9a-140">Zu beachtende Änderungen:</span><span class="sxs-lookup"><span data-stu-id="ada9a-140">Changes to note are:</span></span>

- <span data-ttu-id="ada9a-141">.NET Core-Projekte und vorhandene Projekte werden in separaten Ordnern gespeichert.</span><span class="sxs-lookup"><span data-stu-id="ada9a-141">The .NET Core and existing projects are kept in separate folders.</span></span>
  - <span data-ttu-id="ada9a-142">Durch das Speichern der Projekte in separaten Ordnern ist es nicht mehr notwendig, Visual Studio 2017 oder eine spätere Version zu besitzen.</span><span class="sxs-lookup"><span data-stu-id="ada9a-142">Keeping projects in separate folders avoids forcing you to have Visual Studio 2017 or later versions.</span></span> <span data-ttu-id="ada9a-143">Sie können eine separate Lösung erstellen, die nur die alten Projekte öffnet.</span><span class="sxs-lookup"><span data-stu-id="ada9a-143">You can create a separate solution that only opens the old projects.</span></span>

## <a name="see-also"></a><span data-ttu-id="ada9a-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ada9a-144">See also</span></span>

- [<span data-ttu-id="ada9a-145">Dokumentation zur .NET Core-Portierung</span><span class="sxs-lookup"><span data-stu-id="ada9a-145">.NET Core porting documentation</span></span>](index.md)
