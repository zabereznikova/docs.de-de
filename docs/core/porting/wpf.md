---
title: Portieren einer WPF-App zu .NET Core 3.0
description: Erfahren Sie, wie Sie eine .NET Framework Windows Presentation Foundation-Anwendung zu .NET Core 3.0 für Windows portieren.
author: Thraka
ms.author: adegeo
ms.date: 03/27/2019
ms.custom: ''
ms.openlocfilehash: 5c7e3aca0a473abb831693244d1b194985f2ef7f
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59342205"
---
# <a name="how-to-port-a-wpf-desktop-app-to-net-core"></a><span data-ttu-id="f4ffc-103">Vorgehensweise: Portieren einer WPF-Desktop-App zu .NET Core</span><span class="sxs-lookup"><span data-stu-id="f4ffc-103">How to: Port a WPF desktop app to .NET Core</span></span>

<span data-ttu-id="f4ffc-104">Dieser Artikel beschreibt, wie Sie Ihre WPF-basierte (Windows Presentation Foundation) Desktop-App von .NET Framework zu .NET Core 3.0 portieren.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-104">This article describes how to port your Windows Presentation Foundation-based (WPF) desktop app from .NET Framework to .NET Core 3.0.</span></span> <span data-ttu-id="f4ffc-105">Das .NET Core 3.0 SDK bietet Unterstützung für WPF-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-105">The .NET Core 3.0 SDK includes support for WPF applications.</span></span> <span data-ttu-id="f4ffc-106">WPF ist immer noch ein ausschließlich für Windows bestimmtes Framework und kann nur unter Windows ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-106">WPF is still a Windows-only framework and only runs on Windows.</span></span> <span data-ttu-id="f4ffc-107">In diesem Beispiel verwenden Sie das .NET Core SDK-CLI, um ein Projekt zu erstellen und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-107">This example uses the .NET Core SDK CLI to create and manage your project.</span></span>

<span data-ttu-id="f4ffc-108">In diesem Artikel werden verschiedene Namen zum Identifizieren der für die Migration verwendeten Dateitypen verwendet.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-108">In this article, various names are used to identify types of files used for migration.</span></span> <span data-ttu-id="f4ffc-109">Weil Ihre Dateien anders benannt werden, wenn Sie Ihr Projekt migrieren, gleichen Sie sie mit den unten aufgeführten Versionen ab:</span><span class="sxs-lookup"><span data-stu-id="f4ffc-109">When migrating your project, your files will be named differently, so mentally match them to the ones listed below:</span></span>

| <span data-ttu-id="f4ffc-110">Datei</span><span class="sxs-lookup"><span data-stu-id="f4ffc-110">File</span></span> | <span data-ttu-id="f4ffc-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f4ffc-111">Description</span></span> |
| ---- | ----------- |
| **<span data-ttu-id="f4ffc-112">MyApps.sln</span><span class="sxs-lookup"><span data-stu-id="f4ffc-112">MyApps.sln</span></span>** | <span data-ttu-id="f4ffc-113">Der Name der Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-113">The name of the solution file.</span></span> |
| **<span data-ttu-id="f4ffc-114">MyWPF.csproj</span><span class="sxs-lookup"><span data-stu-id="f4ffc-114">MyWPF.csproj</span></span>** | <span data-ttu-id="f4ffc-115">Der Name des zu portierenden .NET Framework WPF-Projekts.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-115">The name of the .NET Framework WPF project to port.</span></span> |
| **<span data-ttu-id="f4ffc-116">MyWPFCore.csproj</span><span class="sxs-lookup"><span data-stu-id="f4ffc-116">MyWPFCore.csproj</span></span>** | <span data-ttu-id="f4ffc-117">Der Name des neuen .NET Core-Projekts, das Sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-117">The name of the new .NET Core project you create.</span></span> |
| **<span data-ttu-id="f4ffc-118">MyAppCore.exe</span><span class="sxs-lookup"><span data-stu-id="f4ffc-118">MyAppCore.exe</span></span>** | <span data-ttu-id="f4ffc-119">Die ausführbare Datei der .NET Core WPF-App.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-119">The .NET Core WPF app executable.</span></span> |

## <a name="prerequisites"></a><span data-ttu-id="f4ffc-120">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="f4ffc-120">Prerequisites</span></span>

- <span data-ttu-id="f4ffc-121">[Visual Studio-2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) für alle Designerarbeiten, die Sie durchführen möchten.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-121">[Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) for any designer work you want to do.</span></span>

  <span data-ttu-id="f4ffc-122">Installieren Sie die folgenden Visual Studio-Workloads:</span><span class="sxs-lookup"><span data-stu-id="f4ffc-122">Install the following Visual Studio workloads:</span></span>
  - <span data-ttu-id="f4ffc-123">.NET-Desktopentwicklung</span><span class="sxs-lookup"><span data-stu-id="f4ffc-123">.NET desktop development</span></span>
  - <span data-ttu-id="f4ffc-124">Plattformübergreifende .NET-Entwicklung</span><span class="sxs-lookup"><span data-stu-id="f4ffc-124">.NET cross-platform development</span></span>

- <span data-ttu-id="f4ffc-125">Ein funktionierendes WPF-Projekt in einer Projektmappe, die ohne Probleme erstellt und ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-125">A working WPF project in a solution that builds and runs without issue.</span></span>
- <span data-ttu-id="f4ffc-126">Ihr Projekt muss in C# codiert werden.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-126">Your project must be coded in C#.</span></span> 
- <span data-ttu-id="f4ffc-127">Installieren Sie die neueste [.NET Core 3.0](https://aka.ms/netcore3download)-Vorschau.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-127">Install the latest [.NET Core 3.0](https://aka.ms/netcore3download) preview.</span></span>

>[!NOTE]
><span data-ttu-id="f4ffc-128">**Visual Studio 2017** unterstützt .NET Core 3.0-Projekte nicht.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-128">**Visual Studio 2017** doesn't support .NET Core 3.0 projects.</span></span> <span data-ttu-id="f4ffc-129">**Visual Studio 2019** unterstützt .NET Core 3.0-Projekte, aber noch nicht den Visual Designer für .NET Core 3.0-WPF-Projekte.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-129">**Visual Studio 2019** supports .NET Core 3.0 projects but doesn't yet support the visual designer for .NET Core 3.0 WPF projects.</span></span> <span data-ttu-id="f4ffc-130">Ihre Projektmappe muss ein .NET-WPF-Projekt enthalten, das seine Dateien gemeinsam mit dem .NET Core-Projekt verwendet, um den Visual Designer verwenden zu können.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-130">To use the visual designer, you must have a .NET WPF project in your solution that shares its files with the .NET Core project.</span></span>

### <a name="consider"></a><span data-ttu-id="f4ffc-131">Consider</span><span class="sxs-lookup"><span data-stu-id="f4ffc-131">Consider</span></span>

<span data-ttu-id="f4ffc-132">Wenn Sie eine .NET Framework WPF-Anwendung portieren, müssen Sie ein paar Dinge berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-132">When porting a .NET Framework WPF application, there are a few things you must consider.</span></span>

01. <span data-ttu-id="f4ffc-133">Überprüfen Sie, ob Ihre Anwendung ein guter Kandidat für die Migration ist.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-133">Check that your application is a good candidate for migration.</span></span>

    <span data-ttu-id="f4ffc-134">Verwenden Sie den [.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md), um zu bestimmen, ob Ihr Projekt zu .NET Core 3.0 migriert werden kann.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-134">Use the [.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) to determine if your project will migrate to .NET Core 3.0.</span></span> <span data-ttu-id="f4ffc-135">Wenn bei Ihrem Projekt Probleme mit .NET Core 3.0 vorliegen, können Sie diese Probleme mit dem Analyzer identifizieren.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-135">If your project has issues with .NET Core 3.0, the analyzer helps you identify those problems.</span></span>

01. <span data-ttu-id="f4ffc-136">Sie verwenden eine andere Version von WPF.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-136">You're using a different version of WPF.</span></span>

    <span data-ttu-id="f4ffc-137">Als .NET Core 3.0 Preview 1 veröffentlicht wurde, wurde WPF als Open Source auf GitHub zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-137">When .NET Core 3.0 Preview 1 was released, WPF went open-source on GitHub.</span></span> <span data-ttu-id="f4ffc-138">Der Code für .NET Core-WPF ist ein Fork der .NET Framework-WPF-Codebasis.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-138">The code for .NET Core WPF is a fork of the .NET Framework WPF code base.</span></span> <span data-ttu-id="f4ffc-139">Es ist möglich, dass einige Unterschiede bestehen, und Ihre App nicht portiert wird.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-139">It's possible some differences exist and your app won't port.</span></span>

01. <span data-ttu-id="f4ffc-140">Das [Windows Compatibility Pack][compat-pack] könnte Ihnen bei der Migration helfen.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-140">The [Windows Compatibility Pack][compat-pack] may help you migrate.</span></span>

    <span data-ttu-id="f4ffc-141">Einige APIs, die in .NET Framework verfügbar sind, sind nicht in .NET Core 3.0 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-141">Some APIs that are available in .NET Framework aren't available in .NET Core 3.0.</span></span> <span data-ttu-id="f4ffc-142">Das [Windows Compatibility Pack][compat-pack] fügt viele dieser APIs hinzu und könnte die Kompatibilität Ihrer WPF-App mit .NET Core ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-142">The [Windows Compatibility Pack][compat-pack] adds many of these APIs and may help your WPF app become compatible with .NET Core.</span></span>

01. <span data-ttu-id="f4ffc-143">Aktualisieren Sie die NuGet-Pakete, die von Ihrem Projekt verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-143">Update the NuGet packages used by your project.</span></span>

    <span data-ttu-id="f4ffc-144">Es hat sich bewährt, vor jeder Migration die neuesten Versionen der NuGet-Pakete zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-144">It's always a good practice to use the latest versions of NuGet packages before any migration.</span></span> <span data-ttu-id="f4ffc-145">Wenn Ihre Anwendung auf NuGet-Pakete verweist, aktualisieren Sie sie auf die neueste Version.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-145">If your application is referencing any NuGet packages, update them to the latest version.</span></span> <span data-ttu-id="f4ffc-146">Stellen Sie sicher, dass die Anwendung erfolgreich erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-146">Ensure your application builds successfully.</span></span> <span data-ttu-id="f4ffc-147">Wenn nach dem Upgrade Paketfehler auftreten, stufen Sie das Paket auf die neueste Version herab, die Ihren Code nicht beschädigt.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-147">After upgrading, if there are any package errors, downgrade the package to the latest version that doesn't break your code.</span></span>

01. <span data-ttu-id="f4ffc-148">Visual Studio 2019 unterstützt noch nicht den WPF-Designer für .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-148">Visual Studio 2019 doesn't yet support the WPF Designer for .NET Core 3.0</span></span>

    <span data-ttu-id="f4ffc-149">Derzeit müssen Sie Ihre vorhandene .NET Framework-WPF-Projektdatei beibehalten, wenn Sie den WPF-Designer in Visual Studio verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-149">Currently, you need to keep your existing .NET Framework WPF project file if you want to use the WPF Designer from Visual Studio.</span></span>

## <a name="create-a-new-sdk-project"></a><span data-ttu-id="f4ffc-150">Erstellen eines neues SDK-Projekts</span><span class="sxs-lookup"><span data-stu-id="f4ffc-150">Create a new SDK project</span></span>

<span data-ttu-id="f4ffc-151">Das neue .NET Core 3.0-Projekt, das Sie erstellen, muss sich in einem anderen Verzeichnis als das .NET Framework-Projekt befinden.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-151">The new .NET Core 3.0 project you create must be in a different directory from your .NET Framework project.</span></span> <span data-ttu-id="f4ffc-152">Wenn beide sich im gleichen Verzeichnis befinden, können Konflikte mit den Dateien auftreten, die im **obj**-Verzeichnis generiert werden.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-152">If they're both in the same directory, you may run into conflicts with the files that are generated in the **obj** directory.</span></span> <span data-ttu-id="f4ffc-153">In diesem Beispiel erstellen Sie ein Verzeichnis namens **MyWPFAppCore** im Verzeichnis **SolutionFolder**:</span><span class="sxs-lookup"><span data-stu-id="f4ffc-153">In this example, you'll create a directory named **MyWPFAppCore** in the **SolutionFolder** directory:</span></span>

```
SolutionFolder
├───MyApps.sln
├───MyWPFApp
│   └───MyWPF.csproj
└───MyWPFAppCore      <--- New folder for core project
```

<span data-ttu-id="f4ffc-154">Als Nächstes müssen Sie das **MyWPFCore.csproj**-Projekt im Verzeichnis **MyWPFAppCore** erstellen.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-154">Next, you need to create the **MyWPFCore.csproj** project in the **MyWPFAppCore** directory.</span></span> <span data-ttu-id="f4ffc-155">Sie können diese Datei manuell mit dem Text-Editor Ihrer Wahl erstellen.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-155">You can create this file manually by using the text editor of choice.</span></span> <span data-ttu-id="f4ffc-156">Fügen Sie folgende XML-Datei ein:</span><span class="sxs-lookup"><span data-stu-id="f4ffc-156">Paste in the following XML:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
    <UseWPF>true</UseWPF>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="f4ffc-157">Wenn Sie die Projektdatei nicht manuell erstellen möchten, können Sie Visual Studio oder .NET Core SDK zum Generieren des Projekts verwenden.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-157">If you don't want to create the project file manually, you can use Visual Studio or the .NET Core SDK to generate the project.</span></span> <span data-ttu-id="f4ffc-158">Allerdings müssen Sie alle anderen von der Projektvorlage generierten Dateien mit Ausnahme der Projektdatei löschen.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-158">However, you must delete all other files generated by the project template except for the project file.</span></span> <span data-ttu-id="f4ffc-159">Um das SDK verwenden zu können, führen Sie den folgenden Befehl im Verzeichnis **SolutionFolder** aus:</span><span class="sxs-lookup"><span data-stu-id="f4ffc-159">To use the SDK, run the following command from the **SolutionFolder** directory:</span></span>

```cli
dotnet new wpf -o MyWPFAppCore -n MyWPFCore
```

<span data-ttu-id="f4ffc-160">Nach der Erstellung von **MyWPFCore.csproj** sollte Ihre Verzeichnisstruktur wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="f4ffc-160">After you create the **MyWPFCore.csproj**, your directory structure should look like the following:</span></span>

```
SolutionFolder
├───MyApps.sln
├───MyWPFApp
│   └───MyWPF.csproj
└───MyWPFAppCore
    └───MyWPFCore.csproj
```

<span data-ttu-id="f4ffc-161">Verwenden Sie entweder Visual Studio oder die .NET Core-CLI aus dem Verzeichnis **SolutionFolder**, um das **MyWPFCore.csproj**-Projekt zu **MyApps.sln** hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="f4ffc-161">You'll want to add the **MyWPFCore.csproj** project to **MyApps.sln** with either Visual Studio or the .NET Core CLI from the **SolutionFolder** directory:</span></span>

```cli
dotnet sln add .\MyWPFAppCore\MyWPFCore.csproj
```

## <a name="fix-assembly-info-generation"></a><span data-ttu-id="f4ffc-162">Beheben des Generierens von Assemblyinformationen</span><span class="sxs-lookup"><span data-stu-id="f4ffc-162">Fix assembly info generation</span></span>

<span data-ttu-id="f4ffc-163">Windows Presentation Foundation-Projekte, die mit .NET Framework erstellt wurden, enthalten eine `AssemblyInfo.cs`-Datei, die Assemblyattribute wie z. B. die Version der zu generierenden Assembly enthält.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-163">Windows Presentation Foundation projects that were created with .NET Framework include an `AssemblyInfo.cs` file, which contains assembly attributes such as the version of the assembly to be generated.</span></span> <span data-ttu-id="f4ffc-164">Projekte im SDK-Stil generieren diese Informationen auf Grundlage der SDK-Projektdatei automatisch für Sie.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-164">SDK-style projects automatically generate this information for you based on the SDK project file.</span></span> <span data-ttu-id="f4ffc-165">Beide Typen von „Assemblyinformationen“ zu haben verursacht einen Konflikt.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-165">Having both types of "assembly info" creates a conflict.</span></span> <span data-ttu-id="f4ffc-166">Um dieses Problem zu lösen, deaktivieren Sie die automatische Generierung, sodass das Projekt Ihre vorhandene `AssemblyInfo.cs`-Datei verwenden muss.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-166">Resolve this problem by disabling automatic generation, which forces the project to use your existing `AssemblyInfo.cs` file.</span></span>

<span data-ttu-id="f4ffc-167">Drei Einstellungen müssen dem `<PropertyGroup>`-Hauptknoten hinzufügt werden.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-167">There are three settings to add to the main `<PropertyGroup>` node.</span></span> 

- **<span data-ttu-id="f4ffc-168">GenerateAssemblyInfo</span><span class="sxs-lookup"><span data-stu-id="f4ffc-168">GenerateAssemblyInfo</span></span>**\
<span data-ttu-id="f4ffc-169">Wenn Sie für diese Eigenschaft `false` festlegen, generiert sie die Assemblyattribute nicht.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-169">When you set this property to `false`, it won't generate the assembly attributes.</span></span> <span data-ttu-id="f4ffc-170">Dadurch wird der Konflikt mit der vorhandenen `AssemblyInfo.cs`-Datei aus dem .NET Framework-Projekt vermieden.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-170">This avoids the conflict with the existing `AssemblyInfo.cs` file from the .NET Framework project.</span></span>

- **<span data-ttu-id="f4ffc-171">AssemblyName</span><span class="sxs-lookup"><span data-stu-id="f4ffc-171">AssemblyName</span></span>**\
<span data-ttu-id="f4ffc-172">Der Wert dieser Eigenschaft ist die binäre Ausgabe, die erstellt wird, wenn Sie kompilieren.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-172">The value of this property is the output binary created when you compile.</span></span> <span data-ttu-id="f4ffc-173">Dem Namen muss keine Erweiterung hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-173">The name doesn't need an extension added to it.</span></span> <span data-ttu-id="f4ffc-174">Bei Verwendung von `MyCoreApp` entsteht beispielsweise `MyCoreApp.exe`.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-174">For example, using `MyCoreApp` produces `MyCoreApp.exe`.</span></span>

- **<span data-ttu-id="f4ffc-175">RootNamespace</span><span class="sxs-lookup"><span data-stu-id="f4ffc-175">RootNamespace</span></span>**\
<span data-ttu-id="f4ffc-176">Der Standardnamespace, der von Ihrem Projekt verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-176">The default namespace used by your project.</span></span> <span data-ttu-id="f4ffc-177">Dies sollte dem Standardnamespace des .NET Framework-Projekts entsprechen.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-177">This should match the default namespace of the .NET Framework project.</span></span>

<span data-ttu-id="f4ffc-178">Fügen Sie diese drei Elemente dem `<PropertyGroup>`-Knoten in der `MyWPFCore.csproj`-Datei hinzu:</span><span class="sxs-lookup"><span data-stu-id="f4ffc-178">Add these three elements to the `<PropertyGroup>` node in the `MyWPFCore.csproj` file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
    <UseWPF>true</UseWPF>

    <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
    <AssemblyName>MyCoreApp</AssemblyName>
    <RootNamespace>MyWPF</RootNamespace>
  </PropertyGroup>

</Project>
```

## <a name="add-source-code"></a><span data-ttu-id="f4ffc-179">Hinzufügen von Quellcode</span><span class="sxs-lookup"><span data-stu-id="f4ffc-179">Add source code</span></span>
<span data-ttu-id="f4ffc-180">Momentan kompiliert das **MyWPFCore.csproj**-Projekt keinen Code.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-180">Right now, the **MyWPFCore.csproj** project doesn't compile any code.</span></span> <span data-ttu-id="f4ffc-181">.NET Core-Projekte enthalten standardmäßig automatisch sämtlichen Quellcode im aktuellen Verzeichnis und allen untergeordneten Verzeichnissen.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-181">By default, .NET Core projects automatically include all source code in the current directory and any child directories.</span></span> <span data-ttu-id="f4ffc-182">Sie müssen das Projekt so konfigurieren, dass Code aus dem .NET Framework-Projekt mit einem relativen Pfad einbezogen wird.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-182">You must configure the project to include code from the .NET Framework project using a relative path.</span></span> <span data-ttu-id="f4ffc-183">Wenn Ihr .NET Framework-Projekt **RESX**-Dateien für Symbole und Ressourcen für Ihre Fenster und Steuerelemente verwendete, müssen Sie diese ebenfalls einbeziehen.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-183">If your .NET Framework project used **.resx** files for icons and resources for your windows and controls, you'll need to include those too.</span></span> 

<span data-ttu-id="f4ffc-184">Der erste `<ItemGroup>`-Knoten, den Sie zu Ihrem Projekt hinzufügen müssen, enthält die Datei **App.xaml**, die die von Ihrer App verwendete Startkonfiguration sowie die verwendeten Startressourcen darstellt.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-184">The first `<ItemGroup>` node you need to add to your project includes the **App.xaml** file that represents the startup config and resources your app uses.</span></span> <span data-ttu-id="f4ffc-185">Die Datei **App.xaml** verfügt auch über die Begleitdatei **App.xaml.cs**, die jedoch automatisch in eine andere `<ItemGroup>` aufgenommen wird.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-185">The **App.xaml** file also has an accompanying **App.xaml.cs** file, but it will be automatically included in a different `<ItemGroup>`.</span></span>

```xml
  <ItemGroup>
    <ApplicationDefinition Include="..\MyWPFApp\App.xaml">
      <Generator>MSBuild:Compile</Generator>
    </ApplicationDefinition>
  </ItemGroup>
```

<span data-ttu-id="f4ffc-186">Fügen Sie als Nächstes den folgenden `<ItemGroup>`-Knoten zu Ihrem Projekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-186">Next, add the following `<ItemGroup>` node to your project.</span></span> <span data-ttu-id="f4ffc-187">Jede Anweisung enthält ein Dateiglobmuster, das untergeordnete Verzeichnisse enthält.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-187">Each statement includes a file glob pattern that includes child directories.</span></span> <span data-ttu-id="f4ffc-188">Es enthält den Quellcode für Ihr Projekt, alle Einstellungsdateien und Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-188">It includes the source code for your project, any settings files, and any resources.</span></span> <span data-ttu-id="f4ffc-189">Das Verzeichnis **obj** wird explizit ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-189">The **obj** directory is explicitly excluded.</span></span>

```xml
  <ItemGroup>
    <Compile Include="..\MyWPFApp\**\*.cs" Exclude="..\MyWPFApp\obj\**" />
    <None Include="..\MyWPFApp\**\*.settings" />
    <EmbeddedResource Include="..\MyWPFApp\**\*.resx" />
  </ItemGroup>
```

<span data-ttu-id="f4ffc-190">Schließen Sie als Nächstes einen weiteren `<ItemGroup>`-Knoten ein, der einen `<Page>`-Eintrag für jede **XAML**-Datei in Ihrem Projekt enthält, mit Ausnahme der Datei **App.xaml**.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-190">Next, include another `<ItemGroup>` node that contains a `<Page>` entry for every **xaml** file in your project except the **App.xaml** file.</span></span> <span data-ttu-id="f4ffc-191">Diese enthalten alle Fenster, Seiten und Ressourcen im **XAML**-Format.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-191">These contain all of the windows, pages, and resources that are in **xaml** format.</span></span> <span data-ttu-id="f4ffc-192">Sie können hier kein Globmuster verwenden und müssen für jede Datei einen Eintrag hinzufügen und den verwendeten `<Generator>` angeben.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-192">You cannot use a glob pattern here and must add an entry for every file and indicate the `<Generator>` used.</span></span>

```xml
  <ItemGroup>
    <Page Include="..\MyWPFApp\MainWindow.xaml">
      <Generator>MSBuild:Compile</Generator>
    </Page>
  </ItemGroup>
```

## <a name="add-nuget-packages"></a><span data-ttu-id="f4ffc-193">Hinzufügen von NuGet-Paketen</span><span class="sxs-lookup"><span data-stu-id="f4ffc-193">Add NuGet packages</span></span>

<span data-ttu-id="f4ffc-194">Fügen Sie alle NuGet-Pakete, auf die das .NET Framework-Projekt verweist, dem .NET Core-Projekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-194">Add each NuGet package referenced by the .NET Framework project to the .NET Core project.</span></span> 

<span data-ttu-id="f4ffc-195">In den meisten Fällen verfügt Ihre .NET Framework-WPF-App über eine **packages.config**-Datei, die eine Liste aller NuGet-Pakete enthält, auf die Ihr Projekt verweist.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-195">Most likely your .NET Framework WPF app has a **packages.config** file that contains a list of all of the NuGet packages that are referenced by your project.</span></span> <span data-ttu-id="f4ffc-196">Bestimmen Sie anhand dieser Liste, welche NuGet-Pakete Sie dem .NET Core-Projekt hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-196">You can look at this list to determine which NuGet packages to add to the .NET Core project.</span></span> <span data-ttu-id="f4ffc-197">Wenn das .NET Framework-Projekt beispielsweise auf das NuGet-Paket `MahApps.Metro` verweist, fügen Sie es mithilfe von Visual Studio zum Projekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-197">For example, if the .NET Framework project references the `MahApps.Metro` NuGet package, add it to the project with Visual Studio.</span></span> <span data-ttu-id="f4ffc-198">Sie können den Paketverweis auch mit der .NET Core-CLI vom **SolutionFolder**-Verzeichnis hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="f4ffc-198">You can also add the package reference with the .NET Core CLI from the **SolutionFolder** directory:</span></span>

```cli
dotnet add .\MyWPFAppCore\MyWPFCore.csproj package MahApps.Metro -v 2.0.0-alpha0262
```

<span data-ttu-id="f4ffc-199">Der vorherige Befehl würde dem **MyWPFCore.csproj**-Projekt den folgenden NuGet-Verweis hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="f4ffc-199">The previous command would add the following NuGet reference to the **MyWPFCore.csproj** project:</span></span>

```xml
  <ItemGroup>
    <PackageReference Include="MahApps.Metro" Version="2.0.0-alpha0262" />
  </ItemGroup>
```

## <a name="problems-compiling"></a><span data-ttu-id="f4ffc-200">Probleme beim Kompilieren</span><span class="sxs-lookup"><span data-stu-id="f4ffc-200">Problems compiling</span></span>

<span data-ttu-id="f4ffc-201">Wenn beim Kompilieren Ihrer Projekte Probleme auftreten, verwenden Sie möglicherweise einige nur für Windows geeignete APIs, die in .NET Framework, aber nicht in .NET Core verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-201">If you have problems compiling your projects, you may be using some Windows-only APIs that are available in .NET Framework but not available in .NET Core.</span></span> <span data-ttu-id="f4ffc-202">Sie können versuchen, das [Windows Compatibility Pack][ compat-pack] NuGet-Paket Ihrem Projekt hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-202">You can try adding the [Windows Compatibility Pack][compat-pack] NuGet package to your project.</span></span> <span data-ttu-id="f4ffc-203">Dieses Paket kann nur auf Windows ausgeführt werden und fügt .NET Core- und .NET Standard-Projekten ungefähr 20.000 Windows-APIs hinzu.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-203">This package only runs on Windows and adds about 20,000 Windows APIs to .NET Core and .NET Standard projects.</span></span>

```cli
dotnet add .\MyWPFAppCore\MyWPFCore.csproj package Microsoft.Windows.Compatibility
```

<span data-ttu-id="f4ffc-204">Der vorherige Befehl fügt dem **MyWPFCore.csproj**-Projekt Folgendes hinzu:</span><span class="sxs-lookup"><span data-stu-id="f4ffc-204">The previous command adds the following to the **MyWPFCore.csproj** project:</span></span>

```xml
  <ItemGroup>
    <PackageReference Include="Microsoft.Windows.Compatibility" Version="2.0.1" />
  </ItemGroup>
```

## <a name="wpf-designer"></a><span data-ttu-id="f4ffc-205">WPF-Designer</span><span class="sxs-lookup"><span data-stu-id="f4ffc-205">WPF Designer</span></span>

<span data-ttu-id="f4ffc-206">Wie in diesem Artikel ausführlich beschrieben unterstützt Visual Studio 2019 in .NET Framework-Projekten nur den WPF-Designer.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-206">As detailed in this article, Visual Studio 2019 only supports the WPF Designer in .NET Framework projects.</span></span> <span data-ttu-id="f4ffc-207">Durch Erstellen eines parallelen .NET Core-Projekts können Sie Ihr Projekt mit .NET Core testen, während Sie das .NET Framework-Projekt zum Entwerfen von Formularen verwenden.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-207">By creating a side-by-side .NET Core project, you can test your project with .NET Core while you use the .NET Framework project to design forms.</span></span> <span data-ttu-id="f4ffc-208">Die Projektmappendatei enthält sowohl die .NET Framework- als auch die .NET Core-Projekte.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-208">Your solution file includes both the .NET Framework and .NET Core projects.</span></span> <span data-ttu-id="f4ffc-209">Führen Sie das Hinzufügen und Entwerfen Ihrer Formulare und Steuerelemente im .NET Framework-Projekt durch, und auf der Basis der Dateiglobmuster, die wir den .NET Core-Projekten hinzugefügt haben, wird jede neue oder geänderte Datei automatisch in die .NET Core-Projekte einbezogen.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-209">Add and design your forms and controls in the .NET Framework project, and based on the file glob patterns we added to the .NET Core projects, any new or changed files will automatically be included in the .NET Core projects.</span></span>

<span data-ttu-id="f4ffc-210">Sobald Visual Studio 2019 den WPF-Designer unterstützt, können Sie den Inhalt Ihrer .NET Core-Projektdatei kopieren und in die .NET Framework-Projektdatei einfügen.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-210">Once Visual Studio 2019 supports the WPF Designer, you can copy/paste the content of your .NET Core project file into the .NET Framework project file.</span></span> <span data-ttu-id="f4ffc-211">Löschen Sie dann die Dateiglobmuster, die mit dem `<Source>`- und `<EmbeddedResource>`-Element hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-211">Then delete the file glob patterns added with the `<Source>` and `<EmbeddedResource>` items.</span></span> <span data-ttu-id="f4ffc-212">Stellen Sie die Pfade zu jedem von Ihrer App verwendeten Projektverweis wieder her.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-212">Fix the paths to any project reference used by your app.</span></span> <span data-ttu-id="f4ffc-213">Damit wird effektiv das .NET Framework-Projekt zu einem .NET Core-Projekt heraufgestuft.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-213">This effectively upgrades the .NET Framework project to a .NET Core project.</span></span>
 
## <a name="next-steps"></a><span data-ttu-id="f4ffc-214">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="f4ffc-214">Next steps</span></span>

* <span data-ttu-id="f4ffc-215">Lesen Sie mehr über das [Windows Compatibility Pack][compat-pack].</span><span class="sxs-lookup"><span data-stu-id="f4ffc-215">Read more about the [Windows Compatibility Pack][compat-pack].</span></span>
* <span data-ttu-id="f4ffc-216">Sehen Sie sich ein [Video zum Portieren](https://www.youtube.com/watch?v=5MomsgkWkVw&list=PLS__JrkRveTMiWxG-Lv4cBwYfMQ6m2gmt) Ihres .NET Framework-WPF-Projekts zu .NET Core an.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-216">Watch a [video on porting](https://www.youtube.com/watch?v=5MomsgkWkVw&list=PLS__JrkRveTMiWxG-Lv4cBwYfMQ6m2gmt) your .NET Framework WPF project to .NET Core.</span></span>

[compat-pack]: windows-compat-pack.md
