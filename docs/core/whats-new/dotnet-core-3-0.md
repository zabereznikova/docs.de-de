---
title: Neuerungen in .NET Core 3.0
description: Informationen zu den neuen Features in .NET Core 3.0.
dev_langs:
- csharp
- vb
author: thraka
ms.author: adegeo
ms.date: 12/04/2018
ms.openlocfilehash: 3ca833031eb8bb0f43a334f833f2e0075842d57d
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53156668"
---
# <a name="whats-new-in-net-core-30-preview-1"></a><span data-ttu-id="f16ac-103">Neuerungen in .NET Core 3.0 (Vorschauversion 1)</span><span class="sxs-lookup"><span data-stu-id="f16ac-103">What's new in .NET Core 3.0 (Preview 1)</span></span>

<span data-ttu-id="f16ac-104">Dieser Artikel beschreibt die Neuerungen in .NET Core 3.0 (Vorschauversion 1).</span><span class="sxs-lookup"><span data-stu-id="f16ac-104">This article describes what is new in .NET Core 3.0 (preview 1).</span></span> <span data-ttu-id="f16ac-105">Eine der wichtigsten Verbesserungen ist die Unterstützung für Windows-Desktopanwendungen (nur Windows).</span><span class="sxs-lookup"><span data-stu-id="f16ac-105">One of the biggest enhancements is support for Windows desktop applications (Windows only).</span></span> <span data-ttu-id="f16ac-106">Durch die Verwendung einer .NET Core 3.0-Komponente namens Windows Desktop können Sie Ihre Windows Forms Windows Presentation Foundation (WPF)-Anwendungen portieren.</span><span class="sxs-lookup"><span data-stu-id="f16ac-106">By utilizing a .NET Core 3.0 component called Windows Desktop, you can port your Windows Forms Windows Presentation Foundation (WPF) applications.</span></span> <span data-ttu-id="f16ac-107">Die Windows Desktop-Komponente wird ausdrücklich nur für Windows unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f16ac-107">To be clear, the Windows Desktop component is only supported on Windows.</span></span> <span data-ttu-id="f16ac-108">Weitere Informationen finden Sie unten im Abschnitt [Windows Desktop](#windows-desktop).</span><span class="sxs-lookup"><span data-stu-id="f16ac-108">For more information, see the section [Windows desktop](#windows-desktop) below.</span></span>

<span data-ttu-id="f16ac-109">.NET Core 3.0 bietet Unterstützung für C# 8.0.</span><span class="sxs-lookup"><span data-stu-id="f16ac-109">.NET Core 3.0 adds support for C# 8.0.</span></span>

<span data-ttu-id="f16ac-110">[Sie können .NET Core 3 Vorschauversion 1 jetzt für Windows, Mac und Linux herunterladen und sofort starte.](https://aka.ms/netcore3download)</span><span class="sxs-lookup"><span data-stu-id="f16ac-110">[Download and get started with .NET Core 3 Preview 1](https://aka.ms/netcore3download) right now on Windows, Mac and Linux.</span></span> <span data-ttu-id="f16ac-111">Alle Details zu diesem Release finden Sie in den [Versionshinweisen zu .NET Core 3 Vorschauversion 1](https://aka.ms/netcore3releasenotes).</span><span class="sxs-lookup"><span data-stu-id="f16ac-111">You can see complete details of the release in the [.NET Core 3 Preview 1 release notes](https://aka.ms/netcore3releasenotes).</span></span>

<span data-ttu-id="f16ac-112">Weitere Informationen finden Sie unter [Ankündigung zu .NET Core 3.0 Vorschauversion 1](https://blogs.msdn.microsoft.com/dotnet/2018/12/04/announcing-net-core-3-preview-1-and-open-sourcing-windows-desktop-frameworks/).</span><span class="sxs-lookup"><span data-stu-id="f16ac-112">For more information, see the [.NET Core 3.0 Preview 1 announcement](https://blogs.msdn.microsoft.com/dotnet/2018/12/04/announcing-net-core-3-preview-1-and-open-sourcing-windows-desktop-frameworks/).</span></span>

## <a name="net-standard-21"></a><span data-ttu-id="f16ac-113">.NET Standard 2.1</span><span class="sxs-lookup"><span data-stu-id="f16ac-113">.NET Standard 2.1</span></span>

<span data-ttu-id="f16ac-114">.NET Core 3.0 implementiert .NET Standard 2.1.</span><span class="sxs-lookup"><span data-stu-id="f16ac-114">.NET Core 3.0 implements .NET Standard 2.1.</span></span>

## <a name="default-executables"></a><span data-ttu-id="f16ac-115">Standardmäßig ausführbare Dateien</span><span class="sxs-lookup"><span data-stu-id="f16ac-115">Default executables</span></span>

<span data-ttu-id="f16ac-116">.NET Core erstellt die ausführbaren Dateien jetzt standardmäßig.</span><span class="sxs-lookup"><span data-stu-id="f16ac-116">.NET Core will now build executables by default.</span></span> <span data-ttu-id="f16ac-117">Dies ist neu für Anwendungen, die eine global installierte Version von .NET Core verwenden.</span><span class="sxs-lookup"><span data-stu-id="f16ac-117">This is new for applications that use a globally installed version of .NET Core.</span></span> <span data-ttu-id="f16ac-118">Bis jetzt hatten nur [eigenständige Bereitstellungen](../deploying/index.md#self-contained-deployments-scd) ausführbare Dateien.</span><span class="sxs-lookup"><span data-stu-id="f16ac-118">Until now, only [self-contained deployments](../deploying/index.md#self-contained-deployments-scd) had executables.</span></span>

<span data-ttu-id="f16ac-119">Während `dotnet build` oder `dotnet publish` wird eine ausführbare Datei erstellt, die der Umgebung und Plattform des von Ihnen verwendeten SDKs entspricht.</span><span class="sxs-lookup"><span data-stu-id="f16ac-119">During `dotnet build` or `dotnet publish`, an executable is created provided that matches the environment and platform of the SDK you are using.</span></span> <span data-ttu-id="f16ac-120">Diese ausführbaren Dateien bieten Ihnen die gleichen Möglichkeiten wie andere native ausführbare Dateien, wie z.B.:</span><span class="sxs-lookup"><span data-stu-id="f16ac-120">You can expect the same things with these executables as you would other native executables, such as:</span></span>

* <span data-ttu-id="f16ac-121">Sie können die ausführbare Datei doppelklicken.</span><span class="sxs-lookup"><span data-stu-id="f16ac-121">You can double-click on the executable.</span></span>
* <span data-ttu-id="f16ac-122">Sie können die Anwendung direkt aus einer Eingabeaufforderung starten, z.B. `myapp.exe` unter Windows und `./myapp` unter Linux und MacOS.</span><span class="sxs-lookup"><span data-stu-id="f16ac-122">You can launch the application from a command prompt directly, such as `myapp.exe` on Windows, and `./myapp` on Linux and macOS.</span></span>

> [!NOTE]
> <span data-ttu-id="f16ac-123">Die Angabe einer bestimmten Runtime mit `dotnet publish -r`- oder `dotnet build -r`-Argumenten für andere Runtimeumgebungen wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f16ac-123">Specifying a specific runtime with `dotnet publish -r` or `dotnet build -r` arguments for other runtime environments isn't supported.</span></span>

## <a name="build-copies-dependencies"></a><span data-ttu-id="f16ac-124">Build kopiert Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="f16ac-124">Build copies dependencies</span></span>

<span data-ttu-id="f16ac-125">`dotnet build` kopiert jetzt NuGet-Abhängigkeiten für Ihre Anwendung aus dem NuGet-Cache in den Buildausgabeordner.</span><span class="sxs-lookup"><span data-stu-id="f16ac-125">`dotnet build` now copies NuGet dependencies for your application from the NuGet cache to the build output folder.</span></span> <span data-ttu-id="f16ac-126">Bisher wurde Abhängigkeiten nur als Teil von `dotnet publish` kopiert.</span><span class="sxs-lookup"><span data-stu-id="f16ac-126">Previously, dependencies were only copied as part of `dotnet publish`.</span></span> 

<span data-ttu-id="f16ac-127">Es gibt einige Vorgänge, wie das Verlinken und das Veröffentlichen von Razor-Seiten, die noch veröffentlicht werden müssen.</span><span class="sxs-lookup"><span data-stu-id="f16ac-127">There are some operations, like linking and razor page publishing that will still require publishing.</span></span>


## <a name="local-dotnet-tools"></a><span data-ttu-id="f16ac-128">Lokale dotnet-Tools</span><span class="sxs-lookup"><span data-stu-id="f16ac-128">Local dotnet tools</span></span>

<span data-ttu-id="f16ac-129">.NET Core 2.1 unterstützt globale Tools, .NET Core 3.0 verfügt jetzt über lokale Tools.</span><span class="sxs-lookup"><span data-stu-id="f16ac-129">While .NET Core 2.1 supported global tools, .NET Core 3.0 now has local tools.</span></span> <span data-ttu-id="f16ac-130">Lokale Tools ähneln globalen Tools, sind aber mit einem bestimmten Speicherort auf dem Datenträger verknüpft.</span><span class="sxs-lookup"><span data-stu-id="f16ac-130">Local tools are similar to global tools but are associated with a particular location on disk.</span></span> <span data-ttu-id="f16ac-131">Dies ermöglicht die Bereitstellung von Tools für einzelne Projekte und Repositorys.</span><span class="sxs-lookup"><span data-stu-id="f16ac-131">This enables per-project and per-repository tooling.</span></span> <span data-ttu-id="f16ac-132">Jedes lokal installierte Tool ist nicht global verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f16ac-132">Any tool installed locally isn't available globally.</span></span>

<span data-ttu-id="f16ac-133">Lokale Tools basieren auf einer Manifestdatei `dotnet-tools.json` in Ihrem aktuellen Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="f16ac-133">Local tools rely on a manifest file name `dotnet-tools.json` in your current directory.</span></span> <span data-ttu-id="f16ac-134">Diese Manifestdatei definiert die verfügbaren Tools.</span><span class="sxs-lookup"><span data-stu-id="f16ac-134">This manifest file defines the tools to be available.</span></span> <span data-ttu-id="f16ac-135">Durch die Erstellung dieser Manifestdatei im Stammverzeichnis Ihres Repositorys stellen Sie sicher, dass jeder, der Ihren Code klont, die Tools wiederherstellen und verwenden kann, die für eine erfolgreiche Arbeit mit Ihrem Code erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="f16ac-135">By creating this manifest file at the root of your repository, you ensure anyone cloning your code can restore and use the tools that are needed to successfully work with your code.</span></span>

<span data-ttu-id="f16ac-136">Wenn die Manifestdatei für lokale Tools verfügbar ist, verwenden Sie den folgenden Befehl, um diese Tools automatisch herunterzuladen und lokal zu installieren:</span><span class="sxs-lookup"><span data-stu-id="f16ac-136">When the local tools manifest file is available, use the following command to automatically download and install those tools locally:</span></span>

```console
dotnet tool restore
```

<span data-ttu-id="f16ac-137">Führen Sie ein lokales Tool mit dem folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="f16ac-137">Run a local tool with the following command:</span></span>

```console
dotnet tool run <tool-command-name>
```

<span data-ttu-id="f16ac-138">Wenn ein lokales Tool aufgerufen wird, sucht dotnet nach einer Manifestdatei in der Verzeichnisstruktur.</span><span class="sxs-lookup"><span data-stu-id="f16ac-138">When a local tool is called, dotnet searches for a manifest up the directory structure.</span></span> <span data-ttu-id="f16ac-139">Wenn eine Manifestdatei für das Tool gefunden wurde, wird diese nach dem erforderlichen Tool durchsucht.</span><span class="sxs-lookup"><span data-stu-id="f16ac-139">When a tool manifest file is found, it is searched for the requested tool.</span></span> <span data-ttu-id="f16ac-140">Wenn das Tool gefunden wird, enthält es die Informationen, die benötigt werden, um das Tool am Speicherort der globalen NuGet-Pakete zu finden.</span><span class="sxs-lookup"><span data-stu-id="f16ac-140">If the tool is found, it includes the information needed to find the tool in the NuGet global packages location.</span></span> 

<span data-ttu-id="f16ac-141">Wenn das Tool in der Manifestdatei, aber nicht im Cache gefunden wird, erhält der Benutzer eine Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="f16ac-141">If the tool is found in the manifest, but not the cache, the user receives an error.</span></span> <span data-ttu-id="f16ac-142">Diese Meldung wird nach der Vorschauversion 1 verbessert, damit der Benutzer `dotnet tool restore` ausführen muss.</span><span class="sxs-lookup"><span data-stu-id="f16ac-142">The message will be improved after Preview 1 to request the user run `dotnet tool restore`.</span></span>

<span data-ttu-id="f16ac-143">Um lokale Tools zu einem Verzeichnis hinzuzufügen, müssen Sie zuerst die Manifestdatei für das Tool erstellen.</span><span class="sxs-lookup"><span data-stu-id="f16ac-143">To add local tools to a directory, you need to first create the tool manifest file.</span></span> <span data-ttu-id="f16ac-144">Nach der Vorschauversion 1 werden wir einen Mechanismus zum Erstellen von Manifestdateien für das Tool anbieten, wie z.B. eine neue dotnet-Vorlage.</span><span class="sxs-lookup"><span data-stu-id="f16ac-144">After Preview 1, we will offer a mechanism for creating tool manifest files, such as a dotnet new template.</span></span> <span data-ttu-id="f16ac-145">Für die Vorschauversion 1 müssen Sie eine Datei mit dem `dotnet-tools.json` und folgendem Inhalt erstellen:</span><span class="sxs-lookup"><span data-stu-id="f16ac-145">For Preview 1 you must create the file named `dotnet-tools.json` with the following contents:</span></span>

```json
{
  "version": 1,
  "isRoot": true,
  "tools": {}
}
```

<span data-ttu-id="f16ac-146">Wenn die Manifestdatei erstellt wurde, können Sie folgendermaßen lokale Tools hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="f16ac-146">Once the manifest is created, you can add local tools to it using:</span></span>

```console
dotnet tool install <toolPackageId>
```

<span data-ttu-id="f16ac-147">Dieser Befehl installiert die neueste Version des Tools, sofern keine andere Version angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="f16ac-147">This command installs the latest version of the tool, unless another version is specified.</span></span>  <span data-ttu-id="f16ac-148">Auch wenn die neueste Version automatisch ausgewählt wurde, wird die Version des Tools in die Manifestdatei des Tools geschrieben, damit die korrekte Version des Tools wiederhergestellt oder ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="f16ac-148">Even if the latest version was automatically chosen, the version of the tool is written into the tool manifest file to allow the correct version of the tool to be restored or run.</span></span>

<span data-ttu-id="f16ac-149">Die Manifestdatei des Tools ist so konzipiert, dass sie eine manuelle Bearbeitung ermöglicht. Sie müssen die Datei bearbeiten, um die erforderliche Version für die Arbeit mit dem Repository zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="f16ac-149">The tool manifest file is designed to allow hand editing – which you might do to update the required version for working with the repository.</span></span>

<span data-ttu-id="f16ac-150">Hier ist ein Beispiel für eine `dotnet-tools.json`-Datei:</span><span class="sxs-lookup"><span data-stu-id="f16ac-150">Here is an example `dotnet-tools.json` file:</span></span>

```json
{
  "version": 1,
  "isRoot": true,
  "tools": {
    "dotnetsay": {
      "version": "2.1.4",
      "commands": [
        "dotnetsay"
      ]
    },
    "t-rex": {
      "version": "1.0.103",
      "commands": [
        "t-rex"
      ]
    }
  }
}
```

<span data-ttu-id="f16ac-151">Um ein Tool aus der Manifestdatei des Tools zu entfernen, führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="f16ac-151">To remove a tool from the tool manifest file, run the following command:</span></span>

```console
dotnet tool uninstall <toolPackageId>
```

<span data-ttu-id="f16ac-152">Für sowohl globale als auch lokale Tools ist eine kompatible Version der Runtime erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f16ac-152">For both global and local tools, a compatible version of the runtime is required.</span></span> <span data-ttu-id="f16ac-153">Die meisten Tools führen derzeit NuGet.org target .NET Core Runtime 2.1 aus.</span><span class="sxs-lookup"><span data-stu-id="f16ac-153">Many tools currently on NuGet.org target .NET Core Runtime 2.1.</span></span> <span data-ttu-id="f16ac-154">Um diese global oder lokal zu installieren, müssten Sie weiterhin die [NET Core 2.1-Runtime](https://dotnet.microsoft.com/download/dotnet-core/2.1) installieren.</span><span class="sxs-lookup"><span data-stu-id="f16ac-154">To install those globally or locally, you would still need to install the [NET Core 2.1 Runtime](https://dotnet.microsoft.com/download/dotnet-core/2.1).</span></span>

<span data-ttu-id="f16ac-155">Weitere Informationen finden Sie unter [Frühe Vorschaudokumentation für lokale Tools](https://github.com/dotnet/cli/issues/10288).</span><span class="sxs-lookup"><span data-stu-id="f16ac-155">For more information, see [Local Tools Early Preview Documentation](https://github.com/dotnet/cli/issues/10288).</span></span>

## <a name="windows-desktop"></a><span data-ttu-id="f16ac-156">Windows Desktop</span><span class="sxs-lookup"><span data-stu-id="f16ac-156">Windows desktop</span></span>

<span data-ttu-id="f16ac-157">Ab .NET Core 3.0 Vorschauversion 1 können Sie Windows Desktop-Anwendungen mit WPF und Windows Forms erstellen.</span><span class="sxs-lookup"><span data-stu-id="f16ac-157">Starting with .NET Core 3.0 Preview 1, you can build Windows desktop applications using WPF and Windows Forms.</span></span> <span data-ttu-id="f16ac-158">Diese Frameworks unterstützt auch die Verwendung moderner Steuerelemente und des Fluent-Stils aus der Windows-UI-XAML-Bibliothek (WinUI) über [XAML-Inseln](/windows/uwp/xaml-platform/xaml-host-controls).</span><span class="sxs-lookup"><span data-stu-id="f16ac-158">These frameworks also support using modern controls and Fluent styling from the Windows UI XAML Library (WinUI) via [XAML islands](/windows/uwp/xaml-platform/xaml-host-controls).</span></span>

<span data-ttu-id="f16ac-159">Die Windows Desktop-Komponente ist Teil des Windows .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="f16ac-159">The Windows Desktop component is part of the Windows .NET Core 3.0 SDK.</span></span>

<span data-ttu-id="f16ac-160">Mit dem folgenden `dotnet`-Befehl können Sie eine neue WPF- oder Windows Forms-Anwendung erstellen:</span><span class="sxs-lookup"><span data-stu-id="f16ac-160">You can create a new WPF or Windows Forms app with the following `dotnet` commands:</span></span>

```console
dotnet new wpf
dotnet new winforms
```

<span data-ttu-id="f16ac-161">Sie können auch.NET Core 3.0 WPF- und Windows Forms-Projekte in Visual Studio 2019 Vorschauversion 1 öffnen, starten und debuggen.</span><span class="sxs-lookup"><span data-stu-id="f16ac-161">You can also open, launch, and debug .NET Core 3.0 WPF and Windows Forms projects in Visual Studio 2019 Preview 1.</span></span> <span data-ttu-id="f16ac-162">Derzeit können diese Projekte in Visual Studio 2017 15.9 geöffnet werden, das Szenario wird allerdings nicht unterstützt (und Sie müssen [Vorschauversionen aktivieren](https://blogs.msdn.microsoft.com/dotnet/2018/11/13/net-core-tooling-update-for-visual-studio-2017-version-15-9/)).</span><span class="sxs-lookup"><span data-stu-id="f16ac-162">It's currently possible to open these projects in Visual Studio 2017 15.9, however, it isn't a supported scenario (and you need to [enable previews](https://blogs.msdn.microsoft.com/dotnet/2018/11/13/net-core-tooling-update-for-visual-studio-2017-version-15-9/)).</span></span>

<span data-ttu-id="f16ac-163">Die neuen Projekte sind die gleichen wie die bestehenden.NET Core Projekte, mit ein paar Ergänzungen.</span><span class="sxs-lookup"><span data-stu-id="f16ac-163">The new projects are the same as existing .NET Core projects, with a couple additions.</span></span> <span data-ttu-id="f16ac-164">Hier ist der Vergleich eines einfachen .NET Core-Konsolenprojekts mit einem einfachen Windows Forms- und WPF-Projekt.</span><span class="sxs-lookup"><span data-stu-id="f16ac-164">Here is the comparison of the basic .NET Core console project and a basic Windows Forms and WPF project.</span></span>

<span data-ttu-id="f16ac-165">In einem .NET Core-Konsolenprojekt verwendet das Projekt das `Microsoft.NET.Sdk` SDK und deklariert eine Abhängigkeit von .NET Core 3.0 über das `netcoreapp3.0`-Zielframework.</span><span class="sxs-lookup"><span data-stu-id="f16ac-165">In a .NET Core console project, the project uses the `Microsoft.NET.Sdk` SDK and declares a dependency on .NET Core 3.0 via the `netcoreapp3.0` target framework.</span></span> <span data-ttu-id="f16ac-166">Um eine Windows Desktop-Anwendung zu erstellen, verwenden Sie das `Microsoft.NET.Sdk.WindowsDesktop` SDK und wählen Sie das zu verwendende UI-Framework:</span><span class="sxs-lookup"><span data-stu-id="f16ac-166">To create a Windows Desktop app, use the `Microsoft.NET.Sdk.WindowsDesktop` SDK and choose which UI framework to use:</span></span>

```diff
-<Project Sdk="Microsoft.NET.Sdk">
+<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
+   <UseWPF>true</UseWPF>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="f16ac-167">Um Windows Forms und nicht WPF zu wählen, legen Sie `UseWindowsForms` anstelle von `UseWPF` fest:</span><span class="sxs-lookup"><span data-stu-id="f16ac-167">To choose Windows Forms over WPF, set `UseWindowsForms` instead of `UseWPF`:</span></span>

```diff
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
-   <UseWPF>true</UseWPF>
+   <UseWindowsForms>true</UseWindowsForms>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="f16ac-168">Sowohl `UseWPF` als auch `UseWindowsForms` können auf `true` festgelegt werden, wenn die Anwendung beide Frameworks verwendet, z.B. wenn ein Windows Forms-Dialogfeld ein WPF-Steuerelement bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="f16ac-168">Both `UseWPF` and `UseWindowsForms` can be set to `true` if the app uses both frameworks, for example when a Windows Forms dialog is hosting a WPF control.</span></span>

<span data-ttu-id="f16ac-169">Ihr Feedback in den [dotnet/winforms](https://github.com/dotnet/winforms/issues)-, [dotnet/wpf](https://github.com/dotnet/wpf/issues)- und [dotnet/core](https://github.com/dotnet/core/issues)-Repositorys ist jederzeit willkommen.</span><span class="sxs-lookup"><span data-stu-id="f16ac-169">Please share your feedback on the [dotnet/winforms](https://github.com/dotnet/winforms/issues),  [dotnet/wpf](https://github.com/dotnet/wpf/issues) and [dotnet/core](https://github.com/dotnet/core/issues) repos.</span></span>

## <a name="fast-built-in-json-support"></a><span data-ttu-id="f16ac-170">Schneller integrierter JSON-Support</span><span class="sxs-lookup"><span data-stu-id="f16ac-170">Fast built-in JSON support</span></span>

<span data-ttu-id="f16ac-171">`System.Text.Json.Utf8JsonReader` ist ein leistungsstarker, reiner Vorwärtsleser mit geringer Zuordnung für UTF-8-kodierten JSON-Text, der von einem `ReadOnlySpan<byte>` gelesen wird.</span><span class="sxs-lookup"><span data-stu-id="f16ac-171">`System.Text.Json.Utf8JsonReader` is a high-performance, low allocation, forward-only reader for UTF-8 encoded JSON text, read from a `ReadOnlySpan<byte>`.</span></span> <span data-ttu-id="f16ac-172">Der `Utf8JsonReader` ist ein grundlegender, Low-Level-Typ, der zum Erstellen von benutzerdefinierten Parsern und Fehler beim Erstellen des Deserialisierungsprogramms genutzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="f16ac-172">The `Utf8JsonReader` is a foundational, low-level type, that can be leveraged to build custom parsers and deserializers.</span></span> <span data-ttu-id="f16ac-173">Das Durchlesen einer JSON-Nutzlast mit dem neuen `Utf8JsonReader` ist 2x schneller als mit dem Leser von [Json.NET](https://www.newtonsoft.com/json).</span><span class="sxs-lookup"><span data-stu-id="f16ac-173">Reading through a JSON payload using the new `Utf8JsonReader` is 2x faster than using the reader from [Json.NET](https://www.newtonsoft.com/json).</span></span> <span data-ttu-id="f16ac-174">Es wird erst dann zugewiesen, wenn Sie JSON-Token als (UTF-16)-Zeichenfolgen aktualisieren müssen.</span><span class="sxs-lookup"><span data-stu-id="f16ac-174">It does not allocate until you need to actualize JSON tokens as (UTF-16) strings.</span></span>

<span data-ttu-id="f16ac-175">Diese neue API umfasst die folgenden Komponenten:</span><span class="sxs-lookup"><span data-stu-id="f16ac-175">This new API will include the following components:</span></span>

* <span data-ttu-id="f16ac-176">In Vorschauversion 1: JSON-Leser (sequenzieller Zugriff)</span><span class="sxs-lookup"><span data-stu-id="f16ac-176">In Preview 1: JSON reader (sequential access)</span></span>
* <span data-ttu-id="f16ac-177">Geplant: JSON-Writer, DOM (wahlfreier Zugriff), POCO-Serialisierungsprogramm, POCO-Deserialisierungsprogramm</span><span class="sxs-lookup"><span data-stu-id="f16ac-177">Coming next: JSON writer, DOM (random access), poco serializer, poco deserializer</span></span>

<span data-ttu-id="f16ac-178">Hier ist eine einfache Leserschleife für den `Utf8JsonReader`, die als Startpunkt verwendet werden kann:</span><span class="sxs-lookup"><span data-stu-id="f16ac-178">Here is the basic reader loop for the `Utf8JsonReader` that can be used as a starting point:</span></span>

```csharp
using System.Text.Json;

public static void Utf8JsonReaderLoop(ReadOnlySpan<byte> dataUtf8)
{
    var json = new Utf8JsonReader(dataUtf8, isFinalBlock: true, state: default);

    while (json.Read())
    {
        JsonTokenType tokenType = json.TokenType;
        ReadOnlySpan<byte> valueSpan = json.ValueSpan;
        switch (tokenType)
        {
            case JsonTokenType.StartObject:
            case JsonTokenType.EndObject:
                break;
            case JsonTokenType.StartArray:
            case JsonTokenType.EndArray:
                break;
            case JsonTokenType.PropertyName:
                break;
            case JsonTokenType.String:
                string valueString = json.GetStringValue();
                break;
            case JsonTokenType.Number:
                if (!json.TryGetInt32Value(out int valueInteger))
                {
                    throw new FormatException();
                }
                break;
            case JsonTokenType.True:
            case JsonTokenType.False:
                bool valueBool = json.GetBooleanValue();
                break;
            case JsonTokenType.Null:
                break;
            default:
                throw new ArgumentException();
        }
    }

    dataUtf8 = dataUtf8.Slice((int)json.BytesConsumed);
    JsonReaderState state = json.CurrentState;
}
```

<span data-ttu-id="f16ac-179">Das .NET-Ökosystem basiert auf [Json.NET](https://www.newtonsoft.com/json) und anderen beliebten JSON-Bibliotheken, die weiterhin eine gute Wahl sind.</span><span class="sxs-lookup"><span data-stu-id="f16ac-179">The .NET ecosystem has relied on [Json.NET](https://www.newtonsoft.com/json) and other popular JSON libraries, which continue to be good choices.</span></span> <span data-ttu-id="f16ac-180">JSON.NET verwendet .NET-Zeichenfolgen als den Basisdatentyp, die intern UTF-16 sind.</span><span class="sxs-lookup"><span data-stu-id="f16ac-180">JSON.NET uses .NET strings as its base datatype, which are UTF-16 under the hood.</span></span> 

<span data-ttu-id="f16ac-181">In .NET Core 2.1 und 3.0 haben wir neue APIs hinzugefügt, die es ermöglichen, JSON-APIs (z.B. `Utf8JsonReader`) zu schreiben, die viel weniger Speicher benötigen, basierend auf der Verwendung von `Span<T>` und UTF-8-Zeichenfolgen, und die die Anforderungen von Anwendungen mit hohem Durchsatz wie Kestrel, ASP.NET Core Webserver besser erfüllen.</span><span class="sxs-lookup"><span data-stu-id="f16ac-181">In .NET Core 2.1 and 3.0, we added new APIs that makes it possible to write JSON APIs (such as `Utf8JsonReader`) that require much less memory, based on using `Span<T>` and UTF-8 strings, and better serve the needs of high-throughput applications like Kestrel, ASP.NET Core web server.</span></span>

## <a name="ranges-and-indices"></a><span data-ttu-id="f16ac-182">Bereiche und Indizes</span><span class="sxs-lookup"><span data-stu-id="f16ac-182">Ranges and indices</span></span>

<span data-ttu-id="f16ac-183">Der neue `Index`-Typ kann für die Indizierung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f16ac-183">The new `Index` type can be used for indexing.</span></span> <span data-ttu-id="f16ac-184">Sie können einen aus einem `int` erstellen, der vom Anfang aus zählt, oder mit einem Präfix-`^`-Operator (C#), der vom Ende aus zählt:</span><span class="sxs-lookup"><span data-stu-id="f16ac-184">You can create one from an `int` that counts from the beginning, or with a prefix `^` operator (C#) that counts from the end:</span></span>

```csharp
Index i1 = 3;  // number 3 from beginning
Index i2 = ^4; // number 4 from end
int[] a = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };
Console.WriteLine($"{a[i1]}, {a[i2]}"); // "3, 6"
```

<span data-ttu-id="f16ac-185">Es gibt auch einen `Range`-Typ, der aus zwei `Index`-Werten besteht, einen für den Anfang und einen für das Ende, und mit einem `x..y`-Bereichsausdruck (C#) geschrieben werden kann.</span><span class="sxs-lookup"><span data-stu-id="f16ac-185">There is also a `Range` type, which consists of two `Index` values, one for the start and one for the end, and can be written with a `x..y` range expression (C#).</span></span> <span data-ttu-id="f16ac-186">Sie können dann mit einem `Range` indizieren, um einen Slice zu erzeugen:</span><span class="sxs-lookup"><span data-stu-id="f16ac-186">You can then index with a `Range` in order to produce a slice:</span></span>

```csharp
var slice = a[i1..i2]; // { 3, 4, 5 }
```

> [!NOTE]
> <span data-ttu-id="f16ac-187">Nur [ C# 8.0](https://blogs.msdn.microsoft.com/dotnet/2018/11/12/building-c-8-0/) unterstützt die Syntax für `Range` und `Index`.</span><span class="sxs-lookup"><span data-stu-id="f16ac-187">Only [C# 8.0](https://blogs.msdn.microsoft.com/dotnet/2018/11/12/building-c-8-0/) supports syntax for `Range` and `Index`.</span></span>

## <a name="async-streams"></a><span data-ttu-id="f16ac-188">Asynchrone Datenströme</span><span class="sxs-lookup"><span data-stu-id="f16ac-188">Async streams</span></span>

<span data-ttu-id="f16ac-189">Die `IAsyncEnumerable<T>`-Typ ist eine neue asynchrone Version von `IEnumerable<T>`.</span><span class="sxs-lookup"><span data-stu-id="f16ac-189">The `IAsyncEnumerable<T>` type is a new asynchronous version of `IEnumerable<T>`.</span></span> <span data-ttu-id="f16ac-190">Mit der Sprache können Sie `await foreach` dafür ausführen, um diese Elemente zu verarbeiten, und dann `yield return` verwenden, um Elemente zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f16ac-190">The language lets you `await foreach` over these to consume their elements, and `yield return` to them to produce elements.</span></span>

<span data-ttu-id="f16ac-191">Das folgende Beispiel zeigt sowohl die Produktion als auch die Nutzung von asynchronen Datenströmen.</span><span class="sxs-lookup"><span data-stu-id="f16ac-191">The following example demonstrates both production and consumption of async streams.</span></span> <span data-ttu-id="f16ac-192">Die `foreach`-Anweisung ist asynchron und verwendet `yield return`, um einen asynchronen Datenstrom für Anrufer zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f16ac-192">The `foreach` statement is async and itself uses `yield return` to produce an async stream for callers.</span></span> <span data-ttu-id="f16ac-193">Dieses Muster (mit `yield return`) ist das empfohlene Modell zum Erstellen von asynchronen Datenströmen.</span><span class="sxs-lookup"><span data-stu-id="f16ac-193">This pattern (using `yield return`) is the recommended model for producing async streams.</span></span>

```csharp
async IAsyncEnumerable<int> GetBigResultsAsync()
{
    await foreach (var result in GetResultsAsync())
    {
        if (result > 20) yield return result; 
    }
}
```

> [!WARNING]
> <span data-ttu-id="f16ac-194">Bei .NET Core 3.0 Vorschauversion 1 tritt derzeit ein Fehler bei `await foreach` auf.</span><span class="sxs-lookup"><span data-stu-id="f16ac-194">.NET Core 3.0 Preview 1 currently has a bug with `await foreach`.</span></span> <span data-ttu-id="f16ac-195">Verwenden Sie stattdessen `GetEnumerator` und `MoveNext` für die Verarbeitung von Elementen.</span><span class="sxs-lookup"><span data-stu-id="f16ac-195">Instead, use `GetEnumerator` and `MoveNext` to process elements.</span></span> <span data-ttu-id="f16ac-196">Weitere Informationen finden Sie unter [roslyn/#31268](https://github.com/dotnet/roslyn/issues/31268).</span><span class="sxs-lookup"><span data-stu-id="f16ac-196">For more information, see [roslyn/#31268](https://github.com/dotnet/roslyn/issues/31268).</span></span>

<span data-ttu-id="f16ac-197">Zusätzlich zu `await foreach` können Sie auch asynchrone Iteratoren erstellen, z.B. einen Iterator, der `IAsyncEnumerable/IAsyncEnumerator` zurückgibt, in den Sie sowohl `await` als auch `yield` einfügen können.</span><span class="sxs-lookup"><span data-stu-id="f16ac-197">In addition to being able to `await foreach`, you can also create async iterators, for example, an iterator that returns an `IAsyncEnumerable/IAsyncEnumerator` that you can both `await` and `yield` in.</span></span> <span data-ttu-id="f16ac-198">Für Objekte, die gelöscht werden müssen, können Sie `IAsyncDisposable` verwenden, das von verschiedenen BCL-Typen implementiert wird, wie beispielsweise `Stream` und `Timer`.</span><span class="sxs-lookup"><span data-stu-id="f16ac-198">For objects that need to be disposed, you can use `IAsyncDisposable`, which various BCL types implement, such as `Stream` and `Timer`.</span></span>

> [!NOTE]
> <span data-ttu-id="f16ac-199">Nur [ C# 8.0](https://blogs.msdn.microsoft.com/dotnet/2018/11/12/building-c-8-0/) unterstützt die `await foreach`-Syntax.</span><span class="sxs-lookup"><span data-stu-id="f16ac-199">Only [C# 8.0](https://blogs.msdn.microsoft.com/dotnet/2018/11/12/building-c-8-0/) supports `await foreach` syntax.</span></span>

## <a name="type-sequencereader"></a><span data-ttu-id="f16ac-200">Typ: SequenceReader</span><span class="sxs-lookup"><span data-stu-id="f16ac-200">Type: SequenceReader</span></span>

<span data-ttu-id="f16ac-201">In .NET Core 3.0 wurde `System.Buffers.SequenceReader` hinzugefügt, der als Leser für `ReadOnlySequence<T>` verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="f16ac-201">In .NET Core 3.0, `System.Buffers.SequenceReader` has been added which can be used as a reader for `ReadOnlySequence<T>`.</span></span> <span data-ttu-id="f16ac-202">Dies ermöglicht eine einfache, leistungsstarke Zuteilungsanalyse mit geringer Priorität von `System.IO.Pipelines`-Daten, die mehrere Hintergrundpuffer überwinden können.</span><span class="sxs-lookup"><span data-stu-id="f16ac-202">This allows easy, high performance, low allocation parsing of `System.IO.Pipelines` data that can cross multiple backing buffers.</span></span> 

<span data-ttu-id="f16ac-203">Das folgende Beispiel bricht eine Eingabe-`Sequence` in gültige, durch Trennzeichen getrennte `CR/LF`-Zeilen auf:</span><span class="sxs-lookup"><span data-stu-id="f16ac-203">The following example breaks an input `Sequence` into valid `CR/LF` delimited lines:</span></span>

```csharp
private static ReadOnlySpan<byte> CRLF => new byte[] { (byte)'\r', (byte)'\n' };

public static void ReadLines(ReadOnlySequence<byte> sequence)
{
    SequenceReader<byte> reader = new SequenceReader<byte>(sequence);

    while (!reader.End)
    {
        if (!reader.TryReadToAny(out ReadOnlySpan<byte> line, CRLF, advancePastDelimiter:false))
        {
            // Couldn't find another delimiter
            // ...
        }

        if (!reader.IsNext(CRLF, advancePast: true))
        {
            // Not a good CR/LF pair
            // ...
        }

        // line is valid, process
        ProcessLine(line);
    }
}
```

## <a name="type-metadataloadcontext"></a><span data-ttu-id="f16ac-204">Typ: MetadataLoadContext</span><span class="sxs-lookup"><span data-stu-id="f16ac-204">Type: MetadataLoadContext</span></span>

<span data-ttu-id="f16ac-205">Der `MetadataLoadContext`-Typ wurde hinzugefügt, der das Lesen von Assemblymetadaten ermöglicht, ohne die Anwendungsdomäne des Anrufers zu beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="f16ac-205">The `MetadataLoadContext` type has been added that enables reading assembly metadata without affecting the caller’s application domain.</span></span> <span data-ttu-id="f16ac-206">Assemblys werden als Daten gelesen, einschließlich Assemblys, die für andere Architekturen und Plattformen als die aktuelle Runtimeumgebung erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="f16ac-206">Assemblies are read as data, including assemblies built for different architectures and platforms than the current runtime environment.</span></span> <span data-ttu-id="f16ac-207">`MetadataLoadContext` überschneidet sich mit <xref:System.Reflection.Assembly.ReflectionOnlyLoad*>, das nur in .NET Framework verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="f16ac-207">`MetadataLoadContext` overlaps with the <xref:System.Reflection.Assembly.ReflectionOnlyLoad*>, which is only available in the .NET Framework.</span></span>

<span data-ttu-id="f16ac-208">`MetdataLoadContext` ist im [System.Reflection.MetadataLoadContext-Paket](https://www.nuget.org/packages/System.Reflection.MetadataLoadContext) verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f16ac-208">`MetdataLoadContext` is available in the [System.Reflection.MetadataLoadContext package](https://www.nuget.org/packages/System.Reflection.MetadataLoadContext).</span></span> <span data-ttu-id="f16ac-209">Es ist ein .NET Standard 2.0-Paket.</span><span class="sxs-lookup"><span data-stu-id="f16ac-209">It is a .NET Standard 2.0 package.</span></span>

<span data-ttu-id="f16ac-210">Der `MetadataLoadContext` stellt APIs ähnlich dem Typ <xref:System.Runtime.Loader.AssemblyLoadContext> zur Verfügung, basiert aber nicht auf diesem Typ.</span><span class="sxs-lookup"><span data-stu-id="f16ac-210">The `MetadataLoadContext` exposes APIs similar to the <xref:System.Runtime.Loader.AssemblyLoadContext> type, but is not based on that type.</span></span> <span data-ttu-id="f16ac-211">Ähnlich wie <xref:System.Runtime.Loader.AssemblyLoadContext> ermöglicht der `MetadataLoadContext` das Laden von Assemblys innerhalb einer isolierten Umgebung zum Laden von Assemblys.</span><span class="sxs-lookup"><span data-stu-id="f16ac-211">Much like <xref:System.Runtime.Loader.AssemblyLoadContext>, the `MetadataLoadContext` enables loading assemblies within an isolated assembly loading universe.</span></span> <span data-ttu-id="f16ac-212">`MetdataLoadContext`-APIs geben <xref:System.Reflection.Assembly>-Objekte zurück, sodass bekannte Reflektions-APIs verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="f16ac-212">`MetdataLoadContext` APIs return <xref:System.Reflection.Assembly> objects, enabling the use of familiar reflection APIs.</span></span> <span data-ttu-id="f16ac-213">Ausführungsorientierte APIs, wie [MethodBase.Invoke](https://github.com/dotnet/corefx/blob/master/src/System.Reflection.MetadataLoadContext/src/System/Reflection/TypeLoading/Methods/RoMethod.cs#L127) sind nicht zulässig, und geben „InvalidOperationException“ zurück.</span><span class="sxs-lookup"><span data-stu-id="f16ac-213">Execution-oriented APIs, such as [MethodBase.Invoke](https://github.com/dotnet/corefx/blob/master/src/System.Reflection.MetadataLoadContext/src/System/Reflection/TypeLoading/Methods/RoMethod.cs#L127), are not allowed and will throw InvalidOperationException.</span></span>

<span data-ttu-id="f16ac-214">Das folgende Beispiel zeigt, wie Sie den richtigen Typen in einer Assembly findet, die eine bestimmte Schnittstelle implementiert:</span><span class="sxs-lookup"><span data-stu-id="f16ac-214">The following sample demonstrates how to find concrete types in an assembly that implements a given interface:</span></span>

```csharp
var paths = new string[] {@"C:\myapp\mscorlib.dll", @"C:\myapp\myapp.dll"};
var resolver = new PathAssemblyResolver(paths);
using (var lc = new MetadataLoadContext(resolver))
{
    Assembly a = lc.LoadFromAssemblyName("myapp");
    Type myInterface = a.GetType("MyApp.IPluginInterface");
    foreach (Type t in a.GetTypes())
    {
        if (t.IsClass && myInterface.IsAssignableFrom(t))
            Console.WriteLine($"Class {t.FullName} implements IPluginInterface");
    }
}
```

<span data-ttu-id="f16ac-215">Szenarien für `MetadataLoadContext` beinhalten Entwurfszeitfeatures, Buildzeit-Tools und Runtime-Light-Up-Features, die eine Reihe von Assemblys als Daten überprüfen müssen und alle Dateisperren und Speicher freigeben, nachdem die Überprüfung durchgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="f16ac-215">Scenarios for `MetadataLoadContext` include design-time features, build-time tooling, and runtime light-up features that need to inspect a set of assemblies as data and have all file locks and memory freed after inspection is performed.</span></span>

<span data-ttu-id="f16ac-216">Der `MetadataLoadContext` hat eine Resolverklasse, die an dessen Konstruktor übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="f16ac-216">The `MetadataLoadContext` has a resolver class passed to its constructor.</span></span> <span data-ttu-id="f16ac-217">Die Auftrag des Resolvers ist es, eine `Assembly` zu laden, wenn der `AssemblyName` angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="f16ac-217">The resolver's job is to load an `Assembly` given its `AssemblyName`.</span></span> <span data-ttu-id="f16ac-218">Die Resolverklasse wird aus der abstrakten `MetadataAssemblyResolver`-Klasse abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="f16ac-218">The resolver class derives from the abstract `MetadataAssemblyResolver` class.</span></span> <span data-ttu-id="f16ac-219">Die Implementierung des Resolvers für pfadbasierte Szenarien ist durch `PathAssemblyResolver` möglich.</span><span class="sxs-lookup"><span data-stu-id="f16ac-219">An implementation of the resolver for path-based scenarios is provided with `PathAssemblyResolver`.</span></span>

<span data-ttu-id="f16ac-220">Die [MetadataLoadContext-Tests](https://github.com/dotnet/corefx/tree/master/src/System.Reflection.MetadataLoadContext/tests/src/Tests) zeigen viele Anwendungsfälle.</span><span class="sxs-lookup"><span data-stu-id="f16ac-220">The [MetadataLoadContext tests](https://github.com/dotnet/corefx/tree/master/src/System.Reflection.MetadataLoadContext/tests/src/Tests) demonstrate many use cases.</span></span> <span data-ttu-id="f16ac-221">Die [Assemblytests](https://github.com/dotnet/corefx/blob/master/src/System.Reflection.MetadataLoadContext/tests/src/Tests/Assembly/AssemblyTests.cs) sind ein guter Ausgangspunkt.</span><span class="sxs-lookup"><span data-stu-id="f16ac-221">The [Assembly tests](https://github.com/dotnet/corefx/blob/master/src/System.Reflection.MetadataLoadContext/tests/src/Tests/Assembly/AssemblyTests.cs) are a good place to start.</span></span>

## <a name="tls-13--openssl-111-on-linux"></a><span data-ttu-id="f16ac-222">TLS 1.3 & OpenSSL 1.1.1 auf Linux</span><span class="sxs-lookup"><span data-stu-id="f16ac-222">TLS 1.3 & OpenSSL 1.1.1 on Linux</span></span>

<span data-ttu-id="f16ac-223">.NET Core nutzt nun die Unterstützung von [TLS 1.3 in OpenSSL 1.1.1.1](https://www.openssl.org/blog/blog/2018/09/11/release111/), wenn es in einer bestimmten Umgebung verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="f16ac-223">.NET Core will now take advantage of [TLS 1.3 support in OpenSSL 1.1.1](https://www.openssl.org/blog/blog/2018/09/11/release111/), when it is available in a given environment.</span></span> <span data-ttu-id="f16ac-224">Gemäß dem [OpenSSL-Team](https://www.openssl.org/blog/blog/2018/09/11/release111/) hat TLS 1.3 viele Vorteile:</span><span class="sxs-lookup"><span data-stu-id="f16ac-224">There are multiple benefits of TLS 1.3, per the [OpenSSL team](https://www.openssl.org/blog/blog/2018/09/11/release111/):</span></span>

* <span data-ttu-id="f16ac-225">Verbesserte Verbindungszeiten aufgrund einer Reduzierung der erforderlich Roundtrips zwischen Client und Server.</span><span class="sxs-lookup"><span data-stu-id="f16ac-225">Improved connection times due to a reduction in the number of round trips required between the client and server.</span></span>

* <span data-ttu-id="f16ac-226">Höhere Sicherheit durch das Entfernen verschiedener veralteter und unsicher Kryptografiealgorithmen und die Verschlüsselung von mehr des Verbindungshandshake.</span><span class="sxs-lookup"><span data-stu-id="f16ac-226">Improved security due to the removal of various obsolete and insecure cryptographic algorithms and encryption of more of the connection handshake.</span></span>

<span data-ttu-id="f16ac-227">.NET Core 3.0 Vorschauversion 1 kann **OpenSSL 1.1.1**, **OpenSSL 1.1.0** oder **OpenSSL 1.0.2** (was auch immer die geeignete Lösung ist) auf einem Linux-System verwenden.</span><span class="sxs-lookup"><span data-stu-id="f16ac-227">.NET Core 3.0 Preview 1 is capable of utilizing **OpenSSL 1.1.1**, **OpenSSL 1.1.0**, or **OpenSSL 1.0.2** (whatever the best version found is, on a Linux system).</span></span>  <span data-ttu-id="f16ac-228">Wenn **OpenSSL 1.1.1** verfügbar ist, verwenden „SslStream“- und „HttpClient“-Typen **TLS 1.3** bei der Nutzung von `SslProtocols.None` (systemseitige Standardprotokolle), sofern sowohl der Client als auch der Server **TLS 1.3** unterstützen.</span><span class="sxs-lookup"><span data-stu-id="f16ac-228">When **OpenSSL 1.1.1** is available the SslStream and HttpClient types will use **TLS 1.3** when using `SslProtocols.None` (system default protocols), assuming both the client and server support **TLS 1.3**.</span></span>

<span data-ttu-id="f16ac-229">Das folgende Beispiel veranschaulicht .NET Core 3.0 Vorschauversion 1 auf Ubuntu 18.10 beim Verbinden mit <https://www.cloudflare.com>:</span><span class="sxs-lookup"><span data-stu-id="f16ac-229">The following sample demonstrates .NET Core 3.0 Preview 1 on Ubuntu 18.10 connecting to <https://www.cloudflare.com>:</span></span>

```csharp
using System;
using System.Net.Security;
using System.Net.Sockets;
using System.Threading.Tasks;

namespace tlstest
{
    class Program
    {
        static async Task Main()
        {
            using (TcpClient tcpClient = new TcpClient())
            {
                string targetHost = "www.cloudflare.com";

                await tcpClient.ConnectAsync(targetHost, 443);

                using (SslStream sslStream = new SslStream(tcpClient.GetStream()))
                {
                    await sslStream.AuthenticateAsClientAsync(targetHost);
                    await Console.Out.WriteLineAsync($"Connected to {targetHost} with {sslStream.SslProtocol}");
                }
            }
        }
    }
}
```

```console
user@comp-ubuntu1810:~/tlstest$ dotnet run
Connected to www.cloudflare.com with Tls13
user@comp-ubuntu1810:~/tlstest$ openssl version
OpenSSL 1.1.1  11 Sep 2018
```

>[!IMPORTANT]
><span data-ttu-id="f16ac-230">Windows und macOS unterstützen **TLS 1.3** noch nicht.</span><span class="sxs-lookup"><span data-stu-id="f16ac-230">Windows and macOS do not yet support **TLS 1.3**.</span></span> <span data-ttu-id="f16ac-231">.NET Core 3.0 unterstützt **TLS 1.3** auf diesen Betriebssystemen, wenn entsprechender Support verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="f16ac-231">.NET Core 3.0 will support **TLS 1.3** on these operating systems when support becomes available.</span></span>

## <a name="cryptography"></a><span data-ttu-id="f16ac-232">Kryptografie</span><span class="sxs-lookup"><span data-stu-id="f16ac-232">Cryptography</span></span>

<span data-ttu-id="f16ac-233">Unterstützung für **AES-GCM**- und **AES-CCM**-Verschlüsselungen wurde hinzugefügt, implementiert über `System.Security.Cryptography.AesGcm` und `System.Security.Cryptography.AesCcm`.</span><span class="sxs-lookup"><span data-stu-id="f16ac-233">Support has been added for **AES-GCM** and **AES-CCM** ciphers, implemented via `System.Security.Cryptography.AesGcm` and `System.Security.Cryptography.AesCcm`.</span></span> <span data-ttu-id="f16ac-234">Diese Algorithmen sind beide [Authenticated Encryption with Association Data (AEAD)-Algorithmen](https://en.wikipedia.org/wiki/Authenticated_encryption) und die ersten Authenticated Encryption (AE)-Algorithmen, die zu .NET Core hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="f16ac-234">These algorithms are both [Authenticated Encryption with Association Data (AEAD) algorithms](https://en.wikipedia.org/wiki/Authenticated_encryption), and the first Authenticated Encryption (AE) algorithms added to .NET Core.</span></span>

<span data-ttu-id="f16ac-235">Der folgende Code veranschaulicht die Verwendung der **AesGcm**-Verschlüsselung zum Verschlüsseln und Entschlüsseln von Zufallsdaten.</span><span class="sxs-lookup"><span data-stu-id="f16ac-235">The following code demonstrates using **AesGcm** cipher to encrypt and decrypt random data.</span></span>

<span data-ttu-id="f16ac-236">Der Code für **AesCcm** würde fast identisch aussehen (nur der Variablenname der Klasse wäre anders).</span><span class="sxs-lookup"><span data-stu-id="f16ac-236">The code for **AesCcm** would look almost identical (only the class variable names would be different).</span></span>

```csharp
// key should be: pre-known, derived, or transported via another channel, such as RSA encryption
byte[] key = new byte[16];
RandomNumberGenerator.Fill(key);

byte[] nonce = new byte[12];
RandomNumberGenerator.Fill(nonce);

// normally this would be your data
byte[] dataToEncrypt = new byte[1234];
byte[] associatedData = new byte[333];
RandomNumberGenerator.Fill(dataToEncrypt);
RandomNumberGenerator.Fill(associatedData);

// these will be filled during the encryption
byte[] tag = new byte[16];
byte[] ciphertext = new byte[dataToEncrypt.Length];

using (AesGcm aesGcm = new AesGcm(key))
{
    aesGcm.Encrypt(nonce, dataToEncrypt, ciphertext, tag, associatedData);
}

// tag, nonce, ciphertext, associatedData should be sent to the other part

byte[] decryptedData = new byte[ciphertext.Length];

using (AesGcm aesGcm = new AesGcm(key))
{
    aesGcm.Decrypt(nonce, ciphertext, tag, decryptedData, associatedData);
}

// do something with the data
// this should always print that data is the same
Console.WriteLine($"AES-GCM: Decrypted data is{(dataToEncrypt.SequenceEqual(decryptedData) ? "the same as" : "different than")} original data.");
```

## <a name="cryptographic-key-importexport"></a><span data-ttu-id="f16ac-237">Importieren/Exportieren kryptografischer Schlüssel</span><span class="sxs-lookup"><span data-stu-id="f16ac-237">Cryptographic Key Import/Export</span></span>

<span data-ttu-id="f16ac-238">.NET Core 3.0 Vorschauversion 1 unterstützt das Importieren und Exportieren der asymmetrischen öffentliche und private Schlüssel aus den Standardformaten, ohne dass ein x. 509-Zertifikat verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="f16ac-238">.NET Core 3.0 Preview 1 supports the import and export of asymmetric public and private keys from standard formats, without needing to use an X.509 certificate.</span></span>

<span data-ttu-id="f16ac-239">Alle Schlüsseltypen (RSA, DSA, ECDsa, ECDiffieHellman) unterstützten das Format **X.509 SubjectPublicKeyInfo** für öffentliche Schlüssel und die Formate **PKCS#8 PrivateKeyInfo** und **PKCS#8 EncryptedPrivateKeyInfo** für private Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="f16ac-239">All key types (RSA, DSA, ECDsa, ECDiffieHellman) support the **X.509 SubjectPublicKeyInfo** format for public keys, and the **PKCS#8 PrivateKeyInfo** and **PKCS#8 EncryptedPrivateKeyInfo** formats for private keys.</span></span> <span data-ttu-id="f16ac-240">RSA unterstützt zudem **PKCS#1 RSAPublicKey** und **PKCS#1 RSAPrivateKey**.</span><span class="sxs-lookup"><span data-stu-id="f16ac-240">RSA additionally supports **PKCS#1 RSAPublicKey** and **PKCS#1 RSAPrivateKey**.</span></span> <span data-ttu-id="f16ac-241">Die Exportmethoden erstellen alle DER-kodierte Binärdaten, und die Importmethoden erwarten dasselbe.</span><span class="sxs-lookup"><span data-stu-id="f16ac-241">The export methods all produce DER-encoded binary data, and the import methods expect the same.</span></span> <span data-ttu-id="f16ac-242">Wenn ein Schlüssel im textfreundlichen PEM-Format gespeichert ist, muss der Anrufer den Inhalt base64-dekodieren, bevor er eine Importmethode aufruft.</span><span class="sxs-lookup"><span data-stu-id="f16ac-242">If a key is stored in the text-friendly PEM format, the caller will need to base64-decode the content before calling an import method.</span></span>

```csharp
using System;
using System.IO;
using System.Security.Cryptography;

namespace rsakeyprint
{
    class Program
    {
        static void Main(string[] args)
        {
            using (RSA rsa = RSA.Create())
            {
                byte[] keyBytes = File.ReadAllBytes(args[0]);
                rsa.ImportRSAPrivateKey(keyBytes, out int bytesRead);
 
                Console.WriteLine($"Read {bytesRead} bytes, {keyBytes.Length-bytesRead} extra byte(s) in file.");
                RSAParameters rsaParameters = rsa.ExportParameters(true);
                Console.WriteLine(BitConverter.ToString(rsaParameters.D));
            }
        }
    }
}
```

```console
user@comp-ubuntu1810:~/rsakeyprint$ echo Making a small key to save on screen space.
Making a small key to save on screen space.
user@comp-ubuntu1810:~/rsakeyprint$ openssl genrsa 768 | openssl rsa -outform der -out rsa.key
Generating RSA private key, 768 bit long modulus (2 primes)
..+++++++
........+++++++
e is 65537 (0x010001)
writing RSA key
user@comp-ubuntu1810:~/rsakeyprint$ dotnet run rsa.key
Read 461 bytes, 0 extra byte(s) in file.
0F-D0-82-34-F8-13-38-4A-7F-C7-52-4A-F6-93-F8-FB-6D-98-7A-6A-04-3B-BC-35-8C-7D-AC-A5-A3-6E-AD-C1-66-30-81-2C-2A-DE-DA-60-03-6A-2C-D9-76-15-7F-61-97-57-
79-E1-6E-45-62-C3-83-04-97-CB-32-EF-C5-17-5F-99-60-92-AE-B6-34-6F-30-06-03-AC-BF-15-24-43-84-EB-83-60-EF-4D-3B-BD-D9-5D-56-26-F0-51-CE-F1
user@comp-ubuntu1810:~/rsakeyprint$ openssl rsa -in rsa.key -inform der -text -noout | grep -A7 private
privateExponent:
    0f:d0:82:34:f8:13:38:4a:7f:c7:52:4a:f6:93:f8:
    fb:6d:98:7a:6a:04:3b:bc:35:8c:7d:ac:a5:a3:6e:
    ad:c1:66:30:81:2c:2a:de:da:60:03:6a:2c:d9:76:
    15:7f:61:97:57:79:e1:6e:45:62:c3:83:04:97:cb:
    32:ef:c5:17:5f:99:60:92:ae:b6:34:6f:30:06:03:
    ac:bf:15:24:43:84:eb:83:60:ef:4d:3b:bd:d9:5d:
    56:26:f0:51:ce:f1
```

<span data-ttu-id="f16ac-243">PKCS #8-Dateien können mit der `System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo`-Klasse überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="f16ac-243">PKCS#8 files can be inspected with the `System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo` class.</span></span>

<span data-ttu-id="f16ac-244">PFX/PKCS#12-Dateien können mit `System.Security.Cryptography.Pkcs.Pkcs12Info` oder `System.Security.Cryptography.Pkcs.Pkcs12Builder` überprüft und bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="f16ac-244">PFX/PKCS#12 files can be inspected and manipulated with `System.Security.Cryptography.Pkcs.Pkcs12Info` and `System.Security.Cryptography.Pkcs.Pkcs12Builder`, respectively.</span></span>

## <a name="serialport-for-linux"></a><span data-ttu-id="f16ac-245">SerialPort für Linux</span><span class="sxs-lookup"><span data-stu-id="f16ac-245">SerialPort for Linux</span></span>

<span data-ttu-id="f16ac-246">.NET Core 3.0 unterstützt jetzt <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType> auf Linux.</span><span class="sxs-lookup"><span data-stu-id="f16ac-246">.NET Core 3.0 now supports <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType> on Linux.</span></span>

<span data-ttu-id="f16ac-247">Bisher unterstützte .NET Core nur die Verwendung des `SerialPort`-Typs auf Windows.</span><span class="sxs-lookup"><span data-stu-id="f16ac-247">Previously, .NET Core only supported using the `SerialPort` type on Windows.</span></span>

## <a name="more-bcl-improvements"></a><span data-ttu-id="f16ac-248">Weitere BCL-Verbesserungen</span><span class="sxs-lookup"><span data-stu-id="f16ac-248">More BCL Improvements</span></span>

<span data-ttu-id="f16ac-249">Die Typen `Span<T>`, `Memory<T>` und verwandte Typen, die in .NET Core 2.1 eingeführt wurden, wurden in .NET Core 3.0 optimiert.</span><span class="sxs-lookup"><span data-stu-id="f16ac-249">The `Span<T>`, `Memory<T>`, and related types that were introduced in .NET Core 2.1, have been optimized in .NET Core 3.0.</span></span> <span data-ttu-id="f16ac-250">Allgemeine Vorgänge, wie die Bereichserstellung, Slicing, Analyse und Formatierung werden jetzt besser ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f16ac-250">Common operations such as span construction, slicing, parsing, and formatting now perform better.</span></span> 

<span data-ttu-id="f16ac-251">Darüber hinaus haben Typen wie `String` indirekte Verbesserungen, um sie effizienter zu machen, wenn sie als Schlüssel mit `Dictionary<TKey, TValue>` und anderen Sammlungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f16ac-251">Additionally, types like `String` have seen under-the-cover improvements to make them more efficient when used as keys with `Dictionary<TKey, TValue>` and other collections.</span></span> <span data-ttu-id="f16ac-252">Um von diesen Verbesserungen zu profitieren, sind keine Codeänderungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f16ac-252">No code changes are required to benefit from these improvements.</span></span>

<span data-ttu-id="f16ac-253">NET Core 3 Vorschauversion 1 enthält außerdem die folgenden Verbesserungen:</span><span class="sxs-lookup"><span data-stu-id="f16ac-253">The following improvements are also new in .NET Core 3 Preview 1:</span></span>

* <span data-ttu-id="f16ac-254">In HttpClient integrierte Brotli-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="f16ac-254">Brotli support built in to HttpClient</span></span>
* <span data-ttu-id="f16ac-255">ThreadPool.UnsafeQueueWorkItem(IThreadPoolWorkItem)</span><span class="sxs-lookup"><span data-stu-id="f16ac-255">ThreadPool.UnsafeQueueWorkItem(IThreadPoolWorkItem)</span></span>
* <span data-ttu-id="f16ac-256">Unsafe.Unbox</span><span class="sxs-lookup"><span data-stu-id="f16ac-256">Unsafe.Unbox</span></span>
* <span data-ttu-id="f16ac-257">CancellationToken.Unregister</span><span class="sxs-lookup"><span data-stu-id="f16ac-257">CancellationToken.Unregister</span></span>
* <span data-ttu-id="f16ac-258">Komplexe arithmetische Operatoren</span><span class="sxs-lookup"><span data-stu-id="f16ac-258">Complex arithmetic operators</span></span>
* <span data-ttu-id="f16ac-259">Socket-APIs für TCP-Keep-Alive</span><span class="sxs-lookup"><span data-stu-id="f16ac-259">Socket APIs for TCP keep alive</span></span>
* <span data-ttu-id="f16ac-260">StringBuilder.GetChunks</span><span class="sxs-lookup"><span data-stu-id="f16ac-260">StringBuilder.GetChunks</span></span>
* <span data-ttu-id="f16ac-261">IPEndPoint-Analyse</span><span class="sxs-lookup"><span data-stu-id="f16ac-261">IPEndPoint parsing</span></span>
* <span data-ttu-id="f16ac-262">RandomNumberGenerator.GetInt32</span><span class="sxs-lookup"><span data-stu-id="f16ac-262">RandomNumberGenerator.GetInt32</span></span>

## <a name="tiered-compilation"></a><span data-ttu-id="f16ac-263">Mehrstufig Kompilierung</span><span class="sxs-lookup"><span data-stu-id="f16ac-263">Tiered compilation</span></span>

<span data-ttu-id="f16ac-264">Die [mehrstufig Kompilierung](https://blogs.msdn.microsoft.com/dotnet/2018/08/02/tiered-compilation-preview-in-net-core-2-1/) ist bei .NET Core 3.0 standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="f16ac-264">[Tiered compilation](https://blogs.msdn.microsoft.com/dotnet/2018/08/02/tiered-compilation-preview-in-net-core-2-1/) is on by default with .NET Core 3.0.</span></span> <span data-ttu-id="f16ac-265">Es ist ein Feature, das es der Runtime ermöglicht, den Just-In-Time (JIT)-Compiler adaptiver zu nutzen, um eine bessere Leistung zu erzielen, sowohl beim Start als auch zur Maximierung des Durchsatzes.</span><span class="sxs-lookup"><span data-stu-id="f16ac-265">It is a feature that enables the runtime to more adaptively use the Just-In-Time (JIT) compiler to get better performance, both at startup and to maximize throughput.</span></span>

<span data-ttu-id="f16ac-266">Dieses Feature wurde als abonnierbares Feature für [.NET Core 2.1](https://blogs.msdn.microsoft.com/dotnet/2018/05/30/announcing-net-core-2-1/) hinzugefügt, und anschließend standardmäßig in der [.NET Core 2.2 Vorschauversion 2](https://blogs.msdn.microsoft.com/dotnet/2018/09/12/announcing-net-core-2-2-preview-2/) aktiviert.</span><span class="sxs-lookup"><span data-stu-id="f16ac-266">This feature was added as an opt-in feature in [.NET Core 2.1](https://blogs.msdn.microsoft.com/dotnet/2018/05/30/announcing-net-core-2-1/) and then was enabled by default in [.NET Core 2.2 Preview 2](https://blogs.msdn.microsoft.com/dotnet/2018/09/12/announcing-net-core-2-2-preview-2/).</span></span> <span data-ttu-id="f16ac-267">Anschließend wurde es wieder zurückgesetzt, und ist mit dem Release von .NET Core 2.2 wieder abonnierbar.</span><span class="sxs-lookup"><span data-stu-id="f16ac-267">Subsequently, it has been reverted back to opt in with the .NET Core 2.2 release.</span></span>

## <a name="arm64-linux-support"></a><span data-ttu-id="f16ac-268">ARM64-Linux-Support</span><span class="sxs-lookup"><span data-stu-id="f16ac-268">ARM64 Linux support</span></span>

<span data-ttu-id="f16ac-269">Mit diesem Release haben wir Support für ARM64 für Linux hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="f16ac-269">We are adding support for ARM64 for Linux this release.</span></span> <span data-ttu-id="f16ac-270">Wir haben den Support für ARM32 für Linux mit .NET Core 2.1 und Windows mit .NET Core 2.2 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="f16ac-270">For context, we added support for ARM32 for Linux with .NET Core 2.1 and Windows with .NET Core 2.2.</span></span> <span data-ttu-id="f16ac-271">Der primäre Anwendungsfall für ARM64 sind derzeit IoT-Szenarien.</span><span class="sxs-lookup"><span data-stu-id="f16ac-271">The primary use case for ARM64 is currently with IoT scenarios.</span></span>

<span data-ttu-id="f16ac-272">Alpine-, Debian- und Ubuntu-[-Dockerimages sind für .NET Core für ARM64 verfügbar](https://hub.docker.com/r/microsoft/dotnet/).</span><span class="sxs-lookup"><span data-stu-id="f16ac-272">Alpine, Debian and Ubuntu [Docker images are available for .NET Core for ARM64](https://hub.docker.com/r/microsoft/dotnet/).</span></span>

<span data-ttu-id="f16ac-273">Bitte lesen Sie für weitere Informationen [.NET Core-ARM64-Status](https://github.com/dotnet/announcements/issues/82)</span><span class="sxs-lookup"><span data-stu-id="f16ac-273">Please check [.NET Core ARM64 Status](https://github.com/dotnet/announcements/issues/82) for more information.</span></span>

>[!NOTE]
> <span data-ttu-id="f16ac-274">**ARM64** wird von Windows noch nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f16ac-274">**ARM64** Windows support isn't yet available.</span></span>
