---
title: Portieren einer WPF-App zu .NET Core 3.0
description: Erfahren Sie, wie Sie eine .NET Framework Windows Presentation Foundation-Anwendung zu .NET Core 3.0 für Windows portieren.
author: Thraka
ms.author: adegeo
ms.date: 03/27/2019
ms.custom: ''
ms.openlocfilehash: 1528e578a978de38998b3f3f4b7beb72ff7422d4
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117064"
---
# <a name="how-to-port-a-wpf-desktop-app-to-net-core"></a><span data-ttu-id="48506-103">Gewusst wie: Portieren einer WPF-Desktop-App zu .NET Core</span><span class="sxs-lookup"><span data-stu-id="48506-103">How to: Port a WPF desktop app to .NET Core</span></span>

<span data-ttu-id="48506-104">Dieser Artikel beschreibt, wie Sie Ihre WPF-basierte (Windows Presentation Foundation) Desktop-App von .NET Framework zu .NET Core 3.0 portieren.</span><span class="sxs-lookup"><span data-stu-id="48506-104">This article describes how to port your Windows Presentation Foundation-based (WPF) desktop app from .NET Framework to .NET Core 3.0.</span></span> <span data-ttu-id="48506-105">Das .NET Core 3.0 SDK bietet Unterstützung für WPF-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="48506-105">The .NET Core 3.0 SDK includes support for WPF applications.</span></span> <span data-ttu-id="48506-106">WPF ist immer noch ein ausschließlich für Windows bestimmtes Framework und kann nur unter Windows ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="48506-106">WPF is still a Windows-only framework and only runs on Windows.</span></span> <span data-ttu-id="48506-107">In diesem Beispiel verwenden Sie das .NET Core SDK-CLI, um ein Projekt zu erstellen und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="48506-107">This example uses the .NET Core SDK CLI to create and manage your project.</span></span>

<span data-ttu-id="48506-108">In diesem Artikel werden verschiedene Namen zum Identifizieren der für die Migration verwendeten Dateitypen verwendet.</span><span class="sxs-lookup"><span data-stu-id="48506-108">In this article, various names are used to identify types of files used for migration.</span></span> <span data-ttu-id="48506-109">Weil Ihre Dateien anders benannt werden, wenn Sie Ihr Projekt migrieren, gleichen Sie sie mit den unten aufgeführten Versionen ab:</span><span class="sxs-lookup"><span data-stu-id="48506-109">When migrating your project, your files will be named differently, so mentally match them to the ones listed below:</span></span>

| <span data-ttu-id="48506-110">Datei</span><span class="sxs-lookup"><span data-stu-id="48506-110">File</span></span> | <span data-ttu-id="48506-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="48506-111">Description</span></span> |
| ---- | ----------- |
| <span data-ttu-id="48506-112">**MyApps.sln**</span><span class="sxs-lookup"><span data-stu-id="48506-112">**MyApps.sln**</span></span> | <span data-ttu-id="48506-113">Der Name der Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="48506-113">The name of the solution file.</span></span> |
| <span data-ttu-id="48506-114">**MyWPF.csproj**</span><span class="sxs-lookup"><span data-stu-id="48506-114">**MyWPF.csproj**</span></span> | <span data-ttu-id="48506-115">Der Name des zu portierenden .NET Framework WPF-Projekts.</span><span class="sxs-lookup"><span data-stu-id="48506-115">The name of the .NET Framework WPF project to port.</span></span> |
| <span data-ttu-id="48506-116">**MyWPFCore.csproj**</span><span class="sxs-lookup"><span data-stu-id="48506-116">**MyWPFCore.csproj**</span></span> | <span data-ttu-id="48506-117">Der Name des neuen .NET Core-Projekts, das Sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="48506-117">The name of the new .NET Core project you create.</span></span> |
| <span data-ttu-id="48506-118">**MyAppCore.exe**</span><span class="sxs-lookup"><span data-stu-id="48506-118">**MyAppCore.exe**</span></span> | <span data-ttu-id="48506-119">Die ausführbare Datei der .NET Core WPF-App.</span><span class="sxs-lookup"><span data-stu-id="48506-119">The .NET Core WPF app executable.</span></span> |

>[!IMPORTANT]
><span data-ttu-id="48506-120">Obwohl in diesem Artikel C# als Zielsprache verwendet wird, sind die Schritte für VB.NET identisch. Die einzige Ausnahme ist hierbei, dass VB.NET jeweils *VBPROJ*- und *VB*-Dateien anstelle von *CSPROJ*- und *CS*-Dateien verwendet.</span><span class="sxs-lookup"><span data-stu-id="48506-120">Even though this article uses C# as the target language, the steps are the same for VB.NET, except that VB.NET uses *.vbproj* and *.vb* files instead of *.csproj* and *.cs* files, respectively.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="48506-121">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="48506-121">Prerequisites</span></span>

- <span data-ttu-id="48506-122">[Visual Studio-2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) für alle Designerarbeiten, die Sie durchführen möchten.</span><span class="sxs-lookup"><span data-stu-id="48506-122">[Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) for any designer work you want to do.</span></span>

  <span data-ttu-id="48506-123">Installieren Sie die folgenden Visual Studio-Workloads:</span><span class="sxs-lookup"><span data-stu-id="48506-123">Install the following Visual Studio workloads:</span></span>
  - <span data-ttu-id="48506-124">.NET-Desktopentwicklung</span><span class="sxs-lookup"><span data-stu-id="48506-124">.NET desktop development</span></span>
  - <span data-ttu-id="48506-125">Plattformübergreifende .NET-Entwicklung</span><span class="sxs-lookup"><span data-stu-id="48506-125">.NET cross-platform development</span></span>

- <span data-ttu-id="48506-126">Ein funktionierendes WPF-Projekt in einer Projektmappe, die ohne Probleme erstellt und ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="48506-126">A working WPF project in a solution that builds and runs without issue.</span></span>
- <span data-ttu-id="48506-127">Installieren Sie die neueste [.NET Core 3.0](https://aka.ms/netcore3download)-Vorschau.</span><span class="sxs-lookup"><span data-stu-id="48506-127">Install the latest [.NET Core 3.0](https://aka.ms/netcore3download) preview.</span></span>

>[!NOTE]
><span data-ttu-id="48506-128">**Visual Studio 2017** unterstützt .NET Core 3.0-Projekte nicht.</span><span class="sxs-lookup"><span data-stu-id="48506-128">**Visual Studio 2017** doesn't support .NET Core 3.0 projects.</span></span> <span data-ttu-id="48506-129">**Visual Studio 2019** unterstützt .NET Core 3.0-Projekte, bietet jedoch eingeschränkte Unterstützung für den visuellen .NET Core-WPF-Designer.</span><span class="sxs-lookup"><span data-stu-id="48506-129">**Visual Studio 2019** supports .NET Core 3.0 projects but has limited support for the .NET Core WPF visual designer.</span></span> <span data-ttu-id="48506-130">Ihre Projektmappe muss ein .NET Framework-WPF-Projekt enthalten, das seine Dateien gemeinsam mit dem .NET Core-Projekt verwendet, um einen vollständig unterstützten visuellen Designer verwenden zu können.</span><span class="sxs-lookup"><span data-stu-id="48506-130">To use a fully-supported visual designer, you must have a .NET Framework WPF project in your solution that shares its files with the .NET Core project.</span></span>

### <a name="consider"></a><span data-ttu-id="48506-131">Consider</span><span class="sxs-lookup"><span data-stu-id="48506-131">Consider</span></span>

<span data-ttu-id="48506-132">Wenn Sie eine .NET Framework WPF-Anwendung portieren, müssen Sie ein paar Dinge berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="48506-132">When porting a .NET Framework WPF application, there are a few things you must consider.</span></span>

01. <span data-ttu-id="48506-133">Überprüfen Sie, ob Ihre Anwendung ein guter Kandidat für die Migration ist.</span><span class="sxs-lookup"><span data-stu-id="48506-133">Check that your application is a good candidate for migration.</span></span>

    <span data-ttu-id="48506-134">Verwenden Sie den [.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md), um zu bestimmen, ob Ihr Projekt zu .NET Core 3.0 migriert werden kann.</span><span class="sxs-lookup"><span data-stu-id="48506-134">Use the [.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) to determine if your project will migrate to .NET Core 3.0.</span></span> <span data-ttu-id="48506-135">Wenn bei Ihrem Projekt Probleme mit .NET Core 3.0 vorliegen, können Sie diese Probleme mit dem Analyzer identifizieren.</span><span class="sxs-lookup"><span data-stu-id="48506-135">If your project has issues with .NET Core 3.0, the analyzer helps you identify those problems.</span></span>

01. <span data-ttu-id="48506-136">Sie verwenden eine andere Version von WPF.</span><span class="sxs-lookup"><span data-stu-id="48506-136">You're using a different version of WPF.</span></span>

    <span data-ttu-id="48506-137">Als .NET Core 3.0 Preview 1 veröffentlicht wurde, wurde WPF als Open Source auf GitHub zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="48506-137">When .NET Core 3.0 Preview 1 was released, WPF went open-source on GitHub.</span></span> <span data-ttu-id="48506-138">Der Code für .NET Core-WPF ist ein Fork der .NET Framework-WPF-Codebasis.</span><span class="sxs-lookup"><span data-stu-id="48506-138">The code for .NET Core WPF is a fork of the .NET Framework WPF code base.</span></span> <span data-ttu-id="48506-139">Es ist möglich, dass einige Unterschiede bestehen, und Ihre App nicht portiert wird.</span><span class="sxs-lookup"><span data-stu-id="48506-139">It's possible some differences exist and your app won't port.</span></span>

01. <span data-ttu-id="48506-140">Das [Windows Compatibility Pack][compat-pack] könnte Ihnen bei der Migration helfen.</span><span class="sxs-lookup"><span data-stu-id="48506-140">The [Windows Compatibility Pack][compat-pack] may help you migrate.</span></span>

    <span data-ttu-id="48506-141">Einige APIs, die in .NET Framework verfügbar sind, sind nicht in .NET Core 3.0 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="48506-141">Some APIs that are available in .NET Framework aren't available in .NET Core 3.0.</span></span> <span data-ttu-id="48506-142">Das [Windows Compatibility Pack][compat-pack] fügt viele dieser APIs hinzu und könnte die Kompatibilität Ihrer WPF-App mit .NET Core ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="48506-142">The [Windows Compatibility Pack][compat-pack] adds many of these APIs and may help your WPF app become compatible with .NET Core.</span></span>

01. <span data-ttu-id="48506-143">Aktualisieren Sie die NuGet-Pakete, die von Ihrem Projekt verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="48506-143">Update the NuGet packages used by your project.</span></span>

    <span data-ttu-id="48506-144">Es hat sich bewährt, vor jeder Migration die neuesten Versionen der NuGet-Pakete zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="48506-144">It's always a good practice to use the latest versions of NuGet packages before any migration.</span></span> <span data-ttu-id="48506-145">Wenn Ihre Anwendung auf NuGet-Pakete verweist, aktualisieren Sie sie auf die neueste Version.</span><span class="sxs-lookup"><span data-stu-id="48506-145">If your application is referencing any NuGet packages, update them to the latest version.</span></span> <span data-ttu-id="48506-146">Stellen Sie sicher, dass die Anwendung erfolgreich erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="48506-146">Ensure your application builds successfully.</span></span> <span data-ttu-id="48506-147">Wenn nach dem Upgrade Paketfehler auftreten, stufen Sie das Paket auf die neueste Version herab, die Ihren Code nicht beschädigt.</span><span class="sxs-lookup"><span data-stu-id="48506-147">After upgrading, if there are any package errors, downgrade the package to the latest version that doesn't break your code.</span></span>

01. <span data-ttu-id="48506-148">Visual Studio 2019 unterstützt noch nicht den WPF-Designer für .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="48506-148">Visual Studio 2019 doesn't yet support the WPF Designer for .NET Core 3.0</span></span>

    <span data-ttu-id="48506-149">Derzeit müssen Sie Ihre vorhandene .NET Framework-WPF-Projektdatei beibehalten, wenn Sie den WPF-Designer in Visual Studio verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="48506-149">Currently, you need to keep your existing .NET Framework WPF project file if you want to use the WPF Designer from Visual Studio.</span></span>

## <a name="create-a-new-sdk-project"></a><span data-ttu-id="48506-150">Erstellen eines neues SDK-Projekts</span><span class="sxs-lookup"><span data-stu-id="48506-150">Create a new SDK project</span></span>

<span data-ttu-id="48506-151">Das neue .NET Core 3.0-Projekt, das Sie erstellen, muss sich in einem anderen Verzeichnis als das .NET Framework-Projekt befinden.</span><span class="sxs-lookup"><span data-stu-id="48506-151">The new .NET Core 3.0 project you create must be in a different directory from your .NET Framework project.</span></span> <span data-ttu-id="48506-152">Wenn beide sich im gleichen Verzeichnis befinden, können Konflikte mit den Dateien auftreten, die im **obj**-Verzeichnis generiert werden.</span><span class="sxs-lookup"><span data-stu-id="48506-152">If they're both in the same directory, you may run into conflicts with the files that are generated in the **obj** directory.</span></span> <span data-ttu-id="48506-153">In diesem Beispiel erstellen Sie ein Verzeichnis namens **MyWPFAppCore** im Verzeichnis **SolutionFolder**:</span><span class="sxs-lookup"><span data-stu-id="48506-153">In this example, you'll create a directory named **MyWPFAppCore** in the **SolutionFolder** directory:</span></span>

```
SolutionFolder
├───MyApps.sln
├───MyWPFApp
│   └───MyWPF.csproj
└───MyWPFAppCore      <--- New folder for core project
```

<span data-ttu-id="48506-154">Als Nächstes müssen Sie das **MyWPFCore.csproj**-Projekt im Verzeichnis **MyWPFAppCore** erstellen.</span><span class="sxs-lookup"><span data-stu-id="48506-154">Next, you need to create the **MyWPFCore.csproj** project in the **MyWPFAppCore** directory.</span></span> <span data-ttu-id="48506-155">Sie können diese Datei manuell mit dem Text-Editor Ihrer Wahl erstellen.</span><span class="sxs-lookup"><span data-stu-id="48506-155">You can create this file manually by using the text editor of choice.</span></span> <span data-ttu-id="48506-156">Fügen Sie folgende XML-Datei ein:</span><span class="sxs-lookup"><span data-stu-id="48506-156">Paste in the following XML:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
    <UseWPF>true</UseWPF>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="48506-157">Wenn Sie die Projektdatei nicht manuell erstellen möchten, können Sie Visual Studio oder .NET Core SDK zum Generieren des Projekts verwenden.</span><span class="sxs-lookup"><span data-stu-id="48506-157">If you don't want to create the project file manually, you can use Visual Studio or the .NET Core SDK to generate the project.</span></span> <span data-ttu-id="48506-158">Allerdings müssen Sie alle anderen von der Projektvorlage generierten Dateien mit Ausnahme der Projektdatei löschen.</span><span class="sxs-lookup"><span data-stu-id="48506-158">However, you must delete all other files generated by the project template except for the project file.</span></span> <span data-ttu-id="48506-159">Um das SDK verwenden zu können, führen Sie den folgenden Befehl im Verzeichnis **SolutionFolder** aus:</span><span class="sxs-lookup"><span data-stu-id="48506-159">To use the SDK, run the following command from the **SolutionFolder** directory:</span></span>

```dotnetcli
dotnet new wpf -o MyWPFAppCore -n MyWPFCore
```

<span data-ttu-id="48506-160">Nach der Erstellung von **MyWPFCore.csproj** sollte Ihre Verzeichnisstruktur wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="48506-160">After you create the **MyWPFCore.csproj**, your directory structure should look like the following:</span></span>

```
SolutionFolder
├───MyApps.sln
├───MyWPFApp
│   └───MyWPF.csproj
└───MyWPFAppCore
    └───MyWPFCore.csproj
```

<span data-ttu-id="48506-161">Verwenden Sie entweder Visual Studio oder die .NET Core-CLI aus dem Verzeichnis **SolutionFolder**, um das **MyWPFCore.csproj**-Projekt zu **MyApps.sln** hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="48506-161">You'll want to add the **MyWPFCore.csproj** project to **MyApps.sln** with either Visual Studio or the .NET Core CLI from the **SolutionFolder** directory:</span></span>

```dotnetcli
dotnet sln add .\MyWPFAppCore\MyWPFCore.csproj
```

## <a name="fix-assembly-info-generation"></a><span data-ttu-id="48506-162">Beheben des Generierens von Assemblyinformationen</span><span class="sxs-lookup"><span data-stu-id="48506-162">Fix assembly info generation</span></span>

<span data-ttu-id="48506-163">Windows Presentation Foundation-Projekte, die mit .NET Framework erstellt wurden, enthalten eine `AssemblyInfo.cs`-Datei, die Assemblyattribute wie z. B. die Version der zu generierenden Assembly enthält.</span><span class="sxs-lookup"><span data-stu-id="48506-163">Windows Presentation Foundation projects that were created with .NET Framework include an `AssemblyInfo.cs` file, which contains assembly attributes such as the version of the assembly to be generated.</span></span> <span data-ttu-id="48506-164">Projekte im SDK-Stil generieren diese Informationen auf Grundlage der SDK-Projektdatei automatisch für Sie.</span><span class="sxs-lookup"><span data-stu-id="48506-164">SDK-style projects automatically generate this information for you based on the SDK project file.</span></span> <span data-ttu-id="48506-165">Beide Typen von „Assemblyinformationen“ zu haben verursacht einen Konflikt.</span><span class="sxs-lookup"><span data-stu-id="48506-165">Having both types of "assembly info" creates a conflict.</span></span> <span data-ttu-id="48506-166">Um dieses Problem zu lösen, deaktivieren Sie die automatische Generierung, sodass das Projekt Ihre vorhandene `AssemblyInfo.cs`-Datei verwenden muss.</span><span class="sxs-lookup"><span data-stu-id="48506-166">Resolve this problem by disabling automatic generation, which forces the project to use your existing `AssemblyInfo.cs` file.</span></span>

<span data-ttu-id="48506-167">Drei Einstellungen müssen dem `<PropertyGroup>`-Hauptknoten hinzufügt werden.</span><span class="sxs-lookup"><span data-stu-id="48506-167">There are three settings to add to the main `<PropertyGroup>` node.</span></span> 

- <span data-ttu-id="48506-168">**GenerateAssemblyInfo**</span><span class="sxs-lookup"><span data-stu-id="48506-168">**GenerateAssemblyInfo**</span></span>\
<span data-ttu-id="48506-169">Wenn Sie für diese Eigenschaft `false` festlegen, generiert sie die Assemblyattribute nicht.</span><span class="sxs-lookup"><span data-stu-id="48506-169">When you set this property to `false`, it won't generate the assembly attributes.</span></span> <span data-ttu-id="48506-170">Dadurch wird der Konflikt mit der vorhandenen `AssemblyInfo.cs`-Datei aus dem .NET Framework-Projekt vermieden.</span><span class="sxs-lookup"><span data-stu-id="48506-170">This avoids the conflict with the existing `AssemblyInfo.cs` file from the .NET Framework project.</span></span>

- <span data-ttu-id="48506-171">**AssemblyName**</span><span class="sxs-lookup"><span data-stu-id="48506-171">**AssemblyName**</span></span>\
<span data-ttu-id="48506-172">Der Wert dieser Eigenschaft ist die binäre Ausgabe, die erstellt wird, wenn Sie kompilieren.</span><span class="sxs-lookup"><span data-stu-id="48506-172">The value of this property is the output binary created when you compile.</span></span> <span data-ttu-id="48506-173">Dem Namen muss keine Erweiterung hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="48506-173">The name doesn't need an extension added to it.</span></span> <span data-ttu-id="48506-174">Bei Verwendung von `MyCoreApp` entsteht beispielsweise `MyCoreApp.exe`.</span><span class="sxs-lookup"><span data-stu-id="48506-174">For example, using `MyCoreApp` produces `MyCoreApp.exe`.</span></span>

- <span data-ttu-id="48506-175">**RootNamespace**</span><span class="sxs-lookup"><span data-stu-id="48506-175">**RootNamespace**</span></span>\
<span data-ttu-id="48506-176">Der Standardnamespace, der von Ihrem Projekt verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="48506-176">The default namespace used by your project.</span></span> <span data-ttu-id="48506-177">Dies sollte dem Standardnamespace des .NET Framework-Projekts entsprechen.</span><span class="sxs-lookup"><span data-stu-id="48506-177">This should match the default namespace of the .NET Framework project.</span></span>

<span data-ttu-id="48506-178">Fügen Sie diese drei Elemente dem `<PropertyGroup>`-Knoten in der `MyWPFCore.csproj`-Datei hinzu:</span><span class="sxs-lookup"><span data-stu-id="48506-178">Add these three elements to the `<PropertyGroup>` node in the `MyWPFCore.csproj` file:</span></span>

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

## <a name="add-source-code"></a><span data-ttu-id="48506-179">Hinzufügen von Quellcode</span><span class="sxs-lookup"><span data-stu-id="48506-179">Add source code</span></span>
<span data-ttu-id="48506-180">Momentan kompiliert das **MyWPFCore.csproj**-Projekt keinen Code.</span><span class="sxs-lookup"><span data-stu-id="48506-180">Right now, the **MyWPFCore.csproj** project doesn't compile any code.</span></span> <span data-ttu-id="48506-181">.NET Core-Projekte enthalten standardmäßig automatisch sämtlichen Quellcode im aktuellen Verzeichnis und allen untergeordneten Verzeichnissen.</span><span class="sxs-lookup"><span data-stu-id="48506-181">By default, .NET Core projects automatically include all source code in the current directory and any child directories.</span></span> <span data-ttu-id="48506-182">Sie müssen das Projekt so konfigurieren, dass Code aus dem .NET Framework-Projekt mit einem relativen Pfad einbezogen wird.</span><span class="sxs-lookup"><span data-stu-id="48506-182">You must configure the project to include code from the .NET Framework project using a relative path.</span></span> <span data-ttu-id="48506-183">Wenn Ihr .NET Framework-Projekt **RESX**-Dateien für Symbole und Ressourcen für Ihre Fenster und Steuerelemente verwendete, müssen Sie diese ebenfalls einbeziehen.</span><span class="sxs-lookup"><span data-stu-id="48506-183">If your .NET Framework project used **.resx** files for icons and resources for your windows and controls, you'll need to include those too.</span></span> 

<span data-ttu-id="48506-184">Der erste `<ItemGroup>`-Knoten, den Sie zu Ihrem Projekt hinzufügen müssen, enthält die Datei **App.xaml**, die die von Ihrer App verwendete Startkonfiguration sowie die verwendeten Startressourcen darstellt.</span><span class="sxs-lookup"><span data-stu-id="48506-184">The first `<ItemGroup>` node you need to add to your project includes the **App.xaml** file that represents the startup config and resources your app uses.</span></span> <span data-ttu-id="48506-185">Die Datei **App.xaml** verfügt auch über die Begleitdatei **App.xaml.cs**, die jedoch automatisch in eine andere `<ItemGroup>` aufgenommen wird.</span><span class="sxs-lookup"><span data-stu-id="48506-185">The **App.xaml** file also has an accompanying **App.xaml.cs** file, but it will be automatically included in a different `<ItemGroup>`.</span></span>

```xml
  <ItemGroup>
    <ApplicationDefinition Include="..\MyWPFApp\App.xaml">
      <Generator>MSBuild:Compile</Generator>
    </ApplicationDefinition>
  </ItemGroup>
```

<span data-ttu-id="48506-186">Fügen Sie als Nächstes den folgenden `<ItemGroup>`-Knoten zu Ihrem Projekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="48506-186">Next, add the following `<ItemGroup>` node to your project.</span></span> <span data-ttu-id="48506-187">Jede Anweisung enthält ein Dateiglobmuster, das untergeordnete Verzeichnisse enthält.</span><span class="sxs-lookup"><span data-stu-id="48506-187">Each statement includes a file glob pattern that includes child directories.</span></span> <span data-ttu-id="48506-188">Es enthält den Quellcode für Ihr Projekt, alle Einstellungsdateien und Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="48506-188">It includes the source code for your project, any settings files, and any resources.</span></span> <span data-ttu-id="48506-189">Das Verzeichnis **obj** wird explizit ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="48506-189">The **obj** directory is explicitly excluded.</span></span>

```xml
  <ItemGroup>
    <Compile Include="..\MyWPFApp\**\*.cs" Exclude="..\MyWPFApp\obj\**" />
    <None Include="..\MyWPFApp\**\*.settings" />
    <EmbeddedResource Include="..\MyWPFApp\**\*.resx" />
  </ItemGroup>
```

<span data-ttu-id="48506-190">Schließen Sie als Nächstes einen weiteren `<ItemGroup>`-Knoten ein, der einen `<Page>`-Eintrag für jede **XAML**-Datei in Ihrem Projekt enthält, mit Ausnahme der Datei **App.xaml**.</span><span class="sxs-lookup"><span data-stu-id="48506-190">Next, include another `<ItemGroup>` node that contains a `<Page>` entry for every **xaml** file in your project except the **App.xaml** file.</span></span> <span data-ttu-id="48506-191">Diese enthalten alle Fenster, Seiten und Ressourcen im **XAML**-Format.</span><span class="sxs-lookup"><span data-stu-id="48506-191">These contain all of the windows, pages, and resources that are in **xaml** format.</span></span> <span data-ttu-id="48506-192">Sie können hier kein Globmuster verwenden und müssen für jede Datei einen Eintrag hinzufügen und den verwendeten `<Generator>` angeben.</span><span class="sxs-lookup"><span data-stu-id="48506-192">You cannot use a glob pattern here and must add an entry for every file and indicate the `<Generator>` used.</span></span>

```xml
  <ItemGroup>
    <Page Include="..\MyWPFApp\MainWindow.xaml">
      <Generator>MSBuild:Compile</Generator>
    </Page>
  </ItemGroup>
```

## <a name="add-nuget-packages"></a><span data-ttu-id="48506-193">Hinzufügen von NuGet-Paketen</span><span class="sxs-lookup"><span data-stu-id="48506-193">Add NuGet packages</span></span>

<span data-ttu-id="48506-194">Fügen Sie alle NuGet-Pakete, auf die das .NET Framework-Projekt verweist, dem .NET Core-Projekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="48506-194">Add each NuGet package referenced by the .NET Framework project to the .NET Core project.</span></span> 

<span data-ttu-id="48506-195">In den meisten Fällen verfügt Ihre .NET Framework-WPF-App über eine **packages.config**-Datei, die eine Liste aller NuGet-Pakete enthält, auf die Ihr Projekt verweist.</span><span class="sxs-lookup"><span data-stu-id="48506-195">Most likely your .NET Framework WPF app has a **packages.config** file that contains a list of all of the NuGet packages that are referenced by your project.</span></span> <span data-ttu-id="48506-196">Bestimmen Sie anhand dieser Liste, welche NuGet-Pakete Sie dem .NET Core-Projekt hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="48506-196">You can look at this list to determine which NuGet packages to add to the .NET Core project.</span></span> <span data-ttu-id="48506-197">Wenn das .NET Framework-Projekt beispielsweise auf das NuGet-Paket `MahApps.Metro` verweist, fügen Sie es mithilfe von Visual Studio zum Projekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="48506-197">For example, if the .NET Framework project references the `MahApps.Metro` NuGet package, add it to the project with Visual Studio.</span></span> <span data-ttu-id="48506-198">Sie können den Paketverweis auch mit der .NET Core-CLI vom **SolutionFolder**-Verzeichnis hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="48506-198">You can also add the package reference with the .NET Core CLI from the **SolutionFolder** directory:</span></span>

```dotnetcli
dotnet add .\MyWPFAppCore\MyWPFCore.csproj package MahApps.Metro -v 2.0.0-alpha0262
```

<span data-ttu-id="48506-199">Der vorherige Befehl würde dem **MyWPFCore.csproj**-Projekt den folgenden NuGet-Verweis hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="48506-199">The previous command would add the following NuGet reference to the **MyWPFCore.csproj** project:</span></span>

```xml
  <ItemGroup>
    <PackageReference Include="MahApps.Metro" Version="2.0.0-alpha0262" />
  </ItemGroup>
```

## <a name="problems-compiling"></a><span data-ttu-id="48506-200">Probleme beim Kompilieren</span><span class="sxs-lookup"><span data-stu-id="48506-200">Problems compiling</span></span>

<span data-ttu-id="48506-201">Wenn beim Kompilieren Ihrer Projekte Probleme auftreten, verwenden Sie möglicherweise einige nur für Windows geeignete APIs, die in .NET Framework, aber nicht in .NET Core verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="48506-201">If you have problems compiling your projects, you may be using some Windows-only APIs that are available in .NET Framework but not available in .NET Core.</span></span> <span data-ttu-id="48506-202">Sie können versuchen, das [Windows Compatibility Pack][compat-pack] NuGet-Paket Ihrem Projekt hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="48506-202">You can try adding the [Windows Compatibility Pack][compat-pack] NuGet package to your project.</span></span> <span data-ttu-id="48506-203">Dieses Paket kann nur auf Windows ausgeführt werden und fügt .NET Core- und .NET Standard-Projekten ungefähr 20.000 Windows-APIs hinzu.</span><span class="sxs-lookup"><span data-stu-id="48506-203">This package only runs on Windows and adds about 20,000 Windows APIs to .NET Core and .NET Standard projects.</span></span>

```dotnetcli
dotnet add .\MyWPFAppCore\MyWPFCore.csproj package Microsoft.Windows.Compatibility
```

<span data-ttu-id="48506-204">Der vorherige Befehl fügt dem **MyWPFCore.csproj**-Projekt Folgendes hinzu:</span><span class="sxs-lookup"><span data-stu-id="48506-204">The previous command adds the following to the **MyWPFCore.csproj** project:</span></span>

```xml
  <ItemGroup>
    <PackageReference Include="Microsoft.Windows.Compatibility" Version="2.0.1" />
  </ItemGroup>
```

## <a name="wpf-designer"></a><span data-ttu-id="48506-205">WPF-Designer</span><span class="sxs-lookup"><span data-stu-id="48506-205">WPF Designer</span></span>

<span data-ttu-id="48506-206">Wie in diesem Artikel ausführlich beschrieben unterstützt Visual Studio 2019 in .NET Framework-Projekten nur den WPF-Designer.</span><span class="sxs-lookup"><span data-stu-id="48506-206">As detailed in this article, Visual Studio 2019 only supports the WPF Designer in .NET Framework projects.</span></span> <span data-ttu-id="48506-207">Durch Erstellen eines parallelen .NET Core-Projekts können Sie Ihr Projekt mit .NET Core testen, während Sie das .NET Framework-Projekt zum Entwerfen von Formularen verwenden.</span><span class="sxs-lookup"><span data-stu-id="48506-207">By creating a side-by-side .NET Core project, you can test your project with .NET Core while you use the .NET Framework project to design forms.</span></span> <span data-ttu-id="48506-208">Die Projektmappendatei enthält sowohl die .NET Framework- als auch die .NET Core-Projekte.</span><span class="sxs-lookup"><span data-stu-id="48506-208">Your solution file includes both the .NET Framework and .NET Core projects.</span></span> <span data-ttu-id="48506-209">Führen Sie das Hinzufügen und Entwerfen Ihrer Formulare und Steuerelemente im .NET Framework-Projekt durch, und auf der Basis der Dateiglobmuster, die wir den .NET Core-Projekten hinzugefügt haben, wird jede neue oder geänderte Datei automatisch in die .NET Core-Projekte einbezogen.</span><span class="sxs-lookup"><span data-stu-id="48506-209">Add and design your forms and controls in the .NET Framework project, and based on the file glob patterns we added to the .NET Core projects, any new or changed files will automatically be included in the .NET Core projects.</span></span>

<span data-ttu-id="48506-210">Sobald Visual Studio 2019 den WPF-Designer unterstützt, können Sie den Inhalt Ihrer .NET Core-Projektdatei kopieren und in die .NET Framework-Projektdatei einfügen.</span><span class="sxs-lookup"><span data-stu-id="48506-210">Once Visual Studio 2019 supports the WPF Designer, you can copy/paste the content of your .NET Core project file into the .NET Framework project file.</span></span> <span data-ttu-id="48506-211">Löschen Sie dann die Dateiglobmuster, die mit dem `<Source>`- und `<EmbeddedResource>`-Element hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="48506-211">Then delete the file glob patterns added with the `<Source>` and `<EmbeddedResource>` items.</span></span> <span data-ttu-id="48506-212">Stellen Sie die Pfade zu jedem von Ihrer App verwendeten Projektverweis wieder her.</span><span class="sxs-lookup"><span data-stu-id="48506-212">Fix the paths to any project reference used by your app.</span></span> <span data-ttu-id="48506-213">Damit wird effektiv das .NET Framework-Projekt zu einem .NET Core-Projekt heraufgestuft.</span><span class="sxs-lookup"><span data-stu-id="48506-213">This effectively upgrades the .NET Framework project to a .NET Core project.</span></span>

## <a name="next-steps"></a><span data-ttu-id="48506-214">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="48506-214">Next steps</span></span>

- <span data-ttu-id="48506-215">Lesen Sie mehr über das [Windows Compatibility Pack][compat-pack].</span><span class="sxs-lookup"><span data-stu-id="48506-215">Read more about the [Windows Compatibility Pack][compat-pack].</span></span>
- <span data-ttu-id="48506-216">Sehen Sie sich ein [Video zum Portieren](https://www.youtube.com/watch?v=5MomsgkWkVw&list=PLS__JrkRveTMiWxG-Lv4cBwYfMQ6m2gmt) Ihres .NET Framework-WPF-Projekts zu .NET Core an.</span><span class="sxs-lookup"><span data-stu-id="48506-216">Watch a [video on porting](https://www.youtube.com/watch?v=5MomsgkWkVw&list=PLS__JrkRveTMiWxG-Lv4cBwYfMQ6m2gmt) your .NET Framework WPF project to .NET Core.</span></span>

[compat-pack]: windows-compat-pack.md
