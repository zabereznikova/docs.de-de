---
title: Neuigkeiten in .NET Core 2.0
description: Informationen zu den neuen Funktionen in .NET Core.
ms.date: 08/13/2017
ms.openlocfilehash: bdca38d1584107727fe8e20b80ab2337f4cb05f1
ms.sourcegitcommit: 67ebdb695fd017d79d9f1f7f35d145042d5a37f7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/20/2020
ms.locfileid: "92223711"
---
# <a name="whats-new-in-net-core-20"></a><span data-ttu-id="4cf76-103">Neuigkeiten in .NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="4cf76-103">What's new in .NET Core 2.0</span></span>

<span data-ttu-id="4cf76-104">.NET Core 2.0 enthält Verbesserungen und neue Funktionen in folgenden Bereichen:</span><span class="sxs-lookup"><span data-stu-id="4cf76-104">.NET Core 2.0 includes enhancements and new features in the following areas:</span></span>

- [<span data-ttu-id="4cf76-105">Tools</span><span class="sxs-lookup"><span data-stu-id="4cf76-105">Tooling</span></span>](#tooling)
- [<span data-ttu-id="4cf76-106">Sprachenunterstützung</span><span class="sxs-lookup"><span data-stu-id="4cf76-106">Language support</span></span>](#language-support)
- [<span data-ttu-id="4cf76-107">Plattformverbesserungen</span><span class="sxs-lookup"><span data-stu-id="4cf76-107">Platform improvements</span></span>](#platform-improvements)
- [<span data-ttu-id="4cf76-108">API-Änderungen</span><span class="sxs-lookup"><span data-stu-id="4cf76-108">API changes</span></span>](#api-changes-and-library-support)
- [<span data-ttu-id="4cf76-109">Integration von Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4cf76-109">Visual Studio integration</span></span>](#visual-studio-integration)
- [<span data-ttu-id="4cf76-110">Dokumentationsverbesserungen</span><span class="sxs-lookup"><span data-stu-id="4cf76-110">Documentation improvements</span></span>](#documentation-improvements)

## <a name="tooling"></a><span data-ttu-id="4cf76-111">Tools</span><span class="sxs-lookup"><span data-stu-id="4cf76-111">Tooling</span></span>

### <a name="dotnet-restore-runs-implicitly"></a><span data-ttu-id="4cf76-112">„dotnet restore“ wird implizit ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="4cf76-112">dotnet restore runs implicitly</span></span>

<span data-ttu-id="4cf76-113">In früheren Versionen von .NET Core mussten Sie den [dotnet restore](../tools/dotnet-restore.md)-Befehl sowohl ausführen, um Abhängigkeiten sofort nach der Erstellung eines neuen Projekts mit dem [dotnet new](../tools/dotnet-new.md)-Befehl herunterzuladen, als auch immer dann, wenn Sie dem Projekt eine neue Abhängigkeit hinzugefügt hatten.</span><span class="sxs-lookup"><span data-stu-id="4cf76-113">In previous versions of .NET Core, you had to run the [dotnet restore](../tools/dotnet-restore.md) command to download dependencies immediately after you created a new project with the [dotnet new](../tools/dotnet-new.md) command, as well as whenever you added a new dependency to your project.</span></span>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="4cf76-114">Sie können den automatischen Aufruf von `dotnet restore` auch deaktivieren, indem Sie die Befehlszeilenoption `--no-restore` den Befehlen `new`, `run`, `build`, `publish`, `pack` und `test` übergeben.</span><span class="sxs-lookup"><span data-stu-id="4cf76-114">You can also disable the automatic invocation of `dotnet restore` by passing the `--no-restore` switch to the `new`, `run`, `build`, `publish`, `pack`, and `test` commands.</span></span>

### <a name="retargeting-to-net-core-20"></a><span data-ttu-id="4cf76-115">Neuzuweisung zu .NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="4cf76-115">Retargeting to .NET Core 2.0</span></span>

<span data-ttu-id="4cf76-116">Wenn .NET Core 2.0 SDK installiert ist, können Projekte, die .NET Core 1.x zugewiesen sind, .NET Core 2.0 neu zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="4cf76-116">If the .NET Core 2.0 SDK is installed, projects that target .NET Core 1.x can be retargeted to .NET Core 2.0.</span></span>

<span data-ttu-id="4cf76-117">Bearbeiten Sie Ihre Projektdatei für die Neuzuweisung zu .NET Core 2.0 durch Ändern des Werts des `<TargetFramework>`-Elements (oder `<TargetFrameworks>`-Elements, wenn Ihre Projektdatei mehrere Zuweisungen enthält) von 1.x in 2.0:</span><span class="sxs-lookup"><span data-stu-id="4cf76-117">To retarget to .NET Core 2.0, edit your project file by changing the value of the `<TargetFramework>` element (or the `<TargetFrameworks>` element if you have more than one target in your project file) from 1.x to 2.0:</span></span>

```xml
<PropertyGroup>
    <TargetFramework>netcoreapp2.0</TargetFramework>
 </PropertyGroup>
```

<span data-ttu-id="4cf76-118">Auf die gleiche Weise können Sie auch .NET Standard-Bibliotheken zu .NET Standard 2.0 neu zuweisen:</span><span class="sxs-lookup"><span data-stu-id="4cf76-118">You can also retarget .NET Standard libraries to .NET Standard 2.0 the same way:</span></span>

```xml
<PropertyGroup>
    <TargetFramework>netstandard2.0</TargetFramework>
 </PropertyGroup>
```

<span data-ttu-id="4cf76-119">Weitere Informationen zum Migrieren Ihres Projekts zu .NET Core 2.0 finden Sie unter [Migrating from ASP.NET Core 1.x to ASP.NET Core 2.0](/aspnet/core/migration/1x-to-2x/index) (Migrieren von ASP.NET Core 1.x zu ASP.NET Core 2.0).</span><span class="sxs-lookup"><span data-stu-id="4cf76-119">For more information about migrating your project to .NET Core 2.0, see [Migrating from ASP.NET Core 1.x to ASP.NET Core 2.0](/aspnet/core/migration/1x-to-2x/index).</span></span>

## <a name="language-support"></a><span data-ttu-id="4cf76-120">Sprachenunterstützung</span><span class="sxs-lookup"><span data-stu-id="4cf76-120">Language support</span></span>

<span data-ttu-id="4cf76-121">Außer C# und F# unterstützt .NET Core 2.0 auch Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="4cf76-121">In addition to supporting C# and F#, .NET Core 2.0 also supports Visual Basic.</span></span>

### <a name="visual-basic"></a><span data-ttu-id="4cf76-122">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4cf76-122">Visual Basic</span></span>

<span data-ttu-id="4cf76-123">Mit Version 2.0 unterstützt .NET Core jetzt Visual Basic 2017.</span><span class="sxs-lookup"><span data-stu-id="4cf76-123">With version 2.0, .NET Core now supports Visual Basic 2017.</span></span> <span data-ttu-id="4cf76-124">Sie können Visual Basic zum Erstellen folgender Projekttypen verwenden:</span><span class="sxs-lookup"><span data-stu-id="4cf76-124">You can use Visual Basic to create the following project types:</span></span>

- <span data-ttu-id="4cf76-125">.NET Core-Konsolen-Apps</span><span class="sxs-lookup"><span data-stu-id="4cf76-125">.NET Core console apps</span></span>
- <span data-ttu-id="4cf76-126">.NET Core-Klassenbibliotheken</span><span class="sxs-lookup"><span data-stu-id="4cf76-126">.NET Core class libraries</span></span>
- <span data-ttu-id="4cf76-127">.NET Standard-Klassenbibliotheken</span><span class="sxs-lookup"><span data-stu-id="4cf76-127">.NET Standard class libraries</span></span>
- <span data-ttu-id="4cf76-128">.NET Core-Komponententestprojekte</span><span class="sxs-lookup"><span data-stu-id="4cf76-128">.NET Core unit test projects</span></span>
- <span data-ttu-id="4cf76-129">.NET Core-xUnit-Testprojekte</span><span class="sxs-lookup"><span data-stu-id="4cf76-129">.NET Core xUnit test projects</span></span>

<span data-ttu-id="4cf76-130">Führen Sie z.B. zum Erstellen einer „Hello World“-Anwendung in Visual Basic die folgenden Schritte in der Befehlszeile aus:</span><span class="sxs-lookup"><span data-stu-id="4cf76-130">For example, to create a Visual Basic "Hello World" application, do the following steps from the command line:</span></span>

1. <span data-ttu-id="4cf76-131">Öffnen Sie ein Konsolenfenster, erstellen Sie ein Verzeichnis für Ihr Projekt, und machen Sie es zu Ihrem aktuellen Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="4cf76-131">Open a console window, create a directory for your project, and make it the current directory.</span></span>

1. <span data-ttu-id="4cf76-132">Geben Sie den Befehl `dotnet new console -lang vb` ein.</span><span class="sxs-lookup"><span data-stu-id="4cf76-132">Enter the command `dotnet new console -lang vb`.</span></span>

   <span data-ttu-id="4cf76-133">Der Befehl erstellt eine Projektdatei mit einer `.vbproj`-Erweiterung zusammen mit einer Visual Basic-Quellcodedatei mit dem Namen *Program.vb* .</span><span class="sxs-lookup"><span data-stu-id="4cf76-133">The command creates a project file with a `.vbproj` file extension, along with a Visual Basic source code file named *Program.vb* .</span></span> <span data-ttu-id="4cf76-134">Diese Datei enthält den Quellcode, um die Zeichenfolge „Hello World!“</span><span class="sxs-lookup"><span data-stu-id="4cf76-134">This file contains the source code to write the string "Hello World!"</span></span> <span data-ttu-id="4cf76-135">im Konsolenfenster anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="4cf76-135">to the console window.</span></span>

1. <span data-ttu-id="4cf76-136">Geben Sie den Befehl `dotnet run` ein.</span><span class="sxs-lookup"><span data-stu-id="4cf76-136">Enter the command `dotnet run`.</span></span> <span data-ttu-id="4cf76-137">Die [.NET Core-CLI](../tools/index.md) kompiliert die Anwendung automatisch und führt sie aus, um die Meldung „Hallo Welt!“ anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="4cf76-137">The [.NET Core CLI](../tools/index.md) automatically compiles and executes the application, which displays the message "Hello World!"</span></span> <span data-ttu-id="4cf76-138">im Konsolenfenster anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="4cf76-138">in the console window.</span></span>

### <a name="support-for-c-71"></a><span data-ttu-id="4cf76-139">Unterstützung für C# 7.1</span><span class="sxs-lookup"><span data-stu-id="4cf76-139">Support for C# 7.1</span></span>

<span data-ttu-id="4cf76-140">.NET Core 2.0 unterstützt C# 7.1 und wird so durch eine Reihe neuer Funktionen einschließlich der folgenden ergänzt:</span><span class="sxs-lookup"><span data-stu-id="4cf76-140">.NET Core 2.0 supports C# 7.1, which adds a number of new features, including:</span></span>

- <span data-ttu-id="4cf76-141">Die `Main`-Methode, der Einstiegspunkt der Anwendung, kann mit dem [async](../../csharp/language-reference/keywords/async.md)-Schlüsselwort gekennzeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="4cf76-141">The `Main` method, the application entry point, can be marked with the [async](../../csharp/language-reference/keywords/async.md) keyword.</span></span>
- <span data-ttu-id="4cf76-142">Abgeleitete Tupelnamen.</span><span class="sxs-lookup"><span data-stu-id="4cf76-142">Inferred tuple names.</span></span>
- <span data-ttu-id="4cf76-143">Standardausdrücke.</span><span class="sxs-lookup"><span data-stu-id="4cf76-143">Default expressions.</span></span>

<!-- For more information see [link to C# what's new](url). -->

## <a name="platform-improvements"></a><span data-ttu-id="4cf76-144">Plattformverbesserungen</span><span class="sxs-lookup"><span data-stu-id="4cf76-144">Platform improvements</span></span>

<span data-ttu-id="4cf76-145">.NET Core 2.0 umfasst eine Reihe von Funktionen, die das Installieren von .NET Core und die Verwendung auf unterstützten Betriebssystemen erleichtern.</span><span class="sxs-lookup"><span data-stu-id="4cf76-145">.NET Core 2.0 includes a number of features that make it easier to install .NET Core and to use it on supported operating systems.</span></span>

### <a name="net-core-for-linux-is-a-single-implementation"></a><span data-ttu-id="4cf76-146">.NET Core für Linux ist eine einzelne Implementierung.</span><span class="sxs-lookup"><span data-stu-id="4cf76-146">.NET Core for Linux is a single implementation</span></span>

<span data-ttu-id="4cf76-147">.NET Core 2.0 bietet eine einzelne Linux-Implementierung, die für mehrere Linux-Distributionen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="4cf76-147">.NET Core 2.0 offers a single Linux implementation that works on multiple Linux distributions.</span></span> <span data-ttu-id="4cf76-148">.NET Core 1.x setzte das Herunterladen einer distributionsspezifischen Linux-Implementierung voraus.</span><span class="sxs-lookup"><span data-stu-id="4cf76-148">.NET Core 1.x required that you download a distribution-specific Linux implementation.</span></span>

<span data-ttu-id="4cf76-149">Sie können auch Apps entwickeln, die für das Betriebssystem Linux im Allgemeinen vorgesehen sind.</span><span class="sxs-lookup"><span data-stu-id="4cf76-149">You can also develop apps that target Linux as a single operating system.</span></span> <span data-ttu-id="4cf76-150">.NET Core 1.x setzte voraus, dass Sie für jede Linux-Distribution separat entwickeln.</span><span class="sxs-lookup"><span data-stu-id="4cf76-150">.NET Core 1.x required that you target each Linux distribution separately.</span></span>

### <a name="support-for-the-apple-cryptographic-libraries"></a><span data-ttu-id="4cf76-151">Unterstützung der kryptografischen Apple-Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="4cf76-151">Support for the Apple cryptographic libraries</span></span>

<span data-ttu-id="4cf76-152">.NET Core 1.x auf macOS setzte die kryptografische Bibliothek des OpenSSL-Toolkits voraus.</span><span class="sxs-lookup"><span data-stu-id="4cf76-152">.NET Core 1.x on macOS required the OpenSSL toolkit's cryptographic library.</span></span> <span data-ttu-id="4cf76-153">.NET Core 2.0 verwendet die kryptografischen Apple-Bibliotheken und benötigt OpenSSL nicht, sodass Sie auf dessen Installation zukünftig verzichten können.</span><span class="sxs-lookup"><span data-stu-id="4cf76-153">.NET Core 2.0 uses the Apple cryptographic libraries and doesn't require OpenSSL, so you no longer need to install it.</span></span>

## <a name="api-changes-and-library-support"></a><span data-ttu-id="4cf76-154">API-Änderungen und Bibliotheksunterstützung</span><span class="sxs-lookup"><span data-stu-id="4cf76-154">API changes and library support</span></span>

### <a name="support-for-net-standard-20"></a><span data-ttu-id="4cf76-155">Unterstützung für .NET Standard 2.0</span><span class="sxs-lookup"><span data-stu-id="4cf76-155">Support for .NET Standard 2.0</span></span>

<span data-ttu-id="4cf76-156">.NET Standard definiert versionierte APIs, die in allen .NET-Implementierungen verfügbar sein müssen, die dieser Version des Standards entsprechen.</span><span class="sxs-lookup"><span data-stu-id="4cf76-156">.NET Standard defines a versioned set of APIs that must be available on .NET implementations that comply with that version of the standard.</span></span> <span data-ttu-id="4cf76-157">.NET Standard ist auf Bibliotheksentwickler ausgerichtet.</span><span class="sxs-lookup"><span data-stu-id="4cf76-157">.NET Standard is targeted at library developers.</span></span> <span data-ttu-id="4cf76-158">Die Spezifikation soll die Funktionalität garantieren, die einer Bibliothek zur Verfügung steht, die in jeder .NET-Implementierung für eine bestimmte Version von .NET Standard vorgesehen ist.</span><span class="sxs-lookup"><span data-stu-id="4cf76-158">It aims to guarantee the functionality that is available to a library that targets a version of .NET Standard on each .NET implementation.</span></span> <span data-ttu-id="4cf76-159">.NET Core 1.x unterstützt die .NET Standard-Version 1.6, .NET Core 2.0 unterstützt die neueste Version: .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="4cf76-159">.NET Core 1.x supports .NET Standard version 1.6; .NET Core 2.0 supports the latest version, .NET Standard 2.0.</span></span> <span data-ttu-id="4cf76-160">Weitere Informationen finden Sie unter [.NET Standard](../../standard/net-standard.md).</span><span class="sxs-lookup"><span data-stu-id="4cf76-160">For more information, see [.NET Standard](../../standard/net-standard.md).</span></span>

<span data-ttu-id="4cf76-161">.NET Standard 2.0 umfasst mehr als 20.000 APIs, die in .NET Standard 1.6 noch nicht verfügbar waren.</span><span class="sxs-lookup"><span data-stu-id="4cf76-161">.NET Standard 2.0 includes over 20,000 more APIs than were available in .NET Standard 1.6.</span></span> <span data-ttu-id="4cf76-162">Diese Oberflächenerweiterung resultiert zu einem großen Teil aus dem Einbeziehen in .NET Framework und Xamarin üblicher APIs in .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="4cf76-162">Much of this expanded surface area results from incorporating APIs that are common to the .NET Framework and Xamarin into .NET Standard.</span></span>

<span data-ttu-id="4cf76-163">Die Klassenbibliotheken in .NET Standard 2.0 können auch auf .NET Framework-Klassenbibliotheken verweisen. Voraussetzung ist jedoch, dass sie APIs aufrufen, die in .NET Standard 2.0 vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="4cf76-163">.NET Standard 2.0 class libraries can also reference .NET Framework class libraries, provided that they call APIs that are present in .NET Standard 2.0.</span></span> <span data-ttu-id="4cf76-164">Es ist keine Neukompilierung der .NET Framework-Bibliotheken erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4cf76-164">No recompilation of the .NET Framework libraries is required.</span></span>

<span data-ttu-id="4cf76-165">Eine Liste der APIs, die .NET Standard seit der letzten Version (.NET Standard 1.6) hinzugefügt wurden, finden Sie unter [.NET Standard 2.0 im Vergleich zu 1.6](https://raw.githubusercontent.com/dotnet/standard/master/docs/versions/netstandard2.0_diff.md) (.NET Standard 2.0 im Vergleich zu 1.6).</span><span class="sxs-lookup"><span data-stu-id="4cf76-165">For a list of the APIs that have been added to .NET Standard since its last version, .NET Standard 1.6, see [.NET Standard 2.0 vs. 1.6](https://raw.githubusercontent.com/dotnet/standard/master/docs/versions/netstandard2.0_diff.md).</span></span>

### <a name="expanded-surface-area"></a><span data-ttu-id="4cf76-166">Erweiterte Oberfläche</span><span class="sxs-lookup"><span data-stu-id="4cf76-166">Expanded surface area</span></span>

<span data-ttu-id="4cf76-167">Die Gesamtanzahl der in .NET Core 2.0 verfügbaren APIs hat sich im Vergleich zu .NET Core 1.1 mehr als verdoppelt.</span><span class="sxs-lookup"><span data-stu-id="4cf76-167">The total number of APIs available on .NET Core 2.0 has more than doubled in comparison with .NET Core 1.1.</span></span>

<span data-ttu-id="4cf76-168">Und mit dem [Windows Compatibility Pack](../porting/windows-compat-pack.md) ist die Portierung aus .NET Framework ebenfalls viel einfacher geworden.</span><span class="sxs-lookup"><span data-stu-id="4cf76-168">And with the [Windows Compatibility Pack](../porting/windows-compat-pack.md) porting from .NET Framework has also become much simpler.</span></span>

### <a name="support-for-net-framework-libraries"></a><span data-ttu-id="4cf76-169">Unterstützung für .NET Framework-Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="4cf76-169">Support for .NET Framework libraries</span></span>

<span data-ttu-id="4cf76-170">.NET Core-Code kann auf vorhandene .NET Framework-Bibliotheken einschließlich der vorhandenen NuGet-Pakete verweisen.</span><span class="sxs-lookup"><span data-stu-id="4cf76-170">.NET Core code can reference existing .NET Framework libraries, including existing NuGet packages.</span></span> <span data-ttu-id="4cf76-171">Beachten Sie, dass die Bibliotheken APIs verwenden müssen, die im .NET Standard enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="4cf76-171">Note that the libraries must use APIs that are found in .NET Standard.</span></span>

## <a name="visual-studio-integration"></a><span data-ttu-id="4cf76-172">Visual Studio-Integration</span><span class="sxs-lookup"><span data-stu-id="4cf76-172">Visual Studio integration</span></span>

<span data-ttu-id="4cf76-173">Visual Studio 2017 Version 15.3 und in einigen Fällen Visual Studio für Mac bieten eine Reihe erheblicher Verbesserungen für .NET Core-Entwickler.</span><span class="sxs-lookup"><span data-stu-id="4cf76-173">Visual Studio 2017 version 15.3 and in some cases Visual Studio for Mac offer a number of significant enhancements for .NET Core developers.</span></span>

### <a name="retargeting-net-core-apps-and-net-standard-libraries"></a><span data-ttu-id="4cf76-174">Neuzuweisung von .NET Core-Apps und .NET Standard-Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="4cf76-174">Retargeting .NET Core apps and .NET Standard libraries</span></span>

<span data-ttu-id="4cf76-175">Wenn das .NET Core 2.0 SDK installiert ist, können Sie Projekte von .NET Core 1.x zu .NET Core 2.0 und .NET Standard 1.x-Bibliotheken zu .NET-Standard 2.0 neu zuweisen.</span><span class="sxs-lookup"><span data-stu-id="4cf76-175">If the .NET Core 2.0 SDK is installed, you can retarget .NET Core 1.x projects to .NET Core 2.0 and .NET Standard 1.x libraries to .NET Standard 2.0.</span></span>

<span data-ttu-id="4cf76-176">Um Ihr Projekt in Visual Studio neu zuzuweisen, öffnen Sie die Registerkarte **Anwendung** des Eigenschaftendialogfelds des Projekts und ändern den Wert **Zielframework** in **.NET Core 2.0** oder **.NET Standard 2.0** .</span><span class="sxs-lookup"><span data-stu-id="4cf76-176">To retarget your project in Visual Studio, you open the **Application** tab of the project's properties dialog and change the **Target framework** value to **.NET Core 2.0** or **.NET Standard 2.0** .</span></span> <span data-ttu-id="4cf76-177">Sie können es auch ändern, indem Sie mit der rechten Maustaste auf das Projekt klicken und die Option **\*.csproj-Datei bearbeiten** auswählen.</span><span class="sxs-lookup"><span data-stu-id="4cf76-177">You can also change it by right-clicking on the project and selecting the **Edit \*.csproj file** option.</span></span> <span data-ttu-id="4cf76-178">Weitere Informationen finden Sie weiter oben in diesem Thema im Abschnitt [Tools](#tooling).</span><span class="sxs-lookup"><span data-stu-id="4cf76-178">For more information, see the [Tooling](#tooling) section earlier in this topic.</span></span>

### <a name="live-unit-testing-support-for-net-core"></a><span data-ttu-id="4cf76-179">Live Unit Testing-Unterstützung für .NET Core</span><span class="sxs-lookup"><span data-stu-id="4cf76-179">Live Unit Testing support for .NET Core</span></span>

<span data-ttu-id="4cf76-180">Wenn Sie Ihren Code ändern, führt Live Unit Testing automatisch alle betroffenen Komponententests im Hintergrund aus und zeigt die Ergebnisse und die Codeabdeckung in der Visual Studio-Umgebung live an.</span><span class="sxs-lookup"><span data-stu-id="4cf76-180">Whenever you modify your code, Live Unit Testing automatically runs any affected unit tests in the background and displays the results and code coverage live in the Visual Studio environment.</span></span> <span data-ttu-id="4cf76-181">.NET Core 2.0 unterstützt jetzt Live Unit Testing.</span><span class="sxs-lookup"><span data-stu-id="4cf76-181">.NET Core 2.0 now supports Live Unit Testing.</span></span> <span data-ttu-id="4cf76-182">Bisher war Live Unit Testing nur für .NET Framework-Anwendungen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4cf76-182">Previously, Live Unit Testing was available only for .NET Framework applications.</span></span>

<span data-ttu-id="4cf76-183">Weitere Informationen finden Sie unter [Live Unit Testing mit Visual Studio](/visualstudio/test/live-unit-testing) und [Live Unit Testing – häufig gestellte Fragen](/visualstudio/test/live-unit-testing-faq).</span><span class="sxs-lookup"><span data-stu-id="4cf76-183">For more information, see [Live Unit Testing with Visual Studio](/visualstudio/test/live-unit-testing) and the [Live Unit Testing FAQ](/visualstudio/test/live-unit-testing-faq).</span></span>

### <a name="better-support-for-multiple-target-frameworks"></a><span data-ttu-id="4cf76-184">Bessere Unterstützung für mehrere Zielframeworks</span><span class="sxs-lookup"><span data-stu-id="4cf76-184">Better support for multiple target frameworks</span></span>

<span data-ttu-id="4cf76-185">Wenn Sie ein Projekt für mehrere Zielframeworks erstellen, können Sie nun die Zielplattform im Hauptebenenmenü auswählen.</span><span class="sxs-lookup"><span data-stu-id="4cf76-185">If you're building a project for multiple target frameworks, you can now select the target platform from the top-level menu.</span></span> <span data-ttu-id="4cf76-186">In der folgenden Abbildung ist ein Projekt namens „SCD1“ für 64-Bit-macOS X 10.11 (`osx.10.11-x64`) und 64-Bit-Windows 10/Windows Server 2016 (`win10-x64`) bestimmt.</span><span class="sxs-lookup"><span data-stu-id="4cf76-186">In the following figure, a project named SCD1 targets 64-bit macOS X 10.11 (`osx.10.11-x64`) and 64-bit Windows 10/Windows Server 2016 (`win10-x64`).</span></span> <span data-ttu-id="4cf76-187">Sie können das Zielframework vor der Projektschaltfläche auswählen, in diesem Fall zum Ausführen eines Debugbuilds.</span><span class="sxs-lookup"><span data-stu-id="4cf76-187">You can select the target framework before selecting the project button, in this case to run a debug build.</span></span>

![Screenshot mit der Zielframeworkauswahl beim Erstellen eines Projekts](./media/dotnet-core-2-0/target-framework-selection.png)

### <a name="side-by-side-support-for-net-core-sdks"></a><span data-ttu-id="4cf76-189">Parallele Unterstützung für .NET Core-SDKs</span><span class="sxs-lookup"><span data-stu-id="4cf76-189">Side-by-side support for .NET Core SDKs</span></span>

<span data-ttu-id="4cf76-190">Sie können das .NET Core-SDK jetzt unabhängig von Visual Studio installieren.</span><span class="sxs-lookup"><span data-stu-id="4cf76-190">You can now install the .NET Core SDK independently of Visual Studio.</span></span> <span data-ttu-id="4cf76-191">So können mit einer einzelnen Version von Visual Studio Projekte für verschiedene .NET Core-Versionen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="4cf76-191">This makes it possible for a single version of Visual Studio to build projects that target different versions of .NET Core.</span></span> <span data-ttu-id="4cf76-192">Bisher waren Visual Studio und das .NET Core-SDK eng miteinander verbunden; eine bestimmte SDK-Version gehörte zu einer bestimmten Version von Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4cf76-192">Previously, Visual Studio and the .NET Core SDK were tightly coupled; a particular version of the SDK accompanied a particular version of Visual Studio.</span></span>

## <a name="documentation-improvements"></a><span data-ttu-id="4cf76-193">Dokumentationsverbesserungen</span><span class="sxs-lookup"><span data-stu-id="4cf76-193">Documentation improvements</span></span>

### <a name="net-application-architecture"></a><span data-ttu-id="4cf76-194">.NET-Anwendungsarchitektur</span><span class="sxs-lookup"><span data-stu-id="4cf76-194">.NET Application Architecture</span></span>

<span data-ttu-id="4cf76-195">[.NET-Anwendungsarchitektur](https://dotnet.microsoft.com/learn/dotnet/architecture-guides) ermöglicht Ihnen Zugriff auf eine Sammlung von E-Books, die Hilfestellung, bewährte Methoden und Beispielanwendungen zur Verwendung von .NET beim Erstellen folgender Software bieten:</span><span class="sxs-lookup"><span data-stu-id="4cf76-195">[.NET Application Architecture](https://dotnet.microsoft.com/learn/dotnet/architecture-guides) gives you access to a set of e-books that provide guidance, best practices, and sample applications when using .NET to build:</span></span>

- [<span data-ttu-id="4cf76-196">Microservices und Docker-Container</span><span class="sxs-lookup"><span data-stu-id="4cf76-196">Microservices and Docker containers</span></span>](../../architecture/microservices/index.md)
- [<span data-ttu-id="4cf76-197">Webanwendungen mit ASP.NET</span><span class="sxs-lookup"><span data-stu-id="4cf76-197">Web applications with ASP.NET</span></span>](../../architecture/modern-web-apps-azure/index.md)
- [<span data-ttu-id="4cf76-198">Mobile applications with Xamarin (Mobile Anwendungen mit Xamarin)</span><span class="sxs-lookup"><span data-stu-id="4cf76-198">Mobile applications with Xamarin</span></span>](/xamarin/xamarin-forms/enterprise-application-patterns/index)
- [<span data-ttu-id="4cf76-199">Anwendungen, die mit Azure in der Cloud bereitgestellt werden</span><span class="sxs-lookup"><span data-stu-id="4cf76-199">Applications that are deployed to the Cloud with Azure</span></span>](/azure/architecture/reference-architectures/index)

## <a name="see-also"></a><span data-ttu-id="4cf76-200">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4cf76-200">See also</span></span>

- <span data-ttu-id="4cf76-201">[What's new in ASP.NET Core 2.0](/aspnet/core/aspnetcore-2.0) (Neuigkeiten in ASP.NET Core 2.0)</span><span class="sxs-lookup"><span data-stu-id="4cf76-201">[What's new in ASP.NET Core 2.0](/aspnet/core/aspnetcore-2.0)</span></span>
