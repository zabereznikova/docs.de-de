---
title: Portieren einer Windows Forms-App zu .NET Core
description: Hier erfahren Sie, wie Sie eine .NET Framework Windows Forms-Anwendung zu .NET Core für Windows portieren.
author: Thraka
ms.author: adegeo
ms.date: 01/24/2020
ms.openlocfilehash: efa73428c816eddc00c62c2275d3457c92284388
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83206135"
---
# <a name="how-to-port-a-windows-forms-desktop-app-to-net-core"></a><span data-ttu-id="ea1c7-103">Portieren einer Windows Forms-Desktop-App zu .NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="ea1c7-103">How to port a Windows Forms desktop app to .NET Core</span></span>

<span data-ttu-id="ea1c7-104">Dieser Artikel beschreibt, wie Sie Ihre Desktop-App auf Windows Forms-Basis von .NET Framework zu .NET Core 3.0 oder höher portieren.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-104">This article describes how to port your Windows Forms-based desktop app from .NET Framework to .NET Core 3.0 or later.</span></span> <span data-ttu-id="ea1c7-105">Das .NET Core 3.0 SDK bietet Unterstützung für Windows Forms-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-105">The .NET Core 3.0 SDK includes support for Windows Forms applications.</span></span> <span data-ttu-id="ea1c7-106">Windows Forms ist immer noch ein ausschließlich für Windows bestimmtes Framework und kann nur unter Windows ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-106">Windows Forms is still a Windows-only framework and only runs on Windows.</span></span> <span data-ttu-id="ea1c7-107">In diesem Beispiel verwenden Sie das .NET Core SDK-CLI, um ein Projekt zu erstellen und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-107">This example uses the .NET Core SDK CLI to create and manage your project.</span></span>

<span data-ttu-id="ea1c7-108">In diesem Artikel werden verschiedene Namen zum Identifizieren der für die Migration verwendeten Dateitypen verwendet.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-108">In this article, various names are used to identify types of files used for migration.</span></span> <span data-ttu-id="ea1c7-109">Weil Ihre Dateien anders benannt werden, wenn Sie Ihr Projekt migrieren, gleichen Sie sie mit den unten aufgeführten Versionen ab:</span><span class="sxs-lookup"><span data-stu-id="ea1c7-109">When migrating your project, your files will be named differently, so mentally match them to the ones listed below:</span></span>

| <span data-ttu-id="ea1c7-110">Datei</span><span class="sxs-lookup"><span data-stu-id="ea1c7-110">File</span></span> | <span data-ttu-id="ea1c7-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ea1c7-111">Description</span></span> |
| ---- | ----------- |
| <span data-ttu-id="ea1c7-112">**MyApps.sln**</span><span class="sxs-lookup"><span data-stu-id="ea1c7-112">**MyApps.sln**</span></span> | <span data-ttu-id="ea1c7-113">Der Name der Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-113">The name of the solution file.</span></span> |
| <span data-ttu-id="ea1c7-114">**MyForms.csproj**</span><span class="sxs-lookup"><span data-stu-id="ea1c7-114">**MyForms.csproj**</span></span> | <span data-ttu-id="ea1c7-115">Der Name des zu portierenden .NET Framework Windows Forms-Projekts.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-115">The name of the .NET Framework Windows Forms project to port.</span></span> |
| <span data-ttu-id="ea1c7-116">**MyFormsCore.csproj**</span><span class="sxs-lookup"><span data-stu-id="ea1c7-116">**MyFormsCore.csproj**</span></span> | <span data-ttu-id="ea1c7-117">Der Name des neuen .NET Core-Projekts, das Sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-117">The name of the new .NET Core project you create.</span></span> |
| <span data-ttu-id="ea1c7-118">**MyAppCore.exe**</span><span class="sxs-lookup"><span data-stu-id="ea1c7-118">**MyAppCore.exe**</span></span> | <span data-ttu-id="ea1c7-119">Die ausführbare .NET Core-Windows Forms-App.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-119">The .NET Core Windows Forms app executable.</span></span> |

## <a name="prerequisites"></a><span data-ttu-id="ea1c7-120">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="ea1c7-120">Prerequisites</span></span>

- <span data-ttu-id="ea1c7-121">[Visual Studio 2019 16.5 Preview 1](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=community&ch=pre&rel=16) oder höher für alle Aufgaben, die Sie mit dem Designer durchführen möchten.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-121">[Visual Studio 2019 16.5 Preview 1](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=community&ch=pre&rel=16) or later for any designer work you want to do.</span></span> <span data-ttu-id="ea1c7-122">Sie sollten ein Update auf die neueste [Vorschauversion von Visual Studio](https://visualstudio.microsoft.com/vs/preview/) durchführen.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-122">We recommend to update to the latest [Preview version of Visual Studio](https://visualstudio.microsoft.com/vs/preview/).</span></span>

  <span data-ttu-id="ea1c7-123">Installieren Sie die folgenden Visual Studio-Workloads:</span><span class="sxs-lookup"><span data-stu-id="ea1c7-123">Install the following Visual Studio workloads:</span></span>
  
  - <span data-ttu-id="ea1c7-124">.NET-Desktopentwicklung</span><span class="sxs-lookup"><span data-stu-id="ea1c7-124">.NET desktop development</span></span>
  - <span data-ttu-id="ea1c7-125">Plattformübergreifende .NET Core-Entwicklung</span><span class="sxs-lookup"><span data-stu-id="ea1c7-125">.NET Core cross-platform development</span></span>

- <span data-ttu-id="ea1c7-126">Ein funktionierendes Windows Forms-Projekt in einer Projektmappe, die ohne Probleme erstellt und ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-126">A working Windows Forms project in a solution that builds and runs without issue.</span></span>
- <span data-ttu-id="ea1c7-127">Ein in C# programmiertes Projekt.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-127">A project coded in C#.</span></span>

> [!NOTE]
> <span data-ttu-id="ea1c7-128">.NET Core 3.0-Projekte werden nur in **Visual Studio 2019** oder einer höheren Version unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-128">.NET Core 3.0 projects are only supported in **Visual Studio 2019** or a later version.</span></span> <span data-ttu-id="ea1c7-129">Ab **Visual Studio 2019 16.5 Preview 1** wird auch der .NET Core-Windows Forms-Designer unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-129">Starting with **Visual Studio 2019 version 16.5 Preview 1**, the .NET Core Windows Forms designer is also supported.</span></span>
>
> <span data-ttu-id="ea1c7-130">Um den Designer zu aktivieren, wechseln Sie zu **Extras** > **Optionen** > **Umgebung** > **Vorschaufeatures**, und wählen Sie Option **Use the preview Windows Forms designer for .NET Core apps** (Vorschauversion des Windows Forms-Designers für .NET Core-Apps verwenden) aus.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-130">To enable the designer, go to **Tools** > **Options** > **Environment** > **Preview Features** and select the **Use the preview Windows Forms designer for .NET Core apps** option.</span></span>

### <a name="consider"></a><span data-ttu-id="ea1c7-131">Consider</span><span class="sxs-lookup"><span data-stu-id="ea1c7-131">Consider</span></span>

<span data-ttu-id="ea1c7-132">Wenn Sie eine .NET Framework Windows Forms-Anwendung portieren, müssen Sie ein paar Dinge berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-132">When porting a .NET Framework Windows Forms application, there are a few things you must consider.</span></span>

01. <span data-ttu-id="ea1c7-133">Überprüfen Sie, ob Ihre Anwendung ein guter Kandidat für die Migration ist.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-133">Check that your application is a good candidate for migration.</span></span>

    <span data-ttu-id="ea1c7-134">Verwenden Sie den [.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md), um zu bestimmen, ob Ihr Projekt zu .NET Core 3.0 migriert werden kann.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-134">Use the [.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) to determine if your project will migrate to .NET Core 3.0.</span></span> <span data-ttu-id="ea1c7-135">Wenn bei Ihrem Projekt Probleme mit .NET Core 3.0 vorliegen, können Sie diese Probleme mit dem Analyzer identifizieren.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-135">If your project has issues with .NET Core 3.0, the analyzer helps you identify those problems.</span></span>

01. <span data-ttu-id="ea1c7-136">Sie verwenden eine andere Version von Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-136">You're using a different version of Windows Forms.</span></span>

    <span data-ttu-id="ea1c7-137">Als .NET Core 3.0 Preview 1 veröffentlicht wurde, wurde Windows Forms als Open Source auf GitHub zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-137">When .NET Core 3.0 Preview 1 was released, Windows Forms went open source on GitHub.</span></span> <span data-ttu-id="ea1c7-138">Der Code für .NET Core-Windows Forms ist ein Fork der .NET Framework-Windows Forms-Codebasis.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-138">The code for .NET Core Windows Forms is a fork of the .NET Framework Windows Forms codebase.</span></span> <span data-ttu-id="ea1c7-139">Es ist möglich, dass einige Unterschiede bestehen, und Ihre App nicht portiert wird.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-139">It's possible some differences exist and your app won't port.</span></span>

01. <span data-ttu-id="ea1c7-140">Das [Windows Compatibility Pack][compat-pack] könnte Ihnen bei der Migration helfen.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-140">The [Windows Compatibility Pack][compat-pack] may help you migrate.</span></span>

    <span data-ttu-id="ea1c7-141">Einige APIs, die in .NET Framework verfügbar sind, sind nicht in .NET Core 3.0 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-141">Some APIs that are available in .NET Framework aren't available in .NET Core 3.0.</span></span> <span data-ttu-id="ea1c7-142">Das [Windows Compatibility Pack][compat-pack] fügt viele dieser APIs hinzu und könnte zur Kompatibilität Ihrer Windows Forms-App mit .NET Core beitragen.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-142">The [Windows Compatibility Pack][compat-pack] adds many of these APIs and may help your Windows Forms app become compatible with .NET Core.</span></span>

01. <span data-ttu-id="ea1c7-143">Aktualisieren Sie die NuGet-Pakete, die von Ihrem Projekt verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-143">Update the NuGet packages used by your project.</span></span>

    <span data-ttu-id="ea1c7-144">Es hat sich bewährt, vor jeder Migration die neuesten Versionen der NuGet-Pakete zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-144">It's always a good practice to use the latest versions of NuGet packages before any migration.</span></span> <span data-ttu-id="ea1c7-145">Wenn Ihre Anwendung auf NuGet-Pakete verweist, aktualisieren Sie sie auf die neueste Version.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-145">If your application is referencing any NuGet packages, update them to the latest version.</span></span> <span data-ttu-id="ea1c7-146">Stellen Sie sicher, dass die Anwendung erfolgreich erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-146">Ensure your application builds successfully.</span></span> <span data-ttu-id="ea1c7-147">Wenn nach dem Upgrade Paketfehler auftreten, stufen Sie das Paket auf die neueste Version herab, die Ihren Code nicht beschädigt.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-147">After upgrading, if there are any package errors, downgrade the package to the latest version that doesn't break your code.</span></span>

## <a name="create-a-new-sdk-project"></a><span data-ttu-id="ea1c7-148">Erstellen eines neues SDK-Projekts</span><span class="sxs-lookup"><span data-stu-id="ea1c7-148">Create a new SDK project</span></span>

<span data-ttu-id="ea1c7-149">Das neue .NET Core 3.0-Projekt, das Sie erstellen, muss sich in einem anderen Verzeichnis als das .NET Framework-Projekt befinden.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-149">The new .NET Core 3.0 project you create must be in a different directory from your .NET Framework project.</span></span> <span data-ttu-id="ea1c7-150">Wenn beide sich im gleichen Verzeichnis befinden, können Konflikte mit den Dateien auftreten, die im **obj**-Verzeichnis generiert werden.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-150">If they're both in the same directory, you may run into conflicts with the files that are generated in the **obj** directory.</span></span> <span data-ttu-id="ea1c7-151">In diesem Beispiel erstellen wir ein Verzeichnis namens **MyFormsAppCore** im Verzeichnis **SolutionFolder**:</span><span class="sxs-lookup"><span data-stu-id="ea1c7-151">In this example, we'll create a directory named **MyFormsAppCore** in the **SolutionFolder** directory:</span></span>

```
SolutionFolder
├───MyApps.sln
├───MyFormsApp
│   └───MyForms.csproj
└───MyFormsAppCore      <--- New folder for core project
```

<span data-ttu-id="ea1c7-152">Als Nächstes müssen Sie das **MyFormsCore.csproj**-Projekt im Verzeichnis **MyFormsAppCore** erstellen.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-152">Next, you need to create the **MyFormsCore.csproj** project in the **MyFormsAppCore** directory.</span></span> <span data-ttu-id="ea1c7-153">Sie können diese Datei manuell mit dem Text-Editor Ihrer Wahl erstellen.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-153">You can create this file manually by using the text editor of choice.</span></span> <span data-ttu-id="ea1c7-154">Fügen Sie folgende XML-Datei ein:</span><span class="sxs-lookup"><span data-stu-id="ea1c7-154">Paste in the following XML:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
    <UseWindowsForms>true</UseWindowsForms>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="ea1c7-155">Wenn Sie die Projektdatei nicht manuell erstellen möchten, können Sie Visual Studio oder .NET Core SDK zum Generieren des Projekts verwenden.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-155">If you don't want to create the project file manually, you can use Visual Studio or the .NET Core SDK to generate the project.</span></span> <span data-ttu-id="ea1c7-156">Allerdings müssen Sie alle anderen von der Projektvorlage generierten Dateien mit Ausnahme der Projektdatei löschen.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-156">However, you must delete all other files generated by the project template except for the project file.</span></span> <span data-ttu-id="ea1c7-157">Um das SDK verwenden zu können, führen Sie den folgenden Befehl im Verzeichnis **SolutionFolder** aus:</span><span class="sxs-lookup"><span data-stu-id="ea1c7-157">To use the SDK, run the following command from the **SolutionFolder** directory:</span></span>

```dotnetcli
dotnet new winforms -o MyFormsAppCore -n MyFormsCore
```

<span data-ttu-id="ea1c7-158">Nach der Erstellung von **MyFormsCore.csproj** sollte Ihre Verzeichnisstruktur wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="ea1c7-158">After you create the **MyFormsCore.csproj**, your directory structure should look like the following:</span></span>

```
SolutionFolder
├───MyApps.sln
├───MyFormsApp
│   └───MyForms.csproj
└───MyFormsAppCore
    └───MyFormsCore.csproj
```

<span data-ttu-id="ea1c7-159">Fügen Sie das **MyFormsCore.csproj**-Projekt zu **MyApps.sln** hinzu, und verwenden Sie entweder Visual Studio oder die .NET Core-CLI aus dem **SolutionFolder**-Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="ea1c7-159">Add the **MyFormsCore.csproj** project to **MyApps.sln** with either Visual Studio or the .NET Core CLI from the **SolutionFolder** directory:</span></span>

```dotnetcli
dotnet sln add .\MyFormsAppCore\MyFormsCore.csproj
```

## <a name="fix-assembly-info-generation"></a><span data-ttu-id="ea1c7-160">Beheben des Generierens von Assemblyinformationen</span><span class="sxs-lookup"><span data-stu-id="ea1c7-160">Fix assembly info generation</span></span>

<span data-ttu-id="ea1c7-161">Windows Forms-Projekte, die mit .NET Framework erstellt wurden, enthalten eine `AssemblyInfo.cs`-Datei, die Assemblyattribute wie z.B. die Version der zu generierenden Assembly enthält.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-161">Windows Forms projects that were created with .NET Framework include an `AssemblyInfo.cs` file, which contains assembly attributes such as the version of the assembly to be generated.</span></span> <span data-ttu-id="ea1c7-162">Projekte im SDK-Stil generieren diese Informationen auf Grundlage der SDK-Projektdatei automatisch für Sie.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-162">SDK-style projects automatically generate this information for you based on the SDK project file.</span></span> <span data-ttu-id="ea1c7-163">Beide Typen von „Assemblyinformationen“ zu haben verursacht einen Konflikt.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-163">Having both types of "assembly info" creates a conflict.</span></span> <span data-ttu-id="ea1c7-164">Um dieses Problem zu lösen, deaktivieren Sie die automatische Generierung, sodass das Projekt Ihre vorhandene `AssemblyInfo.cs`-Datei verwenden muss.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-164">Resolve this problem by disabling automatic generation, which forces the project to use your existing `AssemblyInfo.cs` file.</span></span>

<span data-ttu-id="ea1c7-165">Drei Einstellungen müssen dem `<PropertyGroup>`-Hauptknoten hinzufügt werden.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-165">There are three settings to add to the main `<PropertyGroup>` node.</span></span>

- <span data-ttu-id="ea1c7-166">**GenerateAssemblyInfo**</span><span class="sxs-lookup"><span data-stu-id="ea1c7-166">**GenerateAssemblyInfo**</span></span>\
<span data-ttu-id="ea1c7-167">Wenn Sie für diese Eigenschaft `false` festlegen, generiert sie die Assemblyattribute nicht.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-167">When you set this property to `false`, it won't generate the assembly attributes.</span></span> <span data-ttu-id="ea1c7-168">Dadurch wird der Konflikt mit der vorhandenen `AssemblyInfo.cs`-Datei aus dem .NET Framework-Projekt vermieden.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-168">This avoids the conflict with the existing `AssemblyInfo.cs` file from the .NET Framework project.</span></span>

- <span data-ttu-id="ea1c7-169">**AssemblyName**</span><span class="sxs-lookup"><span data-stu-id="ea1c7-169">**AssemblyName**</span></span>\
<span data-ttu-id="ea1c7-170">Der Wert dieser Eigenschaft ist die binäre Ausgabe, die erstellt wird, wenn Sie kompilieren.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-170">The value of this property is the output binary created when you compile.</span></span> <span data-ttu-id="ea1c7-171">Dem Namen muss keine Erweiterung hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-171">The name doesn't need an extension added to it.</span></span> <span data-ttu-id="ea1c7-172">Bei Verwendung von `MyCoreApp` entsteht beispielsweise `MyCoreApp.exe`.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-172">For example, using `MyCoreApp` produces `MyCoreApp.exe`.</span></span>

- <span data-ttu-id="ea1c7-173">**RootNamespace**</span><span class="sxs-lookup"><span data-stu-id="ea1c7-173">**RootNamespace**</span></span>\
<span data-ttu-id="ea1c7-174">Der Standardnamespace, der von Ihrem Projekt verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-174">The default namespace used by your project.</span></span> <span data-ttu-id="ea1c7-175">Dies sollte dem Standardnamespace des .NET Framework-Projekts entsprechen.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-175">This should match the default namespace of the .NET Framework project.</span></span>

<span data-ttu-id="ea1c7-176">Fügen Sie diese drei Elemente dem `<PropertyGroup>`-Knoten in der `MyFormsCore.csproj`-Datei hinzu:</span><span class="sxs-lookup"><span data-stu-id="ea1c7-176">Add these three elements to the `<PropertyGroup>` node in the `MyFormsCore.csproj` file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
    <UseWindowsForms>true</UseWindowsForms>

    <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
    <AssemblyName>MyCoreApp</AssemblyName>
    <RootNamespace>WindowsFormsApp1</RootNamespace>
  </PropertyGroup>

</Project>
```

## <a name="add-source-code"></a><span data-ttu-id="ea1c7-177">Hinzufügen von Quellcode</span><span class="sxs-lookup"><span data-stu-id="ea1c7-177">Add source code</span></span>

<span data-ttu-id="ea1c7-178">Momentan kompiliert das **MyFormsCore.csproj**-Projekt keinen Code.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-178">Right now, the **MyFormsCore.csproj** project doesn't compile any code.</span></span> <span data-ttu-id="ea1c7-179">.NET Core-Projekte enthalten standardmäßig automatisch sämtlichen Quellcode im aktuellen Verzeichnis und allen untergeordneten Verzeichnissen.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-179">By default, .NET Core projects automatically include all source code in the current directory and any child directories.</span></span> <span data-ttu-id="ea1c7-180">Sie müssen das Projekt so konfigurieren, dass Code aus dem .NET Framework-Projekt mit einem relativen Pfad einbezogen wird.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-180">You must configure the project to include code from the .NET Framework project using a relative path.</span></span> <span data-ttu-id="ea1c7-181">Wenn Ihr .NET Framework-Projekt **RESX**-Dateien für Symbole und Ressourcen für Ihre Formulare verwendete, müssen Sie diese ebenfalls einbeziehen.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-181">If your .NET Framework project used **.resx** files for icons and resources for your forms, you'll need to include those too.</span></span>

<span data-ttu-id="ea1c7-182">Fügen Sie den folgenden `<ItemGroup>`-Knoten Ihrem Projekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-182">Add the following `<ItemGroup>` node to your project.</span></span> <span data-ttu-id="ea1c7-183">Jede Anweisung enthält ein Dateiglobmuster, das untergeordnete Verzeichnisse enthält.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-183">Each statement includes a file glob pattern that includes child directories.</span></span>

```xml
  <ItemGroup>
    <Compile Include="..\MyFormsApp\**\*.cs" />
    <EmbeddedResource Include="..\MyFormsApp\**\*.resx" />
  </ItemGroup>
```

<span data-ttu-id="ea1c7-184">Alternativ können Sie einen `<Compile>`- oder `<EmbeddedResource>`-Eintrag für jede Datei in Ihrem .NET Framework-Projekt erstellen.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-184">Alternatively, you can create a `<Compile>` or `<EmbeddedResource>` entry for each file in your .NET Framework project.</span></span>

## <a name="add-nuget-packages"></a><span data-ttu-id="ea1c7-185">Hinzufügen von NuGet-Paketen</span><span class="sxs-lookup"><span data-stu-id="ea1c7-185">Add NuGet packages</span></span>

<span data-ttu-id="ea1c7-186">Fügen Sie alle NuGet-Pakete, auf die das .NET Framework-Projekt verweist, dem .NET Core-Projekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-186">Add each NuGet package referenced by the .NET Framework project to the .NET Core project.</span></span>

<span data-ttu-id="ea1c7-187">In den meisten Fällen verfügt Ihre .NET Framework-Windows Forms-App über eine **packages.config**-Datei, die eine Liste aller NuGet-Pakete enthält, auf die Ihr Projekt verweist.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-187">Most likely your .NET Framework Windows Forms app has a **packages.config** file that contains a list of all of the NuGet packages that are referenced by your project.</span></span> <span data-ttu-id="ea1c7-188">Bestimmen Sie anhand dieser Liste, welche NuGet-Pakete Sie dem .NET Core-Projekt hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-188">You can look at this list to determine which NuGet packages to add to the .NET Core project.</span></span> <span data-ttu-id="ea1c7-189">Wenn das .NET Framework-Projekt z.B. auf die `MetroFramework`-, `MetroFramework.Design`- und `MetroFramework.Fonts`-NuGet-Pakete verwies, fügen Sie entweder mit Visual Studio oder der .NET Core-CLI vom **SolutionFolder**-Verzeichnis aus jede dem Projekt hinzu:</span><span class="sxs-lookup"><span data-stu-id="ea1c7-189">For example, if the .NET Framework project referenced the `MetroFramework`, `MetroFramework.Design`, and `MetroFramework.Fonts` NuGet packages, add each to the project with either Visual Studio or the .NET Core CLI from the **SolutionFolder** directory:</span></span>

```dotnetcli
dotnet add .\MyFormsAppCore\MyFormsCore.csproj package MetroFramework
dotnet add .\MyFormsAppCore\MyFormsCore.csproj package MetroFramework.Design
dotnet add .\MyFormsAppCore\MyFormsCore.csproj package MetroFramework.Fonts
```

<span data-ttu-id="ea1c7-190">Die zuvor eingegebenen Befehle würden die folgenden NuGet-Verweise dem **MyFormsCore.csproj**-Projekt hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="ea1c7-190">The previous commands would add the following NuGet references to the **MyFormsCore.csproj** project:</span></span>

```xml
  <ItemGroup>
    <PackageReference Include="MetroFramework" Version="1.2.0.3" />
    <PackageReference Include="MetroFramework.Design" Version="1.2.0.3" />
    <PackageReference Include="MetroFramework.Fonts" Version="1.2.0.3" />
  </ItemGroup>
```

## <a name="port-control-libraries"></a><span data-ttu-id="ea1c7-191">Portieren von Steuerelementbibliotheken</span><span class="sxs-lookup"><span data-stu-id="ea1c7-191">Port control libraries</span></span>

<span data-ttu-id="ea1c7-192">Wenn Sie ein Windows Forms-Steuerelemente-Bibliotheksprojekt portieren müssen, sind die Anweisungen mit Ausnahme von ein paar Einstellungen mit dem Portieren eines .NET Framework-Windows Forms-App-Projekts identisch.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-192">If you have a Windows Forms Controls library project to port, the directions are the same as porting a .NET Framework Windows Forms app project, except for a few settings.</span></span> <span data-ttu-id="ea1c7-193">Anstatt eine ausführbare Datei zu kompilieren, kompilieren Sie in eine Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-193">And instead of compiling to an executable, you compile to a library.</span></span> <span data-ttu-id="ea1c7-194">Der Unterschied zwischen dem ausführbaren Projekt und dem Bibliotheksprojekt ist abgesehen von den Pfaden für die Dateiglobs, die Ihren Quellcode enthalten, minimal.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-194">The difference between the executable project and the library project, besides paths for the file globs that include your source code, is minimal.</span></span>

<span data-ttu-id="ea1c7-195">Erweitern Sie mithilfe des vorherigen Schrittbeispiels, mit welchen Projekten und Dateien wir arbeiten.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-195">Using the previous step's example, lets expand what projects and files we're working with.</span></span>

| <span data-ttu-id="ea1c7-196">Datei</span><span class="sxs-lookup"><span data-stu-id="ea1c7-196">File</span></span> | <span data-ttu-id="ea1c7-197">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ea1c7-197">Description</span></span> |
| ---- | ----------- |
| <span data-ttu-id="ea1c7-198">**MyApps.sln**</span><span class="sxs-lookup"><span data-stu-id="ea1c7-198">**MyApps.sln**</span></span> | <span data-ttu-id="ea1c7-199">Der Name der Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-199">The name of the solution file.</span></span> |
| <span data-ttu-id="ea1c7-200">**MyControls.csproj**</span><span class="sxs-lookup"><span data-stu-id="ea1c7-200">**MyControls.csproj**</span></span> | <span data-ttu-id="ea1c7-201">Der Name des zu portierenden .NET Framework Windows Forms-Steuerelemente-Projekts.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-201">The name of the .NET Framework Windows Forms Controls project to port.</span></span> |
| <span data-ttu-id="ea1c7-202">**MyControlsCore.csproj**</span><span class="sxs-lookup"><span data-stu-id="ea1c7-202">**MyControlsCore.csproj**</span></span> | <span data-ttu-id="ea1c7-203">Der Name des neuen .NET Core-Bibliotheksprojekts, das Sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-203">The name of the new .NET Core library project you create.</span></span> |
| <span data-ttu-id="ea1c7-204">**MyCoreControls.dll**</span><span class="sxs-lookup"><span data-stu-id="ea1c7-204">**MyCoreControls.dll**</span></span> | <span data-ttu-id="ea1c7-205">Die .NET Core-Windows Forms-Steuerelemente-Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-205">The .NET Core Windows Forms Controls library.</span></span> |

```
SolutionFolder
├───MyApps.sln
├───MyFormsApp
│   └───MyForms.csproj
├───MyFormsAppCore
│   └───MyFormsCore.csproj
│
├───MyFormsControls
│   └───MyControls.csproj
└───MyFormsControlsCore
    └───MyControlsCore.csproj   <--- New project for core controls
```

<span data-ttu-id="ea1c7-206">Betrachten Sie die Unterschiede zwischen dem `MyControlsCore.csproj`-Projekt und dem zuvor erstellten `MyFormsCore.csproj`-Projekt.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-206">Consider the differences between the `MyControlsCore.csproj` project and the previously created `MyFormsCore.csproj` project.</span></span>

```diff
 <Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

   <PropertyGroup>
-    <OutputType>WinExe</OutputType>
     <TargetFramework>netcoreapp3.0</TargetFramework>
     <UseWindowsForms>true</UseWindowsForms>

     <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
-    <AssemblyName>MyCoreApp</AssemblyName>
-    <RootNamespace>WindowsFormsApp1</RootNamespace>
+    <AssemblyName>MyControlsCore</AssemblyName>
+    <RootNamespace>WindowsFormsControlLibrary1</RootNamespace>
   </PropertyGroup>

   <ItemGroup>
-    <Compile Include="..\MyFormsApp\**\*.cs" />
-    <EmbeddedResource Include="..\MyFormsApp\**\*.resx" />
+    <Compile Include="..\MyFormsControls\**\*.cs" />
+    <EmbeddedResource Include="..\MyFormsControls\**\*.resx" />
   </ItemGroup>

 </Project>
```

<span data-ttu-id="ea1c7-207">Die Projektdatei der .NET Core-Windows Forms-Steuerelemente-Bibliothek könnte z.B. folgendermaßen aussehen:</span><span class="sxs-lookup"><span data-stu-id="ea1c7-207">Here is an example of what the .NET Core Windows Forms Controls library project file would look like:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>

    <TargetFramework>netcoreapp3.0</TargetFramework>
    <UseWindowsForms>true</UseWindowsForms>

    <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
    <AssemblyName>MyCoreControls</AssemblyName>
    <RootNamespace>WindowsFormsControlLibrary1</RootNamespace>
  </PropertyGroup>

  <ItemGroup>
    <Compile Include="..\MyFormsControls\**\*.cs" />
    <EmbeddedResource Include="..\MyFormsControls\**\*.resx" />
  </ItemGroup>

</Project>
```

<span data-ttu-id="ea1c7-208">Wie Sie sehen können, wurde der `<OutputType>`-Knoten entfernt, der standardmäßig anstelle einer ausführbaren Datei der Compiler zum Erstellen einer Bibliothek ist.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-208">As you can see, the `<OutputType>` node was removed, which defaults the compiler to produce a library instead of an executable.</span></span> <span data-ttu-id="ea1c7-209">`<AssemblyName>` und `<RootNamespace>` wurden geändert.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-209">The `<AssemblyName>` and `<RootNamespace>` were changed.</span></span> <span data-ttu-id="ea1c7-210">Insbesondere der `<RootNamespace>` sollte mit dem Namespace der Windows Forms-Steuerelemente-Bibliothek übereinstimmen, die Sie portieren.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-210">Specifically the `<RootNamespace>` should match the namespace of the Windows Forms Controls library you are porting.</span></span> <span data-ttu-id="ea1c7-211">Schließlich wurden die Knoten `<Compile>` und `<EmbeddedResource>` so angepasst, dass sie auf den Ordner der Windows Forms-Steuerelemente-Bibliothek verweisen, die Sie portieren.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-211">And finally, the `<Compile>` and `<EmbeddedResource>` nodes were adjusted to point to the folder of the Windows Forms Controls library you are porting.</span></span>

<span data-ttu-id="ea1c7-212">Fügen Sie als Nächstes im .NET Core-Hauptprojekt **MyFormsCore.csproj** den Verweis auf die neue Windows Forms-Steuerelementebibliothek von .NET Core hinzu.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-212">Next, in the main .NET Core **MyFormsCore.csproj** project, add a reference to the new .NET Core Windows Forms Control library.</span></span> <span data-ttu-id="ea1c7-213">Fügen Sie entweder mit Visual Studio oder der .NET Core-CLI einen Verweis vom **SolutionFolder**-Verzeichnis hinzu:</span><span class="sxs-lookup"><span data-stu-id="ea1c7-213">Add a reference with either Visual Studio or the .NET Core CLI from the **SolutionFolder** directory:</span></span>

```dotnetcli
dotnet add .\MyFormsAppCore\MyFormsCore.csproj reference .\MyFormsControlsCore\MyControlsCore.csproj
```

<span data-ttu-id="ea1c7-214">Der vorherige Befehl fügt dem **MyFormsCore.csproj**-Projekt Folgendes hinzu:</span><span class="sxs-lookup"><span data-stu-id="ea1c7-214">The previous command adds the following to the **MyFormsCore.csproj** project:</span></span>

```xml
  <ItemGroup>
    <ProjectReference Include="..\MyFormsControlsCore\MyControlsCore.csproj" />
  </ItemGroup>
```

## <a name="compilation-problems"></a><span data-ttu-id="ea1c7-215">Kompilierungsprobleme</span><span class="sxs-lookup"><span data-stu-id="ea1c7-215">Compilation problems</span></span>

<span data-ttu-id="ea1c7-216">Wenn beim Kompilieren Ihrer Projekte Probleme auftreten, verwenden Sie möglicherweise einige nur für Windows geeignete APIs, die in .NET Framework, aber nicht in .NET Core verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-216">If you have problems compiling your projects, you may be using some Windows-only APIs that are available in .NET Framework but not available in .NET Core.</span></span> <span data-ttu-id="ea1c7-217">Sie können versuchen, das [Windows Compatibility Pack][compat-pack] NuGet-Paket Ihrem Projekt hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-217">You can try adding the [Windows Compatibility Pack][compat-pack] NuGet package to your project.</span></span> <span data-ttu-id="ea1c7-218">Dieses Paket kann nur auf Windows ausgeführt werden und fügt .NET Core- und .NET Standard-Projekten ungefähr 20.000 Windows-APIs hinzu.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-218">This package only runs on Windows and adds about 20,000 Windows APIs to .NET Core and .NET Standard projects.</span></span>

```dotnetcli
dotnet add .\MyFormsAppCore\MyFormsCore.csproj package Microsoft.Windows.Compatibility
```

<span data-ttu-id="ea1c7-219">Der vorherige Befehl fügt dem **MyFormsCore.csproj**-Projekt Folgendes hinzu:</span><span class="sxs-lookup"><span data-stu-id="ea1c7-219">The previous command adds the following to the **MyFormsCore.csproj** project:</span></span>

```xml
  <ItemGroup>
    <PackageReference Include="Microsoft.Windows.Compatibility" Version="3.1.0" />
  </ItemGroup>
```

## <a name="windows-forms-designer"></a><span data-ttu-id="ea1c7-220">Windows Forms-Designer</span><span class="sxs-lookup"><span data-stu-id="ea1c7-220">Windows Forms Designer</span></span>

<span data-ttu-id="ea1c7-221">Wie in diesem Artikel ausführlich beschrieben unterstützt Visual Studio 2019 in .NET Framework-Projekten nur den Forms-Designer.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-221">As detailed in this article, Visual Studio 2019 only supports the Forms Designer in .NET Framework projects.</span></span> <span data-ttu-id="ea1c7-222">Durch Erstellen eines parallelen .NET Core-Projekts können Sie Ihr Projekt mit .NET Core testen, während Sie das .NET Framework-Projekt zum Entwerfen von Formularen verwenden.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-222">By creating a side-by-side .NET Core project, you can test your project with .NET Core while you use the .NET Framework project to design forms.</span></span> <span data-ttu-id="ea1c7-223">Die Projektmappendatei enthält sowohl die .NET Framework- als auch die .NET Core-Projekte.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-223">Your solution file includes both the .NET Framework and .NET Core projects.</span></span> <span data-ttu-id="ea1c7-224">Führen Sie das Hinzufügen und Entwerfen Ihrer Formulare und Steuerelemente im .NET Framework-Projekt durch, und auf der Basis der Dateiglobmuster, die wir den .NET Core-Projekten hinzugefügt haben, wird jede neue oder geänderte Datei automatisch in die .NET Core-Projekte einbezogen.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-224">Add and design your forms and controls in the .NET Framework project, and based on the file glob patterns we added to the .NET Core projects, any new or changed files will automatically be included in the .NET Core projects.</span></span>

<span data-ttu-id="ea1c7-225">Sobald Visual Studio 2019 den Windows Forms-Designer unterstützt, können Sie den Inhalt Ihrer .NET Core-Projektdatei kopieren und in die .NET Framework-Projektdatei einfügen.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-225">Once Visual Studio 2019 supports the Windows Forms Designer, you can copy/paste the content of your .NET Core project file into the .NET Framework project file.</span></span> <span data-ttu-id="ea1c7-226">Löschen Sie dann die Dateiglobmuster, die mit dem `<Source>`- und `<EmbeddedResource>`-Element hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-226">Then delete the file glob patterns added with the `<Source>` and `<EmbeddedResource>` items.</span></span> <span data-ttu-id="ea1c7-227">Stellen Sie die Pfade zu jedem von Ihrer App verwendeten Projektverweis wieder her.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-227">Fix the paths to any project reference used by your app.</span></span> <span data-ttu-id="ea1c7-228">Damit wird effektiv das .NET Framework-Projekt zu einem .NET Core-Projekt heraufgestuft.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-228">This effectively upgrades the .NET Framework project to a .NET Core project.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ea1c7-229">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="ea1c7-229">Next steps</span></span>

- <span data-ttu-id="ea1c7-230">Weitere Informationen finden Sie unter [Breaking Changes von .NET Framework zu .NET Core](../compatibility/fx-core.md).</span><span class="sxs-lookup"><span data-stu-id="ea1c7-230">Learn about [breaking changes from .NET Framework to .NET Core](../compatibility/fx-core.md).</span></span>
- <span data-ttu-id="ea1c7-231">Lesen Sie mehr über das [Windows Compatibility Pack][compat-pack].</span><span class="sxs-lookup"><span data-stu-id="ea1c7-231">Read more about the [Windows Compatibility Pack][compat-pack].</span></span>
- <span data-ttu-id="ea1c7-232">Sehen Sie sich ein [Video zum Portieren](https://www.youtube.com/watch?v=upVQEUc_KwU) Ihres .NET Framework-Windows Forms-Projekts zu .NET Core an.</span><span class="sxs-lookup"><span data-stu-id="ea1c7-232">Watch a [video on porting](https://www.youtube.com/watch?v=upVQEUc_KwU) your .NET Framework Windows Forms project to .NET Core.</span></span>

[compat-pack]: windows-compat-pack.md
