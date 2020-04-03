---
title: dotnet-Befehl
description: Erfahren Sie mehr über den dotnet-Befehl (den generischen Treiber für die .NET Core-CLI) und dessen Verwendung.
ms.date: 02/13/2020
ms.openlocfilehash: 8692d419afd528bf49e1dc7dc1a7a5fd698b363b
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2020
ms.locfileid: "80134076"
---
# <a name="dotnet-command"></a><span data-ttu-id="1c70c-103">dotnet-Befehl</span><span class="sxs-lookup"><span data-stu-id="1c70c-103">dotnet command</span></span>

<span data-ttu-id="1c70c-104">**Dieser Artikel gilt für:** ✔️ .NET Core 2.1 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="1c70c-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="1c70c-105">name</span><span class="sxs-lookup"><span data-stu-id="1c70c-105">Name</span></span>

<span data-ttu-id="1c70c-106">`dotnet`: Der generische Treiber für die .NET Core-CLI.</span><span class="sxs-lookup"><span data-stu-id="1c70c-106">`dotnet` - The generic driver for the .NET Core CLI.</span></span>

## <a name="synopsis"></a><span data-ttu-id="1c70c-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="1c70c-107">Synopsis</span></span>

<span data-ttu-id="1c70c-108">So erhalten Sie Informationen über die verfügbaren Befehle und die Umgebung</span><span class="sxs-lookup"><span data-stu-id="1c70c-108">To get information about the available commands and the environment:</span></span>

```dotnetcli
dotnet [-h|--help] [--version] [--info]
    [--list-runtimes] [--list-sdks]
```

<span data-ttu-id="1c70c-109">So führen Sie einen Befehl aus (erfordert eine SDK-Installation)</span><span class="sxs-lookup"><span data-stu-id="1c70c-109">To run a command (requires SDK installation):</span></span>

```dotnetcli
dotnet <COMMAND> [-d|--diagnostics] [-h|--help] [--verbosity]
    [command-options] [arguments]
```

<span data-ttu-id="1c70c-110">So führen Sie eine Anwendung aus</span><span class="sxs-lookup"><span data-stu-id="1c70c-110">To run an application:</span></span>

```dotnetcli
dotnet [--additionalprobingpath] [--additional-deps]
    [--fx-version]  [--roll-forward]
    <PATH_TO_APPLICATION> [arguments]

dotnet exec [--additionalprobingpath] [--additional-deps]
    [--fx-version]  [--roll-forward]
    <PATH_TO_APPLICATION> [arguments]
```

<span data-ttu-id="1c70c-111">`--roll-forward` ist seit .NET Core 3.x verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1c70c-111">`--roll-forward` is available since .NET Core 3.x.</span></span> <span data-ttu-id="1c70c-112">Verwenden Sie `--roll-forward-on-no-candidate-fx` für .NET Core 2.x.</span><span class="sxs-lookup"><span data-stu-id="1c70c-112">Use `--roll-forward-on-no-candidate-fx` for .NET Core 2.x.</span></span>

## <a name="description"></a><span data-ttu-id="1c70c-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1c70c-113">Description</span></span>

<span data-ttu-id="1c70c-114">Der Befehl `dotnet` hat zwei Funktionen:</span><span class="sxs-lookup"><span data-stu-id="1c70c-114">The `dotnet` command has two functions:</span></span>

- <span data-ttu-id="1c70c-115">Es stellt Befehle für die Arbeit mit .NET Core-Projekten bereit.</span><span class="sxs-lookup"><span data-stu-id="1c70c-115">It provides commands for working with .NET Core projects.</span></span>

  <span data-ttu-id="1c70c-116">Beispielsweise erstellt [`dotnet build`](dotnet-build.md) ein Projekt.</span><span class="sxs-lookup"><span data-stu-id="1c70c-116">For example, [`dotnet build`](dotnet-build.md) builds a project.</span></span> <span data-ttu-id="1c70c-117">Jeder Befehl definiert seine eigenen Optionen und Argumente.</span><span class="sxs-lookup"><span data-stu-id="1c70c-117">Each command defines its own options and arguments.</span></span> <span data-ttu-id="1c70c-118">Alle Befehle unterstützen die Option `--help` zum Ausdrucken einer kurzen Dokumentation über die Verwendung des Befehls.</span><span class="sxs-lookup"><span data-stu-id="1c70c-118">All commands support the `--help` option for printing out brief documentation about how to use the command.</span></span>

- <span data-ttu-id="1c70c-119">Sie führt .NET Core-Anwendungen aus.</span><span class="sxs-lookup"><span data-stu-id="1c70c-119">It runs .NET Core applications.</span></span>

  <span data-ttu-id="1c70c-120">Sie geben den Pfad zu einer `.dll`-Datei einer Anwendung zur Ausführung der Anwendung an.</span><span class="sxs-lookup"><span data-stu-id="1c70c-120">You specify the path to an application `.dll` file to run the application.</span></span> <span data-ttu-id="1c70c-121">Beispiel: `dotnet myapp.dll` führt die Anwendung `myapp` aus.</span><span class="sxs-lookup"><span data-stu-id="1c70c-121">For example, `dotnet myapp.dll` runs the `myapp` application.</span></span> <span data-ttu-id="1c70c-122">Weitere Informationen über Bereitstellungsoptionen finden Sie unter [.NET Core-Anwendungsbereitstellung](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="1c70c-122">See [.NET Core application deployment](../deploying/index.md) to learn about deployment options.</span></span>

## <a name="options"></a><span data-ttu-id="1c70c-123">Optionen</span><span class="sxs-lookup"><span data-stu-id="1c70c-123">Options</span></span>

<span data-ttu-id="1c70c-124">Es gibt verschiedene Optionen für `dotnet` allein, für die Ausführung eines Befehls und für die Ausführung einer Anwendung.</span><span class="sxs-lookup"><span data-stu-id="1c70c-124">Different options are available for `dotnet` by itself, for running a command, and for running an application.</span></span>

### <a name="options-for-dotnet-by-itself"></a><span data-ttu-id="1c70c-125">Optionen für dotnet</span><span class="sxs-lookup"><span data-stu-id="1c70c-125">Options for dotnet by itself</span></span>

<span data-ttu-id="1c70c-126">Die folgenden Optionen gelten für `dotnet` allein.</span><span class="sxs-lookup"><span data-stu-id="1c70c-126">The following options are for `dotnet` by itself.</span></span> <span data-ttu-id="1c70c-127">Beispielsweise `dotnet --info`.</span><span class="sxs-lookup"><span data-stu-id="1c70c-127">For example, `dotnet --info`.</span></span> <span data-ttu-id="1c70c-128">Sie drucken Informationen über die Umgebung aus.</span><span class="sxs-lookup"><span data-stu-id="1c70c-128">They print out information about the environment.</span></span>

- **`--info`**

  <span data-ttu-id="1c70c-129">Gibt ausführliche Informationen über eine .NET Core-Installation und die Computerumgebung aus, z.B. das aktuelle Betriebssystem und den Commit-SHA für die .NET Core-Version.</span><span class="sxs-lookup"><span data-stu-id="1c70c-129">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

- **`--version`**

  <span data-ttu-id="1c70c-130">Druckt die Version des verwendeten .NET Core-SDK aus.</span><span class="sxs-lookup"><span data-stu-id="1c70c-130">Prints out the version of the .NET Core SDK in use.</span></span>

- **`--list-runtimes`**

  <span data-ttu-id="1c70c-131">Druckt eine Liste der installierten .NET Core-Runtimes aus.</span><span class="sxs-lookup"><span data-stu-id="1c70c-131">Prints out a list of the installed .NET Core runtimes.</span></span>

- **`--list-sdks`**

  <span data-ttu-id="1c70c-132">Druckt eine Liste der installierten .NET Core-SDKs aus.</span><span class="sxs-lookup"><span data-stu-id="1c70c-132">Prints out a list of the installed .NET Core SDKs.</span></span>

- **`-h|--help`**

  <span data-ttu-id="1c70c-133">Druckt eine Liste der verfügbaren Befehle aus.</span><span class="sxs-lookup"><span data-stu-id="1c70c-133">Prints out a list of available commands.</span></span>

### <a name="sdk-options-for-running-a-command"></a><span data-ttu-id="1c70c-134">SDK-Optionen zum Ausführen eines Befehls</span><span class="sxs-lookup"><span data-stu-id="1c70c-134">SDK options for running a command</span></span>

<span data-ttu-id="1c70c-135">Die folgenden Optionen gelten für `dotnet` mit einem Befehl.</span><span class="sxs-lookup"><span data-stu-id="1c70c-135">The following options are for `dotnet` with a command.</span></span> <span data-ttu-id="1c70c-136">Beispielsweise `dotnet build --help`.</span><span class="sxs-lookup"><span data-stu-id="1c70c-136">For example, `dotnet build --help`.</span></span>

- **`-d|--diagnostics`**

  <span data-ttu-id="1c70c-137">Ermöglicht die diagnostische Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="1c70c-137">Enables diagnostic output.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="1c70c-138">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="1c70c-138">Sets the verbosity level of the command.</span></span> <span data-ttu-id="1c70c-139">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="1c70c-139">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="1c70c-140">Nicht in jedem Befehl unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1c70c-140">Not supported in every command.</span></span> <span data-ttu-id="1c70c-141">Auf der Seite der einzelnen Befehle finden Sie heraus, ob diese Option verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="1c70c-141">See specific command page to determine if this option is available.</span></span>

- **`-h|--help`**

  <span data-ttu-id="1c70c-142">Gibt Dokumentation für einen bestimmten Befehl aus, z.B. `dotnet build --help`.</span><span class="sxs-lookup"><span data-stu-id="1c70c-142">Prints out documentation for a given command, such as `dotnet build --help`.</span></span>

- **`command options`**

  <span data-ttu-id="1c70c-143">Jeder Befehl definiert Optionen, die für diesen Befehl spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="1c70c-143">Each command defines options specific to that command.</span></span> <span data-ttu-id="1c70c-144">Eine Liste der verfügbaren Optionen finden Sie auf einer speziellen Befehlsseite.</span><span class="sxs-lookup"><span data-stu-id="1c70c-144">See specific command page for a list of available options.</span></span>

### <a name="runtime-options"></a><span data-ttu-id="1c70c-145">Laufzeitoptionen</span><span class="sxs-lookup"><span data-stu-id="1c70c-145">Runtime options</span></span>

<span data-ttu-id="1c70c-146">Die folgenden Optionen sind verfügbar, wenn `dotnet` eine Anwendung ausführt.</span><span class="sxs-lookup"><span data-stu-id="1c70c-146">The following options are available when `dotnet` runs an application.</span></span> <span data-ttu-id="1c70c-147">Beispielsweise `dotnet myapp.dll --fx-version 3.1.1`.</span><span class="sxs-lookup"><span data-stu-id="1c70c-147">For example, `dotnet myapp.dll --fx-version 3.1.1`.</span></span>

- **`--additionalprobingpath <PATH>`**

  <span data-ttu-id="1c70c-148">Pfad, der die Suchrichtlinie und die zu suchenden Assemblys enthält.</span><span class="sxs-lookup"><span data-stu-id="1c70c-148">Path containing probing policy and assemblies to probe.</span></span>

- **`--additional-deps <PATH>`**

  <span data-ttu-id="1c70c-149">Pfad zu einer zusätzlichen *.deps.json*-Datei.</span><span class="sxs-lookup"><span data-stu-id="1c70c-149">Path to an additional *.deps.json* file.</span></span> <span data-ttu-id="1c70c-150">Eine *deps.json*-Datei enthält eine Liste mit Abhängigkeiten, Kompilierungsabhängigkeiten und Versionsinformationen, die verwendet werden, um Assemblykonflikte zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="1c70c-150">A *deps.json* file contains a list of dependencies, compilation dependencies, and version information used to address assembly conflicts.</span></span> <span data-ttu-id="1c70c-151">Weitere Informationen finden Sie auf GitHub unter [Laufzeitkonfigurationsdateien](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="1c70c-151">For more information, see [Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) on GitHub.</span></span>

- **`--fx-version <VERSION>`**

  <span data-ttu-id="1c70c-152">Version der .NET Core-Runtime, die zum Ausführen der Anwendung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="1c70c-152">Version of the .NET Core runtime to use to run the application.</span></span>

- **`--runtimeconfig`**

  <span data-ttu-id="1c70c-153">Der Pfad zu einer *runtimeconfig.json*-Datei.</span><span class="sxs-lookup"><span data-stu-id="1c70c-153">Path to a *runtimeconfig.json* file.</span></span> <span data-ttu-id="1c70c-154">Eine *runtimeconfig.json*-Datei ist eine Konfigurationsdatei mit Einstellungen für die Runtime.</span><span class="sxs-lookup"><span data-stu-id="1c70c-154">A *runtimeconfig.json* file is a configuration file that contains run-time settings.</span></span> <span data-ttu-id="1c70c-155">Weitere Informationen finden Sie unter [Konfigurationseinstellungen für die .NET Core-Runtime](../run-time-config/index.md#runtimeconfigjson).</span><span class="sxs-lookup"><span data-stu-id="1c70c-155">For more information, see [.NET Core run-time configuration settings](../run-time-config/index.md#runtimeconfigjson).</span></span>

- <span data-ttu-id="1c70c-156">**`--roll-forward-on-no-candidate-fx <N>`** **Verfügbar im .NET Core 2.x SDK.**</span><span class="sxs-lookup"><span data-stu-id="1c70c-156">**`--roll-forward-on-no-candidate-fx <N>`** **Available in .NET Core 2.x SDK.**</span></span>

  <span data-ttu-id="1c70c-157">Definiert ein Verhalten, wenn das erforderliche freigegebene Framework nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="1c70c-157">Defines behavior when the required shared framework is not available.</span></span> <span data-ttu-id="1c70c-158">`N` kann Folgendes sein:</span><span class="sxs-lookup"><span data-stu-id="1c70c-158">`N` can be:</span></span>

  - <span data-ttu-id="1c70c-159">`0` - Das Ausführen von Rollforward ist auch für die Nebenversion deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="1c70c-159">`0` - Disable even minor version roll forward.</span></span>
  - <span data-ttu-id="1c70c-160">`1` - Rollforward wird in der Nebenversion, nicht aber in der Hauptversion, ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="1c70c-160">`1` - Roll forward on minor version, but not on major version.</span></span> <span data-ttu-id="1c70c-161">Dies ist das Standardverhalten.</span><span class="sxs-lookup"><span data-stu-id="1c70c-161">This is the default behavior.</span></span>
  - <span data-ttu-id="1c70c-162">`2` - Rollforward wird in Neben- und Hauptversionen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="1c70c-162">`2` - Roll forward on minor and major versions.</span></span>

   <span data-ttu-id="1c70c-163">Weitere Informationen finden Sie unter [Rollforward](../whats-new/dotnet-core-2-1.md#roll-forward).</span><span class="sxs-lookup"><span data-stu-id="1c70c-163">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

- <span data-ttu-id="1c70c-164">**`--roll-forward <SETTING>`** **Verfügbar ab .NET Core SDK 3.0.**</span><span class="sxs-lookup"><span data-stu-id="1c70c-164">**`--roll-forward <SETTING>`** **Available starting with .NET Core SDK 3.0.**</span></span>

  <span data-ttu-id="1c70c-165">Steuert, wie der Rollforward auf die App angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="1c70c-165">Controls how roll forward is applied to the app.</span></span> <span data-ttu-id="1c70c-166">`SETTING` kann einer der folgenden Werte sein.</span><span class="sxs-lookup"><span data-stu-id="1c70c-166">The `SETTING` can be one of the following values.</span></span> <span data-ttu-id="1c70c-167">Wenn nichts anderes angegeben wird, wird als Standard `Minor` verwendet.</span><span class="sxs-lookup"><span data-stu-id="1c70c-167">If not specified, `Minor` is the default.</span></span>

  - <span data-ttu-id="1c70c-168">`LatestPatch`: Rollforward zur höchsten Patchversion.</span><span class="sxs-lookup"><span data-stu-id="1c70c-168">`LatestPatch` - Roll forward to the highest patch version.</span></span> <span data-ttu-id="1c70c-169">Dies deaktiviert ein Rollforward zur Nebenversion.</span><span class="sxs-lookup"><span data-stu-id="1c70c-169">This disables minor version roll forward.</span></span>
  - <span data-ttu-id="1c70c-170">`Minor`: Rollforward zur niedrigsten höheren Nebenversion, wenn die angeforderte Nebenversion nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="1c70c-170">`Minor` - Roll forward to the lowest higher minor version, if requested minor version is missing.</span></span> <span data-ttu-id="1c70c-171">Wenn die angeforderte Nebenversion vorhanden ist, wird die LatestPatch-Richtlinie verwendet.</span><span class="sxs-lookup"><span data-stu-id="1c70c-171">If the requested minor version is present, then the LatestPatch policy is used.</span></span>
  - <span data-ttu-id="1c70c-172">`Major`: Rollforward zur niedrigsten höheren Hauptversion – und niedrigsten Nebenversion, wenn die angeforderte Hauptversion nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="1c70c-172">`Major` - Roll forward to lowest higher major version, and lowest minor version, if requested major version is missing.</span></span> <span data-ttu-id="1c70c-173">Wenn die angeforderte Hauptversion vorhanden ist, wird die Minor-Richtlinie verwendet.</span><span class="sxs-lookup"><span data-stu-id="1c70c-173">If the requested major version is present, then the Minor policy is used.</span></span>
  - <span data-ttu-id="1c70c-174">`LatestMinor`: Rollforward zur höchsten Nebenversion – auch dann, wenn die angeforderte Nebenversion vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="1c70c-174">`LatestMinor` - Roll forward to highest minor version, even if requested minor version is present.</span></span> <span data-ttu-id="1c70c-175">Für Komponentenhostingszenarien vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="1c70c-175">Intended for component hosting scenarios.</span></span>
  - <span data-ttu-id="1c70c-176">`LatestMajor`: Rollforward zur höchsten Hauptversion und höchsten Nebenversion – auch dann, wenn die angeforderte Hauptversion vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="1c70c-176">`LatestMajor` - Roll forward to highest major and highest minor version, even if requested major is present.</span></span> <span data-ttu-id="1c70c-177">Für Komponentenhostingszenarien vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="1c70c-177">Intended for component hosting scenarios.</span></span>
  - <span data-ttu-id="1c70c-178">`Disable`: Kein Rollforward.</span><span class="sxs-lookup"><span data-stu-id="1c70c-178">`Disable` - Don't roll forward.</span></span> <span data-ttu-id="1c70c-179">Nur Binden an angegebene Version.</span><span class="sxs-lookup"><span data-stu-id="1c70c-179">Only bind to specified version.</span></span> <span data-ttu-id="1c70c-180">Diese Richtlinie wird nicht zur allgemeinen Verwendung empfohlen, da sie die Möglichkeit eines Rollforwards zu den neuesten Patches ausschließt.</span><span class="sxs-lookup"><span data-stu-id="1c70c-180">This policy isn't recommended for general use because it disables the ability to roll forward to the latest patches.</span></span> <span data-ttu-id="1c70c-181">Dieser Wert wird nur zu Testzwecken empfohlen.</span><span class="sxs-lookup"><span data-stu-id="1c70c-181">This value is only recommended for testing.</span></span>

<span data-ttu-id="1c70c-182">Mit Ausnahme von `Disable` wird für alle Einstellungen die höchste verfügbare Patchversion verwendet.</span><span class="sxs-lookup"><span data-stu-id="1c70c-182">With the exception of `Disable`, all settings will use the highest available patch version.</span></span>

<span data-ttu-id="1c70c-183">Das Rollforwardverhalten kann auch in einer Projektdateieigenschaft, einer Runtime-Konfigurationsdateieigenschaft und einer Umgebungsvariablen konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="1c70c-183">Roll forward behavior can also be configured in a project file property, a run-time configuration file property, and an environment variable.</span></span> <span data-ttu-id="1c70c-184">Weitere Informationen finden Sie unter [Runtimerollforward der Hauptversion](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward).</span><span class="sxs-lookup"><span data-stu-id="1c70c-184">For more information, see [Major-version runtime roll forward](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward).</span></span>

## <a name="dotnet-commands"></a><span data-ttu-id="1c70c-185">dotnet-Befehle</span><span class="sxs-lookup"><span data-stu-id="1c70c-185">dotnet commands</span></span>

### <a name="general"></a><span data-ttu-id="1c70c-186">Allgemein</span><span class="sxs-lookup"><span data-stu-id="1c70c-186">General</span></span>

| <span data-ttu-id="1c70c-187">Befehl</span><span class="sxs-lookup"><span data-stu-id="1c70c-187">Command</span></span>                                       | <span data-ttu-id="1c70c-188">Funktion</span><span class="sxs-lookup"><span data-stu-id="1c70c-188">Function</span></span>                                                            |
| --------------------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="1c70c-189">dotnet build</span><span class="sxs-lookup"><span data-stu-id="1c70c-189">dotnet build</span></span>](dotnet-build.md)               | <span data-ttu-id="1c70c-190">Erstellt eine .NET Core-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="1c70c-190">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="1c70c-191">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="1c70c-191">dotnet build-server</span></span>](dotnet-build-server.md) | <span data-ttu-id="1c70c-192">Interagiert mit Servern, die von einem Build gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="1c70c-192">Interacts with servers started by a build.</span></span>                          |
| [<span data-ttu-id="1c70c-193">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="1c70c-193">dotnet clean</span></span>](dotnet-clean.md)               | <span data-ttu-id="1c70c-194">Bereinigen von Buildausgaben.</span><span class="sxs-lookup"><span data-stu-id="1c70c-194">Clean build outputs.</span></span>                                                |
| [<span data-ttu-id="1c70c-195">dotnet help</span><span class="sxs-lookup"><span data-stu-id="1c70c-195">dotnet help</span></span>](dotnet-help.md)                 | <span data-ttu-id="1c70c-196">Zeigt eine ausführlichere Onlinedokumentation für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="1c70c-196">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="1c70c-197">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="1c70c-197">dotnet migrate</span></span>](dotnet-migrate.md)           | <span data-ttu-id="1c70c-198">Migriert ein gültiges Preview 2-Projekt in ein .NET Core SDK 1.0-Projekt.</span><span class="sxs-lookup"><span data-stu-id="1c70c-198">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="1c70c-199">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="1c70c-199">dotnet msbuild</span></span>](dotnet-msbuild.md)           | <span data-ttu-id="1c70c-200">Ermöglicht den Zugriff auf die MSBuild-Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="1c70c-200">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="1c70c-201">dotnet new</span><span class="sxs-lookup"><span data-stu-id="1c70c-201">dotnet new</span></span>](dotnet-new.md)                   | <span data-ttu-id="1c70c-202">Initialisiert ein C#- oder F#-Projekt für eine bestimmte Vorlage.</span><span class="sxs-lookup"><span data-stu-id="1c70c-202">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="1c70c-203">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="1c70c-203">dotnet pack</span></span>](dotnet-pack.md)                 | <span data-ttu-id="1c70c-204">Erstellt ein NuGet-Paket aus Ihrem Code.</span><span class="sxs-lookup"><span data-stu-id="1c70c-204">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="1c70c-205">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="1c70c-205">dotnet publish</span></span>](dotnet-publish.md)           | <span data-ttu-id="1c70c-206">Veröffentlicht eine .NET Framework-abhängige oder eigenständige Anwendung.</span><span class="sxs-lookup"><span data-stu-id="1c70c-206">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="1c70c-207">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="1c70c-207">dotnet restore</span></span>](dotnet-restore.md)           | <span data-ttu-id="1c70c-208">Stellt die Abhängigkeiten für eine bestimmte Anwendung wieder her.</span><span class="sxs-lookup"><span data-stu-id="1c70c-208">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="1c70c-209">dotnet run</span><span class="sxs-lookup"><span data-stu-id="1c70c-209">dotnet run</span></span>](dotnet-run.md)                   | <span data-ttu-id="1c70c-210">Führt die Anwendung aus der Quelle aus.</span><span class="sxs-lookup"><span data-stu-id="1c70c-210">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="1c70c-211">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="1c70c-211">dotnet sln</span></span>](dotnet-sln.md)                   | <span data-ttu-id="1c70c-212">Optionen zum Hinzufügen, Entfernen und Listen von Projekten in einer Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="1c70c-212">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="1c70c-213">dotnet store</span><span class="sxs-lookup"><span data-stu-id="1c70c-213">dotnet store</span></span>](dotnet-store.md)               | <span data-ttu-id="1c70c-214">Speichert Assemblys im Laufzeitpaketspeicher.</span><span class="sxs-lookup"><span data-stu-id="1c70c-214">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="1c70c-215">dotnet test</span><span class="sxs-lookup"><span data-stu-id="1c70c-215">dotnet test</span></span>](dotnet-test.md)                 | <span data-ttu-id="1c70c-216">Führt Tests mit einem Test Runner aus.</span><span class="sxs-lookup"><span data-stu-id="1c70c-216">Runs tests using a test runner.</span></span>                                     |

### <a name="project-references"></a><span data-ttu-id="1c70c-217">Projektverweise</span><span class="sxs-lookup"><span data-stu-id="1c70c-217">Project references</span></span>

<span data-ttu-id="1c70c-218">Befehl</span><span class="sxs-lookup"><span data-stu-id="1c70c-218">Command</span></span> | <span data-ttu-id="1c70c-219">Funktion</span><span class="sxs-lookup"><span data-stu-id="1c70c-219">Function</span></span>
--- | ---
[<span data-ttu-id="1c70c-220">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="1c70c-220">dotnet add reference</span></span>](dotnet-add-reference.md) | <span data-ttu-id="1c70c-221">Fügt einen Projektverweis hinzu.</span><span class="sxs-lookup"><span data-stu-id="1c70c-221">Adds a project reference.</span></span>
[<span data-ttu-id="1c70c-222">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="1c70c-222">dotnet list reference</span></span>](dotnet-list-reference.md) | <span data-ttu-id="1c70c-223">Listet Projektverweise auf.</span><span class="sxs-lookup"><span data-stu-id="1c70c-223">Lists project references.</span></span>
[<span data-ttu-id="1c70c-224">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="1c70c-224">dotnet remove reference</span></span>](dotnet-remove-reference.md) | <span data-ttu-id="1c70c-225">Entfernt einen Projektverweis.</span><span class="sxs-lookup"><span data-stu-id="1c70c-225">Removes a project reference.</span></span>

### <a name="nuget-packages"></a><span data-ttu-id="1c70c-226">NuGet-Pakete</span><span class="sxs-lookup"><span data-stu-id="1c70c-226">NuGet packages</span></span>

<span data-ttu-id="1c70c-227">Befehl</span><span class="sxs-lookup"><span data-stu-id="1c70c-227">Command</span></span> | <span data-ttu-id="1c70c-228">Funktion</span><span class="sxs-lookup"><span data-stu-id="1c70c-228">Function</span></span>
--- | ---
[<span data-ttu-id="1c70c-229">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="1c70c-229">dotnet add package</span></span>](dotnet-add-package.md) | <span data-ttu-id="1c70c-230">Fügt ein NuGet-Paket hinzu.</span><span class="sxs-lookup"><span data-stu-id="1c70c-230">Adds a NuGet package.</span></span>
[<span data-ttu-id="1c70c-231">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="1c70c-231">dotnet remove package</span></span>](dotnet-remove-package.md) | <span data-ttu-id="1c70c-232">Entfernt ein NuGet-Paket.</span><span class="sxs-lookup"><span data-stu-id="1c70c-232">Removes a NuGet package.</span></span>

### <a name="nuget-commands"></a><span data-ttu-id="1c70c-233">NuGet-Befehle</span><span class="sxs-lookup"><span data-stu-id="1c70c-233">NuGet commands</span></span>

<span data-ttu-id="1c70c-234">Befehl</span><span class="sxs-lookup"><span data-stu-id="1c70c-234">Command</span></span> | <span data-ttu-id="1c70c-235">Funktion</span><span class="sxs-lookup"><span data-stu-id="1c70c-235">Function</span></span>
--- | ---
[<span data-ttu-id="1c70c-236">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="1c70c-236">dotnet nuget delete</span></span>](dotnet-nuget-delete.md) | <span data-ttu-id="1c70c-237">Löscht ein Paket vom Server oder hebt dessen Auflistung auf.</span><span class="sxs-lookup"><span data-stu-id="1c70c-237">Deletes or unlists a package from the server.</span></span>
[<span data-ttu-id="1c70c-238">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="1c70c-238">dotnet nuget push</span></span>](dotnet-nuget-push.md) | <span data-ttu-id="1c70c-239">Überträgt ein Paket auf den Server und veröffentlicht es.</span><span class="sxs-lookup"><span data-stu-id="1c70c-239">Pushes a package to the server and publishes it.</span></span>
[<span data-ttu-id="1c70c-240">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="1c70c-240">dotnet nuget locals</span></span>](dotnet-nuget-locals.md) | <span data-ttu-id="1c70c-241">Löscht lokale NuGet-Ressourcen, z.B. den http-Anforderungscache, den temporären Cache oder den Ordner mit globalen Paketen auf dem Computer, oder listet diese Ressourcen auf.</span><span class="sxs-lookup"><span data-stu-id="1c70c-241">Clears or lists local NuGet resources such as http-request cache, temporary cache, or machine-wide global packages folder.</span></span>
[<span data-ttu-id="1c70c-242">dotnet nuget add source</span><span class="sxs-lookup"><span data-stu-id="1c70c-242">dotnet nuget add source</span></span>](dotnet-nuget-add-source.md) | <span data-ttu-id="1c70c-243">Hiermit fügen Sie eine NuGet-Quelle hinzu.</span><span class="sxs-lookup"><span data-stu-id="1c70c-243">Adds a NuGet source.</span></span>
[<span data-ttu-id="1c70c-244">dotnet nuget disable source</span><span class="sxs-lookup"><span data-stu-id="1c70c-244">dotnet nuget disable source</span></span>](dotnet-nuget-disable-source.md) | <span data-ttu-id="1c70c-245">Hiermit deaktivieren Sie eine NuGet-Quelle.</span><span class="sxs-lookup"><span data-stu-id="1c70c-245">Disables a NuGet source.</span></span>
[<span data-ttu-id="1c70c-246">dotnet nuget enable source</span><span class="sxs-lookup"><span data-stu-id="1c70c-246">dotnet nuget enable source</span></span>](dotnet-nuget-enable-source.md) | <span data-ttu-id="1c70c-247">Hiermit aktivieren Sie eine NuGet-Quelle.</span><span class="sxs-lookup"><span data-stu-id="1c70c-247">Enables a NuGet source.</span></span>
[<span data-ttu-id="1c70c-248">dotnet nuget list source</span><span class="sxs-lookup"><span data-stu-id="1c70c-248">dotnet nuget list source</span></span>](dotnet-nuget-list-source.md) | <span data-ttu-id="1c70c-249">Hiermit werden alle konfigurierten NuGet-Quellen aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="1c70c-249">Lists all configured NuGet sources.</span></span>
[<span data-ttu-id="1c70c-250">dotnet nuget remove source</span><span class="sxs-lookup"><span data-stu-id="1c70c-250">dotnet nuget remove source</span></span>](dotnet-nuget-remove-source.md) | <span data-ttu-id="1c70c-251">Hiermit entfernen Sie eine NuGet-Quelle.</span><span class="sxs-lookup"><span data-stu-id="1c70c-251">Removes a NuGet source.</span></span>
[<span data-ttu-id="1c70c-252">dotnet nuget update source</span><span class="sxs-lookup"><span data-stu-id="1c70c-252">dotnet nuget update source</span></span>](dotnet-nuget-update-source.md) | <span data-ttu-id="1c70c-253">Hiermit aktualisieren Sie eine NuGet-Quelle.</span><span class="sxs-lookup"><span data-stu-id="1c70c-253">Updates a NuGet source.</span></span>

### <a name="global-tool-path-and-local-tools-commands"></a><span data-ttu-id="1c70c-254">Befehle für globale, Toolpfad- und lokale Tools</span><span class="sxs-lookup"><span data-stu-id="1c70c-254">Global, tool-path, and local tools commands</span></span>

<span data-ttu-id="1c70c-255">Tools sind Konsolenanwendungen, die über NuGet-Pakete installiert und über die Eingabeaufforderung aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="1c70c-255">Tools are console applications that are installed from NuGet packages and are invoked from the command prompt.</span></span> <span data-ttu-id="1c70c-256">Sie können Tools selbst schreiben oder Drittanbietertools installieren.</span><span class="sxs-lookup"><span data-stu-id="1c70c-256">You can write tools yourself or install tools written by third parties.</span></span> <span data-ttu-id="1c70c-257">Tools werden auch als globale Tools, Toolpfadtools und lokale Tools bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="1c70c-257">Tools are also known as global tools, tool-path tools, and local tools.</span></span> <span data-ttu-id="1c70c-258">Weitere Informationen finden Sie unter [Übersicht über .NET Core-Tools](global-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1c70c-258">For more information, see [.NET Core tools overview](global-tools.md).</span></span> <span data-ttu-id="1c70c-259">Globale und Toolpfadtools sind ab .NET Core SDK 2.1 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1c70c-259">Global and tool-path tools are available starting with .NET Core SDK 2.1.</span></span> <span data-ttu-id="1c70c-260">Lokale Tools sind ab .NET Core SDK 3.0 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1c70c-260">Local tools are available starting with .NET Core SDK 3.0.</span></span>

<span data-ttu-id="1c70c-261">Befehl</span><span class="sxs-lookup"><span data-stu-id="1c70c-261">Command</span></span> | <span data-ttu-id="1c70c-262">Funktion</span><span class="sxs-lookup"><span data-stu-id="1c70c-262">Function</span></span>
--- | ---
[<span data-ttu-id="1c70c-263">dotnet tool install</span><span class="sxs-lookup"><span data-stu-id="1c70c-263">dotnet tool install</span></span>](dotnet-tool-install.md) | <span data-ttu-id="1c70c-264">Installiert ein Tool auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="1c70c-264">Installs a tool on your machine.</span></span>
[<span data-ttu-id="1c70c-265">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="1c70c-265">dotnet tool list</span></span>](dotnet-tool-list.md) | <span data-ttu-id="1c70c-266">Listet alle globalen, Toolpfad- und lokalen Tools auf, die derzeit auf Ihrem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="1c70c-266">Lists all global, tool-path, or local tools currently installed on your machine.</span></span>
[<span data-ttu-id="1c70c-267">dotnet tool uninstall</span><span class="sxs-lookup"><span data-stu-id="1c70c-267">dotnet tool uninstall</span></span>](dotnet-tool-uninstall.md) | <span data-ttu-id="1c70c-268">Deinstalliert ein Tool von Ihrem Computer.</span><span class="sxs-lookup"><span data-stu-id="1c70c-268">Uninstalls a tool from your machine.</span></span>
[<span data-ttu-id="1c70c-269">dotnet tool update</span><span class="sxs-lookup"><span data-stu-id="1c70c-269">dotnet tool update</span></span>](dotnet-tool-update.md) | <span data-ttu-id="1c70c-270">Aktualisiert ein Tool, das auf Ihrem Computer installiert ist.</span><span class="sxs-lookup"><span data-stu-id="1c70c-270">Updates a tool that is installed on your machine.</span></span>

### <a name="additional-tools"></a><span data-ttu-id="1c70c-271">Weitere Tools</span><span class="sxs-lookup"><span data-stu-id="1c70c-271">Additional tools</span></span>

<span data-ttu-id="1c70c-272">Beginnend mit .NET Core SDK 2.1.300 steht eine Reihe von Tools, die nur auf Projektbasis unter Verwendung von `DotnetCliToolReference` verfügbar waren, jetzt als Teil des .NET Core SDK zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="1c70c-272">Starting with .NET Core SDK 2.1.300, a number of tools that were available only on a per project basis using `DotnetCliToolReference` are now available as part of the .NET Core SDK.</span></span> <span data-ttu-id="1c70c-273">Diese Tools werden in der folgenden Tabelle aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="1c70c-273">These tools are listed in the following table:</span></span>

| <span data-ttu-id="1c70c-274">Tool</span><span class="sxs-lookup"><span data-stu-id="1c70c-274">Tool</span></span>                                              | <span data-ttu-id="1c70c-275">Funktion</span><span class="sxs-lookup"><span data-stu-id="1c70c-275">Function</span></span>                                                     |
| ------------------------------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="1c70c-276">dev-certs</span><span class="sxs-lookup"><span data-stu-id="1c70c-276">dev-certs</span></span>                                         | <span data-ttu-id="1c70c-277">Erstellt und verwaltet Entwicklungszertifikate.</span><span class="sxs-lookup"><span data-stu-id="1c70c-277">Creates and manages development certificates.</span></span>                |
| [<span data-ttu-id="1c70c-278">ef</span><span class="sxs-lookup"><span data-stu-id="1c70c-278">ef</span></span>](/ef/core/miscellaneous/cli/dotnet)           | <span data-ttu-id="1c70c-279">Entity Framework Core-Befehlszeilentools.</span><span class="sxs-lookup"><span data-stu-id="1c70c-279">Entity Framework Core command-line tools.</span></span>                    |
| <span data-ttu-id="1c70c-280">sql-cache</span><span class="sxs-lookup"><span data-stu-id="1c70c-280">sql-cache</span></span>                                         | <span data-ttu-id="1c70c-281">SQL Server-Cache-Befehlszeilentools.</span><span class="sxs-lookup"><span data-stu-id="1c70c-281">SQL Server cache command-line tools.</span></span>                         |
| [<span data-ttu-id="1c70c-282">user-secrets</span><span class="sxs-lookup"><span data-stu-id="1c70c-282">user-secrets</span></span>](/aspnet/core/security/app-secrets) | <span data-ttu-id="1c70c-283">Verwaltet die Entwicklung von Benutzergeheimnissen.</span><span class="sxs-lookup"><span data-stu-id="1c70c-283">Manages development user secrets.</span></span>                            |
| [<span data-ttu-id="1c70c-284">watch</span><span class="sxs-lookup"><span data-stu-id="1c70c-284">watch</span></span>](/aspnet/core/tutorials/dotnet-watch)      | <span data-ttu-id="1c70c-285">Startet einen Datei-Watcher, der einen Befehl ausführt, wenn sich Dateien ändern.</span><span class="sxs-lookup"><span data-stu-id="1c70c-285">Starts a file watcher that runs a command when files change.</span></span> |

<span data-ttu-id="1c70c-286">Geben Sie `dotnet <tool-name> --help` ein, um weitere Informationen zu den einzelnen Tools zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="1c70c-286">For more information about each tool, type `dotnet <tool-name> --help`.</span></span>

## <a name="examples"></a><span data-ttu-id="1c70c-287">Beispiele</span><span class="sxs-lookup"><span data-stu-id="1c70c-287">Examples</span></span>

<span data-ttu-id="1c70c-288">Erstellen einer neuen .NET Core-Konsolenanwendung:</span><span class="sxs-lookup"><span data-stu-id="1c70c-288">Create a new .NET Core console application:</span></span>

```dotnetcli
dotnet new console
```

<span data-ttu-id="1c70c-289">Erstellen eines Projekts und seiner Abhängigkeiten in einem vorgegebenen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="1c70c-289">Build a project and its dependencies in a given directory:</span></span>

```dotnetcli
dotnet build
```

<span data-ttu-id="1c70c-290">Ausführen einer Anwendung:</span><span class="sxs-lookup"><span data-stu-id="1c70c-290">Run an application:</span></span>

```dotnetcli
dotnet myapp.dll
```

## <a name="environment-variables"></a><span data-ttu-id="1c70c-291">Umgebungsvariablen</span><span class="sxs-lookup"><span data-stu-id="1c70c-291">Environment variables</span></span>

- <span data-ttu-id="1c70c-292">`DOTNET_ROOT`, `DOTNET_ROOT(x86)`</span><span class="sxs-lookup"><span data-stu-id="1c70c-292">`DOTNET_ROOT`, `DOTNET_ROOT(x86)`</span></span>

  <span data-ttu-id="1c70c-293">Gibt den Speicherort der .NET Core-Runtimes an, wenn sie nicht am Standardspeicherort installiert sind.</span><span class="sxs-lookup"><span data-stu-id="1c70c-293">Specifies the location of the .NET Core runtimes, if they are not installed in the default location.</span></span> <span data-ttu-id="1c70c-294">Der Standardspeicherort unter Windows ist `C:\Program Files\dotnet`.</span><span class="sxs-lookup"><span data-stu-id="1c70c-294">The default location on Windows is `C:\Program Files\dotnet`.</span></span> <span data-ttu-id="1c70c-295">Der Standardspeicherort unter Linux und macOS ist `/usr/share/dotnet`.</span><span class="sxs-lookup"><span data-stu-id="1c70c-295">The default location on Linux and macOS is `/usr/share/dotnet`.</span></span> <span data-ttu-id="1c70c-296">Diese Umgebungsvariable wird nur beim Ausführen von Anwendungen über generierte ausführbare Dateien (Apphosts) verwendet.</span><span class="sxs-lookup"><span data-stu-id="1c70c-296">This environment variable is used only when running apps via generated executables (apphosts).</span></span> <span data-ttu-id="1c70c-297">`DOTNET_ROOT(x86)` wird stattdessen verwendet, wenn eine ausführbare 32-Bit-Datei auf einem 64-Bit-Betriebssystem ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1c70c-297">`DOTNET_ROOT(x86)` is used instead when running a 32-bit executable on a 64-bit OS.</span></span>

- `DOTNET_PACKAGES`

  <span data-ttu-id="1c70c-298">Der Ordner für globale Pakete.</span><span class="sxs-lookup"><span data-stu-id="1c70c-298">The global packages folder.</span></span> <span data-ttu-id="1c70c-299">Wenn er nicht festgelegt wird, wird standardmäßig `~/.nuget/packages` unter Unix oder `%userprofile%\.nuget\packages` unter Windows verwendet.</span><span class="sxs-lookup"><span data-stu-id="1c70c-299">If not set, it defaults to `~/.nuget/packages` on Unix or `%userprofile%\.nuget\packages` on Windows.</span></span>

- `DOTNET_SERVICING`

  <span data-ttu-id="1c70c-300">Gibt den Speicherort des Wartungsindex an, der vom freigegebenen Host verwendet wird, wenn die Laufzeit geladen wird.</span><span class="sxs-lookup"><span data-stu-id="1c70c-300">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

- `DOTNET_NOLOGO`

  <span data-ttu-id="1c70c-301">Gibt an, ob bei der ersten Ausführung .NET Core-Willkommens- und Telemetriemeldungen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="1c70c-301">Specifies whether .NET Core welcome and telemetry messages are displayed on first run.</span></span> <span data-ttu-id="1c70c-302">Bei Festlegung auf `true` werden diese Meldungen unterdrückt (akzeptierte Werte: `true`, `1` oder `yes`), bei Festlegung auf `false` werden die Meldungen zugelassen (akzeptierte Werte: `false`, `0` oder `no`).</span><span class="sxs-lookup"><span data-stu-id="1c70c-302">Set to `true` to mute these messages (values `true`, `1`, or `yes` accepted) or set to `false` to allow (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="1c70c-303">Sofern nicht festgelegt, lautet der Standardwert `false`, und die Meldungen werden bei der ersten Ausführung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1c70c-303">If not set, the default is `false` and the messages will be displayed on first run.</span></span> <span data-ttu-id="1c70c-304">Beachten Sie, dass dieses Flag keine Auswirkung auf die Telemetrie hat (siehe `DOTNET_CLI_TELEMETRY_OPTOUT` zum Deaktivieren der Übermittlung von Telemetriedaten).</span><span class="sxs-lookup"><span data-stu-id="1c70c-304">Note that this flag has no effect on telemetry (see `DOTNET_CLI_TELEMETRY_OPTOUT` for opting out of sending telemetry).</span></span>

- `DOTNET_CLI_TELEMETRY_OPTOUT`

  <span data-ttu-id="1c70c-305">Gibt an, ob Daten zur Nutzung von .NET Core-Tools gesammelt und an Microsoft gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="1c70c-305">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="1c70c-306">Legen Sie `true` fest, um die Telemetriefunktion zu deaktivieren (Wert `true`, `1` oder `yes` wird akzeptiert).</span><span class="sxs-lookup"><span data-stu-id="1c70c-306">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="1c70c-307">Legen Sie andernfalls `false` fest, um die Telemetriefunktionen zu aktivieren (Wert `false`, `0` oder `no` wird akzeptiert).</span><span class="sxs-lookup"><span data-stu-id="1c70c-307">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="1c70c-308">Ohne Festlegung ist der Standardwert `false`, und die Telemetriefunktion ist aktiviert.</span><span class="sxs-lookup"><span data-stu-id="1c70c-308">If not set, the default is `false` and the telemetry feature is active.</span></span>

- `DOTNET_MULTILEVEL_LOOKUP`

  <span data-ttu-id="1c70c-309">Gibt an, ob die .NET Core-Runtime, das freigegebene Framework oder das SDK vom globalen Speicherort aus aufgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="1c70c-309">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="1c70c-310">Ohne Festlegung ist der Standardwert 1 (logisch `true`).</span><span class="sxs-lookup"><span data-stu-id="1c70c-310">If not set, it defaults to 1 (logical `true`).</span></span> <span data-ttu-id="1c70c-311">Auf 0 (logisch `false`) festgelegt, um nicht vom globalen Speicherort aus aufzulösen und isolierte .NET Core-Installationen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="1c70c-311">Set to 0 (logical `false`) to not resolve from the global location and have isolated .NET Core installations.</span></span> <span data-ttu-id="1c70c-312">Weitere Informationen zu Lookup mit mehreren Ebenen finden Sie unter [Multi-level SharedFX lookup (SharedFX-Lookup mit mehreren Ebenen)](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span><span class="sxs-lookup"><span data-stu-id="1c70c-312">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

- <span data-ttu-id="1c70c-313">`DOTNET_ROLL_FORWARD` **Verfügbar ab .NET Core 3.x SDK.**</span><span class="sxs-lookup"><span data-stu-id="1c70c-313">`DOTNET_ROLL_FORWARD` **Available starting with .NET Core 3.x SDK.**</span></span>

  <span data-ttu-id="1c70c-314">Bestimmt das Rollforwardverhalten.</span><span class="sxs-lookup"><span data-stu-id="1c70c-314">Determines roll forward behavior.</span></span> <span data-ttu-id="1c70c-315">Weitere Informationen finden Sie unter der Option `--roll-forward` weiter oben in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="1c70c-315">For more information, see the `--roll-forward` option earlier in this article.</span></span>

- <span data-ttu-id="1c70c-316">`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX` **Verfügbar im .NET Core 2.x SDK.**</span><span class="sxs-lookup"><span data-stu-id="1c70c-316">`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX` **Available in .NET Core 2.x SDK.**</span></span>

  <span data-ttu-id="1c70c-317">Deaktiviert Rollforward der Nebenversion, wenn `0` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="1c70c-317">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="1c70c-318">Weitere Informationen finden Sie unter [Rollforward](../whats-new/dotnet-core-2-1.md#roll-forward).</span><span class="sxs-lookup"><span data-stu-id="1c70c-318">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

- `DOTNET_CLI_UI_LANGUAGE`

  <span data-ttu-id="1c70c-319">Legt die Sprache der CLI-Benutzeroberfläche mit einem Gebietsschemawert wie `en-us` fest.</span><span class="sxs-lookup"><span data-stu-id="1c70c-319">Sets the language of the CLI UI using a locale value such as `en-us`.</span></span> <span data-ttu-id="1c70c-320">Die unterstützten Werte sind identisch mit denen für Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1c70c-320">The supported values are the same as for Visual Studio.</span></span> <span data-ttu-id="1c70c-321">Weitere Informationen finden Sie im Abschnitt zum Ändern der Sprache des Installationsprogramms in der [Visual Studio-Installationsdokumentation](https://docs.microsoft.com/visualstudio/install/install-visual-studio?view=vs-2019).</span><span class="sxs-lookup"><span data-stu-id="1c70c-321">For more information, see the section on changing the installer language in the [Visual Studio installation documentation](https://docs.microsoft.com/visualstudio/install/install-visual-studio?view=vs-2019).</span></span> <span data-ttu-id="1c70c-322">Es gelten die Regeln des .NET-Ressourcen-Managers, sodass Sie keine genaue Übereinstimmung auswählen müssen, sondern auch Nachfolger in der `CultureInfo`-Struktur auswählen können.</span><span class="sxs-lookup"><span data-stu-id="1c70c-322">The .NET resource manager rules apply, so you don't have to pick an exact match&mdash;you can also pick descendants in the `CultureInfo` tree.</span></span> <span data-ttu-id="1c70c-323">Bei einer Festlegung auf `fr-CA` findet und verwendet die Befehlszeilenschnittstelle z. B. die `fr`-Übersetzungen.</span><span class="sxs-lookup"><span data-stu-id="1c70c-323">For example, if you set it to `fr-CA`, the CLI will find and use the `fr` translations.</span></span> <span data-ttu-id="1c70c-324">Wenn Sie eine nicht unterstützte Sprache festlegen, greift die Befehlszeilenschnittstelle auf Englisch zurück.</span><span class="sxs-lookup"><span data-stu-id="1c70c-324">If you set it to a language that is not supported, the CLI falls back to English.</span></span>

- `DOTNET_DISABLE_GUI_ERRORS`

  <span data-ttu-id="1c70c-325">Für generierte ausführbare Dateien mit aktivierter Benutzeroberfläche – deaktiviert das Dialogfeld-Popupfenster, das normalerweise bei bestimmten Fehlerklassen angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="1c70c-325">For GUI-enabled generated executables - disables dialog popup, which normally shows for certain classes of errors.</span></span> <span data-ttu-id="1c70c-326">In diesen Fällen erfolgt lediglich eine Ausgabe an `stderr` und eine Beendigung.</span><span class="sxs-lookup"><span data-stu-id="1c70c-326">It only writes to `stderr` and exits in those cases.</span></span>
  
- `DOTNET_ADDITIONAL_DEPS`

  <span data-ttu-id="1c70c-327">Entspricht der CLI-Option `--additional-deps`.</span><span class="sxs-lookup"><span data-stu-id="1c70c-327">Equivalent to CLI option `--additional-deps`.</span></span>

- `DOTNET_RUNTIME_ID`

  <span data-ttu-id="1c70c-328">Setzt die erkannte RID außer Kraft.</span><span class="sxs-lookup"><span data-stu-id="1c70c-328">Overrides the detected RID.</span></span>

- `DOTNET_SHARED_STORE`

  <span data-ttu-id="1c70c-329">Speicherort des „gemeinsamen Speichers“, auf den die Assemblyauflösung in einigen Fällen zurückgreift.</span><span class="sxs-lookup"><span data-stu-id="1c70c-329">Location of the "shared store" which assembly resolution falls back to in some cases.</span></span>

- `DOTNET_STARTUP_HOOKS`

  <span data-ttu-id="1c70c-330">Liste der Assemblys zum Laden und Ausführen von Startuphooks.</span><span class="sxs-lookup"><span data-stu-id="1c70c-330">List of assemblies to load and execute startup hooks from.</span></span>

- <span data-ttu-id="1c70c-331">`COREHOST_TRACE`, `COREHOST_TRACEFILE`, `COREHOST_TRACE_VERBOSITY`</span><span class="sxs-lookup"><span data-stu-id="1c70c-331">`COREHOST_TRACE`, `COREHOST_TRACEFILE`, `COREHOST_TRACE_VERBOSITY`</span></span>

  <span data-ttu-id="1c70c-332">Steuert die Diagnoseablaufverfolgung von den Hostingkomponenten wie `dotnet.exe`, `hostfxr` und `hostpolicy`.</span><span class="sxs-lookup"><span data-stu-id="1c70c-332">Controls diagnostics tracing from the hosting components, such as `dotnet.exe`, `hostfxr`, and `hostpolicy`.</span></span>

## <a name="see-also"></a><span data-ttu-id="1c70c-333">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1c70c-333">See also</span></span>

- [<span data-ttu-id="1c70c-334">Laufzeitkonfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="1c70c-334">Runtime Configuration Files</span></span>](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)
- [<span data-ttu-id="1c70c-335">Konfigurationseinstellungen für die .NET Core-Runtime</span><span class="sxs-lookup"><span data-stu-id="1c70c-335">.NET Core run-time configuration settings</span></span>](../run-time-config/index.md)
