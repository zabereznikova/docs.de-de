---
title: Einzeldatei-App
description: Hier erfahren Sie, was eine Einzeldatei-App ist und warum Sie dieses Anwendungsbereitstellungsmodell wählen sollten.
author: lakshanf
ms.author: lakshanf
ms.date: 12/17/2020
ms.openlocfilehash: 10ffc947f6a3adcf2889a03edd2616007ce236f3
ms.sourcegitcommit: 3a8f1979a98c6c19217a1930e0af5908988eb8ba
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2021
ms.locfileid: "98536137"
---
# <a name="single-file-deployment-and-executable"></a><span data-ttu-id="e4a1a-103">Einzeldateibereitstellung und ausführbare Datei</span><span class="sxs-lookup"><span data-stu-id="e4a1a-103">Single file deployment and executable</span></span>

<span data-ttu-id="e4a1a-104">Wenn Sie alle Abhängigkeiten der Anwendung in eine einzelne Binärdatei packen, kann ein Anwendungsentwickler die Anwendung in einer Datei bereitstellen und verteilen.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-104">Bundling all application-dependent files into a single binary provides an application developer with the attractive option to deploy and distribute the application as a single file.</span></span> <span data-ttu-id="e4a1a-105">Dieses Bereitstellungsmodell wurde mit .NET 3.0 eingeführt und in .NET 5.0 erweitert.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-105">This deployment model has been available since .NET Core 3.0 and has been enhanced in .NET 5.0.</span></span> <span data-ttu-id="e4a1a-106">Wenn ein Benutzer zuvor in .NET Core 3.0 eine Einzeldatei-App ausgeführt hat, hat der .NET Core-Host zuerst alle Dateien in ein temporäres Verzeichnis extrahiert, bevor die Anwendung ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-106">Previously in .NET Core 3.0, when a user runs your single-file app, .NET Core host first extracts all files to a temporary directory before running the application.</span></span> <span data-ttu-id="e4a1a-107">In .NET 5.0 wurde der Ablauf verbessert, indem der Code direkt ausgeführt wird, ohne die Dateien aus der App zu extrahieren.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-107">.NET 5.0 improves this experience by directly running the code without the need to extract the files from the app.</span></span>

<span data-ttu-id="e4a1a-108">Die Einzeldateibereitstellung ist für das [frameworkabhängige Bereitstellungsmodell](index.md#publish-framework-dependent) und [eigenständige Anwendungen](index.md#publish-self-contained) verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-108">Single File deployment is available for both the [framework-dependent deployment model](index.md#publish-framework-dependent) and [self-contained applications](index.md#publish-self-contained).</span></span> <span data-ttu-id="e4a1a-109">Bei einer eigenständigen Anwendung handelt es sich dabei um eine große Datei, da die Runtime und die Frameworkbibliotheken enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-109">The size of the single file in a self-contained application will be large since it will include the runtime and the framework libraries.</span></span> <span data-ttu-id="e4a1a-110">Die Einzeldatei-Bereitstellungsoption kann mit den Veröffentlichungsoptionen [ReadyToRun](ready-to-run.md) und [Trim](trim-self-contained.md) (ein experimentelles Feature in .NET 5.0) kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-110">The single file deployment option can be combined with [ReadyToRun](ready-to-run.md) and [Trim (an experimental feature in .NET 5.0)](trim-self-contained.md) publish options.</span></span>

## <a name="api-incompatibility"></a><span data-ttu-id="e4a1a-111">API-Inkompatibilität</span><span class="sxs-lookup"><span data-stu-id="e4a1a-111">API incompatibility</span></span>

<span data-ttu-id="e4a1a-112">Einige APIs sind nicht mit einer Einzeldateibereitstellung kompatibel, und Anwendungen müssen möglicherweise geändert werden, wenn sie diese APIs verwenden.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-112">Some APIs are not compatible with single-file deployment and applications may require modification if they use these APIs.</span></span> <span data-ttu-id="e4a1a-113">Wenn Sie ein Framework oder ein Paket eines Drittanbieters verwenden, verwenden diese möglicherweise auch eine dieser APIs und müssen deshalb geändert werden.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-113">If you use a third-party framework or package, it's possible that they may also use one of these APIs and need modification.</span></span> <span data-ttu-id="e4a1a-114">Die häufigste Ursache für Probleme ist die Abhängigkeit von Dateipfaden für Dateien oder DLLs, die im Lieferumfang der Anwendung enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-114">The most common cause of problems is dependence on file paths for files or DLLs shipped with the application.</span></span>

<span data-ttu-id="e4a1a-115">Die Tabelle unten enthält die relevanten Details zur API der Laufzeitbibliothek für die Verwendung einer einzelnen Datei.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-115">The table below has the relevant runtime library API details for single-file use.</span></span>

| <span data-ttu-id="e4a1a-116">API</span><span class="sxs-lookup"><span data-stu-id="e4a1a-116">API</span></span>                            | <span data-ttu-id="e4a1a-117">Hinweis</span><span class="sxs-lookup"><span data-stu-id="e4a1a-117">Note</span></span>                                                                   |
|--------------------------------|------------------------------------------------------------------------|
| `Assembly.Location`            | <span data-ttu-id="e4a1a-118">Gibt eine leere Zeichenfolge zurück.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-118">Returns an empty string.</span></span>                                               |
| `Module.FullyQualifiedName`    | <span data-ttu-id="e4a1a-119">Diese API gibt eine Zeichenfolge mit dem Wert `<Unknown>` zurück oder löst eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-119">Returns a string with the value of `<Unknown>` or throws an exception.</span></span> |
| `Module.Name`                  | <span data-ttu-id="e4a1a-120">Diese API gibt eine Zeichenfolge mit dem Wert `<Unknown>`zurück.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-120">Returns a string with the value of `<Unknown>`.</span></span>                        |
| `Assembly.GetFile`             | <span data-ttu-id="e4a1a-121">Löst <xref:System.IO.IOException> aus.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-121">Throws <xref:System.IO.IOException>.</span></span>                                   |
| `Assembly.GetFiles`            | <span data-ttu-id="e4a1a-122">Löst <xref:System.IO.IOException> aus.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-122">Throws <xref:System.IO.IOException>.</span></span>                                   |
| `Assembly.CodeBase`            | <span data-ttu-id="e4a1a-123">Löst <xref:System.PlatformNotSupportedException> aus.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-123">Throws <xref:System.PlatformNotSupportedException>.</span></span>                    |
| `Assembly.EscapedCodeBase`     | <span data-ttu-id="e4a1a-124">Löst <xref:System.PlatformNotSupportedException> aus.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-124">Throws <xref:System.PlatformNotSupportedException>.</span></span>                    |
| `AssemblyName.CodeBase`        | <span data-ttu-id="e4a1a-125">Gibt `null`zurück.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-125">Returns `null`.</span></span>                                                        |
| `AssemblyName.EscapedCodeBase` | <span data-ttu-id="e4a1a-126">Gibt `null`zurück.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-126">Returns `null`.</span></span>                                                        |

<span data-ttu-id="e4a1a-127">Es gibt einige Empfehlungen zum Behandeln häufiger Szenarios:</span><span class="sxs-lookup"><span data-stu-id="e4a1a-127">We have some recommendations for fixing common scenarios:</span></span>

* <span data-ttu-id="e4a1a-128">Verwenden Sie <xref:System.AppContext.BaseDirectory?displayProperty=nameWithType>, um auf Dateien neben der ausführbaren Datei zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-128">To access files next to the executable, use <xref:System.AppContext.BaseDirectory?displayProperty=nameWithType>.</span></span>

* <span data-ttu-id="e4a1a-129">Verwenden Sie das erste Element von <xref:System.Environment.GetCommandLineArgs?displayProperty=nameWithType>, um den Dateinamen der ausführbaren Datei zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-129">To find the file name of the executable, use the first element of <xref:System.Environment.GetCommandLineArgs?displayProperty=nameWithType>.</span></span>

* <span data-ttu-id="e4a1a-130">Verwenden Sie die [eingebetteten Ressourcen](../../framework/resources/creating-resource-files-for-desktop-apps.md), um das Versenden loser Dateien zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-130">To avoid shipping loose files entirely, consider using [embedded resources](../../framework/resources/creating-resource-files-for-desktop-apps.md).</span></span>

## <a name="attaching-a-debugger"></a><span data-ttu-id="e4a1a-131">Anfügen eines Debuggers</span><span class="sxs-lookup"><span data-stu-id="e4a1a-131">Attaching a debugger</span></span>

<span data-ttu-id="e4a1a-132">Unter Linux ist [SOS with LLDB](../diagnostics/dotnet-sos.md) der einzige Debugger, der an eigenständige Einzeldateiprozesse angefügt werden kann oder Absturzabbilder debuggen kann.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-132">On Linux, the only debugger which can attach to self-contained single-file processes or debug crash dumps is [SOS with LLDB](../diagnostics/dotnet-sos.md).</span></span>

<span data-ttu-id="e4a1a-133">Unter Windows und Mac können Visual Studio und VS Code zum Debuggen von Absturzabbildern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-133">On Windows and Mac, Visual Studio and VS Code can be used to debug crash dumps.</span></span> <span data-ttu-id="e4a1a-134">Das Anfügen an eine eigenständige ausführbare Einzeldatei erfordert eine zusätzliche Datei: _mscordbi.{dll,so}_ .</span><span class="sxs-lookup"><span data-stu-id="e4a1a-134">Attaching to a running self-contained single-file executable requires an extra file: _mscordbi.{dll,so}_.</span></span>

<span data-ttu-id="e4a1a-135">Ohne diese Datei erzeugt Visual Studio möglicherweise die Fehlermeldung „Anfügen an den Prozess nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-135">Without this file Visual Studio may produce the error "Unable to attach to the process.</span></span> <span data-ttu-id="e4a1a-136">Eine Debugkomponente ist nicht installiert.“, und</span><span class="sxs-lookup"><span data-stu-id="e4a1a-136">A debug component is not installed."</span></span> <span data-ttu-id="e4a1a-137">VS Code erzeigt möglicherweise den Fehler „Fehler beim Anfügen an Prozess: Unbekannter Fehler: 0x80131c3c.“.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-137">and VS Code may produce the error "Failed to attach to process: Unknown Error: 0x80131c3c."</span></span>

<span data-ttu-id="e4a1a-138">Um diese Fehler zu beheben, muss _mscordbi_ neben die ausführbare Datei kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-138">To fix these errors, _mscordbi_ needs to be copied next to the executable.</span></span> <span data-ttu-id="e4a1a-139">_mscordbi_ wird standardmäßig mit `publish` im Unterverzeichnis mit der Runtime-ID der Anwendung veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-139">_mscordbi_ is `publish`ed by default in the subdirectory with the application's runtime ID.</span></span> <span data-ttu-id="e4a1a-140">Wenn ein Benutzer zum Beispiel eine eigenständige ausführbare Einzeldatei mithilfe der `dotnet`-CLI für Windows und den Parametern `-r win-x64` veröffentlichen würde, würde die ausführbare Datei in _bin/Debug/net5.0/win-x64/publish_ platziert werden.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-140">So, for example, if one were to publish a self-contained single-file executable using the `dotnet` CLI for Windows using the parameters `-r win-x64`, the executable would be placed in _bin/Debug/net5.0/win-x64/publish_.</span></span> <span data-ttu-id="e4a1a-141">Eine Kopie von _mscordbi.dll_ wäre dann in _in/Debug/net5.0/win-x64_ enthalten.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-141">A copy of _mscordbi.dll_ would be present in _bin/Debug/net5.0/win-x64_.</span></span>

## <a name="other-considerations"></a><span data-ttu-id="e4a1a-142">Weitere Überlegungen</span><span class="sxs-lookup"><span data-stu-id="e4a1a-142">Other considerations</span></span>

<span data-ttu-id="e4a1a-143">Native Bibliotheken werden nicht standardmäßig in die Einzeldatei gepackt.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-143">Single-file doesn't bundle native libraries by default.</span></span> <span data-ttu-id="e4a1a-144">Unter Linux wird die Runtime im Voraus mit dem Paket verknüpft, und nur anwendungsnative Bibliotheken werden im gleichen Verzeichnis wie die Einzeldatei-App bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-144">On Linux, we prelink the runtime into the bundle and only application native libraries are deployed to the same directory as the single-file app.</span></span> <span data-ttu-id="e4a1a-145">Unter Windows wird nur der Hostingcode im Voraus verknüpft, und die Runtime und anwendungsnative Bibliotheken werden im gleichen Verzeichnis wie die Einzeldatei-App bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-145">On Windows, we prelink only the hosting code and both the runtime and application native libraries are deployed to the same directory as the single-file app.</span></span> <span data-ttu-id="e4a1a-146">Dadurch werden Probleme beim Debuggen vermieden, denn dafür wird vorausgesetzt, dass native Dateien nicht in der Einzeldatei enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-146">This is to ensure a good debugging experience, which requires native files to be excluded from the single file.</span></span> <span data-ttu-id="e4a1a-147">Sie können das Flag `IncludeNativeLibrariesForSelfExtract` festlegen, um native Dateien in das Einzeldateipaket einzufügen. Diese Dateien werden jedoch in ein temporäres Verzeichnis auf dem Clientcomputer extrahiert, wenn die Einzeldatei-App ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-147">There is an option to set a flag, `IncludeNativeLibrariesForSelfExtract`, to include native libraries in the single file bundle, but these files will be extracted to a temporary directory in the client machine when the single file application is run.</span></span>

<span data-ttu-id="e4a1a-148">Wenn Sie `IncludeAllContentForSelfExtract` festlegen, werden alle Dateien extrahiert, bevor die ausführbare Datei ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-148">Specifying `IncludeAllContentForSelfExtract` will extract all files before running the executable.</span></span> <span data-ttu-id="e4a1a-149">Dadurch wird das ursprüngliche Verhalten von .NET Core beibehalten, nur eine Datei bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-149">This preserves the original .NET Core single-file deployment behavior.</span></span>

<span data-ttu-id="e4a1a-150">Die Einzeldateianwendung verfügt über alle zugehörigen PDB-Dateien und wird standardmäßig nicht gebündelt.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-150">Single-file application will have all related PDB files alongside it and will not be bundled by default.</span></span> <span data-ttu-id="e4a1a-151">Wenn Sie PDBs in die Assembly für Projekte, die Sie erstellen, einschließen möchten, legen Sie `DebugType` auf `embedded` fest, wie [unten](#include-pdb-files-inside-the-bundle) ausführlich beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-151">If you want to include PDBs inside the assembly for projects you build, set the `DebugType` to `embedded` as described [below](#include-pdb-files-inside-the-bundle) in detail.</span></span>

<span data-ttu-id="e4a1a-152">Verwaltete C++-Komponenten eignen sich nicht für die Einzeldateibereitstellung. Es wird empfohlen, Anwendungen in C# oder einer anderen nicht verwalteten C++-Programmiersprache zu schreiben, wenn diese mit der Einzeldateibereitstellung kompatibel sein sollen.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-152">Managed C++ components aren't well suited for single-file deployment and we recommend that you write applications in C# or another non-managed C++ language to be single-file compatible.</span></span>

## <a name="exclude-files-from-being-embedded"></a><span data-ttu-id="e4a1a-153">Ausschließen von Dateien aus der Einbettung</span><span class="sxs-lookup"><span data-stu-id="e4a1a-153">Exclude files from being embedded</span></span>

<span data-ttu-id="e4a1a-154">Bestimmte Dateien können explizit aus der Einbettung in die Einzeldatei ausgeschlossen werden, indem Sie die folgenden Metadaten festlegen:</span><span class="sxs-lookup"><span data-stu-id="e4a1a-154">Certain files can be explicitly excluded from being embedded in the single-file by setting following metadata:</span></span>

```xml
<ExcludeFromSingleFile>true</ExcludeFromSingleFile>
```

<span data-ttu-id="e4a1a-155">So können Sie beispielsweise einige Dateien im Veröffentlichungsverzeichnis speichern, ohne diese in die Einzeldatei zu packen:</span><span class="sxs-lookup"><span data-stu-id="e4a1a-155">For example, to place some files in the publish directory but not bundle them in the single-file:</span></span>

```xml
<ItemGroup>
  <Content Update="Plugin.dll">
    <CopyToPublishDirectory>PreserveNewest</CopyToPublishDirectory>
    <ExcludeFromSingleFile>true</ExcludeFromSingleFile>
  </Content>
</ItemGroup>
```

## <a name="include-pdb-files-inside-the-bundle"></a><span data-ttu-id="e4a1a-156">Einschließen von PDB-Dateien in das Bündel</span><span class="sxs-lookup"><span data-stu-id="e4a1a-156">Include PDB files inside the bundle</span></span>

<span data-ttu-id="e4a1a-157">Die PDB-Datei für eine Assembly kann mithilfe der folgenden Einstellung in die Assembly selbst (`.dll`) eingebettet werden.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-157">The PDB file for an assembly can be embedded into the assembly itself (the `.dll`) using the setting below.</span></span> <span data-ttu-id="e4a1a-158">Da die Symbole Teil der Assembly sind, sind sie auch Teil der Einzeldateianwendung:</span><span class="sxs-lookup"><span data-stu-id="e4a1a-158">Since the symbols are part of the assembly, they will be part of the single-file application as well:</span></span>

```xml
<DebugType>embedded</DebugType>
```

<span data-ttu-id="e4a1a-159">Fügen Sie z. B. die folgende Eigenschaft in die Projektdatei einer Assembly ein, um die PDB-Datei in diese Assembly einzubetten:</span><span class="sxs-lookup"><span data-stu-id="e4a1a-159">For example, add the following property to the project file of an assembly to embed the PDB file to that assembly:</span></span>

```xml
<PropertyGroup>
  <DebugType>embedded</DebugType>
</PropertyGroup>
```

## <a name="publish-a-single-file-app---sample-project-file"></a><span data-ttu-id="e4a1a-160">Veröffentlichen einer Einzeldatei-App: Beispielprojektdatei</span><span class="sxs-lookup"><span data-stu-id="e4a1a-160">Publish a single file app - sample project file</span></span>

<span data-ttu-id="e4a1a-161">Hier sehen Sie eine Beispielprojektdatei, in der die Veröffentlichung von Einzeldatei-Apps definiert wird:</span><span class="sxs-lookup"><span data-stu-id="e4a1a-161">Here's a sample project file that specifies single-file publishing:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>net5.0</TargetFramework>
    <PublishSingleFile>true</PublishSingleFile>
    <SelfContained>true</SelfContained>
    <RuntimeIdentifier>win-x64</RuntimeIdentifier>
    <PublishTrimmed>true</PublishTrimmed>
    <PublishReadyToRun>true</PublishReadyToRun>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="e4a1a-162">Diese Eigenschaften verfügen über die folgenden Funktionen:</span><span class="sxs-lookup"><span data-stu-id="e4a1a-162">These properties have the following functions:</span></span>

* <span data-ttu-id="e4a1a-163">`PublishSingleFile`: aktiviert die Veröffentlichung von Einzeldateien</span><span class="sxs-lookup"><span data-stu-id="e4a1a-163">`PublishSingleFile` - Enables single-file publishing.</span></span>
* <span data-ttu-id="e4a1a-164">`SelfContained`: bestimmt, ob die App eigenständig oder frameworkabhängig ist</span><span class="sxs-lookup"><span data-stu-id="e4a1a-164">`SelfContained` - Determines whether the app will be self-contained or framework-dependent.</span></span>
* <span data-ttu-id="e4a1a-165">`RuntimeIdentifier`: gibt das [Betriebssystem und den CPU-Typ](../rid-catalog.md) an, den Sie als Ziel verwenden</span><span class="sxs-lookup"><span data-stu-id="e4a1a-165">`RuntimeIdentifier` - Specifies the [OS and CPU type](../rid-catalog.md) you are targeting.</span></span>
* <span data-ttu-id="e4a1a-166">`PublishTrimmed`: ermöglicht das [Kürzen von Assemblys](trim-self-contained.md). Dies wird nur für eigenständige Apps unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-166">`PublishTrimmed` - Enables use of [assembly trimming](trim-self-contained.md), which is only supported for self-contained apps.</span></span>
* <span data-ttu-id="e4a1a-167">`PublishReadyToRun`: ermöglicht die [Ahead-of-Time-Kompilierung (AOT)](ready-to-run.md)</span><span class="sxs-lookup"><span data-stu-id="e4a1a-167">`PublishReadyToRun` - Enables [ahead-of-time (AOT) compilation](ready-to-run.md).</span></span>

<span data-ttu-id="e4a1a-168">**Hinweise:**</span><span class="sxs-lookup"><span data-stu-id="e4a1a-168">**Notes:**</span></span>

* <span data-ttu-id="e4a1a-169">Apps sind betriebssystem- und architekturspezifisch.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-169">Apps are OS and architecture-specific.</span></span> <span data-ttu-id="e4a1a-170">Sie müssen für jede Konfiguration (z. B. Linux x64, Linux ARM64, Windows x64 usw.) eine App veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-170">You need to publish for each configuration, such as Linux x64, Linux ARM64, Windows x64, and so forth.</span></span>
* <span data-ttu-id="e4a1a-171">Konfigurationsdateien (z. B. *\*.runtimeconfig.json*) sind in der Einzeldatei enthalten.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-171">Configuration files, such as *\*.runtimeconfig.json*, are included in the single file.</span></span> <span data-ttu-id="e4a1a-172">Wenn eine zusätzliche Konfigurationsdatei benötigt wird, können Sie sie neben der Einzeldatei platzieren.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-172">If an additional configuration file is needed, you can place it beside the single file.</span></span>

## <a name="publish-a-single-file-app---cli"></a><span data-ttu-id="e4a1a-173">Veröffentlichen einer Einzeldatei-App (CLI)</span><span class="sxs-lookup"><span data-stu-id="e4a1a-173">Publish a single file app - CLI</span></span>

<span data-ttu-id="e4a1a-174">Sie können Ihre Einzeldatei-App mit dem Befehl [dotnet publish](../tools/dotnet-publish.md) veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-174">Publish a single file application using the [dotnet publish](../tools/dotnet-publish.md) command.</span></span> <span data-ttu-id="e4a1a-175">Legen Sie die folgenden Eigenschaften fest, wenn Sie Ihre App veröffentlichen:</span><span class="sxs-lookup"><span data-stu-id="e4a1a-175">When you publish your app, set the following properties:</span></span>

- <span data-ttu-id="e4a1a-176">Veröffentlichung für eine bestimmte Runtime: `-r win-x64`</span><span class="sxs-lookup"><span data-stu-id="e4a1a-176">Publish for a specific runtime: `-r win-x64`</span></span>
- <span data-ttu-id="e4a1a-177">Veröffentlichung als Einzeldatei: `-p:PublishSingleFile=true`</span><span class="sxs-lookup"><span data-stu-id="e4a1a-177">Publish as a single-file: `-p:PublishSingleFile=true`</span></span>

<span data-ttu-id="e4a1a-178">Im folgenden Beispiel wird eine App für Windows als eigenständige Einzeldatei-App veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-178">The following example publishes an app for Windows as a self-contained single file application.</span></span>

```dotnetcli
dotnet publish -r win-x64 -p:PublishSingleFile=true --self-contained true
```

<span data-ttu-id="e4a1a-179">Im folgenden Beispiel wird eine App für Linux als frameworkabhängige Einzeldatei-App veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-179">The following example publishes an app for Linux as a framework dependent single file application.</span></span>

```dotnetcli
dotnet publish -r linux-x64 -p:PublishSingleFile=true --self-contained false
```

<span data-ttu-id="e4a1a-180">Weitere Informationen finden Sie unter [Veröffentlichen von .NET Core-Apps mit der .NET Core-CLI](deploy-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="e4a1a-180">For more information, see [Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>

## <a name="publish-a-single-file-app---visual-studio"></a><span data-ttu-id="e4a1a-181">Veröffentlichen einer Einzeldatei-App (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="e4a1a-181">Publish a single file app - Visual Studio</span></span>

<span data-ttu-id="e4a1a-182">Visual Studio erstellt wiederverwendbare Veröffentlichungsprofile, die steuern, wie Ihre App veröffentlicht wird.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-182">Visual Studio creates reusable publishing profiles that control how your application is published.</span></span>

01. <span data-ttu-id="e4a1a-183">Klicken Sie im Bereich **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, das Sie veröffentlichen möchten.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-183">On the **Solution Explorer** pane, right-click on the project you want to publish.</span></span> <span data-ttu-id="e4a1a-184">Klicken Sie auf **Veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-184">Select **Publish**.</span></span>

    :::image type="content" source="media/single-file/visual-studio-solution-explorer.png" alt-text="Projektmappen-Explorer mit Kontextmenü und markierter Option zum Veröffentlichen":::

    <span data-ttu-id="e4a1a-186">Wenn Sie noch nicht über ein Veröffentlichungsprofil verfügen, befolgen Sie die Anweisungen zum Erstellen eines solchen Profils, und wählen Sie als Zieltyp **Ordner** aus.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-186">If you don't already have a publishing profile, follow the instructions to create one and choose the **Folder** target-type.</span></span>

01. <span data-ttu-id="e4a1a-187">Wählen Sie **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-187">Choose **Edit**.</span></span>

    :::image type="content" source="media/single-file/visual-studio-publish-edit-settings.png" alt-text="Visual Studio-Veröffentlichungsprofil mit Bearbeitungsschaltfläche":::

01. <span data-ttu-id="e4a1a-189">Legen Sie im Dialogfeld **Profileinstellungen** die folgenden Optionen fest:</span><span class="sxs-lookup"><span data-stu-id="e4a1a-189">In the **Profile settings** dialog, set the following options:</span></span>

    - <span data-ttu-id="e4a1a-190">Legen Sie den **Bereitstellungsmodus** auf **Eigenständig** fest.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-190">Set **Deployment mode** to **Self-contained**.</span></span>
    - <span data-ttu-id="e4a1a-191">Legen Sie die **Zielrumtime** auf die Plattform fest, auf der Sie die App veröffentlichen möchten.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-191">Set **Target runtime** to the platform you want to publish to.</span></span>
    - <span data-ttu-id="e4a1a-192">Klicken Sie auf **Einzelne Datei erstellen**.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-192">Select **Produce single file**.</span></span>

    <span data-ttu-id="e4a1a-193">Klicken Sie auf **Speichern**, um die Einstellungen zu speichern und zum Dialogfeld **Veröffentlichen** zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-193">Choose **Save** to save the settings and return to the **Publish** dialog.</span></span>

    :::image type="content" source="media/single-file/visual-studio-publish-single-file-properties.png" alt-text="Dialogfeld für die Profileinstellungen mit Bereitstellungsmodus, Zielruntime und hervorgehobenen Einzeldateioptionen":::

01. <span data-ttu-id="e4a1a-195">Klicken Sie auf **Veröffentlichen**, um Ihre App als Einzeldatei zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-195">Choose **Publish** to publish your app as a single file.</span></span>

<span data-ttu-id="e4a1a-196">Weitere Informationen finden Sie unter [Veröffentlichen von .NET Core-Apps mit Visual Studio](deploy-with-vs.md).</span><span class="sxs-lookup"><span data-stu-id="e4a1a-196">For more information, see [Publish .NET Core apps with Visual Studio](deploy-with-vs.md).</span></span>

## <a name="publish-a-single-file-app---visual-studio-for-mac"></a><span data-ttu-id="e4a1a-197">Veröffentlichen einer Einzeldatei-App (Visual Studio für Mac)</span><span class="sxs-lookup"><span data-stu-id="e4a1a-197">Publish a single file app - Visual Studio for Mac</span></span>

<span data-ttu-id="e4a1a-198">In Visual Studio für Mac ist es nicht möglich, eine App als Einzeldatei zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-198">Visual Studio for Mac doesn't provide options to publish your app as a single file.</span></span> <span data-ttu-id="e4a1a-199">Sie müssen diese manuell veröffentlichen, indem Sie die Anleitung im Abschnitt [Veröffentlichen einer Einzeldatei-App (CLI)](#publish-a-single-file-app---cli) befolgen.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-199">You'll need to publish manually by following the instructions from the [Publish a single file app - CLI](#publish-a-single-file-app---cli) section.</span></span> <span data-ttu-id="e4a1a-200">Weitere Informationen finden Sie unter [Veröffentlichen von .NET Core-Apps mit der .NET Core-CLI](deploy-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="e4a1a-200">For more information, see [Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e4a1a-201">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e4a1a-201">See also</span></span>

- <span data-ttu-id="e4a1a-202">[.NET Core-Anwendungsbereitstellung](index.md)</span><span class="sxs-lookup"><span data-stu-id="e4a1a-202">[.NET Core application deployment](index.md).</span></span>
- <span data-ttu-id="e4a1a-203">[Veröffentlichen von .NET Core-Apps mit der .NET Core-CLI](deploy-with-cli.md)</span><span class="sxs-lookup"><span data-stu-id="e4a1a-203">[Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>
- <span data-ttu-id="e4a1a-204">[Bereitstellen von .NET Core-Apps mit Visual Studio](deploy-with-vs.md)</span><span class="sxs-lookup"><span data-stu-id="e4a1a-204">[Publish .NET Core apps with Visual Studio](deploy-with-vs.md).</span></span>
- <span data-ttu-id="e4a1a-205">[`dotnet publish`-Befehl](../tools/dotnet-publish.md)</span><span class="sxs-lookup"><span data-stu-id="e4a1a-205">[`dotnet publish` command](../tools/dotnet-publish.md).</span></span>
