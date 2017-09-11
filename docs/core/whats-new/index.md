---
title: Neuigkeiten in .NET Core 2.0
description: Informationen zu den neuen Funktionen in .NET Core.
keywords: .NET, .NET Core
author: rpetrusha
ms.author: ronpet
ms.date: 08/13/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.translationtype: HT
ms.sourcegitcommit: b47d4c74a01b99d743b69328c201096bc8d89794
ms.openlocfilehash: e43f72ebd26c34636c239d8ac9f749d52d3f60a0
ms.contentlocale: de-de
ms.lasthandoff: 08/14/2017

---
# <a name="whats-new-in-net-core"></a><span data-ttu-id="ac945-104">Neuigkeiten in .NET Core</span><span class="sxs-lookup"><span data-stu-id="ac945-104">What's new in .NET Core</span></span>

<span data-ttu-id="ac945-105">.NET Core 2.0 enthält Verbesserungen und neue Funktionen in folgenden Bereichen:</span><span class="sxs-lookup"><span data-stu-id="ac945-105">.NET Core 2.0 includes enhancements and new features in the following areas:</span></span>

- [<span data-ttu-id="ac945-106">Tools</span><span class="sxs-lookup"><span data-stu-id="ac945-106">Tooling</span></span>](#tooling)
- [<span data-ttu-id="ac945-107">Sprachenunterstützung</span><span class="sxs-lookup"><span data-stu-id="ac945-107">Language support</span></span>](#language-support)
- [<span data-ttu-id="ac945-108">Plattformverbesserungen</span><span class="sxs-lookup"><span data-stu-id="ac945-108">Platform improvements</span></span>](#platform-improvements)
- [<span data-ttu-id="ac945-109">API-Änderungen</span><span class="sxs-lookup"><span data-stu-id="ac945-109">API changes</span></span>](#api-changes-and-library-support)
- [<span data-ttu-id="ac945-110">Integration von Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ac945-110">Visual Studio integration</span></span>](#visual-studio-integration)
- [<span data-ttu-id="ac945-111">Dokumentationsverbesserungen</span><span class="sxs-lookup"><span data-stu-id="ac945-111">Documentation improvements</span></span>](#documentation-improvements) 

## <a name="tooling"></a><span data-ttu-id="ac945-112">Tools</span><span class="sxs-lookup"><span data-stu-id="ac945-112">Tooling</span></span>

### <a name="dotnet-restore-runs-implicitly"></a><span data-ttu-id="ac945-113">„dotnet restore“ wird implizit ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ac945-113">dotnet restore runs implicitly</span></span>

<span data-ttu-id="ac945-114">In früheren Versionen von .NET Core mussten Sie den [dotnet restore](../tools/dotnet-restore.md)-Befehl sowohl ausführen, um Abhängigkeiten sofort nach der Erstellung eines neuen Projekts mit dem [dotnet new](../tools/dotnet-new.md)-Befehl herunterzuladen, als auch immer dann, wenn Sie dem Projekt eine neue Abhängigkeit hinzugefügt hatten.</span><span class="sxs-lookup"><span data-stu-id="ac945-114">In previous versions of .NET Core, you had to run the [dotnet restore](../tools/dotnet-restore.md) command to download dependencies immediately after you created a new project with the [dotnet new](../tools/dotnet-new.md) command, as well as whenever you added a new dependency to your project.</span></span> <span data-ttu-id="ac945-115">In .NET Core 2.0 wird `dotnet restore` implizit immer dann ausgeführt, wenn der `dotnet new`-Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ac945-115">In .NET Core 2.0, `dotnet restore` runs implicitly when the `dotnet new` command executes.</span></span> <span data-ttu-id="ac945-116">Der Befehl wird auch dann implizit ausgeführt, wenn Abhängigkeiten aufgrund der Ausführung anderer Befehle wie `run`, `build` und `publish` aktualisiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="ac945-116">It also runs implicitly if dependencies need to be updated when other commands, such as the `run`, `build`, and `publish` commands, execute.</span></span>

<span data-ttu-id="ac945-117">Sie können den automatischen Aufruf von `dotnet restore` auch deaktivieren, indem Sie die Befehlszeilenoption `--no-restore` den Befehlen `new`, `run`, `build`, `publish`, `pack` und `test` übergeben.</span><span class="sxs-lookup"><span data-stu-id="ac945-117">You can also disable the automatic invocation of `dotnet restore` by passing the `--no-restore` switch to the `new`, `run`, `build`, `publish`, `pack`, and `test` commands.</span></span> 

### <a name="retargeting-to-net-core-20"></a><span data-ttu-id="ac945-118">Neuzuweisung zu .NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="ac945-118">Retargeting to .NET Core 2.0</span></span>

<span data-ttu-id="ac945-119">Wenn .NET Core 2.0 SDK installiert ist, können Projekte, die .NET Core 1.x zugewiesen sind, .NET Core 2.0 neu zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="ac945-119">If the .NET Core 2.0 SDK is installed, projects that target .NET Core 1.x can be retargeted to .NET Core 2.0.</span></span> 

<span data-ttu-id="ac945-120">Bearbeiten Sie Ihre Projektdatei für die Neuzuweisung zu .NET Core 2.0 durch Ändern des Werts des `<TargetFramework>`-Elements (oder `<TargetFrameworks>`-Elements, wenn Ihre Projektdatei mehrere Zuweisungen enthält) von 1.x in 2.0:</span><span class="sxs-lookup"><span data-stu-id="ac945-120">To retarget to .NET Core 2.0, edit your project file by changing the value of the `<TargetFramework>` element (or the `<TargetFrameworks>` element if you have more than one target in your project file) from 1.x to 2.0:</span></span>

```xml
<PropertyGroup>
    <TargetFramework>netcoreapp2.0</TargetFramework>
 </PropertyGroup>
```

<span data-ttu-id="ac945-121">Auf die gleiche Weise können Sie auch .NET Standard-Bibliotheken zu .NET Standard 2.0 neu zuweisen:</span><span class="sxs-lookup"><span data-stu-id="ac945-121">You can also retarget .NET Standard libraries to .NET Standard 2.0 the same way:</span></span>

```xml
<PropertyGroup>
    <TargetFramework>netstandard2.0</TargetFramework>
 </PropertyGroup>
```

<span data-ttu-id="ac945-122">Weitere Informationen zum Migrieren Ihres Projekts zu .NET Core 2.0 finden Sie unter [Migrating from ASP.NET Core 1.x to ASP.NET Core 2.0](/aspnet/core/migration/1x-to-2x/index) (Migrieren von ASP.NET Core 1.x zu ASP.NET Core 2.0).</span><span class="sxs-lookup"><span data-stu-id="ac945-122">For more information about migrating your project to .NET Core 2.0, see [Migrating from ASP.NET Core 1.x to ASP.NET Core 2.0](/aspnet/core/migration/1x-to-2x/index).</span></span>

## <a name="language-support"></a><span data-ttu-id="ac945-123">Sprachenunterstützung</span><span class="sxs-lookup"><span data-stu-id="ac945-123">Language support</span></span>

<span data-ttu-id="ac945-124">Außer C# und F# unterstützt .NET Core 2.0 auch Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ac945-124">In addition to supporting C# and F#, .NET Core 2.0 also supports Visual Basic.</span></span>

### <a name="visual-basic"></a><span data-ttu-id="ac945-125">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ac945-125">Visual Basic</span></span>

<span data-ttu-id="ac945-126">Mit Version 2.0 unterstützt .NET Core jetzt Visual Basic 2017.</span><span class="sxs-lookup"><span data-stu-id="ac945-126">With version 2.0, .NET Core now supports Visual Basic 2017.</span></span> <span data-ttu-id="ac945-127">Sie können Visual Basic zum Erstellen folgender Projekttypen verwenden:</span><span class="sxs-lookup"><span data-stu-id="ac945-127">You can use Visual Basic to create the following project types:</span></span>

- <span data-ttu-id="ac945-128">.NET Core-Konsolen-Apps</span><span class="sxs-lookup"><span data-stu-id="ac945-128">.NET Core console apps</span></span>
- <span data-ttu-id="ac945-129">.NET Core-Klassenbibliotheken</span><span class="sxs-lookup"><span data-stu-id="ac945-129">.NET Core class libraries</span></span>
- <span data-ttu-id="ac945-130">.NET Standard-Klassenbibliotheken</span><span class="sxs-lookup"><span data-stu-id="ac945-130">.NET Standard class libraries</span></span>
- <span data-ttu-id="ac945-131">.NET Core-Komponententestprojekte</span><span class="sxs-lookup"><span data-stu-id="ac945-131">.NET Core unit test projects</span></span>
- <span data-ttu-id="ac945-132">.NET Core-xUnit-Testprojekte</span><span class="sxs-lookup"><span data-stu-id="ac945-132">.NET Core xUnit test projects</span></span> 

<span data-ttu-id="ac945-133">Führen Sie z.B. zum Erstellen einer „Hello World“-Anwendung in Visual Basic die folgenden Schritte in der Befehlszeile aus:</span><span class="sxs-lookup"><span data-stu-id="ac945-133">For example, to create a Visual Basic "Hello World" application, do the following steps from the command line:</span></span>

1. <span data-ttu-id="ac945-134">Öffnen Sie ein Konsolenfenster, erstellen Sie ein Verzeichnis für Ihr Projekt, und machen Sie es zu Ihrem aktuellen Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="ac945-134">Open a console window, create a directory for your project, and make it the current directory.</span></span>

1. <span data-ttu-id="ac945-135">Geben Sie den Befehl `dotnet new console -lang vb` ein.</span><span class="sxs-lookup"><span data-stu-id="ac945-135">Enter the command `dotnet new console -lang vb`.</span></span>

   <span data-ttu-id="ac945-136">Der Befehl erstellt eine Projektdatei mit einer `.vbproj`-Erweiterung zusammen mit einer Visual Basic-Quellcodedatei mit dem Namen *Program.vb*.</span><span class="sxs-lookup"><span data-stu-id="ac945-136">The command creates a project file with a `.vbproj` file extension, along with a Visual Basic source code file named *Program.vb*.</span></span> <span data-ttu-id="ac945-137">Diese Datei enthält den Quellcode, um die Zeichenfolge „Hello World!“</span><span class="sxs-lookup"><span data-stu-id="ac945-137">This file contains the source code to write the string "Hello World!"</span></span> <span data-ttu-id="ac945-138">im Konsolenfenster anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ac945-138">to the console window.</span></span>
  
1.  <span data-ttu-id="ac945-139">Geben Sie den Befehl `dotnet run` ein.</span><span class="sxs-lookup"><span data-stu-id="ac945-139">Enter the command `dotnet run`.</span></span> <span data-ttu-id="ac945-140">Die [.NET Core-CLI-Tools](../tools/index.md) kompilieren die Anwendung automatisch und führen sie aus, um die Meldung „Hello World!“</span><span class="sxs-lookup"><span data-stu-id="ac945-140">The [.NET Core CLI tools](../tools/index.md) automatically compile and execute the application, which displays the message "Hello World!"</span></span> <span data-ttu-id="ac945-141">im Konsolenfenster anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ac945-141">in the console window.</span></span>

### <a name="support-for-c-71"></a><span data-ttu-id="ac945-142">Unterstützung für C# 7.1</span><span class="sxs-lookup"><span data-stu-id="ac945-142">Support for C# 7.1</span></span>

<span data-ttu-id="ac945-143">.NET Core 2.0 unterstützt C# 7.1 und wird so durch eine Reihe neuer Funktionen einschließlich der folgenden ergänzt:</span><span class="sxs-lookup"><span data-stu-id="ac945-143">.NET Core 2.0 supports C# 7.1, which adds a number of new features, including:</span></span>

- <span data-ttu-id="ac945-144">Die `Main`-Methode, der Einstiegspunkt der Anwendung, kann mit dem [async](../../csharp/language-reference/keywords/async.md)-Schlüsselwort gekennzeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="ac945-144">The `Main` method, the application entry point, can be marked with the [async](../../csharp/language-reference/keywords/async.md) keyword.</span></span>
- <span data-ttu-id="ac945-145">Abgeleitete Tupelnamen.</span><span class="sxs-lookup"><span data-stu-id="ac945-145">Inferred tuple names.</span></span>
- <span data-ttu-id="ac945-146">Standardausdrücke.</span><span class="sxs-lookup"><span data-stu-id="ac945-146">Default expressions.</span></span>

<!-- For more information see [link to C# what's new](url). -->

## <a name="platform-improvements"></a><span data-ttu-id="ac945-147">Plattformverbesserungen</span><span class="sxs-lookup"><span data-stu-id="ac945-147">Platform improvements</span></span>

<span data-ttu-id="ac945-148">.NET Core 2.0 umfasst eine Reihe von Funktionen, die das Installieren von .NET Core und die Verwendung auf unterstützten Betriebssystemen erleichtern.</span><span class="sxs-lookup"><span data-stu-id="ac945-148">.NET Core 2.0 includes a number of features that make it easier to install .NET Core and to use it on supported operating systems.</span></span>

### <a name="net-core-for-linux-is-a-single-implementation"></a><span data-ttu-id="ac945-149">.NET Core für Linux ist eine einzelne Implementierung.</span><span class="sxs-lookup"><span data-stu-id="ac945-149">.NET Core for Linux is a single implementation</span></span>

<span data-ttu-id="ac945-150">.NET Core 2.0 bietet eine einzelne Linux-Implementierung, die für mehrere Linux-Distributionen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="ac945-150">.NET Core 2.0 offers a single Linux implementation that works on multiple Linux distributions.</span></span> <span data-ttu-id="ac945-151">.NET Core 1.x setzte das Herunterladen einer distributionsspezifischen Linux-Implementierung voraus.</span><span class="sxs-lookup"><span data-stu-id="ac945-151">.NET Core 1.x required that you download a distribution-specific Linux implementation.</span></span>

<span data-ttu-id="ac945-152">Sie können auch Apps entwickeln, die für das Betriebssystem Linux im Allgemeinen vorgesehen sind.</span><span class="sxs-lookup"><span data-stu-id="ac945-152">You can also develop apps that target Linux as a single operating system.</span></span> <span data-ttu-id="ac945-153">.NET Core 1.x setzte voraus, dass Sie für jede Linux-Distribution separat entwickeln.</span><span class="sxs-lookup"><span data-stu-id="ac945-153">.NET Core 1.x required that you target each Linux distribution separately.</span></span> 

### <a name="support-for-the-apple-cryptographic-libraries"></a><span data-ttu-id="ac945-154">Unterstützung der kryptografischen Apple-Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="ac945-154">Support for the Apple cryptographic libraries</span></span>

<span data-ttu-id="ac945-155">.NET Core 1.x auf macOS setzte die kryptografische Bibliothek des OpenSSL-Toolkits voraus.</span><span class="sxs-lookup"><span data-stu-id="ac945-155">.NET Core 1.x on macOS required the OpenSSL toolkit's cryptographic library.</span></span> <span data-ttu-id="ac945-156">.NET Core 2.0 verwendet die kryptografischen Apple-Bibliotheken und benötigt OpenSSL nicht, sodass Sie auf dessen Installation zukünftig verzichten können.</span><span class="sxs-lookup"><span data-stu-id="ac945-156">.NET Core 2.0 uses the Apple cryptographic libraries and doesn't require OpenSSL, so you no longer need to install it.</span></span> 

## <a name="api-changes-and-library-support"></a><span data-ttu-id="ac945-157">API-Änderungen und Bibliotheksunterstützung</span><span class="sxs-lookup"><span data-stu-id="ac945-157">API changes and library support</span></span>

### <a name="support-for-net-standard-20"></a><span data-ttu-id="ac945-158">Unterstützung für .NET Standard 2.0</span><span class="sxs-lookup"><span data-stu-id="ac945-158">Support for .NET Standard 2.0</span></span>

<span data-ttu-id="ac945-159">.NET Standard definiert einen Satz von APIs mit Versionsangabe, die in .NET Implementierungen verfügbar sein müssen, die dieser Version des Standards entsprechen.</span><span class="sxs-lookup"><span data-stu-id="ac945-159">The .NET Standard defines a versioned set of APIs that must be available on .NET implementations that comply with that version of the standard.</span></span> <span data-ttu-id="ac945-160">.NET Standard ist auf Bibliotheksentwickler ausgerichtet.</span><span class="sxs-lookup"><span data-stu-id="ac945-160">The .NET Standard is targeted at library developers.</span></span> <span data-ttu-id="ac945-161">Er soll die Funktionalität garantieren, die einer Bibliothek zur Verfügung steht, die für eine Version von .NET Standard in jeder .NET-Implementierung vorgesehen ist.</span><span class="sxs-lookup"><span data-stu-id="ac945-161">It aims to guarantee the functionality that is available to a library that targets a version of the .NET Standard on each .NET implementation.</span></span> <span data-ttu-id="ac945-162">.NET Core 1.x unterstützt die .NET Standard-Version 1.6; .NET Core 2.0 unterstützt die neueste Version, .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="ac945-162">.NET Core 1.x supports the .NET Standard version 1.6; .NET Core 2.0 supports the latest version, .NET Standard 2.0.</span></span> <span data-ttu-id="ac945-163">Weitere Informationen finden Sie unter [.NET Standard](../../standard/net-standard.md).</span><span class="sxs-lookup"><span data-stu-id="ac945-163">For more information, see [.NET Standard](../../standard/net-standard.md).</span></span>

<span data-ttu-id="ac945-164">.NET Standard 2.0 umfasst über 20.000 APIs mehr, als in .NET Standard 1.6 verfügbar waren.</span><span class="sxs-lookup"><span data-stu-id="ac945-164">.NET Standard 2.0 includes over 20,000 more APIs than were available in the .NET Standard 1.6.</span></span> <span data-ttu-id="ac945-165">Diese Oberflächenerweiterung resultiert zu einem großen Teil aus dem Einbeziehen in .NET Framework und Xamarin üblicher APIs in .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="ac945-165">Much of this expanded surface area results from incorporating APIs that are common to the .NET Framework and Xamarin into .NET Standard.</span></span>

<span data-ttu-id="ac945-166">.NET Standard 2.0-Klassenbibliotheken können auch auf .NET Framework-Klassenbibliotheken verweisen, vorausgesetzt, dass sie APIs aufrufen, die in .NET Standard 2.0 vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="ac945-166">.NET Standard 2.0 class libraries can also reference .NET Framework class libraries, provided that they call APIs that are present in the .NET Standard 2.0.</span></span> <span data-ttu-id="ac945-167">Es ist keine Neukompilierung der .NET Framework-Bibliotheken erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ac945-167">No recompilation of the .NET Framework libraries is required.</span></span>

<span data-ttu-id="ac945-168">Eine Liste der APIs, die .NET Standard seit der letzten Version, .NET Standard 1.6, hinzugefügt wurden, finden Sie unter [.NET Standard 2.0 vs. 1.6](https://raw.githubusercontent.com/dotnet/standard/master/docs/versions/netstandard2.0_diff.md) (.NET Standard 2.0 im Vergleich zu 1.6).</span><span class="sxs-lookup"><span data-stu-id="ac945-168">For a list of the APIs that have been added to the .NET Standard since its last version, the .NET Standard 1.6, see [.NET Standard 2.0 vs. 1.6](https://raw.githubusercontent.com/dotnet/standard/master/docs/versions/netstandard2.0_diff.md).</span></span>

### <a name="expanded-surface-area"></a><span data-ttu-id="ac945-169">Erweiterte Oberfläche</span><span class="sxs-lookup"><span data-stu-id="ac945-169">Expanded surface area</span></span>

<span data-ttu-id="ac945-170">Die Gesamtanzahl der in .NET Core 2.0 verfügbaren APIs hat sich im Vergleich zu .NET Core 1.1 mehr als verdoppelt.</span><span class="sxs-lookup"><span data-stu-id="ac945-170">The total number of APIs available on .NET Core 2.0 has more than doubled in comparison with .NET Core 1.1.</span></span> 

### <a name="support-for-net-framework-libraries"></a><span data-ttu-id="ac945-171">Unterstützung für .NET Framework-Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="ac945-171">Support for .NET Framework libraries</span></span>

<span data-ttu-id="ac945-172">.NET Core-Code kann auf vorhandene .NET Framework-Bibliotheken einschließlich der vorhandenen NuGet-Pakete verweisen.</span><span class="sxs-lookup"><span data-stu-id="ac945-172">.NET Core code can reference existing .NET Framework libraries, including existing NuGet packages.</span></span> <span data-ttu-id="ac945-173">Beachten Sie, dass die Bibliotheken APIs verwenden müssen, die im .NET Standard enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="ac945-173">Note that the libraries must use APIs that are found in .NET Standard.</span></span>

## <a name="visual-studio-integration"></a><span data-ttu-id="ac945-174">Visual Studio-Integration</span><span class="sxs-lookup"><span data-stu-id="ac945-174">Visual Studio integration</span></span>

<span data-ttu-id="ac945-175">Visual Studio 2017 Version 15.3 und in einigen Fällen Visual Studio für Mac bieten eine Reihe erheblicher Verbesserungen für .NET Core-Entwickler.</span><span class="sxs-lookup"><span data-stu-id="ac945-175">Visual Studio 2017 version 15.3 and in some cases Visual Studio for Mac offer a number of significant enhancements for .NET Core developers.</span></span>

### <a name="retargeting-net-core-apps-and-net-standard-libraries"></a><span data-ttu-id="ac945-176">Neuzuweisung von .NET Core-Apps und .NET Standard-Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="ac945-176">Retargeting .NET Core apps and .NET Standard libraries</span></span>

<span data-ttu-id="ac945-177">Wenn das .NET Core 2.0 SDK installiert ist, können Sie Projekte von .NET Core 1.x zu .NET Core 2.0 und .NET Standard 1.x-Bibliotheken zu .NET-Standard 2.0 neu zuweisen.</span><span class="sxs-lookup"><span data-stu-id="ac945-177">If the .NET Core 2.0 SDK is installed, you can retarget .NET Core 1.x projects to .NET Core 2.0 and .NET Standard 1.x libraries to .NET Standard 2.0.</span></span> 

<span data-ttu-id="ac945-178">Um Ihr Projekt in Visual Studio neu zuzuweisen, öffnen Sie die Registerkarte **Anwendung** des Eigenschaftendialogfelds des Projekts und ändern den Wert **Zielframework** in **.NET Core 2.0** oder **.NET Standard 2.0**.</span><span class="sxs-lookup"><span data-stu-id="ac945-178">To retarget your project in Visual Studio, you open the **Application** tab of the project's properties dialog and change the **Target framework** value to **.NET Core 2.0** or **.NET Standard 2.0**.</span></span> <span data-ttu-id="ac945-179">Sie können es auch ändern, indem Sie mit der rechten Maustaste auf das Projekt klicken und die Option **\*.csproj-Datei bearbeiten** auswählen.</span><span class="sxs-lookup"><span data-stu-id="ac945-179">You can also change it by right-clicking on the project and selecting the **Edit \*.csproj file** option.</span></span> <span data-ttu-id="ac945-180">Weitere Informationen finden Sie weiter oben in diesem Thema im Abschnitt [Tools](#tooling).</span><span class="sxs-lookup"><span data-stu-id="ac945-180">For more information, see the [Tooling](#tooling) section earlier in this topic.</span></span>

### <a name="live-unit-testing-support-for-net-core"></a><span data-ttu-id="ac945-181">Live Unit Testing-Unterstützung für .NET Core</span><span class="sxs-lookup"><span data-stu-id="ac945-181">Live Unit Testing support for .NET Core</span></span>

<span data-ttu-id="ac945-182">Wenn Sie Ihren Code ändern, führt Live Unit Testing automatisch alle betroffenen Komponententests im Hintergrund aus und zeigt die Ergebnisse und die Codeabdeckung in der Visual Studio-Umgebung live an.</span><span class="sxs-lookup"><span data-stu-id="ac945-182">Whenever you modify your code, Live Unit Testing automatically runs any affected unit tests in the background and displays the results and code coverage live in the Visual Studio environment.</span></span> <span data-ttu-id="ac945-183">.NET Core 2.0 unterstützt jetzt Live Unit Testing.</span><span class="sxs-lookup"><span data-stu-id="ac945-183">.NET Core 2.0 now supports Live Unit Testing.</span></span> <span data-ttu-id="ac945-184">Bisher war Live Unit Testing nur für .NET Framework-Anwendungen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ac945-184">Previously, Live Unit Testing was available only for .NET Framework applications.</span></span> 

<span data-ttu-id="ac945-185">Weitere Informationen finden Sie unter [Live Unit Testing mit Visual Studio 2017](/visualstudio/test/live-unit-testing) und [Live Unit Testing – häufig gestellte Fragen](/visualstudio/test/live-unit-testing-faq).</span><span class="sxs-lookup"><span data-stu-id="ac945-185">For more information, see [Live Unit Testing with Visual Studio 2017](/visualstudio/test/live-unit-testing) and the [Live Unit Testing FAQ](/visualstudio/test/live-unit-testing-faq).</span></span>

### <a name="better-support-for-multiple-target-frameworks"></a><span data-ttu-id="ac945-186">Bessere Unterstützung für mehrere Zielframeworks</span><span class="sxs-lookup"><span data-stu-id="ac945-186">Better support for multiple target frameworks</span></span>

<span data-ttu-id="ac945-187">Wenn Sie ein Projekt für mehrere Zielframeworks erstellen, können Sie nun die Zielplattform im Hauptebenenmenü auswählen.</span><span class="sxs-lookup"><span data-stu-id="ac945-187">If you're building a project for multiple target frameworks, you can now select the target platform from the top-level menu.</span></span> <span data-ttu-id="ac945-188">In der folgenden Abbildung ist ein Projekt namens SCD1 für 64-Bit-Mac OS X 10.11 (`osx.10.11-x64`) und 64-Bit-Windows 10/Windows Server 2016 (`win10-x64`) bestimmt.</span><span class="sxs-lookup"><span data-stu-id="ac945-188">In the following figure, a project named SCD1 targets 64-bit Mac OS X 10.11 (`osx.10.11-x64`) and 64-bit Windows 10/Windows Server 2016 (`win10-x64`).</span></span> <span data-ttu-id="ac945-189">Sie können das Zielframework vor der Projektschaltfläche auswählen, in diesem Fall zum Ausführen eines Debugbuilds.</span><span class="sxs-lookup"><span data-stu-id="ac945-189">You can select the target framework before selecting the project button, in this case to run a debug build.</span></span>

![Auswahl des Zielframeworks beim Erstellen eines Projekts](media/multitarget.png) 

### <a name="side-by-side-support-for-net-core-sdks"></a><span data-ttu-id="ac945-191">Parallele Unterstützung für .NET Core-SDKs</span><span class="sxs-lookup"><span data-stu-id="ac945-191">Side-by-side support for .NET Core SDKs</span></span>

<span data-ttu-id="ac945-192">Sie können das .NET Core-SDK jetzt unabhängig von Visual Studio installieren.</span><span class="sxs-lookup"><span data-stu-id="ac945-192">You can now install the .NET Core SDK independently of Visual Studio.</span></span> <span data-ttu-id="ac945-193">So können mit einer einzelnen Version von Visual Studio Projekte für verschiedene .NET Core-Versionen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="ac945-193">This makes it possible for a single version of Visual Studio to build projects that target different versions of .NET Core.</span></span> <span data-ttu-id="ac945-194">Bisher waren Visual Studio und das .NET Core-SDK eng miteinander verbunden; eine bestimmte SDK-Version gehörte zu einer bestimmten Version von Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ac945-194">Previously, Visual Studio and the .NET Core SDK were tightly coupled; a particular version of the SDK accompanied a particular version of Visual Studio.</span></span>

## <a name="documentation-improvements"></a><span data-ttu-id="ac945-195">Dokumentationsverbesserungen</span><span class="sxs-lookup"><span data-stu-id="ac945-195">Documentation improvements</span></span>

### <a name="net-application-architecture"></a><span data-ttu-id="ac945-196">.NET-Anwendungsarchitektur</span><span class="sxs-lookup"><span data-stu-id="ac945-196">.NET Application Architecture</span></span>

<span data-ttu-id="ac945-197">[.NET-Anwendungsarchitektur](https://www.microsoft.com/net/learn/architecture) ermöglicht Ihnen Zugriff auf einen Satz von eBooks, die Hilfestellung, bewährte Methoden und Beispielanwendungen zur Verwendung von .NET beim Erstellen folgender Software bieten:</span><span class="sxs-lookup"><span data-stu-id="ac945-197">[.NET Application Architecture](https://www.microsoft.com/net/learn/architecture) gives you access to a set of eBooks that provide guidance, best practices, and sample applications when using .NET to build:</span></span>

- <span data-ttu-id="ac945-198">Microservices und Docker-Container.</span><span class="sxs-lookup"><span data-stu-id="ac945-198">Microservices and Docker containers.</span></span>
- <span data-ttu-id="ac945-199">Webanwendungen mit ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="ac945-199">Web applications with ASP.NET.</span></span>
- <span data-ttu-id="ac945-200">Mobile Anwendungen mit Xamarin.</span><span class="sxs-lookup"><span data-stu-id="ac945-200">Mobile applications with Xamarin.</span></span>
- <span data-ttu-id="ac945-201">Anwendungen, die mit Azure in der Cloud bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="ac945-201">Applications that are deployed to the Cloud with Azure.</span></span>

## <a name="see-also"></a><span data-ttu-id="ac945-202">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ac945-202">See also</span></span>
 <span data-ttu-id="ac945-203">[What's new in ASP.NET Core 2.0](/aspnet/core/aspnetcore-2.0) (Neuigkeiten in ASP.NET Core 2.0)</span><span class="sxs-lookup"><span data-stu-id="ac945-203">[What's new in ASP.NET Core 2.0](/aspnet/core/aspnetcore-2.0)</span></span>

