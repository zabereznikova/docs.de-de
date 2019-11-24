---
title: Behandlung von Problemen bei der Nutzung von .NET Core-Tools
description: Informieren Sie sich über allgemeine Probleme beim Ausführen von .NET Core-Tools sowie über mögliche Lösungen.
author: kdollard
ms.date: 09/23/2019
ms.openlocfilehash: df896405a122050acba220923eee58e87e0b75b6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "74282502"
---
# <a name="troubleshoot-net-core-tool-usage-issues"></a><span data-ttu-id="32b71-103">Behandlung von Problemen bei der Nutzung von .NET Core-Tools</span><span class="sxs-lookup"><span data-stu-id="32b71-103">Troubleshoot .NET Core tool usage issues</span></span>

<span data-ttu-id="32b71-104">Beim Installieren oder Ausführen eines globalen oder lokalen .NET Core-Tools können Probleme auftreten.</span><span class="sxs-lookup"><span data-stu-id="32b71-104">You might come across issues when trying to install or run a .NET Core tool, which can be a global tool or a local tool.</span></span> <span data-ttu-id="32b71-105">In diesem Artikel werden die allgemeinen Grundursachen und einige mögliche Lösungen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="32b71-105">This article describes the common root causes and some possible solutions.</span></span>

## <a name="installed-net-core-tool-fails-to-run"></a><span data-ttu-id="32b71-106">Ausführung eines installierten .NET Core-Tools schlägt fehl</span><span class="sxs-lookup"><span data-stu-id="32b71-106">Installed .NET Core tool fails to run</span></span>

<span data-ttu-id="32b71-107">Wenn die Ausführung eines .NET Core-Tools fehlschlägt, ist sehr wahrscheinlich eines der folgenden Probleme aufgetreten:</span><span class="sxs-lookup"><span data-stu-id="32b71-107">When a .NET Core tool fails to run, most likely you ran into one of the following issues:</span></span>

* <span data-ttu-id="32b71-108">Die ausführbare Datei für das Tool wurde nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="32b71-108">The executable file for the tool wasn't found.</span></span>
* <span data-ttu-id="32b71-109">Die richtige Version der .NET Core-Runtime wurde nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="32b71-109">The correct version of the .NET Core runtime wasn't found.</span></span>

### <a name="executable-file-not-found"></a><span data-ttu-id="32b71-110">Ausführbare Datei nicht gefunden</span><span class="sxs-lookup"><span data-stu-id="32b71-110">Executable file not found</span></span>

<span data-ttu-id="32b71-111">Wenn die ausführbare Datei nicht gefunden wird, wird eine Meldung angezeigt, die in etwa wie folgt lautet:</span><span class="sxs-lookup"><span data-stu-id="32b71-111">If the executable file isn't found, you'll see a message similar to the following:</span></span>

```console
Could not execute because the specified command or file was not found.
Possible reasons for this include:
  * You misspelled a built-in dotnet command.
  * You intended to execute a .NET Core program, but dotnet-xyz does not exist.
  * You intended to run a global tool, but a dotnet-prefixed executable with this name could not be found on the PATH.
```

<span data-ttu-id="32b71-112">Der Name der ausführbaren Datei bestimmt, wie Sie das Tool aufrufen.</span><span class="sxs-lookup"><span data-stu-id="32b71-112">The name of the executable determines how you invoke the tool.</span></span> <span data-ttu-id="32b71-113">Das Format wird in der folgenden Tabelle beschrieben:</span><span class="sxs-lookup"><span data-stu-id="32b71-113">The following table describes the format:</span></span>

| <span data-ttu-id="32b71-114">Format der ausführbaren Datei</span><span class="sxs-lookup"><span data-stu-id="32b71-114">Executable name format</span></span>  | <span data-ttu-id="32b71-115">Aufrufformat</span><span class="sxs-lookup"><span data-stu-id="32b71-115">Invocation format</span></span>   |
|-------------------------|---------------------|
| `dotnet-<toolName>.exe` | `dotnet <toolName>` |
| `<toolName>.exe`        | `<toolName>`        |

* <span data-ttu-id="32b71-116">Globale Tools</span><span class="sxs-lookup"><span data-stu-id="32b71-116">Global tools</span></span>

    <span data-ttu-id="32b71-117">Globale Tools können im Standardverzeichnis oder an einem spezifischen Speicherort installiert werden.</span><span class="sxs-lookup"><span data-stu-id="32b71-117">Global tools can be installed in the default directory or in a specific location.</span></span> <span data-ttu-id="32b71-118">Die Standardverzeichnisse sind:</span><span class="sxs-lookup"><span data-stu-id="32b71-118">The default directories are:</span></span>

    | <span data-ttu-id="32b71-119">Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="32b71-119">OS</span></span>          | <span data-ttu-id="32b71-120">Pfad</span><span class="sxs-lookup"><span data-stu-id="32b71-120">Path</span></span>                          |
    |-------------|-------------------------------|
    | <span data-ttu-id="32b71-121">Linux/macOS</span><span class="sxs-lookup"><span data-stu-id="32b71-121">Linux/macOS</span></span> | `$HOME/.dotnet/tools`         |
    | <span data-ttu-id="32b71-122">Windows</span><span class="sxs-lookup"><span data-stu-id="32b71-122">Windows</span></span>     | `%USERPROFILE%\.dotnet\tools` |

    <span data-ttu-id="32b71-123">Prüfen Sie beim Ausführen eines globalen Tools, ob die Umgebungsvariable `PATH` auf Ihrem Computer den Pfad enthält, unter dem Sie das globale Tool installiert haben, und ob sich die ausführbare Datei in diesem Verzeichnis befindet.</span><span class="sxs-lookup"><span data-stu-id="32b71-123">If you're trying to run a global tool, check that the `PATH` environment variable on your machine contains the path where you installed the global tool and that the executable is in that path.</span></span>

    <span data-ttu-id="32b71-124">Die .NET Core-CLI versucht bei der ersten Verwendung, die Standardspeicherorte der Umgebungsvariable „PATH“ hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="32b71-124">The .NET Core CLI tries to add the default locations to the PATH environment variable on its first usage.</span></span> <span data-ttu-id="32b71-125">Es gibt jedoch einige Szenarios, in denen der Speicherort der Variablen „PATH“ nicht automatisch hinzugefügt werden kann, sodass Sie „PATH“ bearbeiten müssen, um die Variable für folgende Fälle zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="32b71-125">However, there are a couple of scenarios where the location might not be added to PATH automatically, so you'll have to edit PATH to configure it for the following cases:</span></span>

  * <span data-ttu-id="32b71-126">Wenn Sie Linux verwenden und das .NET Core SDK mit *TAR.GZ*-Dateien anstelle von „apt-get“ oder „rpm“ installiert haben.</span><span class="sxs-lookup"><span data-stu-id="32b71-126">If you're using Linux and you've installed the .NET Core SDK using *.tar.gz* files and not apt-get or rpm.</span></span>
  * <span data-ttu-id="32b71-127">Wenn Sie macOS 10.15 „Catalina“ oder höhere Versionen verwenden.</span><span class="sxs-lookup"><span data-stu-id="32b71-127">If you're using macOS 10.15 "Catalina" or later versions.</span></span>
  * <span data-ttu-id="32b71-128">Wenn Sie macOS 10.14 „Mojave“ oder frühere Versionen verwenden und das .NET Core SDK mit *TAR.GZ*-Dateien statt mit *PKG*-Dateien installiert haben.</span><span class="sxs-lookup"><span data-stu-id="32b71-128">If you're using macOS 10.14 "Mojave" or earlier versions, and you've installed the .NET Core SDK using *.tar.gz* files and not *.pkg*.</span></span>
  * <span data-ttu-id="32b71-129">Wenn Sie das .NET Core 3.0 SDK installiert und die Umgebungsvariable `DOTNET_ADD_GLOBAL_TOOLS_TO_PATH` auf `false` festgelegt haben.</span><span class="sxs-lookup"><span data-stu-id="32b71-129">If you've installed the .NET Core 3.0 SDK and you've set the `DOTNET_ADD_GLOBAL_TOOLS_TO_PATH` environment variable to `false`.</span></span>
  * <span data-ttu-id="32b71-130">Wenn Sie .NET Core 2.2 SDK oder frühere Versionen installiert und die Umgebungsvariable `DOTNET_SKIP_FIRST_TIME_EXPERIENCE` auf `true` festgelegt haben.</span><span class="sxs-lookup"><span data-stu-id="32b71-130">If you've installed .NET Core 2.2 SDK or earlier versions, and you've set the `DOTNET_SKIP_FIRST_TIME_EXPERIENCE` environment variable to `true`.</span></span>

  <span data-ttu-id="32b71-131">Weitere Informationen über globale Tools finden Sie unter [Übersicht über globale .NET Core-Tools](global-tools.md).</span><span class="sxs-lookup"><span data-stu-id="32b71-131">For more information about global tools, see [.NET Core Global Tools overview](global-tools.md).</span></span>

* <span data-ttu-id="32b71-132">Lokale Tools</span><span class="sxs-lookup"><span data-stu-id="32b71-132">Local tools</span></span>

  <span data-ttu-id="32b71-133">Prüfen Sie beim Ausführen eines lokalen Tools, ob im aktuellen Verzeichnis oder in einem der übergeordneten Verzeichnisse eine Manifestdatei mit dem Namen *dotnet-tools.json* vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="32b71-133">If you're trying to run a local tool, verify that there's a manifest file called *dotnet-tools.json* in the current directory or any of its parent directories.</span></span> <span data-ttu-id="32b71-134">Diese Datei kann sich auch in einem Ordner mit dem Namen *CONFIG* in der Projektordnerhierarchie statt im Stammverzeichnis befinden.</span><span class="sxs-lookup"><span data-stu-id="32b71-134">This file can also live under a folder named *.config* anywhere in the project folder hierarchy, instead of the root folder.</span></span> <span data-ttu-id="32b71-135">Wenn *dotnet-tools.json* vorhanden ist, öffnen Sie die Datei und überprüfen Sie, ob das Tool enthalten ist, das Sie ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="32b71-135">If *dotnet-tools.json* exists, open it and check for the tool you're trying to run.</span></span> <span data-ttu-id="32b71-136">Wenn die Datei keinen Eintrag für `"isRoot": true` enthält, suchen Sie weiter oben in der Dateihierarchie nach weiteren Manifestdateien des Tools.</span><span class="sxs-lookup"><span data-stu-id="32b71-136">If the file doesn't contain an entry for `"isRoot": true`, then also check further up the file hierarchy for additional tool manifest files.</span></span>

  <span data-ttu-id="32b71-137">Beim Ausführen eines .NET Core-Tools, das mit einem angegebenen Pfad installiert wurde, müssen Sie bei Verwendung des Tools diesen Pfad angeben.</span><span class="sxs-lookup"><span data-stu-id="32b71-137">If you're trying to run a .NET Core tool that was installed with a specified path, you need to include that path when using the tool.</span></span> <span data-ttu-id="32b71-138">Beispiel für die Verwendung eines mit einem Toolpfad installierten Tools:</span><span class="sxs-lookup"><span data-stu-id="32b71-138">An example of using a tool-path installed tool is:</span></span>

  ```console
  ..\<toolDirectory>\dotnet-<toolName>
  ```

### <a name="runtime-not-found"></a><span data-ttu-id="32b71-139">Runtime nicht gefunden</span><span class="sxs-lookup"><span data-stu-id="32b71-139">Runtime not found</span></span>

<span data-ttu-id="32b71-140">.NET Core-Tools sind [Framework-abhängige Anwendungen](../deploying/index.md#framework-dependent-deployments-fdd), d. h. sie sind von der auf Ihrem Computer installierten .NET Core-Runtime abhängig.</span><span class="sxs-lookup"><span data-stu-id="32b71-140">.NET Core tools are [framework-dependent applications](../deploying/index.md#framework-dependent-deployments-fdd), which means they rely on a .NET Core runtime installed on your machine.</span></span> <span data-ttu-id="32b71-141">Wenn die erwartete Runtime nicht gefunden wurde, orientieren sie sich an den normalen Regeln für das Rollforward der .NET Core-Runtime, zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="32b71-141">If the expected runtime isn't found, they follow normal .NET Core runtime roll-forward rules such as:</span></span>

* <span data-ttu-id="32b71-142">Eine Anwendung wird auf das neueste Patchrelease der angegebenen Haupt- und Nebenversion gebracht.</span><span class="sxs-lookup"><span data-stu-id="32b71-142">An application rolls forward to the highest patch release of the specified major and minor version.</span></span>
* <span data-ttu-id="32b71-143">Wenn keine übereinstimmende Runtime mit einer übereinstimmenden Haupt- und Nebenversion vorhanden ist, wird die nächsthöhere Nebenversion verwendet.</span><span class="sxs-lookup"><span data-stu-id="32b71-143">If there's no matching runtime with a matching major and minor version number, the next higher minor version is used.</span></span>
* <span data-ttu-id="32b71-144">Ein Rollforward findet nicht zwischen Vorschauversionen der Runtime oder Vorschauversionen und Releaseversionen statt.</span><span class="sxs-lookup"><span data-stu-id="32b71-144">Roll forward doesn't occur between preview versions of the runtime or between preview versions and release versions.</span></span> <span data-ttu-id="32b71-145">Daher müssen .NET Core-Tools, die mit Vorschauversionen erstellt wurden, vom Autor neu erstellt, veröffentlicht und installiert werden.</span><span class="sxs-lookup"><span data-stu-id="32b71-145">So, .NET Core tools created using preview versions must be rebuilt and republished by the author and reinstalled.</span></span>

<span data-ttu-id="32b71-146">Rollforward findet in zwei gängigen Szenarios nicht standardmäßig statt:</span><span class="sxs-lookup"><span data-stu-id="32b71-146">Roll-forward won't occur by default in two common scenarios:</span></span>

* <span data-ttu-id="32b71-147">Es sind nur frühere Versionen der Runtime verfügbar.</span><span class="sxs-lookup"><span data-stu-id="32b71-147">Only lower versions of the runtime are available.</span></span> <span data-ttu-id="32b71-148">Beim Rollforward werden nur höhere Versionen der Runtime ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="32b71-148">Roll-forward only selects later versions of the runtime.</span></span>
* <span data-ttu-id="32b71-149">Es sind nur höhere Hauptversionen der Runtime verfügbar.</span><span class="sxs-lookup"><span data-stu-id="32b71-149">Only higher major versions of the runtime are available.</span></span> <span data-ttu-id="32b71-150">Mit dem Rollforward werden die Grenzen von Hauptversionen nicht überschritten.</span><span class="sxs-lookup"><span data-stu-id="32b71-150">Roll-forward doesn't cross major version boundaries.</span></span>

<span data-ttu-id="32b71-151">Wenn eine Anwendung keine entsprechende Runtime finden kann, schlägt die Ausführung fehl, und ein Fehler wird gemeldet.</span><span class="sxs-lookup"><span data-stu-id="32b71-151">If an application can't find an appropriate runtime, it fails to run and reports an error.</span></span>

<span data-ttu-id="32b71-152">Sie können die auf Ihrem Computer installierten .NET Core-Runtimes mit einem der folgenden Befehle anzeigen:</span><span class="sxs-lookup"><span data-stu-id="32b71-152">You can find out which .NET Core runtimes are installed on your machine using one of the following commands:</span></span>

```dotnetcli
dotnet --list-runtimes
dotnet --info
```

<span data-ttu-id="32b71-153">Wenn Sie der Meinung sind, dass das Tool die von Ihnen installierte Runtimeversion unterstützen sollte, können Sie den Autor des Tools fragen, ob er die Versionsnummer aktualisieren oder mehrere Ziele zuweisen kann.</span><span class="sxs-lookup"><span data-stu-id="32b71-153">If you think the tool should support the runtime version you currently have installed, you can contact the tool author and see if they can update the version number or multi-target.</span></span> <span data-ttu-id="32b71-154">Nachdem das Toolpaket erneut kompiliert und auf NuGet mit einer aktualisierten Versionsnummer veröffentlicht wurde, können Sie Ihre Kopie aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="32b71-154">Once they've recompiled and republished their tool package to NuGet with an updated version number, you can update your copy.</span></span> <span data-ttu-id="32b71-155">Bis dies geschehen ist, können Sie eine Version der Runtime installieren, die mit dem gewünschten Tool verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="32b71-155">While that doesn't happen, the quickest solution for you is to install a version of the runtime that would work with the tool you're trying to run.</span></span> <span data-ttu-id="32b71-156">Wenn Sie eine bestimmte .NET Core-Runtimeversion herunterladen möchten, besuchen Sie die [.NET Core-Downloadseite](https://dotnet.microsoft.com/download/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="32b71-156">To download a specific .NET Core runtime version, visit the [.NET Core download page](https://dotnet.microsoft.com/download/dotnet-core).</span></span>

<span data-ttu-id="32b71-157">Wenn Sie das .NET Core SDK an einem nicht standardmäßigen Speicherort installieren, müssen Sie die Umgebungsvariable `DOTNET_ROOT` auf das Verzeichnis festlegen, das die ausführbare Datei `dotnet` enthält.</span><span class="sxs-lookup"><span data-stu-id="32b71-157">If you install the .NET Core SDK to a non-default location, you need to set the environment variable `DOTNET_ROOT` to the directory that contains the `dotnet` executable.</span></span>

## <a name="net-core-tool-installation-fails"></a><span data-ttu-id="32b71-158">Fehler bei der Installation von .NET Core-Tools</span><span class="sxs-lookup"><span data-stu-id="32b71-158">.NET Core tool installation fails</span></span>

<span data-ttu-id="32b71-159">Es gibt verschiedene Gründe, warum bei der Installation eines globalen oder lokalen .NET Core-Tools möglicherweise ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="32b71-159">There are a number of reasons the installation of a .NET Core global or local tool may fail.</span></span> <span data-ttu-id="32b71-160">Wenn bei der Installation eines Tools ein Fehler auftritt, wird eine Meldung angezeigt, die in etwa wie folgt lautet:</span><span class="sxs-lookup"><span data-stu-id="32b71-160">When the tool installation fails, you'll see a message similar to following one:</span></span>

```console
Tool '{0}' failed to install. This failure may have been caused by:

* You are attempting to install a preview release and did not use the --version option to specify the version.
* A package by this name was found, but it was not a .NET Core tool.
* The required NuGet feed cannot be accessed, perhaps because of an Internet connection problem.
* You mistyped the name of the tool.

For more reasons, including package naming enforcement, visit https://aka.ms/failure-installing-tool
```

<span data-ttu-id="32b71-161">Um diese Fehler zu diagnostizieren, werden dem Benutzer neben der vorherigen Meldung auch NuGet-Meldungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="32b71-161">To help diagnose these failures, NuGet messages are shown directly to the user, along with the previous message.</span></span> <span data-ttu-id="32b71-162">Mithilfe der NuGet-Meldung können Sie das Problem möglicherweise identifizieren.</span><span class="sxs-lookup"><span data-stu-id="32b71-162">The NuGet message may help you identify the problem.</span></span>

### <a name="package-naming-enforcement"></a><span data-ttu-id="32b71-163">Durchsetzung der Paketbenennung</span><span class="sxs-lookup"><span data-stu-id="32b71-163">Package naming enforcement</span></span>

<span data-ttu-id="32b71-164">Microsoft hat den Leitfaden zur Paket-ID für Tools geändert, was dazu führt, dass eine Reihe von Tools mit dem vorhergesagten Namen nicht gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="32b71-164">Microsoft has changed its guidance on the Package ID for tools, resulting in a number of tools not being found with the predicted name.</span></span> <span data-ttu-id="32b71-165">Der neue Leitfaden besagt, dass alle Microsoft-Tools das Präfix „Microsoft.“ enthalten müssen.</span><span class="sxs-lookup"><span data-stu-id="32b71-165">The new guidance is that all Microsoft tools be prefixed with "Microsoft."</span></span> <span data-ttu-id="32b71-166">Dieses Präfix ist reserviert und kann nur für Pakete verwendet werden, die mit einem autorisierten Microsoft-Zertifikat signiert sind.</span><span class="sxs-lookup"><span data-stu-id="32b71-166">This prefix is reserved and can only be used for packages signed with a Microsoft authorized certificate.</span></span>

<span data-ttu-id="32b71-167">In der Übergangszeit haben einige Microsoft-Tools die alte Form der Paket-ID, während andere die neue Form aufweisen:</span><span class="sxs-lookup"><span data-stu-id="32b71-167">During the transition, some Microsoft tools will have the old form of the package ID, while others will have the new form:</span></span>

```dotnetcli
dotnet tool install -g Microsoft.<toolName>
dotnet tool install -g <toolName>
```

<span data-ttu-id="32b71-168">Bei aktualisierten Paket-IDs müssen Sie zum Abrufen der aktuellen Updates die neue Paket-ID verwenden.</span><span class="sxs-lookup"><span data-stu-id="32b71-168">As package IDs are updated, you'll need to change to the new package ID to get the latest updates.</span></span> <span data-ttu-id="32b71-169">Pakete mit dem vereinfachten Toolnamen gelten als veraltet.</span><span class="sxs-lookup"><span data-stu-id="32b71-169">Packages with the simplified tool name will be deprecated.</span></span>

### <a name="preview-releases"></a><span data-ttu-id="32b71-170">Vorschaureleases</span><span class="sxs-lookup"><span data-stu-id="32b71-170">Preview releases</span></span>

* <span data-ttu-id="32b71-171">Beim Installieren eines Vorschaureleases geben Sie die Version ohne die `--version`-Option an.</span><span class="sxs-lookup"><span data-stu-id="32b71-171">You're attempting to install a preview release and didn't use the `--version` option to specify the version.</span></span>

<span data-ttu-id="32b71-172">.NET Core-Tools, die in einer Vorschauversion vorliegen, müssen zur Kennzeichnung dieses Umstands mit einem Teil des Namens angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="32b71-172">.NET Core tools that are in preview must be specified with a portion of the name to indicate that they are in preview.</span></span> <span data-ttu-id="32b71-173">Dabei müssen Sie nicht die gesamte Vorschauversion angeben.</span><span class="sxs-lookup"><span data-stu-id="32b71-173">You don't need to include the entire preview.</span></span> <span data-ttu-id="32b71-174">Sofern die Versionsnummern im erwarteten Format vorliegen, können Sie das folgende Beispiel oder Ähnliches verwenden:</span><span class="sxs-lookup"><span data-stu-id="32b71-174">Assuming the version numbers are in the expected format, you can use something like the following example:</span></span>

```dotnetcli
dotnet tool install -g --version 1.1.0-pre <toolName>
```

> [!NOTE]
> <span data-ttu-id="32b71-175">Zur Vereinfachung plant das Team für die .NET Core-CLI die Ergänzung durch einen `--preview`-Switch in einem kommenden Release.</span><span class="sxs-lookup"><span data-stu-id="32b71-175">The .NET Core CLI team is planning to add a `--preview` switch in a future release to make this easier.</span></span>

### <a name="package-isnt-a-net-core-tool"></a><span data-ttu-id="32b71-176">Das Paket ist kein .NET Core-Tool</span><span class="sxs-lookup"><span data-stu-id="32b71-176">Package isn't a .NET Core tool</span></span>

* <span data-ttu-id="32b71-177">Es wurde ein NuGet-Paket mit diesem Namen gefunden. Dabei handelt es sich jedoch nicht um ein .NET Core-Tool.</span><span class="sxs-lookup"><span data-stu-id="32b71-177">A NuGet package by this name was found, but it wasn't a .NET Core tool.</span></span>

<span data-ttu-id="32b71-178">Wenn Sie ein NuGet-Paket installieren, bei dem es sich nicht um ein .NET Core-Tool, sondern um ein normales NuGet-Paket handelt, wird eine Fehlermeldung angezeigt, die in etwa wie folgt lautet:</span><span class="sxs-lookup"><span data-stu-id="32b71-178">If you try to install a NuGet package that is a regular NuGet package and not a .NET Core tool, you'll see an error similar to the following:</span></span>

> <span data-ttu-id="32b71-179">NU1212: Ungültige Projekt-/Paket-Kombination für `<ToolName>`.</span><span class="sxs-lookup"><span data-stu-id="32b71-179">NU1212: Invalid project-package combination for `<ToolName>`.</span></span> <span data-ttu-id="32b71-180">Der DotnetToolReference-Projektstil darf nur Verweise vom Typ „DotnetTool“ enthalten.</span><span class="sxs-lookup"><span data-stu-id="32b71-180">DotnetToolReference project style can only contain references of the DotnetTool type.</span></span>

### <a name="nuget-feed-cant-be-accessed"></a><span data-ttu-id="32b71-181">Auf den NuGet-Feed kann nicht zugegriffen werden</span><span class="sxs-lookup"><span data-stu-id="32b71-181">NuGet feed can't be accessed</span></span>

* <span data-ttu-id="32b71-182">Auf den erforderlichen NuGet-Feed kann möglicherweise aufgrund eines Problems mit der Internetverbindung nicht zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="32b71-182">The required NuGet feed can't be accessed, perhaps because of an Internet connection problem.</span></span>

<span data-ttu-id="32b71-183">Für die Installation des Tools muss jedoch auf den NuGet-Feed zugegriffen werden, der das Toolpaket enthält.</span><span class="sxs-lookup"><span data-stu-id="32b71-183">Tool installation requires access to the NuGet feed that contains the tool package.</span></span> <span data-ttu-id="32b71-184">Ist dies nicht möglich, schlägt die Installation fehl.</span><span class="sxs-lookup"><span data-stu-id="32b71-184">It fails if the feed isn't available.</span></span> <span data-ttu-id="32b71-185">Sie können Feeds mit `nuget.config` ändern, eine bestimmte `nuget.config`-Datei anfordern oder mit dem `--add-source`-Switch zusätzliche Feeds angeben.</span><span class="sxs-lookup"><span data-stu-id="32b71-185">You can alter feeds with `nuget.config`, request a specific `nuget.config` file, or specify additional feeds with the `--add-source` switch.</span></span> <span data-ttu-id="32b71-186">NuGet löst standardmäßig für jeden Feed, auf den nicht zugegriffen werden kann, einen Fehler aus.</span><span class="sxs-lookup"><span data-stu-id="32b71-186">By default, NuGet throws an error for any feed that can't connect.</span></span> <span data-ttu-id="32b71-187">Mit dem `--ignore-failed-sources`-Flag können diese nicht erreichbaren Quellen übersprungen werden.</span><span class="sxs-lookup"><span data-stu-id="32b71-187">The flag `--ignore-failed-sources` can skip these non-reachable sources.</span></span>

### <a name="package-id-incorrect"></a><span data-ttu-id="32b71-188">Paket-ID ist fehlerhaft</span><span class="sxs-lookup"><span data-stu-id="32b71-188">Package ID incorrect</span></span>

* <span data-ttu-id="32b71-189">Der Name des Tools wurde falsch eingegeben.</span><span class="sxs-lookup"><span data-stu-id="32b71-189">You mistyped the name of the tool.</span></span>

<span data-ttu-id="32b71-190">Eine häufige Ursache für Fehler ist ein fehlerhafter Toolname.</span><span class="sxs-lookup"><span data-stu-id="32b71-190">A common reason for failure is that the tool name isn't correct.</span></span> <span data-ttu-id="32b71-191">Ursache hierfür kann ein Tippfehler oder die Tatsache sein, dass das Tool verschoben wurde oder als veraltet gilt.</span><span class="sxs-lookup"><span data-stu-id="32b71-191">This can happen because of mistyping, or because the tool has moved or been deprecated.</span></span> <span data-ttu-id="32b71-192">Bei Tools auf NuGet.org können Sie sicherstellen, dass der Name stimmt, indem Sie unter NuGet.org nach dem Tool suchen und den Installationsbefehl kopieren.</span><span class="sxs-lookup"><span data-stu-id="32b71-192">For tools on NuGet.org, one way to ensure you have the name correct is to search for the tool at NuGet.org and copy the installation command.</span></span>

## <a name="see-also"></a><span data-ttu-id="32b71-193">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="32b71-193">See also</span></span>

* [<span data-ttu-id="32b71-194">Übersicht über globale .NET Core-Tools</span><span class="sxs-lookup"><span data-stu-id="32b71-194">.NET Core Global Tools overview</span></span>](global-tools.md)
