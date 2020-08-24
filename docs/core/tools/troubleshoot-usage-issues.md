---
title: Behandlung von Problemen bei der Nutzung von .NET Core-Tools
description: Informieren Sie sich über allgemeine Probleme beim Ausführen von .NET Core-Tools sowie über mögliche Lösungen.
author: kdollard
ms.topic: troubleshooting
ms.date: 02/14/2020
ms.openlocfilehash: db88958e1605fef589c5dbcb12065a6318183705
ms.sourcegitcommit: cbb19e56d48cf88375d35d0c27554d4722761e0d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2020
ms.locfileid: "88608309"
---
# <a name="troubleshoot-net-core-tool-usage-issues"></a><span data-ttu-id="b0979-103">Behandlung von Problemen bei der Nutzung von .NET Core-Tools</span><span class="sxs-lookup"><span data-stu-id="b0979-103">Troubleshoot .NET Core tool usage issues</span></span>

<span data-ttu-id="b0979-104">Beim Installieren oder Ausführen eines globalen oder lokalen .NET Core-Tools können Probleme auftreten.</span><span class="sxs-lookup"><span data-stu-id="b0979-104">You might come across issues when trying to install or run a .NET Core tool, which can be a global tool or a local tool.</span></span> <span data-ttu-id="b0979-105">In diesem Artikel werden die allgemeinen Grundursachen und einige mögliche Lösungen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b0979-105">This article describes the common root causes and some possible solutions.</span></span>

## <a name="installed-net-core-tool-fails-to-run"></a><span data-ttu-id="b0979-106">Ausführung eines installierten .NET Core-Tools schlägt fehl</span><span class="sxs-lookup"><span data-stu-id="b0979-106">Installed .NET Core tool fails to run</span></span>

<span data-ttu-id="b0979-107">Wenn die Ausführung eines .NET Core-Tools fehlschlägt, ist sehr wahrscheinlich eines der folgenden Probleme aufgetreten:</span><span class="sxs-lookup"><span data-stu-id="b0979-107">When a .NET Core tool fails to run, most likely you ran into one of the following issues:</span></span>

* <span data-ttu-id="b0979-108">Die ausführbare Datei für das Tool wurde nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="b0979-108">The executable file for the tool wasn't found.</span></span>
* <span data-ttu-id="b0979-109">Die richtige Version der .NET Core-Runtime wurde nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="b0979-109">The correct version of the .NET Core runtime wasn't found.</span></span>

### <a name="executable-file-not-found"></a><span data-ttu-id="b0979-110">Ausführbare Datei nicht gefunden</span><span class="sxs-lookup"><span data-stu-id="b0979-110">Executable file not found</span></span>

<span data-ttu-id="b0979-111">Wenn die ausführbare Datei nicht gefunden wird, wird eine Meldung angezeigt, die in etwa wie folgt lautet:</span><span class="sxs-lookup"><span data-stu-id="b0979-111">If the executable file isn't found, you'll see a message similar to the following:</span></span>

```console
Could not execute because the specified command or file was not found.
Possible reasons for this include:
  * You misspelled a built-in dotnet command.
  * You intended to execute a .NET Core program, but dotnet-xyz does not exist.
  * You intended to run a global tool, but a dotnet-prefixed executable with this name could not be found on the PATH.
```

<span data-ttu-id="b0979-112">Der Name der ausführbaren Datei bestimmt, wie Sie das Tool aufrufen.</span><span class="sxs-lookup"><span data-stu-id="b0979-112">The name of the executable determines how you invoke the tool.</span></span> <span data-ttu-id="b0979-113">Das Format wird in der folgenden Tabelle beschrieben:</span><span class="sxs-lookup"><span data-stu-id="b0979-113">The following table describes the format:</span></span>

| <span data-ttu-id="b0979-114">Format der ausführbaren Datei</span><span class="sxs-lookup"><span data-stu-id="b0979-114">Executable name format</span></span>  | <span data-ttu-id="b0979-115">Aufrufformat</span><span class="sxs-lookup"><span data-stu-id="b0979-115">Invocation format</span></span>   |
|-------------------------|---------------------|
| `dotnet-<toolName>.exe` | `dotnet <toolName>` |
| `<toolName>.exe`        | `<toolName>`        |

* <span data-ttu-id="b0979-116">Globale Tools</span><span class="sxs-lookup"><span data-stu-id="b0979-116">Global tools</span></span>

  <span data-ttu-id="b0979-117">Globale Tools können im Standardverzeichnis oder an einem spezifischen Speicherort installiert werden.</span><span class="sxs-lookup"><span data-stu-id="b0979-117">Global tools can be installed in the default directory or in a specific location.</span></span> <span data-ttu-id="b0979-118">Die Standardverzeichnisse sind:</span><span class="sxs-lookup"><span data-stu-id="b0979-118">The default directories are:</span></span>

  | <span data-ttu-id="b0979-119">Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="b0979-119">OS</span></span>          | <span data-ttu-id="b0979-120">Pfad</span><span class="sxs-lookup"><span data-stu-id="b0979-120">Path</span></span>                          |
  |-------------|-------------------------------|
  | <span data-ttu-id="b0979-121">Linux/macOS</span><span class="sxs-lookup"><span data-stu-id="b0979-121">Linux/macOS</span></span> | `$HOME/.dotnet/tools`         |
  | <span data-ttu-id="b0979-122">Windows</span><span class="sxs-lookup"><span data-stu-id="b0979-122">Windows</span></span>     | `%USERPROFILE%\.dotnet\tools` |

  <span data-ttu-id="b0979-123">Prüfen Sie beim Ausführen eines globalen Tools, ob die Umgebungsvariable `PATH` auf Ihrem Computer den Pfad enthält, unter dem Sie das globale Tool installiert haben, und ob sich die ausführbare Datei in diesem Verzeichnis befindet.</span><span class="sxs-lookup"><span data-stu-id="b0979-123">If you're trying to run a global tool, check that the `PATH` environment variable on your machine contains the path where you installed the global tool and that the executable is in that path.</span></span>

  <span data-ttu-id="b0979-124">Die .NET Core-CLI versucht bei der ersten Verwendung, den Standardspeicherort der Umgebungsvariable „PATH“ hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="b0979-124">The .NET Core CLI tries to add the default location to the PATH environment variable on its first usage.</span></span> <span data-ttu-id="b0979-125">Es gibt jedoch einige Szenarien, in denen der Speicherort möglicherweise nicht automatisch zu „PATH“ hinzugefügt wird:</span><span class="sxs-lookup"><span data-stu-id="b0979-125">However, there are some scenarios where the location might not be added to PATH automatically:</span></span>

  * <span data-ttu-id="b0979-126">Wenn Sie Linux verwenden und das .NET Core SDK mit *TAR.GZ*-Dateien anstelle von „apt-get“ oder „rpm“ installiert haben.</span><span class="sxs-lookup"><span data-stu-id="b0979-126">If you're using Linux and you've installed the .NET Core SDK using *.tar.gz* files and not apt-get or rpm.</span></span>
  * <span data-ttu-id="b0979-127">Wenn Sie macOS 10.15 „Catalina“ oder höhere Versionen verwenden.</span><span class="sxs-lookup"><span data-stu-id="b0979-127">If you're using macOS 10.15 "Catalina" or later versions.</span></span>
  * <span data-ttu-id="b0979-128">Wenn Sie macOS 10.14 „Mojave“ oder frühere Versionen verwenden und das .NET Core SDK mit *TAR.GZ*-Dateien statt mit *PKG*-Dateien installiert haben.</span><span class="sxs-lookup"><span data-stu-id="b0979-128">If you're using macOS 10.14 "Mojave" or earlier versions, and you've installed the .NET Core SDK using *.tar.gz* files and not *.pkg*.</span></span>
  * <span data-ttu-id="b0979-129">Wenn Sie das .NET Core 3.0 SDK installiert und die Umgebungsvariable `DOTNET_ADD_GLOBAL_TOOLS_TO_PATH` auf `false` festgelegt haben.</span><span class="sxs-lookup"><span data-stu-id="b0979-129">If you've installed the .NET Core 3.0 SDK and you've set the `DOTNET_ADD_GLOBAL_TOOLS_TO_PATH` environment variable to `false`.</span></span>
  * <span data-ttu-id="b0979-130">Wenn Sie .NET Core 2.2 SDK oder frühere Versionen installiert und die Umgebungsvariable `DOTNET_SKIP_FIRST_TIME_EXPERIENCE` auf `true` festgelegt haben.</span><span class="sxs-lookup"><span data-stu-id="b0979-130">If you've installed .NET Core 2.2 SDK or earlier versions, and you've set the `DOTNET_SKIP_FIRST_TIME_EXPERIENCE` environment variable to `true`.</span></span>

  <span data-ttu-id="b0979-131">In diesen Szenarien oder wenn Sie die Option `--tool-path` angegeben haben, enthält die Umgebungsvariable `PATH` auf Ihrem Computer nicht automatisch den Pfad, in dem Sie das globale Tool installiert haben.</span><span class="sxs-lookup"><span data-stu-id="b0979-131">In these scenarios or if you specified the `--tool-path` option, the `PATH` environment variable on your machine doesn't automatically contain the path where you installed the global tool.</span></span> <span data-ttu-id="b0979-132">In diesem Fall fügen Sie den Speicherort des Tools (z. B. `$HOME/.dotnet/tools`) an die Umgebungsvariable `PATH` an, indem Sie die Methode verwenden, die Ihre Shell zur Aktualisierung der Umgebungsvariablen zur Verfügung stellt.</span><span class="sxs-lookup"><span data-stu-id="b0979-132">In that case, append the tool location (for example, `$HOME/.dotnet/tools`) to the `PATH` environment variable by using whatever method your shell provides for updating environment variables.</span></span> <span data-ttu-id="b0979-133">Weitere Informationen finden Sie unter [.NET Core-Tools](global-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b0979-133">For more information, see [.NET Core tools](global-tools.md).</span></span>

* <span data-ttu-id="b0979-134">Lokale Tools</span><span class="sxs-lookup"><span data-stu-id="b0979-134">Local tools</span></span>

  <span data-ttu-id="b0979-135">Prüfen Sie beim Ausführen eines lokalen Tools, ob im aktuellen Verzeichnis oder in einem der übergeordneten Verzeichnisse eine Manifestdatei mit dem Namen *dotnet-tools.json* vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="b0979-135">If you're trying to run a local tool, verify that there's a manifest file called *dotnet-tools.json* in the current directory or any of its parent directories.</span></span> <span data-ttu-id="b0979-136">Diese Datei kann sich auch in einem Ordner mit dem Namen *CONFIG* in der Projektordnerhierarchie statt im Stammverzeichnis befinden.</span><span class="sxs-lookup"><span data-stu-id="b0979-136">This file can also live under a folder named *.config* anywhere in the project folder hierarchy, instead of the root folder.</span></span> <span data-ttu-id="b0979-137">Wenn *dotnet-tools.json* vorhanden ist, öffnen Sie die Datei und überprüfen Sie, ob das Tool enthalten ist, das Sie ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="b0979-137">If *dotnet-tools.json* exists, open it and check for the tool you're trying to run.</span></span> <span data-ttu-id="b0979-138">Wenn die Datei keinen Eintrag für `"isRoot": true` enthält, suchen Sie weiter oben in der Dateihierarchie nach weiteren Manifestdateien des Tools.</span><span class="sxs-lookup"><span data-stu-id="b0979-138">If the file doesn't contain an entry for `"isRoot": true`, then also check further up the file hierarchy for additional tool manifest files.</span></span>

  <span data-ttu-id="b0979-139">Beim Ausführen eines .NET Core-Tools, das mit einem angegebenen Pfad installiert wurde, müssen Sie bei Verwendung des Tools diesen Pfad angeben.</span><span class="sxs-lookup"><span data-stu-id="b0979-139">If you're trying to run a .NET Core tool that was installed with a specified path, you need to include that path when using the tool.</span></span> <span data-ttu-id="b0979-140">Beispiel für die Verwendung eines mit einem Toolpfad installierten Tools:</span><span class="sxs-lookup"><span data-stu-id="b0979-140">An example of using a tool-path installed tool is:</span></span>

  ```console
  ..\<toolDirectory>\dotnet-<toolName>
  ```

### <a name="runtime-not-found"></a><span data-ttu-id="b0979-141">Runtime nicht gefunden</span><span class="sxs-lookup"><span data-stu-id="b0979-141">Runtime not found</span></span>

<span data-ttu-id="b0979-142">.NET Core-Tools sind [Framework-abhängige Anwendungen](../deploying/index.md#publish-framework-dependent), d. h. sie sind von der auf Ihrem Computer installierten .NET Core-Runtime abhängig.</span><span class="sxs-lookup"><span data-stu-id="b0979-142">.NET Core tools are [framework-dependent applications](../deploying/index.md#publish-framework-dependent), which means they rely on a .NET Core runtime installed on your machine.</span></span> <span data-ttu-id="b0979-143">Wenn die erwartete Runtime nicht gefunden wurde, orientieren sie sich an den normalen Regeln für das Rollforward der .NET Core-Runtime, zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b0979-143">If the expected runtime isn't found, they follow normal .NET Core runtime roll-forward rules such as:</span></span>

* <span data-ttu-id="b0979-144">Eine Anwendung wird auf das neueste Patchrelease der angegebenen Haupt- und Nebenversion gebracht.</span><span class="sxs-lookup"><span data-stu-id="b0979-144">An application rolls forward to the highest patch release of the specified major and minor version.</span></span>
* <span data-ttu-id="b0979-145">Wenn keine übereinstimmende Runtime mit einer übereinstimmenden Haupt- und Nebenversion vorhanden ist, wird die nächsthöhere Nebenversion verwendet.</span><span class="sxs-lookup"><span data-stu-id="b0979-145">If there's no matching runtime with a matching major and minor version number, the next higher minor version is used.</span></span>
* <span data-ttu-id="b0979-146">Ein Rollforward findet nicht zwischen Vorschauversionen der Runtime oder Vorschauversionen und Releaseversionen statt.</span><span class="sxs-lookup"><span data-stu-id="b0979-146">Roll forward doesn't occur between preview versions of the runtime or between preview versions and release versions.</span></span> <span data-ttu-id="b0979-147">Daher müssen .NET Core-Tools, die mit Vorschauversionen erstellt wurden, vom Autor neu erstellt, veröffentlicht und installiert werden.</span><span class="sxs-lookup"><span data-stu-id="b0979-147">So, .NET Core tools created using preview versions must be rebuilt and republished by the author and reinstalled.</span></span>

<span data-ttu-id="b0979-148">Rollforward findet in zwei gängigen Szenarios nicht standardmäßig statt:</span><span class="sxs-lookup"><span data-stu-id="b0979-148">Roll-forward won't occur by default in two common scenarios:</span></span>

* <span data-ttu-id="b0979-149">Es sind nur frühere Versionen der Runtime verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b0979-149">Only lower versions of the runtime are available.</span></span> <span data-ttu-id="b0979-150">Beim Rollforward werden nur höhere Versionen der Runtime ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="b0979-150">Roll-forward only selects later versions of the runtime.</span></span>
* <span data-ttu-id="b0979-151">Es sind nur höhere Hauptversionen der Runtime verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b0979-151">Only higher major versions of the runtime are available.</span></span> <span data-ttu-id="b0979-152">Mit dem Rollforward werden die Grenzen von Hauptversionen nicht überschritten.</span><span class="sxs-lookup"><span data-stu-id="b0979-152">Roll-forward doesn't cross major version boundaries.</span></span>

<span data-ttu-id="b0979-153">Wenn eine Anwendung keine entsprechende Runtime finden kann, schlägt die Ausführung fehl, und ein Fehler wird gemeldet.</span><span class="sxs-lookup"><span data-stu-id="b0979-153">If an application can't find an appropriate runtime, it fails to run and reports an error.</span></span>

<span data-ttu-id="b0979-154">Sie können die auf Ihrem Computer installierten .NET Core-Runtimes mit einem der folgenden Befehle anzeigen:</span><span class="sxs-lookup"><span data-stu-id="b0979-154">You can find out which .NET Core runtimes are installed on your machine using one of the following commands:</span></span>

```dotnetcli
dotnet --list-runtimes
dotnet --info
```

<span data-ttu-id="b0979-155">Wenn Sie der Meinung sind, dass das Tool die von Ihnen installierte Runtimeversion unterstützen sollte, können Sie den Autor des Tools fragen, ob er die Versionsnummer aktualisieren oder mehrere Ziele zuweisen kann.</span><span class="sxs-lookup"><span data-stu-id="b0979-155">If you think the tool should support the runtime version you currently have installed, you can contact the tool author and see if they can update the version number or multi-target.</span></span> <span data-ttu-id="b0979-156">Nachdem das Toolpaket erneut kompiliert und auf NuGet mit einer aktualisierten Versionsnummer veröffentlicht wurde, können Sie Ihre Kopie aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="b0979-156">Once they've recompiled and republished their tool package to NuGet with an updated version number, you can update your copy.</span></span> <span data-ttu-id="b0979-157">Bis dies geschehen ist, können Sie eine Version der Runtime installieren, die mit dem gewünschten Tool verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="b0979-157">While that doesn't happen, the quickest solution for you is to install a version of the runtime that would work with the tool you're trying to run.</span></span> <span data-ttu-id="b0979-158">Wenn Sie eine bestimmte .NET Core-Runtimeversion herunterladen möchten, besuchen Sie die [.NET Core-Downloadseite](https://dotnet.microsoft.com/download/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="b0979-158">To download a specific .NET Core runtime version, visit the [.NET Core download page](https://dotnet.microsoft.com/download/dotnet-core).</span></span>

<span data-ttu-id="b0979-159">Wenn Sie das .NET Core SDK an einem nicht standardmäßigen Speicherort installieren, müssen Sie die Umgebungsvariable `DOTNET_ROOT` auf das Verzeichnis festlegen, das die ausführbare Datei `dotnet` enthält.</span><span class="sxs-lookup"><span data-stu-id="b0979-159">If you install the .NET Core SDK to a non-default location, you need to set the environment variable `DOTNET_ROOT` to the directory that contains the `dotnet` executable.</span></span>

## <a name="net-core-tool-installation-fails"></a><span data-ttu-id="b0979-160">Fehler bei der Installation von .NET Core-Tools</span><span class="sxs-lookup"><span data-stu-id="b0979-160">.NET Core tool installation fails</span></span>

<span data-ttu-id="b0979-161">Es gibt verschiedene Gründe, warum bei der Installation eines globalen oder lokalen .NET Core-Tools möglicherweise ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="b0979-161">There are a number of reasons the installation of a .NET Core global or local tool may fail.</span></span> <span data-ttu-id="b0979-162">Wenn bei der Installation eines Tools ein Fehler auftritt, wird eine Meldung angezeigt, die in etwa so lautet:</span><span class="sxs-lookup"><span data-stu-id="b0979-162">When the tool installation fails, you'll see a message similar to the following one:</span></span>

```console
Tool '{0}' failed to install. This failure may have been caused by:

* You are attempting to install a preview release and did not use the --version option to specify the version.
* A package by this name was found, but it was not a .NET Core tool.
* The required NuGet feed cannot be accessed, perhaps because of an Internet connection problem.
* You mistyped the name of the tool.

For more reasons, including package naming enforcement, visit https://aka.ms/failure-installing-tool
```

<span data-ttu-id="b0979-163">Um diese Fehler zu diagnostizieren, werden dem Benutzer neben der vorherigen Meldung auch NuGet-Meldungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b0979-163">To help diagnose these failures, NuGet messages are shown directly to the user, along with the previous message.</span></span> <span data-ttu-id="b0979-164">Mithilfe der NuGet-Meldung können Sie das Problem möglicherweise identifizieren.</span><span class="sxs-lookup"><span data-stu-id="b0979-164">The NuGet message may help you identify the problem.</span></span>

### <a name="package-naming-enforcement"></a><span data-ttu-id="b0979-165">Durchsetzung der Paketbenennung</span><span class="sxs-lookup"><span data-stu-id="b0979-165">Package naming enforcement</span></span>

<span data-ttu-id="b0979-166">Microsoft hat den Leitfaden zur Paket-ID für Tools geändert, was dazu führt, dass eine Reihe von Tools mit dem vorhergesagten Namen nicht gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="b0979-166">Microsoft has changed its guidance on the Package ID for tools, resulting in a number of tools not being found with the predicted name.</span></span> <span data-ttu-id="b0979-167">Der neue Leitfaden besagt, dass alle Microsoft-Tools das Präfix „Microsoft.“ enthalten müssen.</span><span class="sxs-lookup"><span data-stu-id="b0979-167">The new guidance is that all Microsoft tools be prefixed with "Microsoft."</span></span> <span data-ttu-id="b0979-168">Dieses Präfix ist reserviert und kann nur für Pakete verwendet werden, die mit einem autorisierten Microsoft-Zertifikat signiert sind.</span><span class="sxs-lookup"><span data-stu-id="b0979-168">This prefix is reserved and can only be used for packages signed with a Microsoft authorized certificate.</span></span>

<span data-ttu-id="b0979-169">In der Übergangszeit haben einige Microsoft-Tools die alte Form der Paket-ID, während andere die neue Form aufweisen:</span><span class="sxs-lookup"><span data-stu-id="b0979-169">During the transition, some Microsoft tools will have the old form of the package ID, while others will have the new form:</span></span>

```dotnetcli
dotnet tool install -g Microsoft.<toolName>
dotnet tool install -g <toolName>
```

<span data-ttu-id="b0979-170">Bei aktualisierten Paket-IDs müssen Sie zum Abrufen der aktuellen Updates die neue Paket-ID verwenden.</span><span class="sxs-lookup"><span data-stu-id="b0979-170">As package IDs are updated, you'll need to change to the new package ID to get the latest updates.</span></span> <span data-ttu-id="b0979-171">Pakete mit dem vereinfachten Toolnamen gelten als veraltet.</span><span class="sxs-lookup"><span data-stu-id="b0979-171">Packages with the simplified tool name will be deprecated.</span></span>

### <a name="preview-releases"></a><span data-ttu-id="b0979-172">Vorschaureleases</span><span class="sxs-lookup"><span data-stu-id="b0979-172">Preview releases</span></span>

* <span data-ttu-id="b0979-173">Beim Installieren eines Vorschaureleases geben Sie die Version ohne die `--version`-Option an.</span><span class="sxs-lookup"><span data-stu-id="b0979-173">You're attempting to install a preview release and didn't use the `--version` option to specify the version.</span></span>

<span data-ttu-id="b0979-174">.NET Core-Tools, die in einer Vorschauversion vorliegen, müssen zur Kennzeichnung dieses Umstands mit einem Teil des Namens angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="b0979-174">.NET Core tools that are in preview must be specified with a portion of the name to indicate that they are in preview.</span></span> <span data-ttu-id="b0979-175">Dabei müssen Sie nicht die gesamte Vorschauversion angeben.</span><span class="sxs-lookup"><span data-stu-id="b0979-175">You don't need to include the entire preview.</span></span> <span data-ttu-id="b0979-176">Sofern die Versionsnummern im erwarteten Format vorliegen, können Sie das folgende Beispiel oder Ähnliches verwenden:</span><span class="sxs-lookup"><span data-stu-id="b0979-176">Assuming the version numbers are in the expected format, you can use something like the following example:</span></span>

```dotnetcli
dotnet tool install -g --version 1.1.0-pre <toolName>
```

### <a name="package-isnt-a-net-core-tool"></a><span data-ttu-id="b0979-177">Das Paket ist kein .NET Core-Tool</span><span class="sxs-lookup"><span data-stu-id="b0979-177">Package isn't a .NET Core tool</span></span>

* <span data-ttu-id="b0979-178">Es wurde ein NuGet-Paket mit diesem Namen gefunden. Dabei handelt es sich jedoch nicht um ein .NET Core-Tool.</span><span class="sxs-lookup"><span data-stu-id="b0979-178">A NuGet package by this name was found, but it wasn't a .NET Core tool.</span></span>

<span data-ttu-id="b0979-179">Wenn Sie ein NuGet-Paket installieren, bei dem es sich nicht um ein .NET Core-Tool, sondern um ein normales NuGet-Paket handelt, wird eine Fehlermeldung angezeigt, die in etwa wie folgt lautet:</span><span class="sxs-lookup"><span data-stu-id="b0979-179">If you try to install a NuGet package that is a regular NuGet package and not a .NET Core tool, you'll see an error similar to the following:</span></span>

> <span data-ttu-id="b0979-180">NU1212: Ungültige Projekt-/Paket-Kombination für `<ToolName>`.</span><span class="sxs-lookup"><span data-stu-id="b0979-180">NU1212: Invalid project-package combination for `<ToolName>`.</span></span> <span data-ttu-id="b0979-181">Der DotnetToolReference-Projektstil darf nur Verweise vom Typ „DotnetTool“ enthalten.</span><span class="sxs-lookup"><span data-stu-id="b0979-181">DotnetToolReference project style can only contain references of the DotnetTool type.</span></span>

### <a name="nuget-feed-cant-be-accessed"></a><span data-ttu-id="b0979-182">Auf den NuGet-Feed kann nicht zugegriffen werden</span><span class="sxs-lookup"><span data-stu-id="b0979-182">NuGet feed can't be accessed</span></span>

* <span data-ttu-id="b0979-183">Auf den erforderlichen NuGet-Feed kann möglicherweise aufgrund eines Problems mit der Internetverbindung nicht zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="b0979-183">The required NuGet feed can't be accessed, perhaps because of an Internet connection problem.</span></span>

<span data-ttu-id="b0979-184">Für die Installation des Tools muss jedoch auf den NuGet-Feed zugegriffen werden, der das Toolpaket enthält.</span><span class="sxs-lookup"><span data-stu-id="b0979-184">Tool installation requires access to the NuGet feed that contains the tool package.</span></span> <span data-ttu-id="b0979-185">Ist dies nicht möglich, schlägt die Installation fehl.</span><span class="sxs-lookup"><span data-stu-id="b0979-185">It fails if the feed isn't available.</span></span> <span data-ttu-id="b0979-186">Sie können Feeds mit `nuget.config` ändern, eine bestimmte `nuget.config`-Datei anfordern oder mit dem `--add-source`-Switch zusätzliche Feeds angeben.</span><span class="sxs-lookup"><span data-stu-id="b0979-186">You can alter feeds with `nuget.config`, request a specific `nuget.config` file, or specify additional feeds with the `--add-source` switch.</span></span> <span data-ttu-id="b0979-187">NuGet löst standardmäßig für jeden Feed, auf den nicht zugegriffen werden kann, einen Fehler aus.</span><span class="sxs-lookup"><span data-stu-id="b0979-187">By default, NuGet throws an error for any feed that can't connect.</span></span> <span data-ttu-id="b0979-188">Mit dem `--ignore-failed-sources`-Flag können diese nicht erreichbaren Quellen übersprungen werden.</span><span class="sxs-lookup"><span data-stu-id="b0979-188">The flag `--ignore-failed-sources` can skip these non-reachable sources.</span></span>

### <a name="package-id-incorrect"></a><span data-ttu-id="b0979-189">Paket-ID ist fehlerhaft</span><span class="sxs-lookup"><span data-stu-id="b0979-189">Package ID incorrect</span></span>

* <span data-ttu-id="b0979-190">Der Name des Tools wurde falsch eingegeben.</span><span class="sxs-lookup"><span data-stu-id="b0979-190">You mistyped the name of the tool.</span></span>

<span data-ttu-id="b0979-191">Eine häufige Ursache für Fehler ist ein fehlerhafter Toolname.</span><span class="sxs-lookup"><span data-stu-id="b0979-191">A common reason for failure is that the tool name isn't correct.</span></span> <span data-ttu-id="b0979-192">Ursache hierfür kann ein Tippfehler oder die Tatsache sein, dass das Tool verschoben wurde oder als veraltet gilt.</span><span class="sxs-lookup"><span data-stu-id="b0979-192">This can happen because of mistyping, or because the tool has moved or been deprecated.</span></span> <span data-ttu-id="b0979-193">Bei Tools auf NuGet.org können Sie sicherstellen, dass der Name stimmt, indem Sie unter NuGet.org nach dem Tool suchen und den Installationsbefehl kopieren.</span><span class="sxs-lookup"><span data-stu-id="b0979-193">For tools on NuGet.org, one way to ensure you have the name correct is to search for the tool at NuGet.org and copy the installation command.</span></span>

## <a name="see-also"></a><span data-ttu-id="b0979-194">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b0979-194">See also</span></span>

* [<span data-ttu-id="b0979-195">.NET Core-Tools</span><span class="sxs-lookup"><span data-stu-id="b0979-195">.NET Core tools</span></span>](global-tools.md)
