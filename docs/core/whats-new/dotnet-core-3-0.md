---
title: Neuerungen in .NET Core 3.0
description: Informationen zu den neuen Features in .NET Core 3.0.
dev_langs:
- csharp
author: adegeo
ms.author: adegeo
ms.date: 01/27/2020
ms.openlocfilehash: 42d60f919cb6ae0dab262ef9056a7c33c312a911
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726664"
---
# <a name="whats-new-in-net-core-30"></a><span data-ttu-id="f6fae-103">Neuerungen in .NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="f6fae-103">What's new in .NET Core 3.0</span></span>

<span data-ttu-id="f6fae-104">In diesem Artikel werden Neuerungen in .NET Core 3.0 beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f6fae-104">This article describes what is new in .NET Core 3.0.</span></span> <span data-ttu-id="f6fae-105">Eine der wichtigsten Verbesserungen ist die Unterstützung für Windows-Desktopanwendungen (nur Windows).</span><span class="sxs-lookup"><span data-stu-id="f6fae-105">One of the biggest enhancements is support for Windows desktop applications (Windows only).</span></span> <span data-ttu-id="f6fae-106">Mit der .NET Core 3.0 SDK-Komponente Windows Desktop können Sie Ihre Windows Forms- und WPF-Anwendungen (Windows Presentation Foundation) portieren.</span><span class="sxs-lookup"><span data-stu-id="f6fae-106">By using the .NET Core 3.0 SDK component Windows Desktop, you can port your Windows Forms and Windows Presentation Foundation (WPF) applications.</span></span> <span data-ttu-id="f6fae-107">Die Windows Desktop-Komponente wird ausdrücklich nur für Windows unterstützt und ist nur unter Windows enthalten.</span><span class="sxs-lookup"><span data-stu-id="f6fae-107">To be clear, the Windows Desktop component is only supported and included on Windows.</span></span> <span data-ttu-id="f6fae-108">Weitere Informationen finden Sie im Abschnitt [Windows-Desktop](#windows-desktop) weiter unten in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="f6fae-108">For more information, see the [Windows desktop](#windows-desktop) section later in this article.</span></span>

<span data-ttu-id="f6fae-109">.NET Core 3.0 bietet Unterstützung für C# 8.0.</span><span class="sxs-lookup"><span data-stu-id="f6fae-109">.NET Core 3.0 adds support for C# 8.0.</span></span> <span data-ttu-id="f6fae-110">Es wird dringend empfohlen, [Visual Studio 2019 Version 16.3](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) oder höher, [Visual Studio für Mac 8.3](/visualstudio/mac/install-preview) oder höher oder [Visual Studio Code](https://code.visualstudio.com/) mit der neuesten **C#-Erweiterung** zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="f6fae-110">It's highly recommended that you use [Visual Studio 2019 version 16.3](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) or newer, [Visual Studio for Mac 8.3](/visualstudio/mac/install-preview) or newer, or [Visual Studio Code](https://code.visualstudio.com/) with the latest **C# extension**.</span></span>

<span data-ttu-id="f6fae-111">[Sie können .NET Core 3.0 jetzt für Windows, macOS oder Linux herunterladen und sofort starten](https://aka.ms/netcore3download).</span><span class="sxs-lookup"><span data-stu-id="f6fae-111">[Download and get started with .NET Core 3.0](https://aka.ms/netcore3download) right now on Windows, macOS, or Linux.</span></span>

<span data-ttu-id="f6fae-112">Weitere Informationen zu diesem Release finden Sie unter [Ankündigung von .NET Core 3.0](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-0/).</span><span class="sxs-lookup"><span data-stu-id="f6fae-112">For more information about the release, see the [.NET Core 3.0 announcement](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-0/).</span></span>

<span data-ttu-id="f6fae-113">.NET Core RC1 wurde von Microsoft als produktionsbereit betrachtet und vollständig unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f6fae-113">.NET Core RC1 was considered production ready by Microsoft and was fully supported.</span></span> <span data-ttu-id="f6fae-114">Wenn Sie eine Vorschauversion verwenden, müssen Sie für die weitere Unterstützung zur Version RTM wechseln.</span><span class="sxs-lookup"><span data-stu-id="f6fae-114">If you're using a preview release, you must move to the RTM version for continued support.</span></span>

## <a name="language-improvements-c-80"></a><span data-ttu-id="f6fae-115">Sprachverbesserungen in C# 8.0</span><span class="sxs-lookup"><span data-stu-id="f6fae-115">Language improvements C# 8.0</span></span>

<span data-ttu-id="f6fae-116">C# 8.0 ist ebenfalls Teil dieses Releases, welches das Feature mit [Referenztypen, die NULL-Werte zulassen](../../csharp/language-reference/builtin-types/nullable-reference-types.md), asynchrone Datenströme und weitere Muster enthält.</span><span class="sxs-lookup"><span data-stu-id="f6fae-116">C# 8.0 is also part of this release, which includes the [nullable reference types](../../csharp/language-reference/builtin-types/nullable-reference-types.md) feature, async streams, and more patterns.</span></span> <span data-ttu-id="f6fae-117">Weitere Informationen zu Features von C# 8.0 finden Sie unter [Neues in C# 8.0](../../csharp/whats-new/csharp-8.md).</span><span class="sxs-lookup"><span data-stu-id="f6fae-117">For more information about C# 8.0 features, see [What's new in C# 8.0](../../csharp/whats-new/csharp-8.md).</span></span>

<span data-ttu-id="f6fae-118">Tutorials im Zusammenhang mit den C# 8.0-Sprachfeatures:</span><span class="sxs-lookup"><span data-stu-id="f6fae-118">Tutorials related to C# 8.0 language features:</span></span>

- [<span data-ttu-id="f6fae-119">Tutorial: Besseres Ausdrücken Ihrer Entwurfsabsicht mit Verweistypen, die NULL-Werte zulassen und nicht zulassen</span><span class="sxs-lookup"><span data-stu-id="f6fae-119">Tutorial: Express your design intent more clearly with nullable and non-nullable reference types</span></span>](../../csharp/tutorials/nullable-reference-types.md)
- [<span data-ttu-id="f6fae-120">Tutorial: Generieren und Nutzen asynchroner Datenströme mit C# 8.0 und .NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="f6fae-120">Tutorial: Generate and consume async streams using C# 8.0 and .NET Core 3.0</span></span>](../../csharp/tutorials/generate-consume-asynchronous-stream.md)
- [<span data-ttu-id="f6fae-121">Tutorial: Verwenden des Musterabgleichs für buildtypgesteuerte und datengesteuerte Algorithmen</span><span class="sxs-lookup"><span data-stu-id="f6fae-121">Tutorial: Use pattern matching to build type-driven and data-driven algorithms</span></span>](../../csharp/tutorials/pattern-matching.md)

<span data-ttu-id="f6fae-122">Es wurden Spracherweiterungen hinzugefügt, um die folgenden API-Features zu unterstützen:</span><span class="sxs-lookup"><span data-stu-id="f6fae-122">Language enhancements were added to support the following API features detailed below:</span></span>

- [<span data-ttu-id="f6fae-123">Bereiche und Indizes</span><span class="sxs-lookup"><span data-stu-id="f6fae-123">Ranges and indices</span></span>](#ranges-and-indices)
- [<span data-ttu-id="f6fae-124">Asynchrone Datenströme</span><span class="sxs-lookup"><span data-stu-id="f6fae-124">Async streams</span></span>](#async-streams)

## <a name="net-standard-21"></a><span data-ttu-id="f6fae-125">.NET Standard 2.1</span><span class="sxs-lookup"><span data-stu-id="f6fae-125">.NET Standard 2.1</span></span>

<span data-ttu-id="f6fae-126">.NET Core 3.0 implementiert **.NET Standard 2.1**.</span><span class="sxs-lookup"><span data-stu-id="f6fae-126">.NET Core 3.0 implements **.NET Standard 2.1**.</span></span> <span data-ttu-id="f6fae-127">Dennoch generiert die Standardvorlage `dotnet new classlib` weiterhin ein Projekt für **.NET Standard 2.0**.</span><span class="sxs-lookup"><span data-stu-id="f6fae-127">However, the default `dotnet new classlib` template generates a project that still targets **.NET Standard 2.0**.</span></span> <span data-ttu-id="f6fae-128">Ändern Sie für **.NET Standard 2.1** in Ihrer Projektdatei die `TargetFramework`-Eigenschaft in `netstandard2.1`:</span><span class="sxs-lookup"><span data-stu-id="f6fae-128">To target **.NET Standard 2.1**, edit your project file and change the `TargetFramework` property to `netstandard2.1`:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TargetFramework>netstandard2.1</TargetFramework>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="f6fae-129">Wenn Sie Visual Studio verwenden, benötigen Sie [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019), da Visual Studio 2017 **.NET Standard 2.1** und **.NET Core 3.0** nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f6fae-129">If you're using Visual Studio, you need [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019), as Visual Studio 2017 doesn't support **.NET Standard 2.1** or **.NET Core 3.0**.</span></span>

## <a name="compiledeploy"></a><span data-ttu-id="f6fae-130">Kompilieren/bereitstellen</span><span class="sxs-lookup"><span data-stu-id="f6fae-130">Compile/Deploy</span></span>

### <a name="default-executables"></a><span data-ttu-id="f6fae-131">Standardmäßig ausführbare Dateien</span><span class="sxs-lookup"><span data-stu-id="f6fae-131">Default executables</span></span>

<span data-ttu-id="f6fae-132">.NET Core erstellt die [frameworkabhängigen ausführbaren Dateien](../deploying/index.md#publish-framework-dependent) jetzt standardmäßig.</span><span class="sxs-lookup"><span data-stu-id="f6fae-132">.NET Core now builds [framework-dependent executables](../deploying/index.md#publish-framework-dependent) by default.</span></span> <span data-ttu-id="f6fae-133">Dieses Verhalten ist neu für Anwendungen, die eine global installierte Version von .NET Core verwenden.</span><span class="sxs-lookup"><span data-stu-id="f6fae-133">This behavior is new for applications that use a globally installed version of .NET Core.</span></span> <span data-ttu-id="f6fae-134">Vorher produzierten nur [eigenständige Bereitstellungen](../deploying/index.md#publish-self-contained) eine ausführbare Datei.</span><span class="sxs-lookup"><span data-stu-id="f6fae-134">Previously, only [self-contained deployments](../deploying/index.md#publish-self-contained) would produce an executable.</span></span>

<span data-ttu-id="f6fae-135">Während `dotnet build` oder `dotnet publish` wird eine ausführbare Datei (**appHost**) erstellt, die der Umgebung und Plattform des von Ihnen verwendeten SDKs entspricht.</span><span class="sxs-lookup"><span data-stu-id="f6fae-135">During `dotnet build` or `dotnet publish`, an executable (known as the **appHost**) is created that matches the environment and platform of the SDK you're using.</span></span> <span data-ttu-id="f6fae-136">Diese ausführbaren Dateien bieten Ihnen die gleichen Möglichkeiten wie andere native ausführbare Dateien, wie z.B.:</span><span class="sxs-lookup"><span data-stu-id="f6fae-136">You can expect the same things with these executables as you would other native executables, such as:</span></span>

- <span data-ttu-id="f6fae-137">Sie können die ausführbare Datei doppelklicken.</span><span class="sxs-lookup"><span data-stu-id="f6fae-137">You can double-click on the executable.</span></span>
- <span data-ttu-id="f6fae-138">Sie können die Anwendung direkt aus einer Eingabeaufforderung starten, z.B. `myapp.exe` unter Windows und `./myapp` unter Linux und MacOS.</span><span class="sxs-lookup"><span data-stu-id="f6fae-138">You can launch the application from a command prompt directly, such as `myapp.exe` on Windows, and `./myapp` on Linux and macOS.</span></span>

### <a name="macos-apphost-and-notarization"></a><span data-ttu-id="f6fae-139">macOS-appHost und -Notarisierung</span><span class="sxs-lookup"><span data-stu-id="f6fae-139">macOS appHost and notarization</span></span>

<span data-ttu-id="f6fae-140">*nur unter macOS*</span><span class="sxs-lookup"><span data-stu-id="f6fae-140">*macOS only*</span></span>

<span data-ttu-id="f6fae-141">Ab dem notarisierten .NET Core SDK 3.0 für macOS ist die Einstellung zum Erstellen einer ausführbaren Standarddatei („appHost“) standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="f6fae-141">Starting with the notarized .NET Core SDK 3.0 for macOS, the setting to produce a default executable (known as the appHost) is disabled by default.</span></span> <span data-ttu-id="f6fae-142">Weitere Informationen finden Sie unter [macOS Catalina-Notarisierung und die Auswirkungen auf .NET Core-Downloads und -Projekte](../install/macos-notarization-issues.md).</span><span class="sxs-lookup"><span data-stu-id="f6fae-142">For more information, see [macOS Catalina Notarization and the impact on .NET Core downloads and projects](../install/macos-notarization-issues.md).</span></span>

<span data-ttu-id="f6fae-143">Wenn die appHost-Einstellung aktiviert ist, erzeugt .NET Core eine native ausführbare Mach-O-Datei, wenn Sie einen Build- oder Veröffentlichungsprozess ausführen.</span><span class="sxs-lookup"><span data-stu-id="f6fae-143">When the appHost setting is enabled, .NET Core generates a native Mach-O executable when you build or publish.</span></span> <span data-ttu-id="f6fae-144">Ihre App wird im Kontext von appHost ausgeführt, wenn sie mit dem Befehl `dotnet run` über den Quellcode oder durch direktes Starten der ausführbaren Mach-O-Datei ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f6fae-144">Your app runs in the context of the appHost when it is run from source code with the `dotnet run` command, or by starting the Mach-O executable directly.</span></span>

<span data-ttu-id="f6fae-145">Ohne die appHost-Datei können Benutzer eine [frameworkabhängige](../deploying/index.md#publish-framework-dependent) App nur mit dem Befehl `dotnet <filename.dll>` starten.</span><span class="sxs-lookup"><span data-stu-id="f6fae-145">Without the appHost, the only way a user can start a [framework-dependent](../deploying/index.md#publish-framework-dependent) app is with the `dotnet <filename.dll>` command.</span></span> <span data-ttu-id="f6fae-146">Es wird immer eine appHost-Datei erstellt, wenn Sie Ihre App [eigenständig](../deploying/index.md#publish-self-contained) veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="f6fae-146">An appHost is always created when you publish your app [self-contained](../deploying/index.md#publish-self-contained).</span></span>

<span data-ttu-id="f6fae-147">Sie können die appHost-Datei entweder auf Projektebene konfigurieren oder für einen spezifischen `dotnet`-Befehl mit dem `-p:UseAppHost`-Parameter aktivieren:</span><span class="sxs-lookup"><span data-stu-id="f6fae-147">You can either configure the appHost at the project level, or toggle the appHost for a specific `dotnet` command with the `-p:UseAppHost` parameter:</span></span>

- <span data-ttu-id="f6fae-148">Projektdatei</span><span class="sxs-lookup"><span data-stu-id="f6fae-148">Project file</span></span>

  ```xml
  <PropertyGroup>
    <UseAppHost>true</UseAppHost>
  </PropertyGroup>
  ```

- <span data-ttu-id="f6fae-149">Befehlszeilenparameter</span><span class="sxs-lookup"><span data-stu-id="f6fae-149">Command-line parameter</span></span>

  ```dotnetcli
  dotnet run -p:UseAppHost=true
  ```

<span data-ttu-id="f6fae-150">Weitere Informationen über die `UseAppHost`-Einstellung finden Sie unter [MSBuild-Eigenschaften für Microsoft.NET.Sdk](../project-sdk/msbuild-props.md#useapphost).</span><span class="sxs-lookup"><span data-stu-id="f6fae-150">For more information about the `UseAppHost` setting, see [MSBuild properties for Microsoft.NET.Sdk](../project-sdk/msbuild-props.md#useapphost).</span></span>

### <a name="single-file-executables"></a><span data-ttu-id="f6fae-151">Ausführbare Einzeldateien</span><span class="sxs-lookup"><span data-stu-id="f6fae-151">Single-file executables</span></span>

<span data-ttu-id="f6fae-152">Der `dotnet publish`-Befehl unterstützt das Verpacken der App in einer plattformspezifischen ausführbaren Einzeldatei.</span><span class="sxs-lookup"><span data-stu-id="f6fae-152">The `dotnet publish` command supports packaging your app into a platform-specific single-file executable.</span></span> <span data-ttu-id="f6fae-153">Die ausführbare Datei ist selbstextrahierend und enthält alle Abhängigkeiten (einschließlich der nativen), die zum Ausführen der App erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="f6fae-153">The executable is self-extracting and contains all dependencies (including native) that are required to run your app.</span></span> <span data-ttu-id="f6fae-154">Beim ersten Ausführen der App wird die Anwendung in ein Verzeichnis extrahiert, das auf dem Namen und dem Buildbezeichner der App basiert.</span><span class="sxs-lookup"><span data-stu-id="f6fae-154">When the app is first run, the application is extracted to a directory based on the app name and build identifier.</span></span> <span data-ttu-id="f6fae-155">Der Start ist beim erneuten Ausführen der App schneller.</span><span class="sxs-lookup"><span data-stu-id="f6fae-155">Startup is faster when the application is run again.</span></span> <span data-ttu-id="f6fae-156">Die Anwendung muss sich nicht selbst ein zweites Mal extrahieren, sofern keine neue Version verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f6fae-156">The application doesn't need to extract itself a second time unless a new version was used.</span></span>

<span data-ttu-id="f6fae-157">Legen Sie zum Veröffentlichen einer einzelnen ausführbaren Datei `PublishSingleFile` in Ihrem Projekt oder in der Befehlszeile mit dem `dotnet publish`-Befehl fest:</span><span class="sxs-lookup"><span data-stu-id="f6fae-157">To publish a single-file executable, set the `PublishSingleFile` in your project or on the command line with the `dotnet publish` command:</span></span>

```xml
<PropertyGroup>
  <RuntimeIdentifier>win10-x64</RuntimeIdentifier>
  <PublishSingleFile>true</PublishSingleFile>
</PropertyGroup>
```

<span data-ttu-id="f6fae-158">- oder -</span><span class="sxs-lookup"><span data-stu-id="f6fae-158">-or-</span></span>

```dotnetcli
dotnet publish -r win10-x64 -p:PublishSingleFile=true
```

<span data-ttu-id="f6fae-159">Weitere Informationen zum Veröffentlichen einzelner Dateien finden Sie im [Einzeldatei-Bundler-Entwurfsdokument](https://github.com/dotnet/designs/blob/master/accepted/2020/single-file/design.md).</span><span class="sxs-lookup"><span data-stu-id="f6fae-159">For more information about single-file publishing, see the [single-file bundler design document](https://github.com/dotnet/designs/blob/master/accepted/2020/single-file/design.md).</span></span>

### <a name="assembly-linking"></a><span data-ttu-id="f6fae-160">Verknüpfen von Assemblys</span><span class="sxs-lookup"><span data-stu-id="f6fae-160">Assembly linking</span></span>

<span data-ttu-id="f6fae-161">Das.NET Core 3.0 SDK bietet ein Tool, das die Größe von Apps reduzieren kann, indem es IL analysiert und ungenutzte Assemblys trimmt.</span><span class="sxs-lookup"><span data-stu-id="f6fae-161">The .NET core 3.0 SDK comes with a tool that can reduce the size of apps by analyzing IL and trimming unused assemblies.</span></span>

<span data-ttu-id="f6fae-162">Eigenständige Apps enthalten alles, was zum Ausführen Ihres Codes benötigt wird, ohne dass .NET auf dem Hostcomputer installiert sein muss.</span><span class="sxs-lookup"><span data-stu-id="f6fae-162">Self-contained apps include everything needed to run your code, without requiring .NET to be installed on the host computer.</span></span> <span data-ttu-id="f6fae-163">Allerdings benötigt die App oft nur eine kleine Teilmenge des Frameworks, um zu funktionieren, sodass andere ungenutzte Bibliotheken entfernt werden können.</span><span class="sxs-lookup"><span data-stu-id="f6fae-163">However, many times the app only requires a small subset of the framework to function, and other unused libraries could be removed.</span></span>

<span data-ttu-id="f6fae-164">.NET Core bietet nun eine Einstellung, die das Tool [IL linker](https://github.com/mono/linker) verwendet, um die IL Ihrer App zu untersuchen.</span><span class="sxs-lookup"><span data-stu-id="f6fae-164">.NET Core now includes a setting that will use the [IL linker](https://github.com/mono/linker) tool to scan the IL of your app.</span></span> <span data-ttu-id="f6fae-165">Dieses Tool erkennt, welcher Code erforderlich ist, und trimmt dann ungenutzte Bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="f6fae-165">This tool detects what code is required, and then trims unused libraries.</span></span> <span data-ttu-id="f6fae-166">Es kann die Bereitstellungsgröße einiger Apps deutlich reduzieren.</span><span class="sxs-lookup"><span data-stu-id="f6fae-166">This tool can significantly reduce the deployment size of some apps.</span></span>

<span data-ttu-id="f6fae-167">Fügen Sie die Einstellung `<PublishTrimmed>` zu Ihrem Projekt hinzu, und veröffentlichen Sie eine eigenständige App, um dieses Tool zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="f6fae-167">To enable this tool, add the `<PublishTrimmed>` setting in your project and publish a self-contained app:</span></span>

```xml
<PropertyGroup>
  <PublishTrimmed>true</PublishTrimmed>
</PropertyGroup>
```

```dotnetcli
dotnet publish -r <rid> -c Release
```

<span data-ttu-id="f6fae-168">Als Beispiel erreicht die inbegriffene Standardvorlage für neue Konsolenprojekte „hello world“ bei ihrer Veröffentlichung eine Größe von ca.70 MB.</span><span class="sxs-lookup"><span data-stu-id="f6fae-168">As an example, the basic "hello world" new console project template that is included, when published, hits about 70 MB in size.</span></span> <span data-ttu-id="f6fae-169">Mithilfe von `<PublishTrimmed>` wird diese Größe auf ca. 30 MB reduziert.</span><span class="sxs-lookup"><span data-stu-id="f6fae-169">By using `<PublishTrimmed>`, that size is reduced to about 30 MB.</span></span>

<span data-ttu-id="f6fae-170">Wichtig ist die Tatsache, dass Anwendungen oder Frameworks (einschließlich ASP.NET Core und WPF), die Reflektion oder verwandte dynamische Funktionen verwenden, nach dem Trimmen oft nicht mehr funktionieren.</span><span class="sxs-lookup"><span data-stu-id="f6fae-170">It's important to consider that applications or frameworks (including ASP.NET Core and WPF) that use reflection or related dynamic features, will often break when trimmed.</span></span> <span data-ttu-id="f6fae-171">Dies ist der Fall, weil der Linker von diesem dynamischen Verhalten nichts weiß und nicht bestimmen kann, welche Frameworktypen für die Reflektion benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="f6fae-171">This breakage occurs because the linker doesn't know about this dynamic behavior and can't determine which framework types are required for reflection.</span></span> <span data-ttu-id="f6fae-172">Das Tool IL Linker kann so konfiguriert werden, dass es sich dieses Szenarios bewusst ist.</span><span class="sxs-lookup"><span data-stu-id="f6fae-172">The IL Linker tool can be configured to be aware of this scenario.</span></span>

<span data-ttu-id="f6fae-173">Nach dem Trimmen müssen Sie Ihre App unbedingt testen.</span><span class="sxs-lookup"><span data-stu-id="f6fae-173">Above all else, be sure to test your app after trimming.</span></span>

<span data-ttu-id="f6fae-174">Weitere Informationen zum Tool IL Linker finden Sie in der [Dokumentation](../deploying/trim-self-contained.md), oder besuchen Sie das Repository [mono/linker]( https://github.com/mono/linker).</span><span class="sxs-lookup"><span data-stu-id="f6fae-174">For more information about the IL Linker tool, see the [documentation](../deploying/trim-self-contained.md) or visit the [mono/linker]( https://github.com/mono/linker) repo.</span></span>

### <a name="tiered-compilation"></a><span data-ttu-id="f6fae-175">Mehrstufig Kompilierung</span><span class="sxs-lookup"><span data-stu-id="f6fae-175">Tiered compilation</span></span>

<span data-ttu-id="f6fae-176">Die [mehrstufige Kompilierung](https://github.com/dotnet/runtime/blob/master/docs/design/features/tiered-compilation.md) (Tiered Compilation, TC) ist bei .NET Core 3.0 standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="f6fae-176">[Tiered compilation](https://github.com/dotnet/runtime/blob/master/docs/design/features/tiered-compilation.md) (TC) is on by default with .NET Core 3.0.</span></span> <span data-ttu-id="f6fae-177">Dieses Feature ermöglicht der Runtime, den Just-In-Time-Compiler (JIT) adaptiver zu nutzen, um eine bessere Leistung zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="f6fae-177">This feature enables the runtime to more adaptively use the just-in-time (JIT) compiler to achieve better performance.</span></span>

<span data-ttu-id="f6fae-178">Der Hauptvorteil der mehrstufigen Kompilierung (TC, Tiered Compilation) besteht darin, dass sie zwei Methoden zur Just-in-Time-Kompilierung bietet: in einer Stufe mit geringerer Qualität, die aber schneller ist, oder in einer Stufe mit höherer Qualität, die aber langsamer ist.</span><span class="sxs-lookup"><span data-stu-id="f6fae-178">The main benefit of tiered compilation is to provide two ways of jitting methods: in a lower-quality-but-faster tier or a higher-quality-but-slower tier.</span></span> <span data-ttu-id="f6fae-179">Die Qualität bezieht sich darauf, wie gut die Methode optimiert ist.</span><span class="sxs-lookup"><span data-stu-id="f6fae-179">The quality refers to how well the method is optimized.</span></span> <span data-ttu-id="f6fae-180">Die TC verbessert die Leistung einer Anwendung, während sie verschiedene Phasen der Ausführung vom Start bis zum stabilen Zustand durchläuft.</span><span class="sxs-lookup"><span data-stu-id="f6fae-180">TC helps to improve the performance of an application as it goes through various stages of execution, from startup through steady state.</span></span> <span data-ttu-id="f6fae-181">Wenn die TC deaktiviert ist, wird jede Methode auf eine einzige Weise kompiliert, die auf eine stabile Leistung gegenüber der Startleistung ausgerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="f6fae-181">When tiered compilation is disabled, every method is compiled in a single way that's biased to steady-state performance over startup performance.</span></span>

<span data-ttu-id="f6fae-182">Wenn TC aktiviert ist, gilt beim Start einer App das folgende Verhalten für die Methodenkompilierung:</span><span class="sxs-lookup"><span data-stu-id="f6fae-182">When TC is enabled, the following behavior applies for method compilation when an app starts up:</span></span>

- <span data-ttu-id="f6fae-183">Wenn die Methode über AOT-kompilierten Code oder [ReadyToRun](#readytorun-images) verfügt, wird der zuvor generierte Code verwendet.</span><span class="sxs-lookup"><span data-stu-id="f6fae-183">If the method has ahead-of-time-compiled code, or [ReadyToRun](#readytorun-images), the pregenerated code is used.</span></span>
- <span data-ttu-id="f6fae-184">Andernfalls wird die Methode mit JIT kompiliert.</span><span class="sxs-lookup"><span data-stu-id="f6fae-184">Otherwise, the method is jitted.</span></span> <span data-ttu-id="f6fae-185">In der Regel sind diese Methoden Generics über Werttypen.</span><span class="sxs-lookup"><span data-stu-id="f6fae-185">Typically, these methods are generics over value types.</span></span>
  - <span data-ttu-id="f6fae-186">*Quick JIT* erzeugt schneller Code geringerer Qualität (oder weniger optimiert).</span><span class="sxs-lookup"><span data-stu-id="f6fae-186">*Quick JIT* produces lower-quality (or less optimized) code more quickly.</span></span> <span data-ttu-id="f6fae-187">In .NET Core 3.0 ist Quick JIT standardmäßig für Methoden aktiviert, die keine Schleifen enthalten. Während des Starts wird dies bevorzugt.</span><span class="sxs-lookup"><span data-stu-id="f6fae-187">In .NET Core 3.0, Quick JIT is enabled by default for methods that don't contain loops and is preferred during startup.</span></span>
  - <span data-ttu-id="f6fae-188">Die vollständig optimierte Just-In-Time-Kompilierung erzeugt Code höherer Qualität (oder besser optimierten Code), ist aber langsamer.</span><span class="sxs-lookup"><span data-stu-id="f6fae-188">The fully optimizing JIT produces higher-quality (or more optimized) code more slowly.</span></span> <span data-ttu-id="f6fae-189">Für Methoden, bei denen die schnelle JIT-Kompilierung nicht verwendet werden würde (beispielsweise dann, wenn die Methode das Attribut <xref:System.Runtime.CompilerServices.MethodImplOptions.AggressiveOptimization?displayProperty=nameWithType> aufweist), wird die vollständig optimierte JIT-Kompilierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="f6fae-189">For methods where Quick JIT would not be used (for example, if the method is attributed with <xref:System.Runtime.CompilerServices.MethodImplOptions.AggressiveOptimization?displayProperty=nameWithType>), the fully optimizing JIT is used.</span></span>

<span data-ttu-id="f6fae-190">Bei häufig aufgerufenen Methoden erzeugt der Just-in-Time-Compiler schließlich vollständig optimierten Code im Hintergrund.</span><span class="sxs-lookup"><span data-stu-id="f6fae-190">For frequently called methods, the just-in-time compiler eventually creates fully optimized code in the background.</span></span> <span data-ttu-id="f6fae-191">Der optimierte Code ersetzt dann den vorkompilierten Code für diese Methode.</span><span class="sxs-lookup"><span data-stu-id="f6fae-191">The optimized code then replaces the pre-compiled code for that method.</span></span>

<span data-ttu-id="f6fae-192">Code, der von der schnellen JIT-Kompilierung generiert wurde, wird möglicherweise langsamer ausgeführt, belegt mehr Arbeitsspeicher oder nutzt mehr Stapelspeicher.</span><span class="sxs-lookup"><span data-stu-id="f6fae-192">Code generated by Quick JIT may run slower, allocate more memory, or use more stack space.</span></span> <span data-ttu-id="f6fae-193">Wenn es Probleme gibt, können Sie Quick JIT mit dieser MSBuild-Eigenschaft in der Projektdatei deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="f6fae-193">If there are issues, you can disabled Quick JIT using this MSBuild property in the project file:</span></span>

```xml
<PropertyGroup>
  <TieredCompilationQuickJit>false</TieredCompilationQuickJit>
</PropertyGroup>
```

<span data-ttu-id="f6fae-194">Verwenden Sie diese MSBuild-Eigenschaft in der Projektdatei, um die TC vollständig zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="f6fae-194">To disable TC completely, use this MSBuild property in your project file:</span></span>

```xml
<PropertyGroup>
  <TieredCompilation>false</TieredCompilation>
</PropertyGroup>
```

> [!TIP]
> <span data-ttu-id="f6fae-195">Wenn Sie diese Einstellungen in der Projektdatei ändern, müssen Sie möglicherweise einen bereinigten Build durchführen, damit die neuen Einstellungen reflektiert werden. (Löschen Sie die Verzeichnisse `obj` und `bin`, und erstellen Sie diese neu).</span><span class="sxs-lookup"><span data-stu-id="f6fae-195">If you change these settings in the project file, you may need to perform a clean build for the new settings to be reflected (delete the `obj` and `bin` directories and rebuild).</span></span>

<span data-ttu-id="f6fae-196">Weitere Informationen zum Konfigurieren der Kompilierung zur Laufzeit finden Sie unter [Laufzeitkonfigurationsoptionen für die Kompilierung](../run-time-config/compilation.md).</span><span class="sxs-lookup"><span data-stu-id="f6fae-196">For more information about configuring compilation at run time, see [Run-time configuration options for compilation](../run-time-config/compilation.md).</span></span>

### <a name="readytorun-images"></a><span data-ttu-id="f6fae-197">ReadyToRun-Images</span><span class="sxs-lookup"><span data-stu-id="f6fae-197">ReadyToRun images</span></span>

<span data-ttu-id="f6fae-198">Sie können die Startzeit Ihrer.NET Core-Anwendung beschleunigen, indem Sie Ihre Anwendungsassemblys im R2R-Format (ReadyToRun) kompilieren.</span><span class="sxs-lookup"><span data-stu-id="f6fae-198">You can improve the startup time of your .NET Core application by compiling your application assemblies as ReadyToRun (R2R) format.</span></span> <span data-ttu-id="f6fae-199">R2R ist eine Form der AOT-Kompilierung (Ahead-Of-Time).</span><span class="sxs-lookup"><span data-stu-id="f6fae-199">R2R is a form of ahead-of-time (AOT) compilation.</span></span>

<span data-ttu-id="f6fae-200">R2R-Binärdateien verbessern die Startleistung, indem sie den Arbeitsaufwand des JIT-Compilers (Just-in-time) reduzieren, der anfällt, wenn Ihre Anwendung geladen wird.</span><span class="sxs-lookup"><span data-stu-id="f6fae-200">R2R binaries improve startup performance by reducing the amount of work the just-in-time (JIT) compiler needs to do as your application loads.</span></span> <span data-ttu-id="f6fae-201">Die Binärdateien enthalten ähnlichen nativen Code im Vergleich zu dem, was der JIT-Compiler produzieren würde.</span><span class="sxs-lookup"><span data-stu-id="f6fae-201">The binaries contain similar native code compared to what the JIT would produce.</span></span> <span data-ttu-id="f6fae-202">R2R-Binärdateien sind jedoch größer, da sie sowohl IL-Code (Intermediate Language, Zwischensprache), der für einige Szenarios noch benötigt wird, als auch die native Version des gleichen Codes enthalten.</span><span class="sxs-lookup"><span data-stu-id="f6fae-202">However, R2R binaries are larger because they contain both intermediate language (IL) code, which is still needed for some scenarios, and the native version of the same code.</span></span> <span data-ttu-id="f6fae-203">R2R ist nur verfügbar, wenn Sie eine eigenständige Anwendung veröffentlichen, die eine bestimmte Laufzeitumgebung (RID) wie Linux x64 oder Windows x64 als Ziel hat.</span><span class="sxs-lookup"><span data-stu-id="f6fae-203">R2R is only available when you publish a self-contained app that targets specific runtime environments (RID) such as Linux x64 or Windows x64.</span></span>

<span data-ttu-id="f6fae-204">Gehen Sie folgendermaßen vor, um Ihr Projekt als „ReadyToRun“ (Bereit zur Ausführung) zu kompilieren:</span><span class="sxs-lookup"><span data-stu-id="f6fae-204">To compile your project as ReadyToRun, do the following:</span></span>

01. <span data-ttu-id="f6fae-205">Fügen Sie die `<PublishReadyToRun>`-Einstellung in Ihr Projekt ein.</span><span class="sxs-lookup"><span data-stu-id="f6fae-205">Add the `<PublishReadyToRun>` setting to your project:</span></span>

    ```xml
    <PropertyGroup>
      <PublishReadyToRun>true</PublishReadyToRun>
    </PropertyGroup>
    ```

01. <span data-ttu-id="f6fae-206">Veröffentlichen Sie eine eigenständige App.</span><span class="sxs-lookup"><span data-stu-id="f6fae-206">Publish a self-contained app.</span></span> <span data-ttu-id="f6fae-207">Dieser Befehl erstellt beispielsweise eine eigenständige App für die 64-Bit-Version von Windows:</span><span class="sxs-lookup"><span data-stu-id="f6fae-207">For example, this command creates a self-contained app for the 64-bit version of Windows:</span></span>

    ```dotnetcli
    dotnet publish -c Release -r win-x64 --self-contained
    ```

#### <a name="cross-platformarchitecture-restrictions"></a><span data-ttu-id="f6fae-208">Plattformübergreifende bzw. architekturbezogene Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="f6fae-208">Cross platform/architecture restrictions</span></span>

<span data-ttu-id="f6fae-209">Der ReadyToRun-Compiler unterstützt derzeit nicht die versionsübergreifende Angabe von Zielen.</span><span class="sxs-lookup"><span data-stu-id="f6fae-209">The ReadyToRun compiler doesn't currently support cross-targeting.</span></span> <span data-ttu-id="f6fae-210">Die Kompilierung muss für ein bestimmtes Ziel erfolgen.</span><span class="sxs-lookup"><span data-stu-id="f6fae-210">You must compile on a given target.</span></span> <span data-ttu-id="f6fae-211">Wenn Sie beispielsweise R2R-Images für Windows x64 benötigen, müssen Sie den Veröffentlichungsbefehl in dieser Umgebung ausführen.</span><span class="sxs-lookup"><span data-stu-id="f6fae-211">For example, if you want R2R images for Windows x64, you need to run the publish command on that environment.</span></span>

<span data-ttu-id="f6fae-212">Ausnahmen für die versionsübergreifende Angabe von Zielen:</span><span class="sxs-lookup"><span data-stu-id="f6fae-212">Exceptions to cross-targeting:</span></span>

- <span data-ttu-id="f6fae-213">Windows x64 kann verwendet werden, um Windows ARM32-, ARM64- und x86-Images zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="f6fae-213">Windows x64 can be used to compile Windows ARM32, ARM64, and x86 images.</span></span>
- <span data-ttu-id="f6fae-214">Windows x86 kann verwendet werden, um Windows ARM32-Images zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="f6fae-214">Windows x86 can be used to compile Windows ARM32 images.</span></span>
- <span data-ttu-id="f6fae-215">Linux X64 kann verwendet werden, um Linux ARM32- und -ARM64-Images zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="f6fae-215">Linux x64 can be used to compile Linux ARM32 and ARM64 images.</span></span>

<span data-ttu-id="f6fae-216">Weitere Informationen finden Sie auf der Seite zu [Bereit zur Ausführung](../deploying/ready-to-run.md).</span><span class="sxs-lookup"><span data-stu-id="f6fae-216">For more information, see [Ready to Run](../deploying/ready-to-run.md).</span></span>

## <a name="runtimesdk"></a><span data-ttu-id="f6fae-217">Runtime/SDK</span><span class="sxs-lookup"><span data-stu-id="f6fae-217">Runtime/SDK</span></span>

### <a name="major-version-runtime-roll-forward"></a><span data-ttu-id="f6fae-218">Runtimerollforward der Hauptversion</span><span class="sxs-lookup"><span data-stu-id="f6fae-218">Major-version runtime roll forward</span></span>

<span data-ttu-id="f6fae-219">Mit .NET Core 3.0 wird ein Aktivierungsfeature eingeführt, das Ihrer App ein Rollforward auf die neueste Hauptversion von .NET Core ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="f6fae-219">.NET Core 3.0 introduces an opt-in feature that allows your app to roll forward to the latest major version of .NET Core.</span></span> <span data-ttu-id="f6fae-220">Darüber hinaus wurde eine neue Einstellung hinzugefügt, um zu steuern, wie ein Rollforward auf Ihre App angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="f6fae-220">Additionally, a new setting has been added to control how roll forward is applied to your app.</span></span> <span data-ttu-id="f6fae-221">Diese kann folgendermaßen konfiguriert werden:</span><span class="sxs-lookup"><span data-stu-id="f6fae-221">This can be configured in the following ways:</span></span>

- <span data-ttu-id="f6fae-222">Projektdateieigenschaft: `RollForward`</span><span class="sxs-lookup"><span data-stu-id="f6fae-222">Project file property: `RollForward`</span></span>
- <span data-ttu-id="f6fae-223">Eigenschaft der Runtimekonfigurationsdatei: `rollForward`</span><span class="sxs-lookup"><span data-stu-id="f6fae-223">Run-time configuration file property: `rollForward`</span></span>
- <span data-ttu-id="f6fae-224">Umgebungsvariable: `DOTNET_ROLL_FORWARD`</span><span class="sxs-lookup"><span data-stu-id="f6fae-224">Environment variable: `DOTNET_ROLL_FORWARD`</span></span>
- <span data-ttu-id="f6fae-225">Befehlszeilenargument: `--roll-forward`</span><span class="sxs-lookup"><span data-stu-id="f6fae-225">Command-line argument: `--roll-forward`</span></span>

<span data-ttu-id="f6fae-226">Einer der folgenden Werte muss angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="f6fae-226">One of the following values must be specified.</span></span> <span data-ttu-id="f6fae-227">Wenn die Einstellung ausgelassen wird, ist **Minor** die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="f6fae-227">If the setting is omitted, **Minor** is the default.</span></span>

- <span data-ttu-id="f6fae-228">**LatestPatch**</span><span class="sxs-lookup"><span data-stu-id="f6fae-228">**LatestPatch**</span></span>\
<span data-ttu-id="f6fae-229">Rollforward zur höchsten Patchversion.</span><span class="sxs-lookup"><span data-stu-id="f6fae-229">Roll forward to the highest patch version.</span></span> <span data-ttu-id="f6fae-230">Dies deaktiviert ein Rollforward zur Nebenversion.</span><span class="sxs-lookup"><span data-stu-id="f6fae-230">This disables minor version roll forward.</span></span>
- <span data-ttu-id="f6fae-231">**Minor**</span><span class="sxs-lookup"><span data-stu-id="f6fae-231">**Minor**</span></span>\
<span data-ttu-id="f6fae-232">Rollforward zur niedrigsten höheren Nebenversion, wenn die angeforderte Nebenversion nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="f6fae-232">Roll forward to the lowest higher minor version, if requested minor version is missing.</span></span> <span data-ttu-id="f6fae-233">Wenn die angeforderte Nebenversion vorhanden ist, wird die **LatestPatch**-Richtlinie verwendet.</span><span class="sxs-lookup"><span data-stu-id="f6fae-233">If the requested minor version is present, then the **LatestPatch** policy is used.</span></span>
- <span data-ttu-id="f6fae-234">**Major**</span><span class="sxs-lookup"><span data-stu-id="f6fae-234">**Major**</span></span>\
<span data-ttu-id="f6fae-235">Rollforward zur niedrigsten höheren Hauptversion – und niedrigsten Nebenversion, wenn die angeforderte Hauptversion nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="f6fae-235">Roll forward to lowest higher major version, and lowest minor version, if requested major version is missing.</span></span> <span data-ttu-id="f6fae-236">Wenn die angeforderte Hauptversion vorhanden ist, wird die **Minor**-Richtlinie verwendet.</span><span class="sxs-lookup"><span data-stu-id="f6fae-236">If the requested major version is present, then the **Minor** policy is used.</span></span>
- <span data-ttu-id="f6fae-237">**LatestMinor**</span><span class="sxs-lookup"><span data-stu-id="f6fae-237">**LatestMinor**</span></span>\
<span data-ttu-id="f6fae-238">Rollforward zur höchsten Nebenversion – auch dann, wenn die angeforderte Nebenversion vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="f6fae-238">Roll forward to highest minor version, even if requested minor version is present.</span></span> <span data-ttu-id="f6fae-239">Für Komponentenhostingszenarien vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="f6fae-239">Intended for component hosting scenarios.</span></span>
- <span data-ttu-id="f6fae-240">**LatestMajor**</span><span class="sxs-lookup"><span data-stu-id="f6fae-240">**LatestMajor**</span></span>\
<span data-ttu-id="f6fae-241">Rollforward zur höchsten Hauptversion und höchsten Nebenversion – auch dann, wenn die angeforderte Hauptversion vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="f6fae-241">Roll forward to highest major and highest minor version, even if requested major is present.</span></span> <span data-ttu-id="f6fae-242">Für Komponentenhostingszenarien vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="f6fae-242">Intended for component hosting scenarios.</span></span>
- <span data-ttu-id="f6fae-243">**Disable**</span><span class="sxs-lookup"><span data-stu-id="f6fae-243">**Disable**</span></span>\
<span data-ttu-id="f6fae-244">Kein Rollforward.</span><span class="sxs-lookup"><span data-stu-id="f6fae-244">Don't roll forward.</span></span> <span data-ttu-id="f6fae-245">Nur Binden an angegebene Version.</span><span class="sxs-lookup"><span data-stu-id="f6fae-245">Only bind to specified version.</span></span> <span data-ttu-id="f6fae-246">Diese Richtlinie wird nicht zur allgemeinen Verwendung empfohlen, da sie die Möglichkeit eines Rollforwards zu den neuesten Patches ausschließt.</span><span class="sxs-lookup"><span data-stu-id="f6fae-246">This policy isn't recommended for general use because it disables the ability to roll forward to the latest patches.</span></span> <span data-ttu-id="f6fae-247">Dieser Wert wird nur zu Testzwecken empfohlen.</span><span class="sxs-lookup"><span data-stu-id="f6fae-247">This value is only recommended for testing.</span></span>

<span data-ttu-id="f6fae-248">Abgesehen von der **Disable**-Einstellung verwenden alle Einstellungen die höchste verfügbare Patchversion.</span><span class="sxs-lookup"><span data-stu-id="f6fae-248">Besides the **Disable** setting, all settings will use the highest available patch version.</span></span>

<span data-ttu-id="f6fae-249">Wenn die angeforderte Version (wie in `.runtimeconfig.json` für die Anwendung angegeben) eine endgültige Produktversion ist, werden standardmäßig nur endgültige Produktversionen für das Rollforward berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="f6fae-249">By default, if the requested version (as specified in `.runtimeconfig.json` for the application) is a release version, only release versions are considered for roll forward.</span></span> <span data-ttu-id="f6fae-250">Vorabversionen werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="f6fae-250">Any pre-release versions are ignored.</span></span> <span data-ttu-id="f6fae-251">Wenn keine passende endgültige Produktversion vorhanden ist, werden Vorabversionen berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="f6fae-251">If there is no matching release version, then pre-release versions are taken into account.</span></span> <span data-ttu-id="f6fae-252">Dieses Verhalten kann durch Festlegen von `DOTNET_ROLL_FORWARD_TO_PRERELEASE=1` geändert werden. In diesem Fall werden immer alle Versionen berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="f6fae-252">This behavior can be changed by setting `DOTNET_ROLL_FORWARD_TO_PRERELEASE=1`, in which case all versions are always considered.</span></span>

### <a name="build-copies-dependencies"></a><span data-ttu-id="f6fae-253">Build kopiert Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="f6fae-253">Build copies dependencies</span></span>

<span data-ttu-id="f6fae-254">Der `dotnet build`-Befehl kopiert jetzt NuGet-Abhängigkeiten für Ihre Anwendung aus dem NuGet-Cache in den Buildausgabeordner.</span><span class="sxs-lookup"><span data-stu-id="f6fae-254">The `dotnet build` command now copies NuGet dependencies for your application from the NuGet cache to the build output folder.</span></span> <span data-ttu-id="f6fae-255">Bisher wurde Abhängigkeiten nur als Teil von `dotnet publish` kopiert.</span><span class="sxs-lookup"><span data-stu-id="f6fae-255">Previously, dependencies were only copied as part of `dotnet publish`.</span></span>

<span data-ttu-id="f6fae-256">Es gibt einige Vorgänge, wie das Verlinken und das Veröffentlichen von Razor-Seiten, die noch veröffentlicht werden müssen.</span><span class="sxs-lookup"><span data-stu-id="f6fae-256">There are some operations, like linking and razor page publishing that will still require publishing.</span></span>

### <a name="local-tools"></a><span data-ttu-id="f6fae-257">Lokale Tools</span><span class="sxs-lookup"><span data-stu-id="f6fae-257">Local tools</span></span>

<span data-ttu-id="f6fae-258">Mit .NET Core 3.0 werden lokale Tools eingeführt.</span><span class="sxs-lookup"><span data-stu-id="f6fae-258">.NET Core 3.0 introduces local tools.</span></span> <span data-ttu-id="f6fae-259">Lokale Tools ähneln [globalen Tools](../tools/global-tools.md), sind aber mit einem bestimmten Speicherort auf dem Datenträger verknüpft.</span><span class="sxs-lookup"><span data-stu-id="f6fae-259">Local tools are similar to [global tools](../tools/global-tools.md) but are associated with a particular location on disk.</span></span> <span data-ttu-id="f6fae-260">Lokale Tools sind nicht global verfügbar und werden als NuGet-Pakete verteilt.</span><span class="sxs-lookup"><span data-stu-id="f6fae-260">Local tools aren't available globally and are distributed as NuGet packages.</span></span>

> [!WARNING]
> <span data-ttu-id="f6fae-261">Wenn Sie lokale Tools in .NET Core 3.0 Preview 1 ausprobiert haben, z.B. Ausführung von `dotnet tool restore` oder `dotnet tool install`, löschen Sie den Cacheordner der lokalen Tools.</span><span class="sxs-lookup"><span data-stu-id="f6fae-261">If you tried local tools in .NET Core 3.0 Preview 1, such as running `dotnet tool restore` or `dotnet tool install`, delete the local tools cache folder.</span></span> <span data-ttu-id="f6fae-262">Andernfalls funktionieren die lokalen Tools nicht in einem neueren Release.</span><span class="sxs-lookup"><span data-stu-id="f6fae-262">Otherwise, local tools won't work on any newer release.</span></span> <span data-ttu-id="f6fae-263">Je nach Betriebssystem werden die Ordnerpfade wie folgt gelöscht:</span><span class="sxs-lookup"><span data-stu-id="f6fae-263">This folder is located at:</span></span>
>
> <span data-ttu-id="f6fae-264">Unter macOS, Linux: `rm -r $HOME/.dotnet/toolResolverCache`</span><span class="sxs-lookup"><span data-stu-id="f6fae-264">On macOS, Linux: `rm -r $HOME/.dotnet/toolResolverCache`</span></span>
>
> <span data-ttu-id="f6fae-265">Windows: `rmdir /s %USERPROFILE%\.dotnet\toolResolverCache`</span><span class="sxs-lookup"><span data-stu-id="f6fae-265">On Windows: `rmdir /s %USERPROFILE%\.dotnet\toolResolverCache`</span></span>

<span data-ttu-id="f6fae-266">Lokale Tools basieren auf einer Manifestdatei `dotnet-tools.json` in Ihrem aktuellen Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="f6fae-266">Local tools rely on a manifest file name `dotnet-tools.json` in your current directory.</span></span> <span data-ttu-id="f6fae-267">In dieser Manifestdatei werden die Tools festgelegt, die im Verzeichnis und in den Unterverzeichnissen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="f6fae-267">This manifest file defines the tools to be available at that folder and below.</span></span> <span data-ttu-id="f6fae-268">Sie können die Manifestdatei mit dem Code verteilen, um sicherzustellen, dass jeder Benutzer, der mit Ihrem Code arbeitet, dieselben Tools wiederherstellen und verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="f6fae-268">You can distribute the manifest file with your code to ensure that anyone who works with your code can restore and use the same tools.</span></span>

<span data-ttu-id="f6fae-269">Für sowohl globale als auch lokale Tools ist eine kompatible Version der Runtime erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f6fae-269">For both global and local tools, a compatible version of the runtime is required.</span></span> <span data-ttu-id="f6fae-270">Die meisten Tools führen derzeit NuGet.org target .NET Core Runtime 2.1 aus.</span><span class="sxs-lookup"><span data-stu-id="f6fae-270">Many tools currently on NuGet.org target .NET Core Runtime 2.1.</span></span> <span data-ttu-id="f6fae-271">Um diese Tools global oder lokal zu installieren, müssten Sie weiterhin die [NET Core 2.1-Runtime](https://dotnet.microsoft.com/download/dotnet-core/2.1) installieren.</span><span class="sxs-lookup"><span data-stu-id="f6fae-271">To install these tools globally or locally, you would still need to install the [NET Core 2.1 Runtime](https://dotnet.microsoft.com/download/dotnet-core/2.1).</span></span>

### <a name="new-globaljson-options"></a><span data-ttu-id="f6fae-272">Neue global.json-Optionen</span><span class="sxs-lookup"><span data-stu-id="f6fae-272">New global.json options</span></span>

<span data-ttu-id="f6fae-273">Die Datei *global.json* verfügt über neue Optionen, die mehr Flexibilität bei der Definition der verwendeten .NET Core SDK-Version bieten.</span><span class="sxs-lookup"><span data-stu-id="f6fae-273">The *global.json* file has new options that provide more flexibility when you're trying to define which version of the .NET Core SDK is used.</span></span> <span data-ttu-id="f6fae-274">Folgende neue Optionen sind verfügbar:</span><span class="sxs-lookup"><span data-stu-id="f6fae-274">The new options are:</span></span>

- <span data-ttu-id="f6fae-275">`allowPrerelease`: Gibt an, ob der SDK-Resolver bei der Auswahl der zu verwendenden SDK-Version Vorabversionen berücksichtigen soll.</span><span class="sxs-lookup"><span data-stu-id="f6fae-275">`allowPrerelease`: Indicates whether the SDK resolver should consider prerelease versions when selecting the SDK version to use.</span></span>
- <span data-ttu-id="f6fae-276">`rollForward`: Gibt die Rollforwardrichtlinie an, die beim Auswählen einer SDK-Version verwendet werden soll, entweder als Fallback, wenn eine bestimmte SDK-Version fehlt, oder als Anweisung, damit eine höhere Version verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f6fae-276">`rollForward`: Indicates the roll-forward policy to use when selecting an SDK version, either as a fallback when a specific SDK version is missing or as a directive to use a higher version.</span></span>

<span data-ttu-id="f6fae-277">Weitere Informationen zu den Änderungen, einschließlich Standardwerten, unterstützten Werten und neuen Abgleichsregeln, finden Sie unter [global.json: Übersicht](../tools/global-json.md).</span><span class="sxs-lookup"><span data-stu-id="f6fae-277">For more information about the changes including default values, supported values, and new matching rules, see [global.json overview](../tools/global-json.md).</span></span>

### <a name="smaller-garbage-collection-heap-sizes"></a><span data-ttu-id="f6fae-278">Kleinere Garbage Collection-Heapgrößen</span><span class="sxs-lookup"><span data-stu-id="f6fae-278">Smaller Garbage Collection heap sizes</span></span>

<span data-ttu-id="f6fae-279">Die Standardheapgröße des Garbage Collectors wurde reduziert, sodass .NET Core weniger Arbeitsspeicher benötigt.</span><span class="sxs-lookup"><span data-stu-id="f6fae-279">The Garbage Collector's default heap size has been reduced resulting in .NET Core using less memory.</span></span> <span data-ttu-id="f6fae-280">Diese Änderung entspricht eher dem Zuordnungsbudget von Generation 0 mit modernen Prozessorcachegrößen.</span><span class="sxs-lookup"><span data-stu-id="f6fae-280">This change better aligns with the generation 0 allocation budget with modern processor cache sizes.</span></span>

### <a name="garbage-collection-large-page-support"></a><span data-ttu-id="f6fae-281">Garbage Collection: Unterstützung von „Large Pages“</span><span class="sxs-lookup"><span data-stu-id="f6fae-281">Garbage Collection Large Page support</span></span>

<span data-ttu-id="f6fae-282">„Large Pages“ (umfangreiche Seiten, unter Linux auch als „Huge Pages“ bekannt) ist eine Funktion, die dem Betriebssystem ermöglicht, Speicherbereiche einzurichten, die die native Seitengröße (häufig 4KB) überschreiten, um die Leistung der Anwendung zu verbessern, die diese große Seiten anfordert.</span><span class="sxs-lookup"><span data-stu-id="f6fae-282">Large Pages (also known as Huge Pages on Linux) is a feature where the operating system is able to establish memory regions larger than the native page size (often 4K) to improve performance of the application requesting these large pages.</span></span>

<span data-ttu-id="f6fae-283">Der Garbage Collector kann nun mit der Einstellung **GCLargePages** als Aktivierungsfeature zum Auswählen der Zuordnung großer Seiten auf Windows konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="f6fae-283">The Garbage Collector can now be configured with the **GCLargePages** setting as an opt-in feature to choose to allocate large pages on Windows.</span></span>

## <a name="windows-desktop--com"></a><span data-ttu-id="f6fae-284">Windows Desktop und COM</span><span class="sxs-lookup"><span data-stu-id="f6fae-284">Windows Desktop & COM</span></span>

### <a name="net-core-sdk-windows-installer"></a><span data-ttu-id="f6fae-285">Windows Installer von .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="f6fae-285">.NET Core SDK Windows Installer</span></span>

<span data-ttu-id="f6fae-286">Das MSI-Installationsprogramm für Windows wurde ab .NET Core 3.0 geändert.</span><span class="sxs-lookup"><span data-stu-id="f6fae-286">The MSI installer for Windows has changed starting with .NET Core 3.0.</span></span> <span data-ttu-id="f6fae-287">Die SDK-Installer aktualisieren nun vorhandene Releases von SDK-Featuregruppen.</span><span class="sxs-lookup"><span data-stu-id="f6fae-287">The SDK installers will now upgrade SDK feature-band releases in place.</span></span> <span data-ttu-id="f6fae-288">Featuregruppen werden in den *Hundertergruppen* des *Patchabschnitts* der Versionsnummer definiert.</span><span class="sxs-lookup"><span data-stu-id="f6fae-288">Feature bands are defined in the *hundreds* groups in the *patch* section of the version number.</span></span> <span data-ttu-id="f6fae-289">**3.0._101_** und **3.0._201_** sind beispielsweise Versionen in zwei verschiedenen Featuregruppen, während sich **3.0._101_** und **3.0._199_** in derselben Featuregruppe befinden.</span><span class="sxs-lookup"><span data-stu-id="f6fae-289">For example, **3.0._101_** and **3.0._201_** are versions in two different feature bands while **3.0._101_** and **3.0._199_** are in the same feature band.</span></span> <span data-ttu-id="f6fae-290">Wenn .NET Core SDK **3.0._101_** installiert wird, wird .NET Core SDK **3.0._100_** (sofern vorhanden) vom Computer entfernt.</span><span class="sxs-lookup"><span data-stu-id="f6fae-290">And, when .NET Core SDK **3.0._101_** is installed, .NET Core SDK **3.0._100_** will be removed from the machine if it exists.</span></span> <span data-ttu-id="f6fae-291">Wenn .NET Core SDK **3.0._200_** auf demselben Computer installiert ist, wird .NET Core SDK **3.0._101_** nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="f6fae-291">When .NET Core SDK **3.0._200_** is installed on the same machine, .NET Core SDK **3.0._101_** won't be removed.</span></span>

<span data-ttu-id="f6fae-292">Weitere Informationen zur Versionsverwaltung finden Sie unter [Übersicht über die .NET Core-Versionsverwaltung](../versions/index.md).</span><span class="sxs-lookup"><span data-stu-id="f6fae-292">For more information about versioning, see [Overview of how .NET Core is versioned](../versions/index.md).</span></span>

### <a name="windows-desktop"></a><span data-ttu-id="f6fae-293">Windows-Desktop</span><span class="sxs-lookup"><span data-stu-id="f6fae-293">Windows desktop</span></span>

<span data-ttu-id="f6fae-294">.NET Core 3.0 unterstützt die Windows-Desktopanwendungen mit Windows Presentation Foundation (WPF) und Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="f6fae-294">.NET Core 3.0 supports Windows desktop applications using Windows Presentation Foundation (WPF) and Windows Forms.</span></span> <span data-ttu-id="f6fae-295">Diese Frameworks unterstützt auch die Verwendung moderner Steuerelemente und des Fluent-Stils aus der Windows-UI-XAML-Bibliothek (WinUI) über [XAML-Inseln](/windows/uwp/xaml-platform/xaml-host-controls).</span><span class="sxs-lookup"><span data-stu-id="f6fae-295">These frameworks also support using modern controls and Fluent styling from the Windows UI XAML Library (WinUI) via [XAML islands](/windows/uwp/xaml-platform/xaml-host-controls).</span></span>

<span data-ttu-id="f6fae-296">Die Windows Desktop-Komponente ist Teil des Windows .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="f6fae-296">The Windows Desktop component is part of the Windows .NET Core 3.0 SDK.</span></span>

<span data-ttu-id="f6fae-297">Mit dem folgenden `dotnet`-Befehl können Sie eine neue WPF- oder Windows Forms-Anwendung erstellen:</span><span class="sxs-lookup"><span data-stu-id="f6fae-297">You can create a new WPF or Windows Forms app with the following `dotnet` commands:</span></span>

```dotnetcli
dotnet new wpf
dotnet new winforms
```

<span data-ttu-id="f6fae-298">Neu in Visual Studio 2019 sind Vorlagen für die Option **Neues Projekt** für Windows Forms und WPF in .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="f6fae-298">Visual Studio 2019 adds **New Project** templates for .NET Core 3.0 Windows Forms and WPF.</span></span>

<span data-ttu-id="f6fae-299">Weitere Informationen zum Portieren einer vorhandenen .NET Framework-Anwendung finden Sie unter [Portieren von WPF-Projekten](/dotnet/desktop/wpf/migration/convert-project-from-net-framework) und [Portieren von Windows Forms-Projekten](/dotnet/desktop/winforms/migration/?view=netdesktop-5.0&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="f6fae-299">For more information about how to port an existing .NET Framework application, see [Port WPF projects](/dotnet/desktop/wpf/migration/convert-project-from-net-framework) and [Port Windows Forms projects](/dotnet/desktop/winforms/migration/?view=netdesktop-5.0&preserve-view=true).</span></span>

#### <a name="winforms-high-dpi"></a><span data-ttu-id="f6fae-300">WinForms mit hohem DPI-Wert</span><span class="sxs-lookup"><span data-stu-id="f6fae-300">WinForms high DPI</span></span>

<span data-ttu-id="f6fae-301">.NET Core-Windows Forms-Anwendungen können den Modus für hohe DPI-Werte mit <xref:System.Windows.Forms.Application.SetHighDpiMode(System.Windows.Forms.HighDpiMode)?displayProperty=nameWithType> festlegen.</span><span class="sxs-lookup"><span data-stu-id="f6fae-301">.NET Core Windows Forms applications can set high DPI mode with <xref:System.Windows.Forms.Application.SetHighDpiMode(System.Windows.Forms.HighDpiMode)?displayProperty=nameWithType>.</span></span> <span data-ttu-id="f6fae-302">Die `SetHighDpiMode`-Methode legt den entsprechenden Modus für hohe DPI-Werte fest, sofern er nicht mit anderen Mitteln wie `App.Manifest` oder „P/Invoke“ vor dem `Application.Run` festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="f6fae-302">The `SetHighDpiMode` method sets the corresponding high DPI mode unless the setting has been set by other means like `App.Manifest` or P/Invoke before `Application.Run`.</span></span>

<span data-ttu-id="f6fae-303">Die möglichen `highDpiMode`-Werte, wie durch die <xref:System.Windows.Forms.HighDpiMode?displayProperty=nameWithType>-Enumeration ausgedrückt, sind:</span><span class="sxs-lookup"><span data-stu-id="f6fae-303">The possible `highDpiMode` values, as expressed by the <xref:System.Windows.Forms.HighDpiMode?displayProperty=nameWithType> enum are:</span></span>

- `DpiUnaware`
- `SystemAware`
- `PerMonitor`
- `PerMonitorV2`
- `DpiUnawareGdiScaled`

<span data-ttu-id="f6fae-304">Weitere Informationen zu hohen DPI-Werten finden Sie unter [Entwicklung von Desktopanwendungen mit hohen DPI-Werten unter Windows](/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows).</span><span class="sxs-lookup"><span data-stu-id="f6fae-304">For more information about high DPI modes, see [High DPI Desktop Application Development on Windows](/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows).</span></span>

### <a name="create-com-components"></a><span data-ttu-id="f6fae-305">Erstellen von COM-Komponenten</span><span class="sxs-lookup"><span data-stu-id="f6fae-305">Create COM components</span></span>

<span data-ttu-id="f6fae-306">Unter Windows können Sie jetzt COM-aufrufbare verwaltete Komponenten erstellen.</span><span class="sxs-lookup"><span data-stu-id="f6fae-306">On Windows, you can now create COM-callable managed components.</span></span> <span data-ttu-id="f6fae-307">Diese Funktion ist für die Verwendung von .NET Core mit COM-Add-in-Modellen und auch zur Parität mit .NET Framework wichtig.</span><span class="sxs-lookup"><span data-stu-id="f6fae-307">This capability is critical to use .NET Core with COM add-in models and also to provide parity with .NET Framework.</span></span>

<span data-ttu-id="f6fae-308">Im Gegensatz zu .NET Framework, wo *mscoree.dll* als COM-Server verwendet wurde, fügt .NET Core dem *bin*-Verzeichnis eine native Startprogramm-DLL hinzu, wenn Sie Ihre COM-Komponente erstellen.</span><span class="sxs-lookup"><span data-stu-id="f6fae-308">Unlike .NET Framework where the *mscoree.dll* was used as the COM server, .NET Core will add a native launcher dll to the *bin* directory when you build your COM component.</span></span>

<span data-ttu-id="f6fae-309">Ein Beispiel für das Erstellen einer COM‑Komponente und ihre Verwendung finden Sie in der [COM-Demo](https://github.com/dotnet/samples/tree/master/core/extensions/COMServerDemo).</span><span class="sxs-lookup"><span data-stu-id="f6fae-309">For an example of how to create a COM component and consume it, see the [COM Demo](https://github.com/dotnet/samples/tree/master/core/extensions/COMServerDemo).</span></span>

### <a name="windows-native-interop"></a><span data-ttu-id="f6fae-310">Native Windows-Interop-API</span><span class="sxs-lookup"><span data-stu-id="f6fae-310">Windows Native Interop</span></span>

<span data-ttu-id="f6fae-311">Windows stellt eine umfassende native API mit grundlegenden C-APIs (ohne C++-Features), COM und WinRT bereit.</span><span class="sxs-lookup"><span data-stu-id="f6fae-311">Windows offers a rich native API in the form of flat C APIs, COM, and WinRT.</span></span> <span data-ttu-id="f6fae-312">Während .NET Core **P/Invoke** unterstützt, fügt .NET Core 3.0 die Fähigkeit zum **CoCreate von COM-APIs** und **Aktivieren von WinRT-APIs** hinzu.</span><span class="sxs-lookup"><span data-stu-id="f6fae-312">While .NET Core supports **P/Invoke**, .NET Core 3.0 adds the ability to **CoCreate COM APIs** and **Activate WinRT APIs**.</span></span> <span data-ttu-id="f6fae-313">Ein Codebeispiel finden Sie in der [Excel-Demo](https://github.com/dotnet/samples/tree/master/core/extensions/ExcelDemo).</span><span class="sxs-lookup"><span data-stu-id="f6fae-313">For a code example, see the [Excel Demo](https://github.com/dotnet/samples/tree/master/core/extensions/ExcelDemo).</span></span>

### <a name="msix-deployment"></a><span data-ttu-id="f6fae-314">MSIX-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="f6fae-314">MSIX Deployment</span></span>

<span data-ttu-id="f6fae-315">[MSIX](/windows/msix/) ist ein neues Windows-Anwendungspaketformat.</span><span class="sxs-lookup"><span data-stu-id="f6fae-315">[MSIX](/windows/msix/) is a new Windows application package format.</span></span> <span data-ttu-id="f6fae-316">Es kann zum Bereitstellen von .NET Core 3.0-Desktopanwendungen auf Windows 10 verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f6fae-316">It can be used to deploy .NET Core 3.0 desktop applications to Windows 10.</span></span>

<span data-ttu-id="f6fae-317">In Visual Studio 2019 können mit dem enthaltenen [Paketerstellungsprojekt für Windows-Anwendungen](/windows/uwp/porting/desktop-to-uwp-packaging-dot-net) MSIX-Pakete mit [eigenständigen](../deploying/index.md#publish-self-contained) .NET Core-Anwendungen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="f6fae-317">The [Windows Application Packaging Project](/windows/uwp/porting/desktop-to-uwp-packaging-dot-net), available in Visual Studio 2019, allows you to create MSIX packages with [self-contained](../deploying/index.md#publish-self-contained) .NET Core applications.</span></span>

<span data-ttu-id="f6fae-318">Die unterstützten Laufzeiten müssen in der `<RuntimeIdentifiers>`-Eigenschaft der .NET Core-Projektdatei angegeben werden:</span><span class="sxs-lookup"><span data-stu-id="f6fae-318">The .NET Core project file must specify the supported runtimes in the `<RuntimeIdentifiers>` property:</span></span>

```xml
<RuntimeIdentifiers>win-x86;win-x64</RuntimeIdentifiers>
```

## <a name="linux-improvements"></a><span data-ttu-id="f6fae-319">Verbesserungen für Linux</span><span class="sxs-lookup"><span data-stu-id="f6fae-319">Linux improvements</span></span>

### <a name="serialport-for-linux"></a><span data-ttu-id="f6fae-320">SerialPort für Linux</span><span class="sxs-lookup"><span data-stu-id="f6fae-320">SerialPort for Linux</span></span>

<span data-ttu-id="f6fae-321">.NET Core 3.0 bietet grundlegende Unterstützung für <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType> unter Linux.</span><span class="sxs-lookup"><span data-stu-id="f6fae-321">.NET Core 3.0 provides basic support for <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType> on Linux.</span></span>

<span data-ttu-id="f6fae-322">Bisher unterstützte .NET Core nur die Verwendung von `SerialPort` auf Windows.</span><span class="sxs-lookup"><span data-stu-id="f6fae-322">Previously, .NET Core only supported using `SerialPort` on Windows.</span></span>

<span data-ttu-id="f6fae-323">Weitere Informationen zur eingeschränkten Unterstützung für den seriellen Anschluss unter Linux finden Sie unter [GitHub-Issue 33146](https://github.com/dotnet/corefx/issues/33146).</span><span class="sxs-lookup"><span data-stu-id="f6fae-323">For more information about the limited support for the serial port on Linux, see [GitHub issue #33146](https://github.com/dotnet/corefx/issues/33146).</span></span>

### <a name="docker-and-cgroup-memory-limits"></a><span data-ttu-id="f6fae-324">Arbeitsspeicherlimits bei Docker und Cgroup</span><span class="sxs-lookup"><span data-stu-id="f6fae-324">Docker and cgroup memory Limits</span></span>

<span data-ttu-id="f6fae-325">Die Ausführung von .NET Core 3.0 unter Linux mit Docker funktioniert besser mit Cgroup-Arbeitsspeicherlimits.</span><span class="sxs-lookup"><span data-stu-id="f6fae-325">Running .NET Core 3.0 on Linux with Docker works better with cgroup memory limits.</span></span> <span data-ttu-id="f6fae-326">Das Ausführen eines Docker-Containers mit Arbeitsspeicherlimits, z.B. mit `docker run -m`, ändert das Verhalten von .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f6fae-326">Running a Docker container with memory limits, such as with `docker run -m`, changes how .NET Core behaves.</span></span>

- <span data-ttu-id="f6fae-327">Standardmäßige Heapgröße des Garbage Collectors (GC): maximal 20MB oder 75% des Arbeitsspeicherlimits für den Container.</span><span class="sxs-lookup"><span data-stu-id="f6fae-327">Default Garbage Collector (GC) heap size: maximum of 20 mb or 75% of the memory limit on the container.</span></span>
- <span data-ttu-id="f6fae-328">Die explizite Größe kann als absolute Anzahl oder Prozentsatz des Cgroup-Limits festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="f6fae-328">Explicit size can be set as an absolute number or percentage of cgroup limit.</span></span>
- <span data-ttu-id="f6fae-329">Die minimale reservierte Segmentgröße pro GC-Heap beträgt 16MB.</span><span class="sxs-lookup"><span data-stu-id="f6fae-329">Minimum reserved segment size per GC heap is 16 mb.</span></span> <span data-ttu-id="f6fae-330">Diese Größe reduziert die Anzahl der Heaps, die auf Computern erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="f6fae-330">This size reduces the number of heaps that are created on machines.</span></span>

### <a name="gpio-support-for-raspberry-pi"></a><span data-ttu-id="f6fae-331">GPIO-Unterstützung für Raspberry Pi</span><span class="sxs-lookup"><span data-stu-id="f6fae-331">GPIO Support for Raspberry Pi</span></span>

<span data-ttu-id="f6fae-332">Über NuGet können nun zwei Pakete für die GPIO-Programmierung bezogen werden:</span><span class="sxs-lookup"><span data-stu-id="f6fae-332">Two packages have been released to NuGet that you can use for GPIO programming:</span></span>

- [<span data-ttu-id="f6fae-333">System.Device.Gpio</span><span class="sxs-lookup"><span data-stu-id="f6fae-333">System.Device.Gpio</span></span>](https://www.nuget.org/packages/System.Device.Gpio)
- [<span data-ttu-id="f6fae-334">Iot.Device.Bindings</span><span class="sxs-lookup"><span data-stu-id="f6fae-334">Iot.Device.Bindings</span></span>](https://www.nuget.org/packages/Iot.Device.Bindings)

<span data-ttu-id="f6fae-335">Die GPIO-Pakete enthalten APIs für *GPIO*-, *SPI*-, *I2C*- und *PWM*-Geräte.</span><span class="sxs-lookup"><span data-stu-id="f6fae-335">The GPIO packages include APIs for *GPIO*, *SPI*, *I2C*, and *PWM* devices.</span></span> <span data-ttu-id="f6fae-336">Das IoT-Bindungenpaket enthält Gerätebindungen.</span><span class="sxs-lookup"><span data-stu-id="f6fae-336">The IoT bindings package includes device bindings.</span></span> <span data-ttu-id="f6fae-337">Weitere Informationen finden Sie im [GitHub-Repository zu Geräten](https://github.com/dotnet/iot/blob/master/src/devices/).</span><span class="sxs-lookup"><span data-stu-id="f6fae-337">For more information, see the [devices GitHub repo](https://github.com/dotnet/iot/blob/master/src/devices/).</span></span>

### <a name="arm64-linux-support"></a><span data-ttu-id="f6fae-338">ARM64-Linux-Support</span><span class="sxs-lookup"><span data-stu-id="f6fae-338">ARM64 Linux support</span></span>

<span data-ttu-id="f6fae-339">.NET Core 3.0 fügt Unterstützung für ARM64 für Linux hinzu.</span><span class="sxs-lookup"><span data-stu-id="f6fae-339">.NET Core 3.0 adds support for ARM64 for Linux.</span></span> <span data-ttu-id="f6fae-340">Der primäre Anwendungsfall für ARM64 sind derzeit IoT-Szenarien.</span><span class="sxs-lookup"><span data-stu-id="f6fae-340">The primary use case for ARM64 is currently with IoT scenarios.</span></span> <span data-ttu-id="f6fae-341">Weitere Informationen finden Sie unter [.NET Core Runtime ARM64 Status](https://github.com/dotnet/announcements/issues/82) (.NET Core-Runtime-ARM64-Status).</span><span class="sxs-lookup"><span data-stu-id="f6fae-341">For more information, see [.NET Core ARM64 Status](https://github.com/dotnet/announcements/issues/82).</span></span>

<span data-ttu-id="f6fae-342">[Dockerimages für .NET Core unter ARM64](https://hub.docker.com/r/microsoft/dotnet/) sind für Alpine, Debian und Ubuntu verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f6fae-342">[Docker images for .NET Core on ARM64](https://hub.docker.com/r/microsoft/dotnet/) are available for Alpine, Debian, and Ubuntu.</span></span>

> [!NOTE]
> <span data-ttu-id="f6fae-343">**ARM64** wird von Windows noch nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f6fae-343">**ARM64** Windows support isn't yet available.</span></span>

## <a name="security"></a><span data-ttu-id="f6fae-344">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="f6fae-344">Security</span></span>

### <a name="tls-13--openssl-111-on-linux"></a><span data-ttu-id="f6fae-345">TLS 1.3 & OpenSSL 1.1.1 auf Linux</span><span class="sxs-lookup"><span data-stu-id="f6fae-345">TLS 1.3 & OpenSSL 1.1.1 on Linux</span></span>

<span data-ttu-id="f6fae-346">.NET Core nutzt nun die Unterstützung von [TLS 1.3 in OpenSSL 1.1.1.1](https://www.openssl.org/blog/blog/2018/09/11/release111/), wenn es in einer bestimmten Umgebung verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="f6fae-346">.NET Core now takes advantage of [TLS 1.3 support in OpenSSL 1.1.1](https://www.openssl.org/blog/blog/2018/09/11/release111/), when it's available in a given environment.</span></span> <span data-ttu-id="f6fae-347">Mit TLS 1.3:</span><span class="sxs-lookup"><span data-stu-id="f6fae-347">With TLS 1.3:</span></span>

- <span data-ttu-id="f6fae-348">Verbindungszeiten werden durch Reduzierung der erforderlichen Roundtrips zwischen Client und Server verbessert.</span><span class="sxs-lookup"><span data-stu-id="f6fae-348">Connection times are improved with reduced round trips required between the client and server.</span></span>
- <span data-ttu-id="f6fae-349">Verbesserte Sicherheit wg. Entfernen verschiedener veralteter und unsicherer kryptografischer Algorithmen.</span><span class="sxs-lookup"><span data-stu-id="f6fae-349">Improved security because of the removal of various obsolete and insecure cryptographic algorithms.</span></span>

<span data-ttu-id="f6fae-350">Sofern verfügbar, verwendet .NET Core 3.0 **OpenSSL 1.1.1**, **OpenSSL 1.1.0** oder **OpenSSL 1.0.2** auf einem Linuxsystem.</span><span class="sxs-lookup"><span data-stu-id="f6fae-350">When available, .NET Core 3.0 uses **OpenSSL 1.1.1**, **OpenSSL 1.1.0**, or **OpenSSL 1.0.2** on a Linux system.</span></span> <span data-ttu-id="f6fae-351">Wenn **OpenSSL 1.1.1** verfügbar ist, verwendet sowohl der <xref:System.Net.Security.SslStream?displayProperty=nameWithType>- als auch <xref:System.Net.Http.HttpClient?displayProperty=nameWithType>-Typ **TLS 1.3** (vorausgesetzt, dass Client und Server **TLS 1.3** unterstützen).</span><span class="sxs-lookup"><span data-stu-id="f6fae-351">When **OpenSSL 1.1.1** is available, both <xref:System.Net.Security.SslStream?displayProperty=nameWithType> and <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> types will use **TLS 1.3** (assuming both the client and server support **TLS 1.3**).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f6fae-352">Windows und macOS unterstützen **TLS 1.3** noch nicht.</span><span class="sxs-lookup"><span data-stu-id="f6fae-352">Windows and macOS do not yet support **TLS 1.3**.</span></span>

<span data-ttu-id="f6fae-353">Das folgende Beispiel für C# 8.0 veranschaulicht das Herstellen der Verbindung von .NET Core 3.0 auf Ubuntu 18.10 mit <https://www.cloudflare.com>:</span><span class="sxs-lookup"><span data-stu-id="f6fae-353">The following C# 8.0 example demonstrates .NET Core 3.0 on Ubuntu 18.10 connecting to <https://www.cloudflare.com>:</span></span>

[!code-csharp[TLSExample](./snippets/dotnet-core-3-0/csharp/TLS.cs#TLS)]

### <a name="cryptography-ciphers"></a><span data-ttu-id="f6fae-354">Kryptografieverschlüsselungen</span><span class="sxs-lookup"><span data-stu-id="f6fae-354">Cryptography ciphers</span></span>

<span data-ttu-id="f6fae-355">.NET 3.0 fügt Unterstützung für die Verschlüsselungsmodi **AES-GCM** und **AES-CCM** hinzu, die jeweils mit <xref:System.Security.Cryptography.AesGcm?displayProperty=nameWithType> bzw. <xref:System.Security.Cryptography.AesCcm?displayProperty=nameWithType> implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="f6fae-355">.NET Core 3.0 adds support for **AES-GCM** and **AES-CCM** ciphers, implemented with <xref:System.Security.Cryptography.AesGcm?displayProperty=nameWithType> and <xref:System.Security.Cryptography.AesCcm?displayProperty=nameWithType> respectively.</span></span> <span data-ttu-id="f6fae-356">Beide Algorithmen sind [AEAD-Algorithmen (Authenticated Encryption with Association Data)](https://en.wikipedia.org/wiki/Authenticated_encryption).</span><span class="sxs-lookup"><span data-stu-id="f6fae-356">These algorithms are both [Authenticated Encryption with Association Data (AEAD) algorithms](https://en.wikipedia.org/wiki/Authenticated_encryption).</span></span>

<span data-ttu-id="f6fae-357">Der folgende Code veranschaulicht die Verwendung der `AesGcm`-Verschlüsselung zum Verschlüsseln und Entschlüsseln von Zufallsdaten.</span><span class="sxs-lookup"><span data-stu-id="f6fae-357">The following code demonstrates using `AesGcm` cipher to encrypt and decrypt random data.</span></span>

[!code-csharp[AesGcm](./snippets/dotnet-core-3-0/csharp/Cipher.cs#AesGcm)]

### <a name="cryptographic-key-importexport"></a><span data-ttu-id="f6fae-358">Importieren/Exportieren kryptografischer Schlüssel</span><span class="sxs-lookup"><span data-stu-id="f6fae-358">Cryptographic Key Import/Export</span></span>

<span data-ttu-id="f6fae-359">.NET Core 3.0 unterstützt das Importieren und Exportieren der asymmetrischen öffentlichen und privaten Schlüssel aus den Standardformaten.</span><span class="sxs-lookup"><span data-stu-id="f6fae-359">.NET Core 3.0 supports the import and export of asymmetric public and private keys from standard formats.</span></span> <span data-ttu-id="f6fae-360">Sie müssen kein X.509-Zertifikat verwenden.</span><span class="sxs-lookup"><span data-stu-id="f6fae-360">You don't need to use an X.509 certificate.</span></span>

<span data-ttu-id="f6fae-361">Alle Schlüsseltypen wie *RSA*, *DSA*, *ECDsa* und *ECDiffieHellman* unterstützen die folgenden Formate:</span><span class="sxs-lookup"><span data-stu-id="f6fae-361">All key types, such as *RSA*, *DSA*, *ECDsa*, and *ECDiffieHellman*, support the following formats:</span></span>

- <span data-ttu-id="f6fae-362">**Öffentlicher Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="f6fae-362">**Public Key**</span></span>
  - <span data-ttu-id="f6fae-363">X.509 SubjectPublicKeyInfo</span><span class="sxs-lookup"><span data-stu-id="f6fae-363">X.509 SubjectPublicKeyInfo</span></span>

- <span data-ttu-id="f6fae-364">**Privater Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="f6fae-364">**Private key**</span></span>
  - <span data-ttu-id="f6fae-365">PKCS#8 PrivateKeyInfo</span><span class="sxs-lookup"><span data-stu-id="f6fae-365">PKCS#8 PrivateKeyInfo</span></span>
  - <span data-ttu-id="f6fae-366">PKCS#8 EncryptedPrivateKeyInfo</span><span class="sxs-lookup"><span data-stu-id="f6fae-366">PKCS#8 EncryptedPrivateKeyInfo</span></span>

<span data-ttu-id="f6fae-367">RSA-Schlüsseln unterstützen auch:</span><span class="sxs-lookup"><span data-stu-id="f6fae-367">RSA keys also support:</span></span>

- <span data-ttu-id="f6fae-368">**Öffentlicher Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="f6fae-368">**Public Key**</span></span>
  - <span data-ttu-id="f6fae-369">PKCS#1 RSAPublicKey</span><span class="sxs-lookup"><span data-stu-id="f6fae-369">PKCS#1 RSAPublicKey</span></span>

- <span data-ttu-id="f6fae-370">**Privater Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="f6fae-370">**Private key**</span></span>
  - <span data-ttu-id="f6fae-371">PKCS#1 RSAPrivateKey</span><span class="sxs-lookup"><span data-stu-id="f6fae-371">PKCS#1 RSAPrivateKey</span></span>

<span data-ttu-id="f6fae-372">Die Exportmethoden erstellen DER-kodierte Binärdaten, und die Importmethoden erwarten dasselbe.</span><span class="sxs-lookup"><span data-stu-id="f6fae-372">The export methods produce DER-encoded binary data, and the import methods expect the same.</span></span> <span data-ttu-id="f6fae-373">Wenn ein Schlüssel im textfreundlichen PEM-Format gespeichert ist, muss der Anrufer den Inhalt base64-dekodieren, bevor er eine Importmethode aufruft.</span><span class="sxs-lookup"><span data-stu-id="f6fae-373">If a key is stored in the text-friendly PEM format, the caller will need to base64-decode the content before calling an import method.</span></span>

[!code-csharp[RSA](./snippets/dotnet-core-3-0/csharp/RSA.cs#Rsa)]

<span data-ttu-id="f6fae-374">**PKCS#8**-Dateien können mit <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo?displayProperty=nameWithType> überprüft werden, und **PFX/PKCS#12**-Dateien mit <xref:System.Security.Cryptography.Pkcs.Pkcs12Info?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f6fae-374">**PKCS#8** files can be inspected with <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo?displayProperty=nameWithType> and **PFX/PKCS#12** files can be inspected with <xref:System.Security.Cryptography.Pkcs.Pkcs12Info?displayProperty=nameWithType>.</span></span> <span data-ttu-id="f6fae-375">**PFX/PKCS#12**-Dateien können mit <xref:System.Security.Cryptography.Pkcs.Pkcs12Builder?displayProperty=nameWithType> bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="f6fae-375">**PFX/PKCS#12** files can be manipulated with <xref:System.Security.Cryptography.Pkcs.Pkcs12Builder?displayProperty=nameWithType>.</span></span>

## <a name="net-core-30-api-changes"></a><span data-ttu-id="f6fae-376">Änderungen der .NET Core 3.0-API</span><span class="sxs-lookup"><span data-stu-id="f6fae-376">.NET Core 3.0 API changes</span></span>

### <a name="ranges-and-indices"></a><span data-ttu-id="f6fae-377">Bereiche und Indizes</span><span class="sxs-lookup"><span data-stu-id="f6fae-377">Ranges and indices</span></span>

<span data-ttu-id="f6fae-378">Der neue <xref:System.Index?displayProperty=nameWithType>-Typ kann für die Indizierung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f6fae-378">The new <xref:System.Index?displayProperty=nameWithType> type can be used for indexing.</span></span> <span data-ttu-id="f6fae-379">Sie können einen aus einem `int` erstellen, der vom Anfang aus zählt, oder mit einem Präfix-`^`-Operator (C#), der vom Ende aus zählt:</span><span class="sxs-lookup"><span data-stu-id="f6fae-379">You can create one from an `int` that counts from the beginning, or with a prefix `^` operator (C#) that counts from the end:</span></span>

```csharp
Index i1 = 3;  // number 3 from beginning
Index i2 = ^4; // number 4 from end
int[] a = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };
Console.WriteLine($"{a[i1]}, {a[i2]}"); // "3, 6"
```

<span data-ttu-id="f6fae-380">Es gibt auch einen <xref:System.Range?displayProperty=nameWithType>-Typ, der aus zwei `Index`-Werten besteht, einen für den Anfang und einen für das Ende, und mit einem `x..y`-Bereichsausdruck (C#) geschrieben werden kann.</span><span class="sxs-lookup"><span data-stu-id="f6fae-380">There's also the <xref:System.Range?displayProperty=nameWithType> type, which consists of two `Index` values, one for the start and one for the end, and can be written with a `x..y` range expression (C#).</span></span> <span data-ttu-id="f6fae-381">Sie können dann mit einem `Range` indizieren, der ein Segment erzeugt:</span><span class="sxs-lookup"><span data-stu-id="f6fae-381">You can then index with a `Range`, which produces a slice:</span></span>

```csharp
var slice = a[i1..i2]; // { 3, 4, 5 }
```

<span data-ttu-id="f6fae-382">Weitere Informationen finden Sie im Tutorial [Bereiche und Indizes](../../csharp/tutorials/ranges-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="f6fae-382">For more information, see the [ranges and indices tutorial](../../csharp/tutorials/ranges-indexes.md).</span></span>

### <a name="async-streams"></a><span data-ttu-id="f6fae-383">Asynchrone Datenströme</span><span class="sxs-lookup"><span data-stu-id="f6fae-383">Async streams</span></span>

<span data-ttu-id="f6fae-384">Die <xref:System.Collections.Generic.IAsyncEnumerable%601>-Typ ist eine neue asynchrone Version von <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="f6fae-384">The <xref:System.Collections.Generic.IAsyncEnumerable%601> type is a new asynchronous version of <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="f6fae-385">In C# 8.0 können Sie `await foreach` zur Verarbeitung der `IAsyncEnumerable<T>`-Elemente nutzen und anschließend `yield return` zum Erstellen von Elementen verwenden.</span><span class="sxs-lookup"><span data-stu-id="f6fae-385">The language lets you `await foreach` over `IAsyncEnumerable<T>` to consume their elements, and use `yield return` to them to produce elements.</span></span>

<span data-ttu-id="f6fae-386">Das folgende Beispiel zeigt sowohl die Produktion als auch die Nutzung von asynchronen Datenströmen.</span><span class="sxs-lookup"><span data-stu-id="f6fae-386">The following example demonstrates both production and consumption of async streams.</span></span> <span data-ttu-id="f6fae-387">Die `foreach`-Anweisung ist asynchron und verwendet `yield return`, um einen asynchronen Datenstrom für Anrufer zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f6fae-387">The `foreach` statement is async and itself uses `yield return` to produce an async stream for callers.</span></span> <span data-ttu-id="f6fae-388">Dieses Muster (mit `yield return`) ist das empfohlene Modell zum Erstellen von asynchronen Datenströmen.</span><span class="sxs-lookup"><span data-stu-id="f6fae-388">This pattern (using `yield return`) is the recommended model for producing async streams.</span></span>

```csharp
async IAsyncEnumerable<int> GetBigResultsAsync()
{
    await foreach (var result in GetResultsAsync())
    {
        if (result > 20) yield return result;
    }
}
```

<span data-ttu-id="f6fae-389">Zusätzlich zu `await foreach` können Sie auch asynchrone Iteratoren erstellen, z.B. einen Iterator, der `IAsyncEnumerable/IAsyncEnumerator` zurückgibt, in den Sie sowohl `await` als auch `yield` einfügen können.</span><span class="sxs-lookup"><span data-stu-id="f6fae-389">In addition to being able to `await foreach`, you can also create async iterators, for example, an iterator that returns an `IAsyncEnumerable/IAsyncEnumerator` that you can both `await` and `yield` in.</span></span> <span data-ttu-id="f6fae-390">Für Objekte, die gelöscht werden müssen, können Sie `IAsyncDisposable` verwenden, das von verschiedenen BCL-Typen implementiert wird, wie beispielsweise `Stream` und `Timer`.</span><span class="sxs-lookup"><span data-stu-id="f6fae-390">For objects that need to be disposed, you can use `IAsyncDisposable`, which various BCL types implement, such as `Stream` and `Timer`.</span></span>

<span data-ttu-id="f6fae-391">Weitere Informationen finden Sie im Tutorial [Generieren und Nutzen asynchroner Datenströme mit C# 8.0 und .NET Core 3.0](../../csharp/tutorials/generate-consume-asynchronous-stream.md).</span><span class="sxs-lookup"><span data-stu-id="f6fae-391">For more information, see the [async streams tutorial](../../csharp/tutorials/generate-consume-asynchronous-stream.md).</span></span>

### <a name="ieee-floating-point"></a><span data-ttu-id="f6fae-392">IEEE-Gleitkomma</span><span class="sxs-lookup"><span data-stu-id="f6fae-392">IEEE Floating-point</span></span>

<span data-ttu-id="f6fae-393">APIs für Gleitkommazahlen werden aktuell der [Revision des Standards IEEE 754-2008](https://en.wikipedia.org/wiki/IEEE_754-2008_revision) angepasst.</span><span class="sxs-lookup"><span data-stu-id="f6fae-393">Floating point APIs are being updated to comply with [IEEE 754-2008 revision](https://en.wikipedia.org/wiki/IEEE_754-2008_revision).</span></span> <span data-ttu-id="f6fae-394">Ziel dieser Änderungen ist, alle **erforderlichen** Operationen verfügbar zu machen und sicherzustellen, dass sie mit dem in der IEEE-Spezifikation beschriebenen Verhalten kompatibel sind. Weitere Informationen über Gleitkommaverbesserungen finden Sie im Blogbeitrag [Floating-Point Parsing and Formatting improvements in .NET Core 3.0](https://devblogs.microsoft.com/dotnet/floating-point-parsing-and-formatting-improvements-in-net-core-3-0/) (Verbesserungen zu Gleitkommaanalyse und Formatierung in .NET Core 3.0).</span><span class="sxs-lookup"><span data-stu-id="f6fae-394">The goal of these changes is to expose all **required** operations and ensure that they're behaviorally compliant with the IEEE spec. For more information about floating-point improvements, see the [Floating-Point Parsing and Formatting improvements in .NET Core 3.0](https://devblogs.microsoft.com/dotnet/floating-point-parsing-and-formatting-improvements-in-net-core-3-0/) blog post.</span></span>

<span data-ttu-id="f6fae-395">Zu den Korrekturen für Analyse und Formatierung zählen:</span><span class="sxs-lookup"><span data-stu-id="f6fae-395">Parsing and formatting fixes include:</span></span>

- <span data-ttu-id="f6fae-396">Eingaben mit beliebiger Länge werden richtig analysiert und gerundet.</span><span class="sxs-lookup"><span data-stu-id="f6fae-396">Correctly parse and round inputs of any length.</span></span>
- <span data-ttu-id="f6fae-397">Die negative Null wird richtig analysiert und formatiert.</span><span class="sxs-lookup"><span data-stu-id="f6fae-397">Correctly parse and format negative zero.</span></span>
- <span data-ttu-id="f6fae-398">`Infinity`- und `NaN`-Werte werden mithilfe einer Überprüfung, bei der nicht zwischen Groß-/Kleinbuchstaben unterschieden wird, richtig analysiert. Außerdem ist, falls erforderlich, optional das vorangestellte `+`-Zeichen zulässig.</span><span class="sxs-lookup"><span data-stu-id="f6fae-398">Correctly parse `Infinity` and `NaN` by doing a case-insensitive check and allowing an optional preceding `+` where applicable.</span></span>

<span data-ttu-id="f6fae-399">Zu den neuen <xref:System.Math?displayProperty=nameWithType>-APIs zählen:</span><span class="sxs-lookup"><span data-stu-id="f6fae-399">New <xref:System.Math?displayProperty=nameWithType> APIs include:</span></span>

- <span data-ttu-id="f6fae-400"><xref:System.Math.BitIncrement(System.Double)> und <xref:System.Math.BitDecrement(System.Double)></span><span class="sxs-lookup"><span data-stu-id="f6fae-400"><xref:System.Math.BitIncrement(System.Double)> and <xref:System.Math.BitDecrement(System.Double)></span></span>\
<span data-ttu-id="f6fae-401">entspricht den IEEE-Operationen `nextUp` und `nextDown`.</span><span class="sxs-lookup"><span data-stu-id="f6fae-401">Corresponds to the `nextUp` and `nextDown` IEEE operations.</span></span> <span data-ttu-id="f6fae-402">Diese geben jeweils die kleinste Gleitkommazahl zurück, die größer oder kleiner als der Eingabewert ist.</span><span class="sxs-lookup"><span data-stu-id="f6fae-402">They return the smallest floating-point number that compares greater or lesser than the input (respectively).</span></span> <span data-ttu-id="f6fae-403">`Math.BitIncrement(0.0)` gibt beispielsweise `double.Epsilon` zurück.</span><span class="sxs-lookup"><span data-stu-id="f6fae-403">For example, `Math.BitIncrement(0.0)` would return `double.Epsilon`.</span></span>

- <span data-ttu-id="f6fae-404"><xref:System.Math.MaxMagnitude(System.Double,System.Double)> und <xref:System.Math.MinMagnitude(System.Double,System.Double)></span><span class="sxs-lookup"><span data-stu-id="f6fae-404"><xref:System.Math.MaxMagnitude(System.Double,System.Double)> and <xref:System.Math.MinMagnitude(System.Double,System.Double)></span></span>\
<span data-ttu-id="f6fae-405">entspricht den IEEE-Operationen `maxNumMag` und `minNumMag`. Diese geben für zwei Eingabewerte jeweils den Wert zurück, für den ein größerer oder kleinerer Absolutbetrag ermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="f6fae-405">Corresponds to the `maxNumMag` and `minNumMag` IEEE operations, they return the value that is greater or lesser in magnitude of the two inputs (respectively).</span></span> <span data-ttu-id="f6fae-406">`Math.MaxMagnitude(2.0, -3.0)` gibt beispielsweise `-3.0` zurück.</span><span class="sxs-lookup"><span data-stu-id="f6fae-406">For example, `Math.MaxMagnitude(2.0, -3.0)` would return `-3.0`.</span></span>

- <xref:System.Math.ILogB(System.Double)>\
<span data-ttu-id="f6fae-407">Entspricht der IEEE-Operation `logB`, die einen integralen Wert zurückgibt. Der Rückgabewert ist der integrale Wert des Logarithmus zur Basis 2 des Eingabeparameters.</span><span class="sxs-lookup"><span data-stu-id="f6fae-407">Corresponds to the `logB` IEEE operation that returns an integral value, it returns the integral base-2 log of the input parameter.</span></span> <span data-ttu-id="f6fae-408">Diese Methode entspricht im Wesentlichen `floor(log2(x))`, jedoch ist der Rundungsfehler minimal.</span><span class="sxs-lookup"><span data-stu-id="f6fae-408">This method is effectively the same as `floor(log2(x))`, but done with minimal rounding error.</span></span>

- <xref:System.Math.ScaleB(System.Double,System.Int32)>\
<span data-ttu-id="f6fae-409">Entspricht der IEEE-Operation `scaleB`, der ein integraler Wert übergeben wird. Zurückgegeben wird im Wesentlichen `x * pow(2, n)`, jedoch ist der Rundungsfehler minimal.</span><span class="sxs-lookup"><span data-stu-id="f6fae-409">Corresponds to the `scaleB` IEEE operation that takes an integral value, it returns effectively `x * pow(2, n)`, but is done with minimal rounding error.</span></span>

- <xref:System.Math.Log2(System.Double)>\
<span data-ttu-id="f6fae-410">entspricht der IEEE-Operation `log2`, die den Logarithmus zur Basis 2 zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="f6fae-410">Corresponds to the `log2` IEEE operation, it returns the base-2 logarithm.</span></span> <span data-ttu-id="f6fae-411">Diese Operation minimiert den Rundungsfehler.</span><span class="sxs-lookup"><span data-stu-id="f6fae-411">It minimizes rounding error.</span></span>

- <xref:System.Math.FusedMultiplyAdd(System.Double,System.Double,System.Double)>\
<span data-ttu-id="f6fae-412">entspricht der IEEE-Operation `fma`, die eine Fused-Multiply-Add-Operation durchführt.</span><span class="sxs-lookup"><span data-stu-id="f6fae-412">Corresponds to the `fma` IEEE operation, it performs a fused multiply add.</span></span> <span data-ttu-id="f6fae-413">Dabei wird `(x * y) + z` als einzelne Operation ausgeführt, wodurch der Rundungsfehler minimiert wird.</span><span class="sxs-lookup"><span data-stu-id="f6fae-413">That is, it does `(x * y) + z` as a single operation, thereby minimizing the rounding error.</span></span> <span data-ttu-id="f6fae-414">Ein Beispiel hierfür ist `FusedMultiplyAdd(1e308, 2.0, -1e308)`, diese gibt `1e308` zurück.</span><span class="sxs-lookup"><span data-stu-id="f6fae-414">An example is `FusedMultiplyAdd(1e308, 2.0, -1e308)`, which returns `1e308`.</span></span> <span data-ttu-id="f6fae-415">Die reguläre Operation `(1e308 * 2.0) - 1e308` gibt `double.PositiveInfinity` zurück.</span><span class="sxs-lookup"><span data-stu-id="f6fae-415">The regular `(1e308 * 2.0) - 1e308` returns `double.PositiveInfinity`.</span></span>

- <xref:System.Math.CopySign(System.Double,System.Double)>\
<span data-ttu-id="f6fae-416">entspricht der IEEE-Operation `copySign`. Diese gibt den Wert von `x` mit dem Vorzeichen von `y` zurück.</span><span class="sxs-lookup"><span data-stu-id="f6fae-416">Corresponds to the `copySign` IEEE operation, it returns the value of `x`, but with the sign of `y`.</span></span>

### <a name="net-platform-dependent-intrinsics"></a><span data-ttu-id="f6fae-417">Von der .NET-Plattform abhängige systeminterne Funktionen</span><span class="sxs-lookup"><span data-stu-id="f6fae-417">.NET Platform-Dependent Intrinsics</span></span>

<span data-ttu-id="f6fae-418">Mit neuen APIs kann auf bestimmte leistungsorientierte CPU-Anweisungen wie **SIMD** oder **Bit Manipulation Instruction Sets** zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="f6fae-418">APIs have been added that allow access to certain perf-oriented CPU instructions, such as the **SIMD** or **Bit Manipulation instruction** sets.</span></span> <span data-ttu-id="f6fae-419">Diese Anweisungen können in bestimmten Szenarios wie der effizienten parallelen Datenverarbeitung zu deutlichen Leistungssteigerungen führen.</span><span class="sxs-lookup"><span data-stu-id="f6fae-419">These instructions can help achieve significant performance improvements in certain scenarios, such as processing data efficiently in parallel.</span></span>

<span data-ttu-id="f6fae-420">Wo möglich, haben die .NET-Bibliotheken begonnen, mithilfe dieser Anweisungen die Leistung zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="f6fae-420">Where appropriate, the .NET libraries have begun using these instructions to improve performance.</span></span>

<span data-ttu-id="f6fae-421">Weitere Informationen finden Sie unter [Von der .NET-Plattform abhängige intrinsische Funktionen](https://github.com/dotnet/designs/blob/master/accepted/2018/platform-intrinsics.md).</span><span class="sxs-lookup"><span data-stu-id="f6fae-421">For more information, see [.NET Platform-Dependent Intrinsics](https://github.com/dotnet/designs/blob/master/accepted/2018/platform-intrinsics.md).</span></span>

### <a name="improved-net-core-version-apis"></a><span data-ttu-id="f6fae-422">Verbesserte .NET Core-Versions-APIs</span><span class="sxs-lookup"><span data-stu-id="f6fae-422">Improved .NET Core Version APIs</span></span>

<span data-ttu-id="f6fae-423">Ab .NET Core 3.0 geben die mit .NET Core gelieferten Versions-APIs jetzt die Informationen zurück, die Sie erwarten.</span><span class="sxs-lookup"><span data-stu-id="f6fae-423">Starting with .NET Core 3.0, the version APIs provided with .NET Core now return the information you expect.</span></span> <span data-ttu-id="f6fae-424">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f6fae-424">For example:</span></span>

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
// New result (notice the value includes any preview release information)
//   RuntimeInformation.FrameworkDescription: .NET Core 3.0.0-preview4-27615-11
```

> [!WARNING]
> <span data-ttu-id="f6fae-425">Entscheidende Änderung.</span><span class="sxs-lookup"><span data-stu-id="f6fae-425">Breaking change.</span></span> <span data-ttu-id="f6fae-426">Dies ist technisch gesehen eine entscheidende Änderung, da das Schema der Versionsverwaltung sich geändert hat.</span><span class="sxs-lookup"><span data-stu-id="f6fae-426">This is technically a breaking change because the versioning scheme has changed.</span></span>

### <a name="fast-built-in-json-support"></a><span data-ttu-id="f6fae-427">Schneller integrierter JSON-Support</span><span class="sxs-lookup"><span data-stu-id="f6fae-427">Fast built-in JSON support</span></span>

<span data-ttu-id="f6fae-428">.NET-Benutzer haben sich weitgehend auf [Newtonsoft.Json](https://www.newtonsoft.com/json) und andere beliebte JSON-Bibliotheken verlassen, die weiterhin eine gute Wahl sind.</span><span class="sxs-lookup"><span data-stu-id="f6fae-428">.NET users have largely relied on [Newtonsoft.Json](https://www.newtonsoft.com/json) and other popular JSON libraries, which continue to be good choices.</span></span> <span data-ttu-id="f6fae-429">`Newtonsoft.Json` verwendet als Basisdatentyp .NET-Zeichenfolgen, die intern in UTF-16 codiert sind.</span><span class="sxs-lookup"><span data-stu-id="f6fae-429">`Newtonsoft.Json` uses .NET strings as its base datatype, which is UTF-16 under the hood.</span></span>

<span data-ttu-id="f6fae-430">Die neue integrierte JSON-Unterstützung ist überaus leistungsfähig mit geringer Zuteilung und funktioniert mit UTF-8-codiertem JSON-Text.</span><span class="sxs-lookup"><span data-stu-id="f6fae-430">The new built-in JSON support is high-performance, low allocation, and works with UTF-8 encoded JSON text.</span></span> <span data-ttu-id="f6fae-431">Weitere Informationen zum Namespace <xref:System.Text.Json> und den Typen finden Sie in den folgenden Artikeln:</span><span class="sxs-lookup"><span data-stu-id="f6fae-431">For more information about the <xref:System.Text.Json> namespace and types, see the following articles:</span></span>

* [<span data-ttu-id="f6fae-432">Übersicht zur JSON-Serialisierung in .NET</span><span class="sxs-lookup"><span data-stu-id="f6fae-432">JSON serialization in .NET - overview</span></span>](../../standard/serialization/system-text-json-overview.md)
* <span data-ttu-id="f6fae-433">[Serialisieren und Deserialisieren von JSON-Daten in .NET](../../standard/serialization/system-text-json-how-to.md):</span><span class="sxs-lookup"><span data-stu-id="f6fae-433">[How to serialize and deserialize JSON in .NET](../../standard/serialization/system-text-json-how-to.md).</span></span>
* [<span data-ttu-id="f6fae-434">Migrieren aus Newtonsoft.Json zu System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="f6fae-434">How to migrate from Newtonsoft.Json to System.Text.Json</span></span>](../../standard/serialization/system-text-json-migrate-from-newtonsoft-how-to.md)

### <a name="http2-support"></a><span data-ttu-id="f6fae-435">HTTP/2-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="f6fae-435">HTTP/2 support</span></span>

<span data-ttu-id="f6fae-436">Der <xref:System.Net.Http.HttpClient?displayProperty=nameWithType>-Typ unterstützt das HTTP/2-Protokoll.</span><span class="sxs-lookup"><span data-stu-id="f6fae-436">The <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> type supports the HTTP/2 protocol.</span></span> <span data-ttu-id="f6fae-437">Wenn HTTP/2 aktiviert ist, wird die HTTP-Protokollversion über TLS/ALPN ausgehandelt, und HTTP/2 wird bei Auswahl durch den Server verwendet.</span><span class="sxs-lookup"><span data-stu-id="f6fae-437">If HTTP/2 is enabled, the HTTP protocol version is negotiated via TLS/ALPN, and HTTP/2 is used if the server elects to use it.</span></span>

<span data-ttu-id="f6fae-438">Das Standardprotokoll bleibt HTTP/1.1, aber HTTP/2 kann auf zwei verschiedene Arten aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="f6fae-438">The default protocol remains HTTP/1.1, but HTTP/2 can be enabled in two different ways.</span></span> <span data-ttu-id="f6fae-439">Erstens können Sie die HTTP-Anforderungsnachricht so festlegen, dass HTTP/2 verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="f6fae-439">First, you can set the HTTP request message to use HTTP/2:</span></span>

[!code-csharp[Http2Request](./snippets/dotnet-core-3-0/csharp/http.cs#Request)]

<span data-ttu-id="f6fae-440">Zweitens können Sie <xref:System.Net.Http.HttpClient> so ändern, dass HTTP/2 standardmäßig verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="f6fae-440">Second, you can change <xref:System.Net.Http.HttpClient> to use HTTP/2 by default:</span></span>

[!code-csharp[Http2Client](./snippets/dotnet-core-3-0/csharp/http.cs#Client)]

<span data-ttu-id="f6fae-441">Oftmals möchten Sie bei der Entwicklung einer Anwendung eine unverschlüsselte Verbindung verwenden.</span><span class="sxs-lookup"><span data-stu-id="f6fae-441">Many times when you're developing an application, you want to use an unencrypted connection.</span></span> <span data-ttu-id="f6fae-442">Wenn Sie wissen, dass der Zielendpunkt HTTP/2 verwendet, können Sie unverschlüsselte Verbindungen für HTTP/2 aktivieren.</span><span class="sxs-lookup"><span data-stu-id="f6fae-442">If you know the target endpoint will be using HTTP/2, you can turn on unencrypted connections for HTTP/2.</span></span> <span data-ttu-id="f6fae-443">Sie können sie aktivieren, indem Sie die Umgebungsvariable `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2UNENCRYPTEDSUPPORT` auf `1` festlegen oder sie im App-Kontext aktivieren:</span><span class="sxs-lookup"><span data-stu-id="f6fae-443">You can turn it on by setting the `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2UNENCRYPTEDSUPPORT` environment variable to `1` or by enabling it in the app context:</span></span>

[!code-csharp[Http2Context](./snippets/dotnet-core-3-0/csharp/http.cs#AppContext)]

## <a name="next-steps"></a><span data-ttu-id="f6fae-444">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="f6fae-444">Next steps</span></span>

- [<span data-ttu-id="f6fae-445">Informationen zu den wichtigsten Unterschieden zwischen .NET Core 2.2 und 3.0</span><span class="sxs-lookup"><span data-stu-id="f6fae-445">Review the breaking changes between .NET Core 2.2 and 3.0.</span></span>](../compatibility/2.2-3.0.md)
- [<span data-ttu-id="f6fae-446">Überprüfen von Breaking Changes in .NET Core 3.0 für Windows Forms-Apps</span><span class="sxs-lookup"><span data-stu-id="f6fae-446">Review the breaking changes in .NET Core 3.0 for Windows Forms apps.</span></span>](../compatibility/winforms.md#net-core-30)
