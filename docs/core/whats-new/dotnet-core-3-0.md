---
title: Neuerungen in .NET Core 3.0
description: Informationen zu den neuen Features in .NET Core 3.0.
dev_langs:
- csharp
- vb
author: thraka
ms.author: adegeo
ms.date: 08/21/2019
ms.openlocfilehash: 5f9d7026b270a010d2ba5d4b1165728a100ab6ed
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69922565"
---
# <a name="whats-new-in-net-core-30-preview-8"></a><span data-ttu-id="4c037-103">Neuerungen in .NET Core 3.0 (Preview 8)</span><span class="sxs-lookup"><span data-stu-id="4c037-103">What's new in .NET Core 3.0 (Preview 8)</span></span>

<span data-ttu-id="4c037-104">In diesem Artikel werden Neuerungen in .NET Core 3.0 (in Preview 8) beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4c037-104">This article describes what is new in .NET Core 3.0 (through preview 8).</span></span> <span data-ttu-id="4c037-105">Eine der wichtigsten Verbesserungen ist die Unterstützung für Windows-Desktopanwendungen (nur Windows).</span><span class="sxs-lookup"><span data-stu-id="4c037-105">One of the biggest enhancements is support for Windows desktop applications (Windows only).</span></span> <span data-ttu-id="4c037-106">Mit der .NET Core 3.0 SDK-Komponente Windows Desktop können Sie Ihre Windows Forms- und WPF-Anwendungen (Windows Presentation Foundation) portieren.</span><span class="sxs-lookup"><span data-stu-id="4c037-106">By using the .NET Core 3.0 SDK component Windows Desktop, you can port your Windows Forms and Windows Presentation Foundation (WPF) applications.</span></span> <span data-ttu-id="4c037-107">Die Windows Desktop-Komponente wird ausdrücklich nur für Windows unterstützt und ist nur unter Windows enthalten.</span><span class="sxs-lookup"><span data-stu-id="4c037-107">To be clear, the Windows Desktop component is only supported and included on Windows.</span></span> <span data-ttu-id="4c037-108">Weitere Informationen finden Sie im Abschnitt [Windows-Desktop](#windows-desktop) weiter unten in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="4c037-108">For more information, see the [Windows desktop](#windows-desktop) section later in this article.</span></span>

<span data-ttu-id="4c037-109">.NET Core 3.0 bietet Unterstützung für C# 8.0.</span><span class="sxs-lookup"><span data-stu-id="4c037-109">.NET Core 3.0 adds support for C# 8.0.</span></span> <span data-ttu-id="4c037-110">Verwenden Sie unbedingt die [neueste Vorschauversion von Visual Studio](https://visualstudio.microsoft.com/vs/preview/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+preview) oder Visual Studio Code mit der OmniSharp-Erweiterung.</span><span class="sxs-lookup"><span data-stu-id="4c037-110">It's highly recommended that you use the [latest release of Visual Studio Preview](https://visualstudio.microsoft.com/vs/preview/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+preview), or Visual Studio Code with the OmniSharp extension.</span></span>

<span data-ttu-id="4c037-111">[Sie können .NET Core 3.0 Preview 8 jetzt für Windows, macOS oder Linux herunterladen und sofort starten.](https://aka.ms/netcore3download)</span><span class="sxs-lookup"><span data-stu-id="4c037-111">[Download and get started with .NET Core 3.0 preview 8](https://aka.ms/netcore3download) right now on Windows, macOS, or Linux.</span></span>

<span data-ttu-id="4c037-112">Weitere Informationen zu den einzelnen Vorschauversionen finden Sie in den folgenden Ankündigungen:</span><span class="sxs-lookup"><span data-stu-id="4c037-112">For more information about each preview release, see the following announcements:</span></span>

- [<span data-ttu-id="4c037-113">Ankündigung von .NET Core 3.0 Preview 8</span><span class="sxs-lookup"><span data-stu-id="4c037-113">.NET Core 3.0 Preview 8 announcement</span></span>](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-0-preview-8/)
- [<span data-ttu-id="4c037-114">Ankündigung von .NET Core 3.0 Preview 7</span><span class="sxs-lookup"><span data-stu-id="4c037-114">.NET Core 3.0 Preview 7 announcement</span></span>](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-0-preview-7/)
- [<span data-ttu-id="4c037-115">Ankündigung von .NET Core 3.0 Vorschauversion 6</span><span class="sxs-lookup"><span data-stu-id="4c037-115">.NET Core 3.0 Preview 6 announcement</span></span>](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-0-preview-6/)
- [<span data-ttu-id="4c037-116">Ankündigung von .NET Core 3.0 Vorschauversion 5</span><span class="sxs-lookup"><span data-stu-id="4c037-116">.NET Core 3.0 Preview 5 announcement</span></span>](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-0-preview-5/)
- [<span data-ttu-id="4c037-117">Ankündigung von .NET Core 3.0 Vorschauversion 4</span><span class="sxs-lookup"><span data-stu-id="4c037-117">.NET Core 3.0 Preview 4 announcement</span></span>](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-preview-4/)
- [<span data-ttu-id="4c037-118">Ankündigung von .NET Core 3.0 Vorschauversion 3</span><span class="sxs-lookup"><span data-stu-id="4c037-118">.NET Core 3.0 Preview 3 announcement</span></span>](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-preview-3/)
- [<span data-ttu-id="4c037-119">.NET Core 3.0 Preview 2 announcement (Ankündigung von .NET Core 3.0 Preview 2)</span><span class="sxs-lookup"><span data-stu-id="4c037-119">.NET Core 3.0 Preview 2 announcement</span></span>](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-preview-2/)
- [<span data-ttu-id="4c037-120">.NET Core 3.0 Preview 1 announcement (Ankündigung von .NET Core 3.0 Preview 1)</span><span class="sxs-lookup"><span data-stu-id="4c037-120">.NET Core 3.0 Preview 1 announcement</span></span>](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-preview-1-and-open-sourcing-windows-desktop-frameworks/)

## <a name="production-supported-preview"></a><span data-ttu-id="4c037-121">Von der Produktion unterstützte Vorschauversion</span><span class="sxs-lookup"><span data-stu-id="4c037-121">Production supported preview</span></span>

<span data-ttu-id="4c037-122">.NET Core Preview 8 wird von Microsoft als produktionsbereit betrachtet und vollständig unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4c037-122">.NET Core Preview 8 is considered production ready by Microsoft and is fully supported.</span></span> <span data-ttu-id="4c037-123">Ab Preview 7 liegt der Fokus bei Releases auf der Optimierung von .NET Core 3.0 und nicht auf dem Hinzuzufügen neuer Features.</span><span class="sxs-lookup"><span data-stu-id="4c037-123">Starting with preview 7, releases will focus on polishing .NET Core 3.0 instead of adding new features.</span></span> <span data-ttu-id="4c037-124">Weitere Informationen zu Änderungen in Preview 8 finden Sie in der [Ankündigung zu .NET Core 3.0 Preview 8](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-0-preview-8/).</span><span class="sxs-lookup"><span data-stu-id="4c037-124">For more information about what has changed in preview 8, see the [preview 8 announcement](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-0-preview-8/).</span></span>

<span data-ttu-id="4c037-125">Wenn Sie eine vorherige Vorschauversion verwenden, müssen Sie für die weitere Unterstützung von „Go Live“ zu Preview 8 wechseln.</span><span class="sxs-lookup"><span data-stu-id="4c037-125">If you're using a previous preview release, you must move to Preview 8 for continued "Go Live" support.</span></span>

## <a name="net-core-sdk-windows-installer"></a><span data-ttu-id="4c037-126">Windows Installer von .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="4c037-126">.NET Core SDK Windows Installer</span></span>

<span data-ttu-id="4c037-127">Das MSI-Installationsprogramm für Windows wurde ab .NET Core 3.0 geändert.</span><span class="sxs-lookup"><span data-stu-id="4c037-127">The MSI installer for Windows has changed starting with .NET Core 3.0.</span></span> <span data-ttu-id="4c037-128">Die SDK-Installer aktualisieren nun vorhandene Releases von SDK-Featuregruppen.</span><span class="sxs-lookup"><span data-stu-id="4c037-128">The SDK installers will now upgrade SDK feature-band releases in place.</span></span> <span data-ttu-id="4c037-129">Featuregruppen werden in den *Hundertergruppen* des *Patchabschnitts* der Versionsnummer definiert.</span><span class="sxs-lookup"><span data-stu-id="4c037-129">Feature bands are defined in the *hundreds* groups in the *patch* section of the version number.</span></span> <span data-ttu-id="4c037-130">**3.0._101_** und **3.0._201_** sind beispielsweise Versionen in zwei verschiedenen Featuregruppen, während sich **3.0._101_** und **3.0._199_** in derselben Featuregruppe befinden.</span><span class="sxs-lookup"><span data-stu-id="4c037-130">For example, **3.0._101_** and **3.0._201_** are versions in two different feature bands while **3.0._101_** and **3.0._199_** are in the same feature band.</span></span> <span data-ttu-id="4c037-131">Wenn .NET Core SDK **3.0._101_** installiert wird, wird .NET Core SDK **3.0._100_** (sofern vorhanden) vom Computer entfernt.</span><span class="sxs-lookup"><span data-stu-id="4c037-131">And, when .NET Core SDK **3.0._101_** is installed, .NET Core SDK **3.0._100_** will be removed from the machine if it exists.</span></span> <span data-ttu-id="4c037-132">Wenn .NET Core SDK **3.0._200_** auf demselben Computer installiert ist, wird .NET Core SDK **3.0._101_** nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="4c037-132">When .NET Core SDK **3.0._200_** is installed on the same machine, .NET Core SDK **3.0._101_** won't be removed.</span></span>

<span data-ttu-id="4c037-133">Weitere Informationen zur Versionsverwaltung finden Sie unter [Übersicht über die .NET Core-Versionsverwaltung](../versions/index.md).</span><span class="sxs-lookup"><span data-stu-id="4c037-133">For more information about versioning, see [Overview of how .NET Core is versioned](../versions/index.md).</span></span>

## <a name="c-80-preview"></a><span data-ttu-id="4c037-134">C# 8.0 Vorschauversion</span><span class="sxs-lookup"><span data-stu-id="4c037-134">C# 8.0 preview</span></span>

<span data-ttu-id="4c037-135">.NET Core 3.0 unterstützt C# 8 Vorschauversion.</span><span class="sxs-lookup"><span data-stu-id="4c037-135">.NET Core 3.0 supports C# 8 preview.</span></span> <span data-ttu-id="4c037-136">Weitere Informationen zu Features von C# 8.0 finden Sie unter [Neues in C# 8.0](../../csharp/whats-new/csharp-8.md).</span><span class="sxs-lookup"><span data-stu-id="4c037-136">For more information about C# 8.0 features, see [What's new in C# 8.0](../../csharp/whats-new/csharp-8.md).</span></span>

## <a name="net-standard-21"></a><span data-ttu-id="4c037-137">.NET Standard 2.1</span><span class="sxs-lookup"><span data-stu-id="4c037-137">.NET Standard 2.1</span></span>

<span data-ttu-id="4c037-138">Obwohl .NET Core 3.0 **.NET Standard 2.1** unterstützt, generiert die Standardvorlage `dotnet new classlib` ein Projekt für **.NET Standard 2.0**.</span><span class="sxs-lookup"><span data-stu-id="4c037-138">Even though .NET Core 3.0 supports **.NET Standard 2.1**, the default `dotnet new classlib` template generates a project that targets **.NET Standard 2.0**.</span></span> <span data-ttu-id="4c037-139">Ändern Sie für **.NET Standard 2.1** in Ihrer Projektdatei die `TargetFramework`-Eigenschaft in `netstandard2.1`:</span><span class="sxs-lookup"><span data-stu-id="4c037-139">To target **.NET Standard 2.1**, edit your project file and change the `TargetFramework` property to `netstandard2.1`:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TargetFramework>netstandard2.1</TargetFramework>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="4c037-140">Wenn Sie Visual Studio verwenden, benötigen Sie [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019), da Visual Studio 2017 **.NET Standard 2.1** und **.NET Core 3.0** nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4c037-140">If you're using Visual Studio, you need [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019), as Visual Studio 2017 doesn't support **.NET Standard 2.1** or **.NET Core 3.0**.</span></span>

## <a name="improved-net-core-version-apis"></a><span data-ttu-id="4c037-141">Verbesserte .NET Core-Versions-APIs</span><span class="sxs-lookup"><span data-stu-id="4c037-141">Improved .NET Core Version APIs</span></span>

<span data-ttu-id="4c037-142">Ab .NET Core 3.0 geben die mit .NET Core gelieferten Versions-APIs jetzt die Informationen zurück, die Sie erwarten.</span><span class="sxs-lookup"><span data-stu-id="4c037-142">Starting with .NET Core 3.0, the version APIs provided with .NET Core now return the information you expect.</span></span> <span data-ttu-id="4c037-143">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="4c037-143">For example:</span></span>

```csharp
System.Console.WriteLine($"Environment.Version: {System.Environment.Version}");

// Old result
//   Environment.Version: 4.0.30319.42000
//
// New result
//   Environment.Version: 3.0.0
```

```csharp
System.Console.WriteLine($"RuntimeInformation.FrameworkDescription: {System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription}");

// Old result
//   RuntimeInformation.FrameworkDescription: .NET Core 4.6.27415.71
//
// New result
//   RuntimeInformation.FrameworkDescription: .NET Core 3.0.0-preview4-27615-11
```

> [!WARNING]
> <span data-ttu-id="4c037-144">Entscheidende Änderung.</span><span class="sxs-lookup"><span data-stu-id="4c037-144">Breaking change.</span></span> <span data-ttu-id="4c037-145">Dies ist technisch gesehen eine entscheidende Änderung, da das Schema der Versionsverwaltung sich geändert hat.</span><span class="sxs-lookup"><span data-stu-id="4c037-145">This is technically a breaking change because the versioning scheme has changed.</span></span>

## <a name="net-platform-dependent-intrinsics"></a><span data-ttu-id="4c037-146">Von der .NET-Plattform abhängige systeminterne Funktionen</span><span class="sxs-lookup"><span data-stu-id="4c037-146">.NET Platform-Dependent Intrinsics</span></span>

<span data-ttu-id="4c037-147">Mit neuen APIs kann auf bestimmte leistungsorientierte CPU-Anweisungen wie **SIMD** oder **Bit Manipulation Instruction Sets** zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="4c037-147">APIs have been added that allow access to certain perf-oriented CPU instructions, such as the **SIMD** or **Bit Manipulation instruction** sets.</span></span> <span data-ttu-id="4c037-148">Diese Anweisungen können in bestimmten Szenarios wie der effizienten parallelen Datenverarbeitung zu deutlichen Leistungssteigerungen führen.</span><span class="sxs-lookup"><span data-stu-id="4c037-148">These instructions can help achieve significant performance improvements in certain scenarios, such as processing data efficiently in parallel.</span></span>

<span data-ttu-id="4c037-149">Wo möglich, haben die .NET-Bibliotheken begonnen, mithilfe dieser Anweisungen die Leistung zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="4c037-149">Where appropriate, the .NET libraries have begun using these instructions to improve performance.</span></span>

<span data-ttu-id="4c037-150">Weitere Informationen finden Sie unter [.NET Platform Dependent Intrinsics](https://github.com/dotnet/designs/blob/master/accepted/platform-intrinsics.md) (Von der .NET-Plattform abhängige systeminterne Funktionen).</span><span class="sxs-lookup"><span data-stu-id="4c037-150">For more information, see [.NET Platform Dependent Intrinsics](https://github.com/dotnet/designs/blob/master/accepted/platform-intrinsics.md).</span></span>

## <a name="default-executables"></a><span data-ttu-id="4c037-151">Standardmäßig ausführbare Dateien</span><span class="sxs-lookup"><span data-stu-id="4c037-151">Default executables</span></span>

<span data-ttu-id="4c037-152">.NET Core erstellt die [frameworkabhängigen ausführbaren Dateien](../deploying/index.md#framework-dependent-executables-fde) jetzt standardmäßig.</span><span class="sxs-lookup"><span data-stu-id="4c037-152">.NET Core now builds [framework-dependent executables](../deploying/index.md#framework-dependent-executables-fde) by default.</span></span> <span data-ttu-id="4c037-153">Dieses Verhalten ist neu für Anwendungen, die eine global installierte Version von .NET Core verwenden.</span><span class="sxs-lookup"><span data-stu-id="4c037-153">This behavior is new for applications that use a globally installed version of .NET Core.</span></span> <span data-ttu-id="4c037-154">Vorher produzierten nur [eigenständige Bereitstellungen](../deploying/index.md#self-contained-deployments-scd) eine ausführbare Datei.</span><span class="sxs-lookup"><span data-stu-id="4c037-154">Previously, only [self-contained deployments](../deploying/index.md#self-contained-deployments-scd) would produce an executable.</span></span>

<span data-ttu-id="4c037-155">Während `dotnet build` oder `dotnet publish` wird eine ausführbare Datei erstellt, die der Umgebung und Plattform des von Ihnen verwendeten SDKs entspricht.</span><span class="sxs-lookup"><span data-stu-id="4c037-155">During `dotnet build` or `dotnet publish`, an executable is created that matches the environment and platform of the SDK you're using.</span></span> <span data-ttu-id="4c037-156">Diese ausführbaren Dateien bieten Ihnen die gleichen Möglichkeiten wie andere native ausführbare Dateien, wie z.B.:</span><span class="sxs-lookup"><span data-stu-id="4c037-156">You can expect the same things with these executables as you would other native executables, such as:</span></span>

- <span data-ttu-id="4c037-157">Sie können die ausführbare Datei doppelklicken.</span><span class="sxs-lookup"><span data-stu-id="4c037-157">You can double-click on the executable.</span></span>
- <span data-ttu-id="4c037-158">Sie können die Anwendung direkt aus einer Eingabeaufforderung starten, z.B. `myapp.exe` unter Windows und `./myapp` unter Linux und MacOS.</span><span class="sxs-lookup"><span data-stu-id="4c037-158">You can launch the application from a command prompt directly, such as `myapp.exe` on Windows, and `./myapp` on Linux and macOS.</span></span>

## <a name="single-file-executables"></a><span data-ttu-id="4c037-159">Ausführbare Einzeldateien</span><span class="sxs-lookup"><span data-stu-id="4c037-159">Single-file executables</span></span>

<span data-ttu-id="4c037-160">Der `dotnet publish`-Befehl unterstützt das Verpacken der App in einer plattformspezifischen ausführbaren Einzeldatei.</span><span class="sxs-lookup"><span data-stu-id="4c037-160">The `dotnet publish` command supports packaging your app into a platform-specific single-file executable.</span></span> <span data-ttu-id="4c037-161">Die ausführbare Datei ist selbstextrahierend und enthält alle Abhängigkeiten (einschließlich der nativen), die zum Ausführen der App erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="4c037-161">The executable is self-extracting and contains all dependencies (including native) that are required to run your app.</span></span> <span data-ttu-id="4c037-162">Beim ersten Ausführen der App wird die Anwendung in ein Verzeichnis extrahiert, das auf dem Namen und dem Buildbezeichner der App basiert.</span><span class="sxs-lookup"><span data-stu-id="4c037-162">When the app is first run, the application is extracted to a directory based on the app name and build identifier.</span></span> <span data-ttu-id="4c037-163">Der Start ist beim erneuten Ausführen der App schneller.</span><span class="sxs-lookup"><span data-stu-id="4c037-163">Startup is faster when the application is run again.</span></span> <span data-ttu-id="4c037-164">Die Anwendung muss sich nicht selbst ein zweites Mal extrahieren, sofern keine neue Version verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4c037-164">The application doesn't need to extract itself a second time unless a new version was used.</span></span>

<span data-ttu-id="4c037-165">Legen Sie zum Veröffentlichen einer einzelnen ausführbaren Datei `PublishSingleFile` in Ihrem Projekt oder in der Befehlszeile mit dem `dotnet publish`-Befehl fest:</span><span class="sxs-lookup"><span data-stu-id="4c037-165">To publish a single-file executable, set the `PublishSingleFile` in your project or on the command line with the `dotnet publish` command:</span></span>

```xml
<PropertyGroup>
  <RuntimeIdentifier>win10-x64</RuntimeIdentifier>
  <PublishSingleFile>true</PublishSingleFile>
</PropertyGroup>
```

<span data-ttu-id="4c037-166">Oder</span><span class="sxs-lookup"><span data-stu-id="4c037-166">-or-</span></span>

```console
dotnet publish -r win10-x64 /p:PublishSingleFile=true
```

<span data-ttu-id="4c037-167">Weitere Informationen zum Veröffentlichen einzelner Dateien finden Sie im [Einzeldatei-Bundler-Entwurfsdokument](https://github.com/dotnet/designs/blob/master/accepted/single-file/design.md).</span><span class="sxs-lookup"><span data-stu-id="4c037-167">For more information about single-file publishing, see the [single-file bundler design document](https://github.com/dotnet/designs/blob/master/accepted/single-file/design.md).</span></span>

## <a name="assembly-linking"></a><span data-ttu-id="4c037-168">Verknüpfen von Assemblys</span><span class="sxs-lookup"><span data-stu-id="4c037-168">Assembly linking</span></span>

<span data-ttu-id="4c037-169">Das.NET Core 3.0 SDK bietet ein Tool, das die Größe von Apps reduzieren kann, indem es IL analysiert und ungenutzte Assemblys trimmt.</span><span class="sxs-lookup"><span data-stu-id="4c037-169">The .NET core 3.0 SDK comes with a tool that can reduce the size of apps by analyzing IL and trimming unused assemblies.</span></span>

<span data-ttu-id="4c037-170">Eigenständige Apps enthalten alles, was zum Ausführen Ihres Codes benötigt wird, ohne dass .NET auf dem Hostcomputer installiert sein muss.</span><span class="sxs-lookup"><span data-stu-id="4c037-170">Self-contained apps include everything needed to run your code, without requiring .NET to be installed on the host computer.</span></span> <span data-ttu-id="4c037-171">Allerdings benötigt die App oft nur eine kleine Teilmenge des Frameworks, um zu funktionieren, sodass andere ungenutzte Bibliotheken entfernt werden können.</span><span class="sxs-lookup"><span data-stu-id="4c037-171">However, many times the app only requires a small subset of the framework to function, and other unused libraries could be removed.</span></span>

<span data-ttu-id="4c037-172">.NET Core bietet nun eine Einstellung, die das Tool [IL linker](https://github.com/mono/linker) verwendet, um die IL Ihrer App zu untersuchen.</span><span class="sxs-lookup"><span data-stu-id="4c037-172">.NET Core now includes a setting that will use the [IL linker](https://github.com/mono/linker) tool to scan the IL of your app.</span></span> <span data-ttu-id="4c037-173">Dieses Tool erkennt, welcher Code benötigt wird, und trimmt dann ungenutzte Bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="4c037-173">this tool detects what code is required, and then trims unused libraries.</span></span> <span data-ttu-id="4c037-174">Es kann die Bereitstellungsgröße einiger Apps deutlich reduzieren.</span><span class="sxs-lookup"><span data-stu-id="4c037-174">This tool can significantly reduce the deployment size of some apps.</span></span>

<span data-ttu-id="4c037-175">Fügen Sie die Einstellung `<PublishTrimmed>` zu Ihrem Projekt hinzu, und veröffentlichen Sie eine eigenständige App, um dieses Tool zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="4c037-175">To enable this tool, add the `<PublishTrimmed>` setting in your project and publish a self-contained app:</span></span>

```xml
<PropertyGroup>
  <PublishTrimmed>true</PublishTrimmed>
</PropertyGroup>
```

```console
dotnet publish -r <rid> -c Release
```

<span data-ttu-id="4c037-176">Als Beispiel erreicht die inbegriffene Standardvorlage für neue Konsolenprojekte „hello world“ bei ihrer Veröffentlichung eine Größe von ca.70 MB.</span><span class="sxs-lookup"><span data-stu-id="4c037-176">As an example, the basic "hello world" new console project template that is included, when published, hits about 70 MB in size.</span></span> <span data-ttu-id="4c037-177">Mithilfe von `<PublishTrimmed>` wird diese Größe auf ca. 30 MB reduziert.</span><span class="sxs-lookup"><span data-stu-id="4c037-177">By using `<PublishTrimmed>`, that size is reduced to about 30 MB.</span></span>

<span data-ttu-id="4c037-178">Wichtig ist die Tatsache, dass Anwendungen oder Frameworks (einschließlich ASP.NET Core und WPF), die Reflektion oder verwandte dynamische Funktionen verwenden, nach dem Trimmen oft nicht mehr funktionieren.</span><span class="sxs-lookup"><span data-stu-id="4c037-178">It's important to consider that applications or frameworks (including ASP.NET Core and WPF) that use reflection or related dynamic features, will often break when trimmed.</span></span> <span data-ttu-id="4c037-179">Dies ist der Fall, weil der Linker von diesem dynamischen Verhalten nichts weiß und nicht bestimmen kann, welche Frameworktypen für die Reflektion benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="4c037-179">This breakage occurs because the linker doesn't know about this dynamic behavior and can't determine which framework types are required for reflection.</span></span> <span data-ttu-id="4c037-180">Das Tool IL Linker kann so konfiguriert werden, dass es sich dieses Szenarios bewusst ist.</span><span class="sxs-lookup"><span data-stu-id="4c037-180">The IL Linker tool can be configured to be aware of this scenario.</span></span>

<span data-ttu-id="4c037-181">Nach dem Trimmen müssen Sie Ihre App unbedingt testen.</span><span class="sxs-lookup"><span data-stu-id="4c037-181">Above all else, be sure to test your app after trimming.</span></span>

<span data-ttu-id="4c037-182">Weitere Informationen zum Tool IL Linker finden Sie in der [Dokumentation](https://aka.ms/dotnet-illink), oder besuchen Sie das Repository [mono/linker]( https://github.com/mono/linker).</span><span class="sxs-lookup"><span data-stu-id="4c037-182">For more information about the IL Linker tool, see the [documentation](https://aka.ms/dotnet-illink) or visit the [mono/linker]( https://github.com/mono/linker) repo.</span></span>

## <a name="tiered-compilation"></a><span data-ttu-id="4c037-183">Mehrstufig Kompilierung</span><span class="sxs-lookup"><span data-stu-id="4c037-183">Tiered compilation</span></span>

<span data-ttu-id="4c037-184">Die [mehrstufige Kompilierung](https://devblogs.microsoft.com/dotnet/tiered-compilation-preview-in-net-core-2-1/) (Tiered Compilation, TC) ist bei .NET Core 3.0 standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="4c037-184">[Tiered compilation](https://devblogs.microsoft.com/dotnet/tiered-compilation-preview-in-net-core-2-1/) (TC) is on by default with .NET Core 3.0.</span></span> <span data-ttu-id="4c037-185">Dieses Feature ermöglicht der Runtime, den Just-In-Time-Compiler (JIT) adaptiver zu nutzen, um eine bessere Leistung zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="4c037-185">This feature enables the runtime to more adaptively use the Just-In-Time (JIT) compiler to get better performance.</span></span>

<span data-ttu-id="4c037-186">Der Hauptvorteil von TC ist, Methoden zur (erneuten) Just-in-Time-Kompilierung mit einer „Lower-Quality-but-faster“- oder „Higher-Quality-but-slower“-Stufe zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="4c037-186">The main benefit of TC is to enable (re-)jitting methods with a lower-quality-but-faster tier or a higher-quality-but-slower tier.</span></span> <span data-ttu-id="4c037-187">Dies steigert die Leistung einer Anwendung, während sie verschiedene Phasen der Ausführung vom Start bis zum stabilen Zustand durchläuft.</span><span class="sxs-lookup"><span data-stu-id="4c037-187">This helps increase performance of an application as it goes through various stages of execution, from startup through steady-state.</span></span> <span data-ttu-id="4c037-188">Dies steht im Gegensatz zum Nicht-TC-Ansatz, wo jede Methode auf eine einzelne Art kompiliert wird (identisch mit der Hochwertigkeitsstufe) und der Trend eher zum stabilen Zustand als zur Startleistung geht.</span><span class="sxs-lookup"><span data-stu-id="4c037-188">This contrasts with the non-TC approach, where every method is compiled a single way (the same as the high-quality tier), which is biased to steady-state over startup performance.</span></span>

<span data-ttu-id="4c037-189">Um schnelle Just-in-Time-Kompilierung (auf Stufe 0 Just-in-Time-kompilierter Code) zu aktivieren, verwenden Sie diese Einstellung in Ihrer Projektdatei:</span><span class="sxs-lookup"><span data-stu-id="4c037-189">To enable Quick JIT (tier 0 jitted code), use this setting in your project file:</span></span>

```xml
<PropertyGroup>
  <TieredCompilationQuickJit>true</TieredCompilationQuickJit>
</PropertyGroup>
```

<span data-ttu-id="4c037-190">Um TC vollständig zu deaktivieren, verwenden Sie diese Einstellung in Ihrer Projektdatei:</span><span class="sxs-lookup"><span data-stu-id="4c037-190">To disable TC completely, use this setting in your project file:</span></span>

```xml
<TieredCompilation>false</TieredCompilation>
```

## <a name="readytorun-images"></a><span data-ttu-id="4c037-191">ReadyToRun-Images</span><span class="sxs-lookup"><span data-stu-id="4c037-191">ReadyToRun images</span></span>

<span data-ttu-id="4c037-192">Sie können die Startzeit Ihrer.NET Core-Anwendung beschleunigen, indem Sie Ihre Anwendungsassemblys im R2R-Format (ReadyToRun) kompilieren.</span><span class="sxs-lookup"><span data-stu-id="4c037-192">You can improve the startup time of your .NET Core application by compiling your application assemblies as ReadyToRun (R2R) format.</span></span> <span data-ttu-id="4c037-193">R2R ist eine Form der AOT-Kompilierung (Ahead-Of-Time).</span><span class="sxs-lookup"><span data-stu-id="4c037-193">R2R is a form of ahead-of-time (AOT) compilation.</span></span>

<span data-ttu-id="4c037-194">R2R-Binärdateien verbessern die Startleistung, indem sie den Arbeitsaufwand des JIT-Compilers (Just-in-time) reduzieren, der anfällt, wenn Ihre Anwendung geladen wird.</span><span class="sxs-lookup"><span data-stu-id="4c037-194">R2R binaries improve startup performance by reducing the amount of work the just-in-time (JIT) compiler needs to do as your application loads.</span></span> <span data-ttu-id="4c037-195">Die Binärdateien enthalten ähnlichen nativen Code im Vergleich zu dem, was der JIT-Compiler produzieren würde.</span><span class="sxs-lookup"><span data-stu-id="4c037-195">The binaries contain similar native code compared to what the JIT would produce.</span></span> <span data-ttu-id="4c037-196">R2R-Binärdateien sind jedoch größer, da sie sowohl IL-Code (Intermediate Language, Zwischensprache), der für einige Szenarios noch benötigt wird, als auch die native Version des gleichen Codes enthalten.</span><span class="sxs-lookup"><span data-stu-id="4c037-196">However, R2R binaries are larger because they contain both intermediate language (IL) code, which is still needed for some scenarios, and the native version of the same code.</span></span> <span data-ttu-id="4c037-197">R2R ist nur verfügbar, wenn Sie eine eigenständige Anwendung veröffentlichen, die eine bestimmte Laufzeitumgebung (RID) wie Linux x64 oder Windows x64 als Ziel hat.</span><span class="sxs-lookup"><span data-stu-id="4c037-197">R2R is only available when you publish a self-contained app that targets specific runtime environments (RID) such as Linux x64 or Windows x64.</span></span>

<span data-ttu-id="4c037-198">Gehen Sie folgendermaßen vor, um Ihr Projekt als „ReadyToRun“ (Bereit zur Ausführung) zu kompilieren:</span><span class="sxs-lookup"><span data-stu-id="4c037-198">To compile your project as ReadyToRun, do the following:</span></span>

01. <span data-ttu-id="4c037-199">Fügen Sie die `<PublishReadyToRun>`-Einstellung in Ihr Projekt ein.</span><span class="sxs-lookup"><span data-stu-id="4c037-199">Add the `<PublishReadyToRun>` setting to your project</span></span>

    ```xml
    <PropertyGroup>
      <PublishReadyToRun>true</PublishReadyToRun>
    </PropertyGroup>
    ```

01. <span data-ttu-id="4c037-200">Veröffentlichen Sie eine eigenständige App.</span><span class="sxs-lookup"><span data-stu-id="4c037-200">Publish a self-contained app.</span></span> <span data-ttu-id="4c037-201">Dieser Befehl erstellt beispielsweise eine eigenständige App für die 64-Bit-Version von Windows:</span><span class="sxs-lookup"><span data-stu-id="4c037-201">For example, this command creates a self-contained app for the 64-bit version of Windows:</span></span>

    ```console
    dotnet publish -c Release -r win-x64 --self-contained true
    ```

### <a name="cross-platformarchitecture-restrictions"></a><span data-ttu-id="4c037-202">Plattformübergreifende bzw. architekturbezogene Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="4c037-202">Cross platform/architecture restrictions</span></span>

<span data-ttu-id="4c037-203">Der ReadyToRun-Compiler unterstützt derzeit nicht die versionsübergreifende Angabe von Zielen.</span><span class="sxs-lookup"><span data-stu-id="4c037-203">The ReadyToRun compiler doesn't currently support cross-targeting.</span></span> <span data-ttu-id="4c037-204">Die Kompilierung muss für ein bestimmtes Ziel erfolgen.</span><span class="sxs-lookup"><span data-stu-id="4c037-204">You must compile on a given target.</span></span> <span data-ttu-id="4c037-205">Wenn Sie beispielsweise R2R-Images für Windows x64 benötigen, müssen Sie den Veröffentlichungsbefehl in dieser Umgebung ausführen.</span><span class="sxs-lookup"><span data-stu-id="4c037-205">For example, if you want R2R images for Windows x64, you need to run the publish command on that environment.</span></span>

<span data-ttu-id="4c037-206">Ausnahmen für die versionsübergreifende Angabe von Zielen:</span><span class="sxs-lookup"><span data-stu-id="4c037-206">Exceptions to cross-targeting:</span></span>

- <span data-ttu-id="4c037-207">Windows x64 kann verwendet werden, um Windows ARM32-, ARM64- und x86-Images zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="4c037-207">Windows x64 can be used to compile Windows ARM32, ARM64, and x86 images.</span></span>
- <span data-ttu-id="4c037-208">Windows x86 kann verwendet werden, um Windows ARM32-Images zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="4c037-208">Windows x86 can be used to compile Windows ARM32 images.</span></span>
- <span data-ttu-id="4c037-209">Linux X64 kann verwendet werden, um Linux ARM32- und -ARM64-Images zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="4c037-209">Linux x64 can be used to compile Linux ARM32 and ARM64 images.</span></span>

## <a name="build-copies-dependencies"></a><span data-ttu-id="4c037-210">Build kopiert Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="4c037-210">Build copies dependencies</span></span>

<span data-ttu-id="4c037-211">Der `dotnet build`-Befehl kopiert jetzt NuGet-Abhängigkeiten für Ihre Anwendung aus dem NuGet-Cache in den Buildausgabeordner.</span><span class="sxs-lookup"><span data-stu-id="4c037-211">The `dotnet build` command now copies NuGet dependencies for your application from the NuGet cache to the build output folder.</span></span> <span data-ttu-id="4c037-212">Bisher wurde Abhängigkeiten nur als Teil von `dotnet publish` kopiert.</span><span class="sxs-lookup"><span data-stu-id="4c037-212">Previously, dependencies were only copied as part of `dotnet publish`.</span></span>

<span data-ttu-id="4c037-213">Es gibt einige Vorgänge, wie das Verlinken und das Veröffentlichen von Razor-Seiten, die noch veröffentlicht werden müssen.</span><span class="sxs-lookup"><span data-stu-id="4c037-213">There are some operations, like linking and razor page publishing that will still require publishing.</span></span>

## <a name="local-tools"></a><span data-ttu-id="4c037-214">Lokale Tools</span><span class="sxs-lookup"><span data-stu-id="4c037-214">Local tools</span></span>

<span data-ttu-id="4c037-215">Mit .NET Core 3.0 werden lokale Tools eingeführt.</span><span class="sxs-lookup"><span data-stu-id="4c037-215">.NET Core 3.0 introduces local tools.</span></span> <span data-ttu-id="4c037-216">Lokale Tools ähneln [globalen Tools](../tools/global-tools.md), sind aber mit einem bestimmten Speicherort auf dem Datenträger verknüpft.</span><span class="sxs-lookup"><span data-stu-id="4c037-216">Local tools are similar to [global tools](../tools/global-tools.md) but are associated with a particular location on disk.</span></span> <span data-ttu-id="4c037-217">Lokale Tools sind nicht global verfügbar und werden als NuGet-Pakete verteilt.</span><span class="sxs-lookup"><span data-stu-id="4c037-217">Local tools aren't available globally and are distributed as NuGet packages.</span></span>

> [!WARNING]
> <span data-ttu-id="4c037-218">Wenn Sie lokale Tools in .NET Core 3.0 Preview 1 ausprobiert haben, z.B. Ausführung von `dotnet tool restore` oder `dotnet tool install`, löschen Sie den Cacheordner der lokalen Tools.</span><span class="sxs-lookup"><span data-stu-id="4c037-218">If you tried local tools in .NET Core 3.0 Preview 1, such as running `dotnet tool restore` or `dotnet tool install`, delete the local tools cache folder.</span></span> <span data-ttu-id="4c037-219">Andernfalls funktionieren die lokalen Tools nicht in einem neueren Release.</span><span class="sxs-lookup"><span data-stu-id="4c037-219">Otherwise, local tools won't work on any newer release.</span></span> <span data-ttu-id="4c037-220">Je nach Betriebssystem werden die Ordnerpfade wie folgt gelöscht:</span><span class="sxs-lookup"><span data-stu-id="4c037-220">This folder is located at:</span></span>
>
> <span data-ttu-id="4c037-221">Unter macOS, Linux: `rm -r $HOME/.dotnet/toolResolverCache`</span><span class="sxs-lookup"><span data-stu-id="4c037-221">On macOS, Linux: `rm -r $HOME/.dotnet/toolResolverCache`</span></span>
>
> <span data-ttu-id="4c037-222">Windows: `rmdir /s %USERPROFILE%\.dotnet\toolResolverCache`</span><span class="sxs-lookup"><span data-stu-id="4c037-222">On Windows: `rmdir /s %USERPROFILE%\.dotnet\toolResolverCache`</span></span>

<span data-ttu-id="4c037-223">Lokale Tools basieren auf einer Manifestdatei `dotnet-tools.json` in Ihrem aktuellen Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="4c037-223">Local tools rely on a manifest file name `dotnet-tools.json` in your current directory.</span></span> <span data-ttu-id="4c037-224">In dieser Manifestdatei werden die Tools festgelegt, die im Verzeichnis und in den Unterverzeichnissen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="4c037-224">This manifest file defines the tools to be available at that folder and below.</span></span> <span data-ttu-id="4c037-225">Sie können die Manifestdatei mit dem Code verteilen, um sicherzustellen, dass jeder Benutzer, der mit Ihrem Code arbeitet, dieselben Tools wiederherstellen und verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="4c037-225">You can distribute the manifest file with your code to ensure that anyone who works with your code can restore and use the same tools.</span></span>

<span data-ttu-id="4c037-226">Für sowohl globale als auch lokale Tools ist eine kompatible Version der Runtime erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4c037-226">For both global and local tools, a compatible version of the runtime is required.</span></span> <span data-ttu-id="4c037-227">Die meisten Tools führen derzeit NuGet.org target .NET Core Runtime 2.1 aus.</span><span class="sxs-lookup"><span data-stu-id="4c037-227">Many tools currently on NuGet.org target .NET Core Runtime 2.1.</span></span> <span data-ttu-id="4c037-228">Um diese Tools global oder lokal zu installieren, müssten Sie weiterhin die [NET Core 2.1-Runtime](https://dotnet.microsoft.com/download/dotnet-core/2.1) installieren.</span><span class="sxs-lookup"><span data-stu-id="4c037-228">To install these tools globally or locally, you would still need to install the [NET Core 2.1 Runtime](https://dotnet.microsoft.com/download/dotnet-core/2.1).</span></span>

## <a name="major-version-roll-forward"></a><span data-ttu-id="4c037-229">Rollforward der Hauptversion</span><span class="sxs-lookup"><span data-stu-id="4c037-229">Major-version Roll Forward</span></span>

<span data-ttu-id="4c037-230">Mit .NET Core 3.0 wird ein Aktivierungsfeature eingeführt, das Ihrer App ein Rollforward auf die neueste Hauptversion von .NET Core ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="4c037-230">.NET Core 3.0 introduces an opt-in feature that allows your app to roll forward to the latest major version of .NET Core.</span></span> <span data-ttu-id="4c037-231">Darüber hinaus wurde eine neue Einstellung hinzugefügt, um zu steuern, wie ein Rollforward auf Ihre App angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="4c037-231">Additionally, a new setting has been added to control how roll forward is applied to your app.</span></span> <span data-ttu-id="4c037-232">Diese kann folgendermaßen konfiguriert werden:</span><span class="sxs-lookup"><span data-stu-id="4c037-232">This can be configured in the following ways:</span></span>

- <span data-ttu-id="4c037-233">Projektdateieigenschaft: `RollForward`</span><span class="sxs-lookup"><span data-stu-id="4c037-233">Project file property: `RollForward`</span></span>
- <span data-ttu-id="4c037-234">Runtimekonfigurationsdatei-Eigenschaft: `rollForward`</span><span class="sxs-lookup"><span data-stu-id="4c037-234">Runtime configuration file property: `rollForward`</span></span>
- <span data-ttu-id="4c037-235">Umgebungsvariable: `DOTNET_ROLL_FORWARD`</span><span class="sxs-lookup"><span data-stu-id="4c037-235">Environment variable: `DOTNET_ROLL_FORWARD`</span></span>
- <span data-ttu-id="4c037-236">Befehlszeilenargument: `--roll-forward`</span><span class="sxs-lookup"><span data-stu-id="4c037-236">Command-line argument: `--roll-forward`</span></span>

<span data-ttu-id="4c037-237">Einer der folgenden Werte muss angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="4c037-237">One of the following values must be specified.</span></span> <span data-ttu-id="4c037-238">Wenn die Einstellung ausgelassen wird, ist **Minor** die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="4c037-238">If the setting is omitted, **Minor** is the default.</span></span>

- <span data-ttu-id="4c037-239">**LatestPatch**</span><span class="sxs-lookup"><span data-stu-id="4c037-239">**LatestPatch**</span></span>\
<span data-ttu-id="4c037-240">Rollforward zur höchsten Patchversion.</span><span class="sxs-lookup"><span data-stu-id="4c037-240">Roll forward to the highest patch version.</span></span> <span data-ttu-id="4c037-241">Dies deaktiviert ein Rollforward zur Nebenversion.</span><span class="sxs-lookup"><span data-stu-id="4c037-241">This disables minor version roll forward.</span></span>
- <span data-ttu-id="4c037-242">**Minor**</span><span class="sxs-lookup"><span data-stu-id="4c037-242">**Minor**</span></span>\
<span data-ttu-id="4c037-243">Rollforward zur niedrigsten höheren Nebenversion, wenn die angeforderte Nebenversion nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="4c037-243">Roll forward to the lowest higher minor version, if requested minor version is missing.</span></span> <span data-ttu-id="4c037-244">Wenn die angeforderte Nebenversion vorhanden ist, wird die **LatestPatch**-Richtlinie verwendet.</span><span class="sxs-lookup"><span data-stu-id="4c037-244">If the requested minor version is present, then the **LatestPatch** policy is used.</span></span>
- <span data-ttu-id="4c037-245">**Major**</span><span class="sxs-lookup"><span data-stu-id="4c037-245">**Major**</span></span>\
<span data-ttu-id="4c037-246">Rollforward zur niedrigsten höheren Hauptversion – und niedrigsten Nebenversion, wenn die angeforderte Hauptversion nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="4c037-246">Roll forward to lowest higher major version, and lowest minor version, if requested major version is missing.</span></span> <span data-ttu-id="4c037-247">Wenn die angeforderte Hauptversion vorhanden ist, wird die **Minor**-Richtlinie verwendet.</span><span class="sxs-lookup"><span data-stu-id="4c037-247">If the requested major version is present, then the **Minor** policy is used.</span></span>
- <span data-ttu-id="4c037-248">**LatestMinor**</span><span class="sxs-lookup"><span data-stu-id="4c037-248">**LatestMinor**</span></span>\
<span data-ttu-id="4c037-249">Rollforward zur höchsten Nebenversion – auch dann, wenn die angeforderte Nebenversion vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="4c037-249">Roll forward to highest minor version, even if requested minor version is present.</span></span> <span data-ttu-id="4c037-250">Für Komponentenhostingszenarien vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="4c037-250">Intended for component hosting scenarios.</span></span>
- <span data-ttu-id="4c037-251">**LatestMajor**</span><span class="sxs-lookup"><span data-stu-id="4c037-251">**LatestMajor**</span></span>\
<span data-ttu-id="4c037-252">Rollforward zur höchsten Hauptversion und höchsten Nebenversion – auch dann, wenn die angeforderte Hauptversion vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="4c037-252">Roll forward to highest major and highest minor version, even if requested major is present.</span></span> <span data-ttu-id="4c037-253">Für Komponentenhostingszenarien vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="4c037-253">Intended for component hosting scenarios.</span></span>
- <span data-ttu-id="4c037-254">**Disable**</span><span class="sxs-lookup"><span data-stu-id="4c037-254">**Disable**</span></span>\
<span data-ttu-id="4c037-255">Kein Rollforward.</span><span class="sxs-lookup"><span data-stu-id="4c037-255">Don't roll forward.</span></span> <span data-ttu-id="4c037-256">Nur Binden an angegebene Version.</span><span class="sxs-lookup"><span data-stu-id="4c037-256">Only bind to specified version.</span></span> <span data-ttu-id="4c037-257">Diese Richtlinie wird nicht zur allgemeinen Verwendung empfohlen, da sie die Möglichkeit eines Rollforwards zu den neuesten Patches ausschließt.</span><span class="sxs-lookup"><span data-stu-id="4c037-257">This policy isn't recommended for general use because it disables the ability to roll forward to the latest patches.</span></span> <span data-ttu-id="4c037-258">Dieser Wert wird nur zu Testzwecken empfohlen.</span><span class="sxs-lookup"><span data-stu-id="4c037-258">This value is only recommended for testing.</span></span>

<span data-ttu-id="4c037-259">Abgesehen von der **Disable**-Einstellung verwenden alle Einstellungen die höchste verfügbare Patchversion.</span><span class="sxs-lookup"><span data-stu-id="4c037-259">Besides the **Disable** setting, all settings will use the highest available patch version.</span></span>

## <a name="windows-desktop"></a><span data-ttu-id="4c037-260">Windows-Desktop</span><span class="sxs-lookup"><span data-stu-id="4c037-260">Windows desktop</span></span>

<span data-ttu-id="4c037-261">.NET Core 3.0 unterstützt die Windows-Desktopanwendungen mit Windows Presentation Foundation (WPF) und Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="4c037-261">.NET Core 3.0 supports Windows desktop applications using Windows Presentation Foundation (WPF) and Windows Forms.</span></span> <span data-ttu-id="4c037-262">Diese Frameworks unterstützt auch die Verwendung moderner Steuerelemente und des Fluent-Stils aus der Windows-UI-XAML-Bibliothek (WinUI) über [XAML-Inseln](/windows/uwp/xaml-platform/xaml-host-controls).</span><span class="sxs-lookup"><span data-stu-id="4c037-262">These frameworks also support using modern controls and Fluent styling from the Windows UI XAML Library (WinUI) via [XAML islands](/windows/uwp/xaml-platform/xaml-host-controls).</span></span>

<span data-ttu-id="4c037-263">Die Windows Desktop-Komponente ist Teil des Windows .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="4c037-263">The Windows Desktop component is part of the Windows .NET Core 3.0 SDK.</span></span>

<span data-ttu-id="4c037-264">Mit dem folgenden `dotnet`-Befehl können Sie eine neue WPF- oder Windows Forms-Anwendung erstellen:</span><span class="sxs-lookup"><span data-stu-id="4c037-264">You can create a new WPF or Windows Forms app with the following `dotnet` commands:</span></span>

```console
dotnet new wpf
dotnet new winforms
```

<span data-ttu-id="4c037-265">Neu in Visual Studio 2019 sind Vorlagen für die Option **Neues Projekt** für Windows Forms und WPF in .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="4c037-265">Visual Studio 2019 adds **New Project** templates for .NET Core 3.0 Windows Forms and WPF.</span></span>

<span data-ttu-id="4c037-266">Weitere Informationen zum Portieren einer vorhandenen .NET Framework-Anwendung finden Sie unter [Portieren von WPF-Projekten](../porting/wpf.md) und [Portieren von Windows Forms-Projekten](../porting/winforms.md).</span><span class="sxs-lookup"><span data-stu-id="4c037-266">For more information about how to port an existing .NET Framework application, see [Port WPF projects](../porting/wpf.md) and [Port Windows Forms projects](../porting/winforms.md).</span></span>

## <a name="com-callable-components---windows-desktop"></a><span data-ttu-id="4c037-267">COM-aufrufbare Komponenten – Windows-Desktop</span><span class="sxs-lookup"><span data-stu-id="4c037-267">COM-callable components - Windows Desktop</span></span>

<span data-ttu-id="4c037-268">Unter Windows können Sie jetzt COM-aufrufbare verwaltete Komponenten erstellen.</span><span class="sxs-lookup"><span data-stu-id="4c037-268">On Windows, you can now create COM-callable managed components.</span></span> <span data-ttu-id="4c037-269">Diese Funktion ist für die Verwendung von .NET Core mit COM-Add-in-Modellen und auch zur Parität mit .NET Framework wichtig.</span><span class="sxs-lookup"><span data-stu-id="4c037-269">This capability is critical to use .NET Core with COM add-in models and also to provide parity with .NET Framework.</span></span>

<span data-ttu-id="4c037-270">Im Gegensatz zu .NET Framework, wo *mscoree.dll* als COM-Server verwendet wurde, fügt .NET Core dem *bin*-Verzeichnis eine native Startprogramm-DLL hinzu, wenn Sie Ihre COM-Komponente erstellen.</span><span class="sxs-lookup"><span data-stu-id="4c037-270">Unlike .NET Framework where the *mscoree.dll* was used as the COM server, .NET Core will add a native launcher dll to the *bin* directory when you build your COM component.</span></span>

<span data-ttu-id="4c037-271">Ein Beispiel für das Erstellen einer COM‑Komponente und ihre Verwendung finden Sie in der [COM-Demo](https://github.com/dotnet/samples/tree/master/core/extensions/COMServerDemo).</span><span class="sxs-lookup"><span data-stu-id="4c037-271">For an example of how to create a COM component and consume it, see the [COM Demo](https://github.com/dotnet/samples/tree/master/core/extensions/COMServerDemo).</span></span>

## <a name="msix-deployment---windows-desktop"></a><span data-ttu-id="4c037-272">MSIX-Bereitstellung – Windows-Desktop</span><span class="sxs-lookup"><span data-stu-id="4c037-272">MSIX Deployment - Windows Desktop</span></span>

<span data-ttu-id="4c037-273">[MSIX](https://docs.microsoft.com/windows/msix/) ist ein neues Windows-Anwendungspaketformat.</span><span class="sxs-lookup"><span data-stu-id="4c037-273">[MSIX](https://docs.microsoft.com/windows/msix/) is a new Windows application package format.</span></span> <span data-ttu-id="4c037-274">Es kann zum Bereitstellen von .NET Core 3.0-Desktopanwendungen auf Windows 10 verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4c037-274">It can be used to deploy .NET Core 3.0 desktop applications to Windows 10.</span></span>

<span data-ttu-id="4c037-275">In Visual Studio 2019 können mit dem enthaltenen [Paketerstellungsprojekt für Windows-Anwendungen](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-packaging-dot-net) MSIX-Pakete mit [eigenständigen](../deploying/index.md#self-contained-deployments-scd) .NET Core-Anwendungen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="4c037-275">The [Windows Application Packaging Project](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-packaging-dot-net), available in Visual Studio 2019, allows you to create MSIX packages with [self-contained](../deploying/index.md#self-contained-deployments-scd) .NET Core applications.</span></span>

<span data-ttu-id="4c037-276">Die unterstützten Laufzeiten müssen in der `<RuntimeIdentifiers>`-Eigenschaft der .NET Core-Projektdatei angegeben werden:</span><span class="sxs-lookup"><span data-stu-id="4c037-276">The .NET Core project file must specify the supported runtimes in the `<RuntimeIdentifiers>` property:</span></span>

```xml
<RuntimeIdentifiers>win-x86;win-x64</RuntimeIdentifiers>
```

## <a name="winforms-high-dpi"></a><span data-ttu-id="4c037-277">WinForms mit hohem DPI-Wert</span><span class="sxs-lookup"><span data-stu-id="4c037-277">WinForms high DPI</span></span>

<span data-ttu-id="4c037-278">.NET Core-Windows Forms-Anwendungen können den Modus für hohe DPI-Werte mit <xref:System.Windows.Forms.Application.SetHighDpiMode(System.Windows.Forms.HighDpiMode)?displayProperty=nameWithType> festlegen.</span><span class="sxs-lookup"><span data-stu-id="4c037-278">.NET Core Windows Forms applications can set high DPI mode with <xref:System.Windows.Forms.Application.SetHighDpiMode(System.Windows.Forms.HighDpiMode)?displayProperty=nameWithType>.</span></span> <span data-ttu-id="4c037-279">Die `SetHighDpiMode`-Methode legt den entsprechenden Modus für hohe DPI-Werte fest, sofern er nicht mit anderen Mitteln wie `App.Manifest` oder „P/Invoke“ vor dem `Application.Run` festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="4c037-279">The `SetHighDpiMode` method sets the corresponding high DPI mode unless the setting has been set by other means like `App.Manifest` or P/Invoke before `Application.Run`.</span></span>

<span data-ttu-id="4c037-280">Die möglichen `highDpiMode`-Werte, wie durch die <xref:System.Windows.Forms.HighDpiMode?displayProperty=nameWithType>-Enumeration ausgedrückt, sind:</span><span class="sxs-lookup"><span data-stu-id="4c037-280">The possible `highDpiMode` values, as expressed by the <xref:System.Windows.Forms.HighDpiMode?displayProperty=nameWithType> enum are:</span></span>

- `DpiUnaware`
- `SystemAware`
- `PerMonitor`
- `PerMonitorV2`
- `DpiUnawareGdiScaled`

<span data-ttu-id="4c037-281">Weitere Informationen zu hohen DPI-Werten finden Sie unter [Entwicklung von Desktopanwendungen mit hohen DPI-Werten unter Windows](/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows).</span><span class="sxs-lookup"><span data-stu-id="4c037-281">For more information about high DPI modes, see [High DPI Desktop Application Development on Windows](/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows).</span></span>

## <a name="ranges-and-indices"></a><span data-ttu-id="4c037-282">Bereiche und Indizes</span><span class="sxs-lookup"><span data-stu-id="4c037-282">Ranges and indices</span></span>

<span data-ttu-id="4c037-283">Der neue <xref:System.Index?displayProperty=nameWithType>-Typ kann für die Indizierung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4c037-283">The new <xref:System.Index?displayProperty=nameWithType> type can be used for indexing.</span></span> <span data-ttu-id="4c037-284">Sie können einen aus einem `int` erstellen, der vom Anfang aus zählt, oder mit einem Präfix-`^`-Operator (C#), der vom Ende aus zählt:</span><span class="sxs-lookup"><span data-stu-id="4c037-284">You can create one from an `int` that counts from the beginning, or with a prefix `^` operator (C#) that counts from the end:</span></span>

```csharp
Index i1 = 3;  // number 3 from beginning
Index i2 = ^4; // number 4 from end
int[] a = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };
Console.WriteLine($"{a[i1]}, {a[i2]}"); // "3, 6"
```

<span data-ttu-id="4c037-285">Es gibt auch einen <xref:System.Range?displayProperty=nameWithType>-Typ, der aus zwei `Index`-Werten besteht, einen für den Anfang und einen für das Ende, und mit einem `x..y`-Bereichsausdruck (C#) geschrieben werden kann.</span><span class="sxs-lookup"><span data-stu-id="4c037-285">There's also the <xref:System.Range?displayProperty=nameWithType> type, which consists of two `Index` values, one for the start and one for the end, and can be written with a `x..y` range expression (C#).</span></span> <span data-ttu-id="4c037-286">Sie können dann mit einem `Range` indizieren, der ein Segment erzeugt:</span><span class="sxs-lookup"><span data-stu-id="4c037-286">You can then index with a `Range`, which produces a slice:</span></span>

```csharp
var slice = a[i1..i2]; // { 3, 4, 5 }
```

<span data-ttu-id="4c037-287">Weitere Informationen finden Sie im Tutorial [Bereiche und Indizes](../../csharp/tutorials/ranges-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="4c037-287">For more information, see the [ranges and indices tutorial](../../csharp/tutorials/ranges-indexes.md).</span></span>

## <a name="async-streams"></a><span data-ttu-id="4c037-288">Asynchrone Datenströme</span><span class="sxs-lookup"><span data-stu-id="4c037-288">Async streams</span></span>

<span data-ttu-id="4c037-289">Die <xref:System.Collections.Generic.IAsyncEnumerable%601>-Typ ist eine neue asynchrone Version von <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="4c037-289">The <xref:System.Collections.Generic.IAsyncEnumerable%601> type is a new asynchronous version of <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="4c037-290">In C# 8.0 können Sie `await foreach` zur Verarbeitung der `IAsyncEnumerable<T>`-Elemente nutzen und anschließend `yield return` zum Erstellen von Elementen verwenden.</span><span class="sxs-lookup"><span data-stu-id="4c037-290">The language lets you `await foreach` over `IAsyncEnumerable<T>` to consume their elements, and use `yield return` to them to produce elements.</span></span>

<span data-ttu-id="4c037-291">Das folgende Beispiel zeigt sowohl die Produktion als auch die Nutzung von asynchronen Datenströmen.</span><span class="sxs-lookup"><span data-stu-id="4c037-291">The following example demonstrates both production and consumption of async streams.</span></span> <span data-ttu-id="4c037-292">Die `foreach`-Anweisung ist asynchron und verwendet `yield return`, um einen asynchronen Datenstrom für Anrufer zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4c037-292">The `foreach` statement is async and itself uses `yield return` to produce an async stream for callers.</span></span> <span data-ttu-id="4c037-293">Dieses Muster (mit `yield return`) ist das empfohlene Modell zum Erstellen von asynchronen Datenströmen.</span><span class="sxs-lookup"><span data-stu-id="4c037-293">This pattern (using `yield return`) is the recommended model for producing async streams.</span></span>

```csharp
async IAsyncEnumerable<int> GetBigResultsAsync()
{
    await foreach (var result in GetResultsAsync())
    {
        if (result > 20) yield return result;
    }
}
```

<span data-ttu-id="4c037-294">Zusätzlich zu `await foreach` können Sie auch asynchrone Iteratoren erstellen, z.B. einen Iterator, der `IAsyncEnumerable/IAsyncEnumerator` zurückgibt, in den Sie sowohl `await` als auch `yield` einfügen können.</span><span class="sxs-lookup"><span data-stu-id="4c037-294">In addition to being able to `await foreach`, you can also create async iterators, for example, an iterator that returns an `IAsyncEnumerable/IAsyncEnumerator` that you can both `await` and `yield` in.</span></span> <span data-ttu-id="4c037-295">Für Objekte, die gelöscht werden müssen, können Sie `IAsyncDisposable` verwenden, das von verschiedenen BCL-Typen implementiert wird, wie beispielsweise `Stream` und `Timer`.</span><span class="sxs-lookup"><span data-stu-id="4c037-295">For objects that need to be disposed, you can use `IAsyncDisposable`, which various BCL types implement, such as `Stream` and `Timer`.</span></span>

<span data-ttu-id="4c037-296">Weitere Informationen finden Sie im Tutorial [Generieren und Nutzen asynchroner Datenströme mit C# 8.0 und .NET Core 3.0](../../csharp/tutorials/generate-consume-asynchronous-stream.md).</span><span class="sxs-lookup"><span data-stu-id="4c037-296">For more information, see the [async streams tutorial](../../csharp/tutorials/generate-consume-asynchronous-stream.md).</span></span>

## <a name="ieee-floating-point-improvements"></a><span data-ttu-id="4c037-297">Verbesserungen bei Gleitkommazahlen gemäß IEEE-Spezifikation</span><span class="sxs-lookup"><span data-stu-id="4c037-297">IEEE Floating-point improvements</span></span>

<span data-ttu-id="4c037-298">APIs für Gleitkommazahlen werden aktuell der [Revision des Standards IEEE 754-2008](https://en.wikipedia.org/wiki/IEEE_754-2008_revision) angepasst.</span><span class="sxs-lookup"><span data-stu-id="4c037-298">Floating point APIs are being updated to comply with [IEEE 754-2008 revision](https://en.wikipedia.org/wiki/IEEE_754-2008_revision).</span></span> <span data-ttu-id="4c037-299">Ziel dieser Änderungen ist, alle **erforderlichen** Operationen verfügbar zu machen und sicherzustellen, dass sie mit dem in der IEEE-Spezifikation beschriebenen Verhalten kompatibel sind. Weitere Informationen über Gleitkommaverbesserungen finden Sie im Blogbeitrag [Floating-Point Parsing and Formatting improvements in .NET Core 3.0](https://devblogs.microsoft.com/dotnet/floating-point-parsing-and-formatting-improvements-in-net-core-3-0/) (Verbesserungen zu Gleitkommaanalyse und Formatierung in .NET Core 3.0).</span><span class="sxs-lookup"><span data-stu-id="4c037-299">The goal of these changes is to expose all **required** operations and ensure that they're behaviorally compliant with the IEEE spec. For more information about floating-point improvements, see the [Floating-Point Parsing and Formatting improvements in .NET Core 3.0](https://devblogs.microsoft.com/dotnet/floating-point-parsing-and-formatting-improvements-in-net-core-3-0/) blog post.</span></span>

<span data-ttu-id="4c037-300">Zu den Korrekturen für Analyse und Formatierung zählen:</span><span class="sxs-lookup"><span data-stu-id="4c037-300">Parsing and formatting fixes include:</span></span>

- <span data-ttu-id="4c037-301">Eingaben mit beliebiger Länge werden richtig analysiert und gerundet.</span><span class="sxs-lookup"><span data-stu-id="4c037-301">Correctly parse and round inputs of any length.</span></span>
- <span data-ttu-id="4c037-302">Die negative Null wird richtig analysiert und formatiert.</span><span class="sxs-lookup"><span data-stu-id="4c037-302">Correctly parse and format negative zero.</span></span>
- <span data-ttu-id="4c037-303">`Infinity`- und `NaN`-Werte werden mithilfe einer Überprüfung, bei der nicht zwischen Groß-/Kleinbuchstaben unterschieden wird, richtig analysiert. Außerdem ist, falls erforderlich, optional das vorangestellte `+`-Zeichen zulässig.</span><span class="sxs-lookup"><span data-stu-id="4c037-303">Correctly parse `Infinity` and `NaN` by doing a case-insensitive check and allowing an optional preceding `+` where applicable.</span></span>

<span data-ttu-id="4c037-304">Zu den neuen <xref:System.Math?displayProperty=nameWithType>-APIs zählen:</span><span class="sxs-lookup"><span data-stu-id="4c037-304">New <xref:System.Math?displayProperty=nameWithType> APIs include:</span></span>

- <span data-ttu-id="4c037-305"><xref:System.Math.BitIncrement(System.Double)> und <xref:System.Math.BitDecrement(System.Double)></span><span class="sxs-lookup"><span data-stu-id="4c037-305"><xref:System.Math.BitIncrement(System.Double)> and <xref:System.Math.BitDecrement(System.Double)></span></span>\
<span data-ttu-id="4c037-306">entspricht den IEEE-Operationen `nextUp` und `nextDown`.</span><span class="sxs-lookup"><span data-stu-id="4c037-306">Corresponds to the `nextUp` and `nextDown` IEEE operations.</span></span> <span data-ttu-id="4c037-307">Diese geben jeweils die kleinste Gleitkommazahl zurück, die größer oder kleiner als der Eingabewert ist.</span><span class="sxs-lookup"><span data-stu-id="4c037-307">They return the smallest floating-point number that compares greater or lesser than the input (respectively).</span></span> <span data-ttu-id="4c037-308">`Math.BitIncrement(0.0)` gibt beispielsweise `double.Epsilon` zurück.</span><span class="sxs-lookup"><span data-stu-id="4c037-308">For example, `Math.BitIncrement(0.0)` would return `double.Epsilon`.</span></span>

- <span data-ttu-id="4c037-309"><xref:System.Math.MaxMagnitude(System.Double,System.Double)> und <xref:System.Math.MinMagnitude(System.Double,System.Double)></span><span class="sxs-lookup"><span data-stu-id="4c037-309"><xref:System.Math.MaxMagnitude(System.Double,System.Double)> and <xref:System.Math.MinMagnitude(System.Double,System.Double)></span></span>\
<span data-ttu-id="4c037-310">entspricht den IEEE-Operationen `maxNumMag` und `minNumMag`. Diese geben für zwei Eingabewerte jeweils den Wert zurück, für den ein größerer oder kleinerer Absolutbetrag ermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="4c037-310">Corresponds to the `maxNumMag` and `minNumMag` IEEE operations, they return the value that is greater or lesser in magnitude of the two inputs (respectively).</span></span> <span data-ttu-id="4c037-311">`Math.MaxMagnitude(2.0, -3.0)` gibt beispielsweise `-3.0` zurück.</span><span class="sxs-lookup"><span data-stu-id="4c037-311">For example, `Math.MaxMagnitude(2.0, -3.0)` would return `-3.0`.</span></span>

- <xref:System.Math.ILogB(System.Double)>\
<span data-ttu-id="4c037-312">Entspricht der IEEE-Operation `logB`, die einen integralen Wert zurückgibt. Der Rückgabewert ist der integrale Wert des Logarithmus zur Basis 2 des Eingabeparameters.</span><span class="sxs-lookup"><span data-stu-id="4c037-312">Corresponds to the `logB` IEEE operation that returns an integral value, it returns the integral base-2 log of the input parameter.</span></span> <span data-ttu-id="4c037-313">Diese Methode entspricht im Wesentlichen `floor(log2(x))`, jedoch ist der Rundungsfehler minimal.</span><span class="sxs-lookup"><span data-stu-id="4c037-313">This method is effectively the same as `floor(log2(x))`, but done with minimal rounding error.</span></span>

- <xref:System.Math.ScaleB(System.Double,System.Int32)>\
<span data-ttu-id="4c037-314">Entspricht der IEEE-Operation `scaleB`, der ein integraler Wert übergeben wird. Zurückgegeben wird im Wesentlichen `x * pow(2, n)`, jedoch ist der Rundungsfehler minimal.</span><span class="sxs-lookup"><span data-stu-id="4c037-314">Corresponds to the `scaleB` IEEE operation that takes an integral value, it returns effectively `x * pow(2, n)`, but is done with minimal rounding error.</span></span>

- <xref:System.Math.Log2(System.Double)>\
<span data-ttu-id="4c037-315">entspricht der IEEE-Operation `log2`, die den Logarithmus zur Basis 2 zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="4c037-315">Corresponds to the `log2` IEEE operation, it returns the base-2 logarithm.</span></span> <span data-ttu-id="4c037-316">Diese Operation minimiert den Rundungsfehler.</span><span class="sxs-lookup"><span data-stu-id="4c037-316">It minimizes rounding error.</span></span>

- <xref:System.Math.FusedMultiplyAdd(System.Double,System.Double,System.Double)>\
<span data-ttu-id="4c037-317">entspricht der IEEE-Operation `fma`, die eine Fused-Multiply-Add-Operation durchführt.</span><span class="sxs-lookup"><span data-stu-id="4c037-317">Corresponds to the `fma` IEEE operation, it performs a fused multiply add.</span></span> <span data-ttu-id="4c037-318">Dabei wird `(x * y) + z` als einzelne Operation ausgeführt, wodurch der Rundungsfehler minimiert wird.</span><span class="sxs-lookup"><span data-stu-id="4c037-318">That is, it does `(x * y) + z` as a single operation, thereby minimizing the rounding error.</span></span> <span data-ttu-id="4c037-319">`FusedMultiplyAdd(1e308, 2.0, -1e308)` gibt beispielsweise `1e308` zurück.</span><span class="sxs-lookup"><span data-stu-id="4c037-319">An example would be `FusedMultiplyAdd(1e308, 2.0, -1e308)` which returns `1e308`.</span></span> <span data-ttu-id="4c037-320">Die reguläre Operation `(1e308 * 2.0) - 1e308` gibt `double.PositiveInfinity` zurück.</span><span class="sxs-lookup"><span data-stu-id="4c037-320">The regular `(1e308 * 2.0) - 1e308` returns `double.PositiveInfinity`.</span></span>

- <xref:System.Math.CopySign(System.Double,System.Double)>\
<span data-ttu-id="4c037-321">entspricht der IEEE-Operation `copySign`. Diese gibt den Wert von `x` mit dem Vorzeichen von `y` zurück.</span><span class="sxs-lookup"><span data-stu-id="4c037-321">Corresponds to the `copySign` IEEE operation, it returns the value of `x`, but with the sign of `y`.</span></span>

## <a name="fast-built-in-json-support"></a><span data-ttu-id="4c037-322">Schneller integrierter JSON-Support</span><span class="sxs-lookup"><span data-stu-id="4c037-322">Fast built-in JSON support</span></span>

<span data-ttu-id="4c037-323">.NET-Benutzer haben sich weitgehend auf [**Json.NET**](https://www.newtonsoft.com/json) und andere beliebte JSON-Bibliotheken verlassen, die weiterhin eine gute Wahl sind.</span><span class="sxs-lookup"><span data-stu-id="4c037-323">.NET users have largely relied on [**Json.NET**](https://www.newtonsoft.com/json) and other popular JSON libraries, which continue to be good choices.</span></span> <span data-ttu-id="4c037-324">**Json.NET** verwendet als Basisdatentyp .NET-Zeichenfolgen, die intern in UTF-16 codiert sind.</span><span class="sxs-lookup"><span data-stu-id="4c037-324">**Json.NET** uses .NET strings as its base datatype, which is UTF-16 under the hood.</span></span>

<span data-ttu-id="4c037-325">Die neue integrierte JSON-Unterstützung ist überaus leistungsfähig und basiert auf `Span<byte>`. Außerdem wird damit nur wenig Speicher belegt.</span><span class="sxs-lookup"><span data-stu-id="4c037-325">The new built-in JSON support is high-performance, low allocation, and based on `Span<byte>`.</span></span> <span data-ttu-id="4c037-326">In .NET Core 3.0 wurden dem Namespace <xref:System.Text.Json?displayProperty=nameWithType> drei neue JSON-bezogene Typen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="4c037-326">Three new main JSON-related types have been added to .NET Core 3.0 the <xref:System.Text.Json?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="4c037-327">Diese Typen unterstützen die POCO-Serialisierung und Deserialisierung (Plain Old CLR Object) *noch* nicht.</span><span class="sxs-lookup"><span data-stu-id="4c037-327">These types don't *yet* support plain old CLR object (POCO) serialization and deserialization.</span></span>

### <a name="utf8jsonreader"></a><span data-ttu-id="4c037-328">Utf8JsonReader</span><span class="sxs-lookup"><span data-stu-id="4c037-328">Utf8JsonReader</span></span>

<span data-ttu-id="4c037-329"><xref:System.Text.Json.Utf8JsonReader?displayProperty=nameWithType> ist ein leistungsstarker, reiner Vorwärtsleser mit geringer Zuordnung für UTF-8-kodierten JSON-Text, der von einem `ReadOnlySpan<byte>` gelesen wird.</span><span class="sxs-lookup"><span data-stu-id="4c037-329"><xref:System.Text.Json.Utf8JsonReader?displayProperty=nameWithType> is a high-performance, low allocation, forward-only reader for UTF-8 encoded JSON text, read from a `ReadOnlySpan<byte>`.</span></span> <span data-ttu-id="4c037-330">Der `Utf8JsonReader` ist ein grundlegender, Low-Level-Typ, der zum Erstellen von benutzerdefinierten Parsern und Deserialisierungsprogrammen genutzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="4c037-330">The `Utf8JsonReader` is a foundational, low-level type, that can be used to build custom parsers and deserializers.</span></span> <span data-ttu-id="4c037-331">Das Durchlesen einer JSON-Nutzlast mit dem neuen `Utf8JsonReader` ist 2x schneller als mit dem Leser von **Json.NET**.</span><span class="sxs-lookup"><span data-stu-id="4c037-331">Reading through a JSON payload using the new `Utf8JsonReader` is 2x faster than using the reader from **Json.NET**.</span></span> <span data-ttu-id="4c037-332">Die Zuweisung erfolgt erst, wenn Sie JSON-Token als (UTF-16-)Zeichenfolgen aktualisieren müssen.</span><span class="sxs-lookup"><span data-stu-id="4c037-332">It doesn't allocate until you need to actualize JSON tokens as (UTF-16) strings.</span></span>

<span data-ttu-id="4c037-333">Es folgt ein Beispiel des Lesens der von Visual Studio Code erstellten Datei [**launch.json**](https://github.com/dotnet/samples/blob/master/snippets/core/whats-new/whats-new-in-30/cs/launch.json):</span><span class="sxs-lookup"><span data-stu-id="4c037-333">Here is an example of reading through the [**launch.json**](https://github.com/dotnet/samples/blob/master/snippets/core/whats-new/whats-new-in-30/cs/launch.json) file created by Visual Studio Code:</span></span>

[!CODE-csharp[Utf8JsonReader](~/samples/snippets/core/whats-new/whats-new-in-30/cs/program.cs#PrintJson)]

[!CODE-csharp[Utf8JsonReader](~/samples/snippets/core/whats-new/whats-new-in-30/cs/program.cs#PrintJsonCall)]

### <a name="utf8jsonwriter"></a><span data-ttu-id="4c037-334">Utf8JsonWriter</span><span class="sxs-lookup"><span data-stu-id="4c037-334">Utf8JsonWriter</span></span>

<span data-ttu-id="4c037-335">Mit <xref:System.Text.Json.Utf8JsonWriter?displayProperty=nameWithType> lassen sich in UTF-8 codierte JSON-Texte aus gängigen .NET-Typen wie `String`, `Int32` und `DateTime` schnell, vorwärtsgerichtet und ohne Zwischenspeichern schreiben.</span><span class="sxs-lookup"><span data-stu-id="4c037-335"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=nameWithType> provides a high-performance, non-cached, forward-only way to write UTF-8 encoded JSON text from common .NET types like `String`, `Int32`, and `DateTime`.</span></span> <span data-ttu-id="4c037-336">Der Writer ist ebenso wie der Reader ein grundlegender Low-Level-Typ, der zum Erstellen von benutzerdefinierten Serialisierungsmodulen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="4c037-336">Like the reader, the writer is a foundational, low-level type, that can be used to build custom serializers.</span></span> <span data-ttu-id="4c037-337">Mit der neuen `Utf8JsonWriter`-Klasse werden JSON-Nutzlasten 30 bis 80% schneller geschrieben als mit dem **Json.NET**-Writer. Außerdem findet keine Speicherbelegung statt.</span><span class="sxs-lookup"><span data-stu-id="4c037-337">Writing a JSON payload using the new `Utf8JsonWriter` is 30-80% faster than using the writer from **Json.NET** and doesn't allocate.</span></span>

### <a name="jsondocument"></a><span data-ttu-id="4c037-338">JsonDocument</span><span class="sxs-lookup"><span data-stu-id="4c037-338">JsonDocument</span></span>

<span data-ttu-id="4c037-339"><xref:System.Text.Json.JsonDocument?displayProperty=nameWithType> basiert auf `Utf8JsonReader`.</span><span class="sxs-lookup"><span data-stu-id="4c037-339"><xref:System.Text.Json.JsonDocument?displayProperty=nameWithType> is built on top of the `Utf8JsonReader`.</span></span> <span data-ttu-id="4c037-340">Mit `JsonDocument` können JSON-Daten analysiert werden. Zusätzlich kann damit ein schreibgeschütztes Dokumentobjektmodell (DOM) erstellt werden, das zur Unterstützung von zufälligen Zugriffen und Enumerationen abgefragt werden kann.</span><span class="sxs-lookup"><span data-stu-id="4c037-340">The `JsonDocument` provides the ability to parse JSON data and build a read-only Document Object Model (DOM) that can be queried to support random access and enumeration.</span></span> <span data-ttu-id="4c037-341">Auf die JSON-Elemente, aus denen sich die Daten zusammensetzen, kann über den Typ <xref:System.Text.Json.JsonElement> zugegriffen werden, der von `JsonDocument` als `RootElement`-Eigenschaft verfügbar gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="4c037-341">The JSON elements that compose the data can be accessed via the <xref:System.Text.Json.JsonElement> type that is exposed by the `JsonDocument` as a property called `RootElement`.</span></span> <span data-ttu-id="4c037-342">`JsonElement` enthält das JSON-Array und Objektenumeratoren sowie APIs zum Konvertieren von JSON-Text in gängige .NET-Typen.</span><span class="sxs-lookup"><span data-stu-id="4c037-342">The `JsonElement` contains the JSON array and object enumerators along with APIs to convert JSON text to common .NET types.</span></span> <span data-ttu-id="4c037-343">Die Analyse einer typischen JSON-Nutzlast und der Zugriff auf alle zugehörigen Member mithilfe von `JsonDocument` wird zwei- bis dreimal so schnell durchgeführt wie mit **Json.NET**. Dabei wird für eine überschaubare Datengröße (d.h. < 1MB) nur wenig Speicher belegt.</span><span class="sxs-lookup"><span data-stu-id="4c037-343">Parsing a typical JSON payload and accessing all its members using the `JsonDocument` is 2-3x faster than **Json.NET** with little allocations for data that is reasonably sized (that is, < 1 MB).</span></span>

<span data-ttu-id="4c037-344">Das folgende Beispiel enthält für `JsonDocument` und `JsonElement` ein Anwendungsszenario, das als Ausgangspunkt verwendet werden kann:</span><span class="sxs-lookup"><span data-stu-id="4c037-344">Here is a sample usage of the `JsonDocument` and `JsonElement` that can be used as a starting point:</span></span>

[!CODE-csharp[JsonDocument](~/samples/snippets/core/whats-new/whats-new-in-30/cs/program.cs#ReadJson)]

<span data-ttu-id="4c037-345">Es folgt ein Beispiel für C# 8.0 des Lesens der von Visual Studio Code erstellten Datei [**launch.json**](https://github.com/dotnet/samples/blob/master/snippets/core/whats-new/whats-new-in-30/cs/launch.json):</span><span class="sxs-lookup"><span data-stu-id="4c037-345">Here is a C# 8.0 example of reading through the [**launch.json**](https://github.com/dotnet/samples/blob/master/snippets/core/whats-new/whats-new-in-30/cs/launch.json) file created by Visual Studio Code:</span></span>

[!CODE-csharp[JsonDocument](~/samples/snippets/core/whats-new/whats-new-in-30/cs/program.cs#ReadJsonCall)]

### <a name="jsonserializer"></a><span data-ttu-id="4c037-346">JsonSerializer</span><span class="sxs-lookup"><span data-stu-id="4c037-346">JsonSerializer</span></span>

<span data-ttu-id="4c037-347"><xref:System.Text.Json.JsonSerializer?displayProperty=nameWithType> ist auf der Basis von <xref:System.Text.Json.Utf8JsonReader> und <xref:System.Text.Json.Utf8JsonWriter> erstellt, um eine schnelle Serialisierungsoption mit geringer Arbeitsspeicherzuweisung zur Arbeit mit JSON-Dokumenten und -Fragmenten bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="4c037-347"><xref:System.Text.Json.JsonSerializer?displayProperty=nameWithType> is built on top of <xref:System.Text.Json.Utf8JsonReader> and <xref:System.Text.Json.Utf8JsonWriter> to provide a fast, low-memory serialization option when working with JSON documents and fragments.</span></span>

<span data-ttu-id="4c037-348">Hier ist ein Beispiel für die Serialisierung eines Objekts in JSON:</span><span class="sxs-lookup"><span data-stu-id="4c037-348">Here is an example of serializing an object to JSON:</span></span>

[!CODE-csharp[JsonSerializer](~/samples/snippets/core/whats-new/whats-new-in-30/cs/JSON.cs#JsonSerialize)]

<span data-ttu-id="4c037-349">Hier ist ein Beispiel für die Deserialisierung einer JSON-Zeichenfolge in ein Objekt.</span><span class="sxs-lookup"><span data-stu-id="4c037-349">Here is an example of deserializing a JSON string to an object.</span></span> <span data-ttu-id="4c037-350">Sie können die im vorherigen Beispiel erzeugte JSON-Zeichenfolge verwenden:</span><span class="sxs-lookup"><span data-stu-id="4c037-350">You can use the JSON string produced by the previous example:</span></span>

[!CODE-csharp[JsonDeserializer](~/samples/snippets/core/whats-new/whats-new-in-30/cs/JSON.cs#JsonDeserialize)]

## <a name="interop-improvements"></a><span data-ttu-id="4c037-351">Interopverbesserungen</span><span class="sxs-lookup"><span data-stu-id="4c037-351">Interop improvements</span></span>

<span data-ttu-id="4c037-352">.NET Core 3.0 verbessert natives API-Interop.</span><span class="sxs-lookup"><span data-stu-id="4c037-352">.NET Core 3.0 improves native API interop.</span></span>

### <a name="type-nativelibrary"></a><span data-ttu-id="4c037-353">Typ: NativeLibrary</span><span class="sxs-lookup"><span data-stu-id="4c037-353">Type: NativeLibrary</span></span>

<span data-ttu-id="4c037-354"><xref:System.Runtime.InteropServices.NativeLibrary?displayProperty=nameWithType> bietet eine Kapselung zum Laden einer nativen Bibliothek (mit derselben Lastlogik wie .NET Core P/Invoke) und Bereitstellen der relevanten Hilfsfunktionen wie z.B. `getSymbol`.</span><span class="sxs-lookup"><span data-stu-id="4c037-354"><xref:System.Runtime.InteropServices.NativeLibrary?displayProperty=nameWithType> provides an encapsulation for loading a native library (using the same load logic as .NET Core P/Invoke) and providing the relevant helper functions such as `getSymbol`.</span></span> <span data-ttu-id="4c037-355">Ein Codebeispiel finden Sie in der [DLLMap-Demo](https://github.com/dotnet/samples/tree/master/core/extensions/AppWithPlugin).</span><span class="sxs-lookup"><span data-stu-id="4c037-355">For a code example, see the [DLLMap Demo](https://github.com/dotnet/samples/tree/master/core/extensions/AppWithPlugin).</span></span>

### <a name="windows-native-interop"></a><span data-ttu-id="4c037-356">Native Windows-Interop-API</span><span class="sxs-lookup"><span data-stu-id="4c037-356">Windows Native Interop</span></span>

<span data-ttu-id="4c037-357">Windows stellt eine umfassende native API mit grundlegenden C-APIs (ohne C++-Features), COM und WinRT bereit.</span><span class="sxs-lookup"><span data-stu-id="4c037-357">Windows offers a rich native API in the form of flat C APIs, COM, and WinRT.</span></span> <span data-ttu-id="4c037-358">Während .NET Core **P/Invoke** unterstützt, fügt .NET Core 3.0 die Fähigkeit zum **CoCreate von COM-APIs** und **Aktivieren von WinRT-APIs** hinzu.</span><span class="sxs-lookup"><span data-stu-id="4c037-358">While .NET Core supports **P/Invoke**, .NET Core 3.0 adds the ability to **CoCreate COM APIs** and **Activate WinRT APIs**.</span></span> <span data-ttu-id="4c037-359">Ein Codebeispiel finden Sie in der [Excel-Demo](https://github.com/dotnet/samples/tree/master/core/extensions/ExcelDemo).</span><span class="sxs-lookup"><span data-stu-id="4c037-359">For a code example, see the [Excel Demo](https://github.com/dotnet/samples/tree/master/core/extensions/ExcelDemo).</span></span>

## <a name="http2-support"></a><span data-ttu-id="4c037-360">HTTP/2-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="4c037-360">HTTP/2 support</span></span>

<span data-ttu-id="4c037-361">Der <xref:System.Net.Http.HttpClient?displayProperty=nameWithType>-Typ unterstützt das HTTP/2-Protokoll.</span><span class="sxs-lookup"><span data-stu-id="4c037-361">The <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> type supports the HTTP/2 protocol.</span></span> <span data-ttu-id="4c037-362">Wenn HTTP/2 aktiviert ist, wird die HTTP-Protokollversion über TLS/ALPN ausgehandelt, und HTTP/2 wird bei Auswahl durch den Server verwendet.</span><span class="sxs-lookup"><span data-stu-id="4c037-362">If HTTP/2 is enabled, the HTTP protocol version is negotiated via TLS/ALPN, and HTTP/2 is used if the server elects to use it.</span></span>

<span data-ttu-id="4c037-363">Das Standardprotokoll bleibt HTTP/1.1, aber HTTP/2 kann auf zwei verschiedene Arten aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="4c037-363">The default protocol remains HTTP/1.1, but HTTP/2 can be enabled in two different ways.</span></span> <span data-ttu-id="4c037-364">Erstens können Sie die HTTP-Anforderungsnachricht so festlegen, dass HTTP/2 verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="4c037-364">First, you can set the HTTP request message to use HTTP/2:</span></span>

[!CODE-csharp[Http2Request](~/samples/snippets/core/whats-new/whats-new-in-30/cs/http.cs#Request)]

<span data-ttu-id="4c037-365">Zweitens können Sie <xref:System.Net.Http.HttpClient> so ändern, dass HTTP/2 standardmäßig verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="4c037-365">Second, you can change <xref:System.Net.Http.HttpClient> to use HTTP/2 by default:</span></span>

[!CODE-csharp[Http2Client](~/samples/snippets/core/whats-new/whats-new-in-30/cs/http.cs#Client)]

<span data-ttu-id="4c037-366">Oftmals möchten Sie bei der Entwicklung einer Anwendung eine unverschlüsselte Verbindung verwenden.</span><span class="sxs-lookup"><span data-stu-id="4c037-366">Many times when you're developing an application, you want to use an unencrypted connection.</span></span> <span data-ttu-id="4c037-367">Wenn Sie wissen, dass der Zielendpunkt HTTP/2 verwendet, können Sie unverschlüsselte Verbindungen für HTTP/2 aktivieren.</span><span class="sxs-lookup"><span data-stu-id="4c037-367">If you know the target endpoint will be using HTTP/2, you can turn on unencrypted connections for HTTP/2.</span></span> <span data-ttu-id="4c037-368">Sie können sie aktivieren, indem Sie die Umgebungsvariable `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2UNENCRYPTEDSUPPORT` auf `1` festlegen oder sie im App-Kontext aktivieren:</span><span class="sxs-lookup"><span data-stu-id="4c037-368">You can turn it on by setting the `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2UNENCRYPTEDSUPPORT` environment variable to `1` or by enabling it in the app context:</span></span>

[!CODE-csharp[Http2Context](~/samples/snippets/core/whats-new/whats-new-in-30/cs/http.cs#AppContext)]

## <a name="tls-13--openssl-111-on-linux"></a><span data-ttu-id="4c037-369">TLS 1.3 & OpenSSL 1.1.1 auf Linux</span><span class="sxs-lookup"><span data-stu-id="4c037-369">TLS 1.3 & OpenSSL 1.1.1 on Linux</span></span>

<span data-ttu-id="4c037-370">.NET Core nutzt nun die Unterstützung von [TLS 1.3 in OpenSSL 1.1.1.1](https://www.openssl.org/blog/blog/2018/09/11/release111/), wenn es in einer bestimmten Umgebung verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="4c037-370">.NET Core now takes advantage of [TLS 1.3 support in OpenSSL 1.1.1](https://www.openssl.org/blog/blog/2018/09/11/release111/), when it's available in a given environment.</span></span> <span data-ttu-id="4c037-371">Mit TLS 1.3:</span><span class="sxs-lookup"><span data-stu-id="4c037-371">With TLS 1.3:</span></span>

- <span data-ttu-id="4c037-372">Verbindungszeiten werden durch Reduzierung der erforderlichen Roundtrips zwischen Client und Server verbessert.</span><span class="sxs-lookup"><span data-stu-id="4c037-372">Connection times are improved with reduced round trips required between the client and server.</span></span>
- <span data-ttu-id="4c037-373">Verbesserte Sicherheit wg. Entfernen verschiedener veralteter und unsicherer kryptografischer Algorithmen.</span><span class="sxs-lookup"><span data-stu-id="4c037-373">Improved security because of the removal of various obsolete and insecure cryptographic algorithms.</span></span>

<span data-ttu-id="4c037-374">Sofern verfügbar, verwendet .NET Core 3.0 **OpenSSL 1.1.1**, **OpenSSL 1.1.0** oder **OpenSSL 1.0.2** auf einem Linuxsystem.</span><span class="sxs-lookup"><span data-stu-id="4c037-374">When available, .NET Core 3.0 uses **OpenSSL 1.1.1**, **OpenSSL 1.1.0**, or **OpenSSL 1.0.2** on a Linux system.</span></span> <span data-ttu-id="4c037-375">Wenn **OpenSSL 1.1.1** verfügbar ist, verwendet sowohl der <xref:System.Net.Security.SslStream?displayProperty=nameWithType>- als auch <xref:System.Net.Http.HttpClient?displayProperty=nameWithType>-Typ **TLS 1.3** (vorausgesetzt, dass Client und Server **TLS 1.3** unterstützen).</span><span class="sxs-lookup"><span data-stu-id="4c037-375">When **OpenSSL 1.1.1** is available, both <xref:System.Net.Security.SslStream?displayProperty=nameWithType> and <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> types will use **TLS 1.3** (assuming both the client and server support **TLS 1.3**).</span></span>

>[!IMPORTANT]
><span data-ttu-id="4c037-376">Windows und macOS unterstützen **TLS 1.3** noch nicht.</span><span class="sxs-lookup"><span data-stu-id="4c037-376">Windows and macOS do not yet support **TLS 1.3**.</span></span> <span data-ttu-id="4c037-377">.NET Core 3.0 unterstützt **TLS 1.3** auf diesen Betriebssystemen, wenn entsprechender Support verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="4c037-377">.NET Core 3.0 will support **TLS 1.3** on these operating systems when support becomes available.</span></span>

<span data-ttu-id="4c037-378">Das folgende Beispiel für C# 8.0 veranschaulicht das Herstellen der Verbindung von .NET Core 3.0 auf Ubuntu 18.10 mit <https://www.cloudflare.com>:</span><span class="sxs-lookup"><span data-stu-id="4c037-378">The following C# 8.0 example demonstrates .NET Core 3.0 on Ubuntu 18.10 connecting to <https://www.cloudflare.com>:</span></span>

[!CODE-csharp[TLSExample](~/samples/snippets/core/whats-new/whats-new-in-30/cs/TLS.cs#TLS)]

## <a name="cryptography-ciphers"></a><span data-ttu-id="4c037-379">Kryptografieverschlüsselungen</span><span class="sxs-lookup"><span data-stu-id="4c037-379">Cryptography ciphers</span></span>

<span data-ttu-id="4c037-380">.NET 3.0 fügt Unterstützung für **AES-GCM**- und **AES-CCM-** -Verschlüsselungen hinzu, implementiert mit <xref:System.Security.Cryptography.AesGcm?displayProperty=nameWithType> bzw. <xref:System.Security.Cryptography.AesCcm?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4c037-380">.NET 3.0 adds support for **AES-GCM** and **AES-CCM** ciphers, implemented with <xref:System.Security.Cryptography.AesGcm?displayProperty=nameWithType> and <xref:System.Security.Cryptography.AesCcm?displayProperty=nameWithType> respectively.</span></span> <span data-ttu-id="4c037-381">Beide Algorithmen sind [AEAD-Algorithmen (Authenticated Encryption with Association Data)](https://en.wikipedia.org/wiki/Authenticated_encryption).</span><span class="sxs-lookup"><span data-stu-id="4c037-381">These algorithms are both [Authenticated Encryption with Association Data (AEAD) algorithms](https://en.wikipedia.org/wiki/Authenticated_encryption).</span></span>

<span data-ttu-id="4c037-382">Der folgende Code veranschaulicht die Verwendung der `AesGcm`-Verschlüsselung zum Verschlüsseln und Entschlüsseln von Zufallsdaten.</span><span class="sxs-lookup"><span data-stu-id="4c037-382">The following code demonstrates using `AesGcm` cipher to encrypt and decrypt random data.</span></span>

[!CODE-csharp[AesGcm](~/samples/snippets/core/whats-new/whats-new-in-30/cs/Cipher.cs#AesGcm)]

## <a name="cryptographic-key-importexport"></a><span data-ttu-id="4c037-383">Importieren/Exportieren kryptografischer Schlüssel</span><span class="sxs-lookup"><span data-stu-id="4c037-383">Cryptographic Key Import/Export</span></span>

<span data-ttu-id="4c037-384">.NET Core 3.0 unterstützt das Importieren und Exportieren der asymmetrischen öffentlichen und privaten Schlüssel aus den Standardformaten.</span><span class="sxs-lookup"><span data-stu-id="4c037-384">.NET Core 3.0 supports the import and export of asymmetric public and private keys from standard formats.</span></span> <span data-ttu-id="4c037-385">Sie müssen kein X.509-Zertifikat verwenden.</span><span class="sxs-lookup"><span data-stu-id="4c037-385">You don't need to use an X.509 certificate.</span></span>

<span data-ttu-id="4c037-386">Alle Schlüsseltypen wie *RSA*, *DSA*, *ECDsa* und *ECDiffieHellman* unterstützen die folgenden Formate:</span><span class="sxs-lookup"><span data-stu-id="4c037-386">All key types, such as *RSA*, *DSA*, *ECDsa*, and *ECDiffieHellman*, support the following formats:</span></span>

- <span data-ttu-id="4c037-387">**Öffentlicher Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="4c037-387">**Public Key**</span></span>
  - <span data-ttu-id="4c037-388">X.509 SubjectPublicKeyInfo</span><span class="sxs-lookup"><span data-stu-id="4c037-388">X.509 SubjectPublicKeyInfo</span></span>

- <span data-ttu-id="4c037-389">**Privater Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="4c037-389">**Private key**</span></span>
  - <span data-ttu-id="4c037-390">PKCS#8 PrivateKeyInfo</span><span class="sxs-lookup"><span data-stu-id="4c037-390">PKCS#8 PrivateKeyInfo</span></span>
  - <span data-ttu-id="4c037-391">PKCS#8 EncryptedPrivateKeyInfo</span><span class="sxs-lookup"><span data-stu-id="4c037-391">PKCS#8 EncryptedPrivateKeyInfo</span></span>

<span data-ttu-id="4c037-392">RSA-Schlüsseln unterstützen auch:</span><span class="sxs-lookup"><span data-stu-id="4c037-392">RSA keys also support:</span></span>

- <span data-ttu-id="4c037-393">**Öffentlicher Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="4c037-393">**Public Key**</span></span>
  - <span data-ttu-id="4c037-394">PKCS#1 RSAPublicKey</span><span class="sxs-lookup"><span data-stu-id="4c037-394">PKCS#1 RSAPublicKey</span></span>

- <span data-ttu-id="4c037-395">**Privater Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="4c037-395">**Private key**</span></span>
  - <span data-ttu-id="4c037-396">PKCS#1 RSAPrivateKey</span><span class="sxs-lookup"><span data-stu-id="4c037-396">PKCS#1 RSAPrivateKey</span></span>

<span data-ttu-id="4c037-397">Die Exportmethoden erstellen DER-kodierte Binärdaten, und die Importmethoden erwarten dasselbe.</span><span class="sxs-lookup"><span data-stu-id="4c037-397">The export methods produce DER-encoded binary data, and the import methods expect the same.</span></span> <span data-ttu-id="4c037-398">Wenn ein Schlüssel im textfreundlichen PEM-Format gespeichert ist, muss der Anrufer den Inhalt base64-dekodieren, bevor er eine Importmethode aufruft.</span><span class="sxs-lookup"><span data-stu-id="4c037-398">If a key is stored in the text-friendly PEM format, the caller will need to base64-decode the content before calling an import method.</span></span>

[!CODE-csharp[RSA](~/samples/snippets/core/whats-new/whats-new-in-30/cs/RSA.cs#Rsa)]

<span data-ttu-id="4c037-399">**PKCS#8**-Dateien können mit <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo?displayProperty=nameWithType> überprüft werden, und **PFX/PKCS#12**-Dateien mit <xref:System.Security.Cryptography.Pkcs.Pkcs12Info?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4c037-399">**PKCS#8** files can be inspected with <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo?displayProperty=nameWithType> and **PFX/PKCS#12** files can be inspected with <xref:System.Security.Cryptography.Pkcs.Pkcs12Info?displayProperty=nameWithType>.</span></span> <span data-ttu-id="4c037-400">**PFX/PKCS#12**-Dateien können mit <xref:System.Security.Cryptography.Pkcs.Pkcs12Builder?displayProperty=nameWithType> bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="4c037-400">**PFX/PKCS#12** files can be manipulated with <xref:System.Security.Cryptography.Pkcs.Pkcs12Builder?displayProperty=nameWithType>.</span></span>

## <a name="serialport-for-linux"></a><span data-ttu-id="4c037-401">SerialPort für Linux</span><span class="sxs-lookup"><span data-stu-id="4c037-401">SerialPort for Linux</span></span>

<span data-ttu-id="4c037-402">.NET Core 3.0 bietet grundlegende Unterstützung für <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType> unter Linux.</span><span class="sxs-lookup"><span data-stu-id="4c037-402">.NET Core 3.0 provides basic support for <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType> on Linux.</span></span>

<span data-ttu-id="4c037-403">Bisher unterstützte .NET Core nur die Verwendung von `SerialPort` auf Windows.</span><span class="sxs-lookup"><span data-stu-id="4c037-403">Previously, .NET Core only supported using `SerialPort` on Windows.</span></span>

<span data-ttu-id="4c037-404">Weitere Informationen zur eingeschränkten Unterstützung für den seriellen Anschluss unter Linux finden Sie unter [GitHub-Issue 33146](https://github.com/dotnet/corefx/issues/33146).</span><span class="sxs-lookup"><span data-stu-id="4c037-404">For more information about the limited support for the serial port on Linux, see [GitHub issue #33146](https://github.com/dotnet/corefx/issues/33146).</span></span>

## <a name="docker-and-cgroup-memory-limits"></a><span data-ttu-id="4c037-405">Arbeitsspeicherlimits bei Docker und Cgroup</span><span class="sxs-lookup"><span data-stu-id="4c037-405">Docker and cgroup memory Limits</span></span>

<span data-ttu-id="4c037-406">Ab Vorschauversion 3 funktioniert die Ausführung von .NET Core 3.0 unter Linux mit Docker besser mit Cgroup-Arbeitsspeicherlimits.</span><span class="sxs-lookup"><span data-stu-id="4c037-406">Starting with Preview 3, running .NET Core 3.0 on Linux with Docker works better with cgroup memory limits.</span></span> <span data-ttu-id="4c037-407">Das Ausführen eines Docker-Containers mit Arbeitsspeicherlimits, z.B. mit `docker run -m`, ändert das Verhalten von .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4c037-407">Running a Docker container with memory limits, such as with `docker run -m`, changes how .NET Core behaves.</span></span>

- <span data-ttu-id="4c037-408">Standardmäßige Heapgröße des Garbage Collectors (GC): maximal 20MB oder 75% des Arbeitsspeicherlimits für den Container.</span><span class="sxs-lookup"><span data-stu-id="4c037-408">Default Garbage Collector (GC) heap size: maximum of 20 mb or 75% of the memory limit on the container.</span></span>
- <span data-ttu-id="4c037-409">Die explizite Größe kann als absolute Anzahl oder Prozentsatz des Cgroup-Limits festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="4c037-409">Explicit size can be set as an absolute number or percentage of cgroup limit.</span></span>
- <span data-ttu-id="4c037-410">Die minimale reservierte Segmentgröße pro GC-Heap beträgt 16MB.</span><span class="sxs-lookup"><span data-stu-id="4c037-410">Minimum reserved segment size per GC heap is 16 mb.</span></span> <span data-ttu-id="4c037-411">Diese Größe reduziert die Anzahl der Heaps, die auf Computern erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="4c037-411">This size reduces the number of heaps that are created on machines.</span></span>

## <a name="smaller-garbage-collection-heap-sizes"></a><span data-ttu-id="4c037-412">Kleinere Garbage Collection-Heapgrößen</span><span class="sxs-lookup"><span data-stu-id="4c037-412">Smaller Garbage Collection heap sizes</span></span>

<span data-ttu-id="4c037-413">Die Standardheapgröße des Garbage Collectors wurde reduziert, sodass .NET Core weniger Arbeitsspeicher benötigt.</span><span class="sxs-lookup"><span data-stu-id="4c037-413">The Garbage Collector's default heap size has been reduced resulting in .NET Core using less memory.</span></span> <span data-ttu-id="4c037-414">Diese Änderung entspricht eher dem Zuordnungsbudget von Generation 0 mit modernen Prozessorcachegrößen.</span><span class="sxs-lookup"><span data-stu-id="4c037-414">This change better aligns with the generation 0 allocation budget with modern processor cache sizes.</span></span>

## <a name="garbage-collection-large-page-support"></a><span data-ttu-id="4c037-415">Garbage Collection: Unterstützung von „Large Pages“</span><span class="sxs-lookup"><span data-stu-id="4c037-415">Garbage Collection Large Page support</span></span>

<span data-ttu-id="4c037-416">„Large Pages“ (umfangreiche Seiten, unter Linux auch als „Huge Pages“ bekannt) ist eine Funktion, die dem Betriebssystem ermöglicht, Speicherbereiche einzurichten, die die native Seitengröße (häufig 4KB) überschreiten, um die Leistung der Anwendung zu verbessern, die diese große Seiten anfordert.</span><span class="sxs-lookup"><span data-stu-id="4c037-416">Large Pages (also known as Huge Pages on Linux) is a feature where the operating system is able to establish memory regions larger than the native page size (often 4K) to improve performance of the application requesting these large pages.</span></span>

<span data-ttu-id="4c037-417">Der Garbage Collector kann nun mit der Einstellung **GCLargePages** als Aktivierungsfeature zum Auswählen der Zuordnung großer Seiten auf Windows konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="4c037-417">The Garbage Collector can now be configured with the **GCLargePages** setting as an opt-in feature to choose to allocate large pages on Windows.</span></span>

## <a name="gpio-support-for-raspberry-pi"></a><span data-ttu-id="4c037-418">GPIO-Unterstützung für Raspberry Pi</span><span class="sxs-lookup"><span data-stu-id="4c037-418">GPIO Support for Raspberry Pi</span></span>

<span data-ttu-id="4c037-419">Über NuGet können nun zwei Pakete für die GPIO-Programmierung bezogen werden:</span><span class="sxs-lookup"><span data-stu-id="4c037-419">Two packages have been released to NuGet that you can use for GPIO programming:</span></span>

- [<span data-ttu-id="4c037-420">System.Device.Gpio</span><span class="sxs-lookup"><span data-stu-id="4c037-420">System.Device.Gpio</span></span>](https://www.nuget.org/packages/System.Device.Gpio)
- [<span data-ttu-id="4c037-421">Iot.Device.Bindings</span><span class="sxs-lookup"><span data-stu-id="4c037-421">Iot.Device.Bindings</span></span>](https://www.nuget.org/packages/Iot.Device.Bindings)

<span data-ttu-id="4c037-422">Die GPIO-Pakete enthalten APIs für *GPIO*-, *SPI*-, *I2C*- und *PWM*-Geräte.</span><span class="sxs-lookup"><span data-stu-id="4c037-422">The GPIO packages include APIs for *GPIO*, *SPI*, *I2C*, and *PWM* devices.</span></span> <span data-ttu-id="4c037-423">Das IoT-Bindungenpaket enthält Gerätebindungen.</span><span class="sxs-lookup"><span data-stu-id="4c037-423">The IoT bindings package includes device bindings.</span></span> <span data-ttu-id="4c037-424">Weitere Informationen finden Sie im [GitHub-Repository zu Geräten](https://github.com/dotnet/iot/blob/master/src/devices/).</span><span class="sxs-lookup"><span data-stu-id="4c037-424">For more information, see the [devices GitHub repo](https://github.com/dotnet/iot/blob/master/src/devices/).</span></span>

## <a name="arm64-linux-support"></a><span data-ttu-id="4c037-425">ARM64-Linux-Support</span><span class="sxs-lookup"><span data-stu-id="4c037-425">ARM64 Linux support</span></span>

<span data-ttu-id="4c037-426">.NET Core 3.0 fügt Unterstützung für ARM64 für Linux hinzu.</span><span class="sxs-lookup"><span data-stu-id="4c037-426">.NET Core 3.0 adds support for ARM64 for Linux.</span></span> <span data-ttu-id="4c037-427">Der primäre Anwendungsfall für ARM64 sind derzeit IoT-Szenarien.</span><span class="sxs-lookup"><span data-stu-id="4c037-427">The primary use case for ARM64 is currently with IoT scenarios.</span></span> <span data-ttu-id="4c037-428">Weitere Informationen finden Sie unter [.NET Core Runtime ARM64 Status](https://github.com/dotnet/announcements/issues/82) (.NET Core-Runtime-ARM64-Status).</span><span class="sxs-lookup"><span data-stu-id="4c037-428">For more information, see [.NET Core ARM64 Status](https://github.com/dotnet/announcements/issues/82).</span></span>

<span data-ttu-id="4c037-429">[Dockerimages für .NET Core unter ARM64](https://hub.docker.com/r/microsoft/dotnet/) sind für Alpine, Debian und Ubuntu verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4c037-429">[Docker images for .NET Core on ARM64](https://hub.docker.com/r/microsoft/dotnet/) are available for Alpine, Debian, and Ubuntu.</span></span>

> [!NOTE]
> <span data-ttu-id="4c037-430">**ARM64** wird von Windows noch nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4c037-430">**ARM64** Windows support isn't yet available.</span></span>
