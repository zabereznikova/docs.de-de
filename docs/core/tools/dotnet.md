---
title: dotnet-Befehl
description: Erfahren Sie mehr über den dotnet-Befehl (den generischen Treiber für die .NET Core-CLI) und dessen Verwendung.
ms.date: 02/13/2020
ms.openlocfilehash: 6a08297499d955db44e342dc82fed25b7b9b8171
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739077"
---
# <a name="dotnet-command"></a><span data-ttu-id="4e6b0-103">dotnet-Befehl</span><span class="sxs-lookup"><span data-stu-id="4e6b0-103">dotnet command</span></span>

<span data-ttu-id="4e6b0-104">**Dieser Artikel gilt für:** ✔️ .NET Core 2.1 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="4e6b0-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="4e6b0-105">name</span><span class="sxs-lookup"><span data-stu-id="4e6b0-105">Name</span></span>

<span data-ttu-id="4e6b0-106">`dotnet`: Der generische Treiber für die .NET Core-CLI.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-106">`dotnet` - The generic driver for the .NET Core CLI.</span></span>

## <a name="synopsis"></a><span data-ttu-id="4e6b0-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="4e6b0-107">Synopsis</span></span>

<span data-ttu-id="4e6b0-108">So erhalten Sie Informationen über die verfügbaren Befehle und die Umgebung</span><span class="sxs-lookup"><span data-stu-id="4e6b0-108">To get information about the available commands and the environment:</span></span>

```dotnetcli
dotnet [--version] [--info] [--list-runtimes] [--list-sdks]

dotnet -h|--help
```

<span data-ttu-id="4e6b0-109">So führen Sie einen Befehl aus (erfordert eine SDK-Installation)</span><span class="sxs-lookup"><span data-stu-id="4e6b0-109">To run a command (requires SDK installation):</span></span>

```dotnetcli
dotnet <COMMAND> [-d|--diagnostics] [-h|--help] [--verbosity <LEVEL>]
    [command-options] [arguments]
```

<span data-ttu-id="4e6b0-110">So führen Sie eine Anwendung aus</span><span class="sxs-lookup"><span data-stu-id="4e6b0-110">To run an application:</span></span>

```dotnetcli
dotnet [--additionalprobingpath <PATH>] [--additional-deps <PATH>]
    [--fx-version <VERSION>]  [--roll-forward <SETTING>]
    <PATH_TO_APPLICATION> [arguments]

dotnet exec [--additionalprobingpath] [--additional-deps <PATH>]
    [--fx-version <VERSION>]  [--roll-forward <SETTING>]
    <PATH_TO_APPLICATION> [arguments]
```

<span data-ttu-id="4e6b0-111">`--roll-forward` ist seit .NET Core 3.x verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-111">`--roll-forward` is available since .NET Core 3.x.</span></span> <span data-ttu-id="4e6b0-112">Verwenden Sie `--roll-forward-on-no-candidate-fx` für .NET Core 2.x.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-112">Use `--roll-forward-on-no-candidate-fx` for .NET Core 2.x.</span></span>

## <a name="description"></a><span data-ttu-id="4e6b0-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4e6b0-113">Description</span></span>

<span data-ttu-id="4e6b0-114">Der Befehl `dotnet` hat zwei Funktionen:</span><span class="sxs-lookup"><span data-stu-id="4e6b0-114">The `dotnet` command has two functions:</span></span>

- <span data-ttu-id="4e6b0-115">Es stellt Befehle für die Arbeit mit .NET Core-Projekten bereit.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-115">It provides commands for working with .NET Core projects.</span></span>

  <span data-ttu-id="4e6b0-116">Beispielsweise erstellt [`dotnet build`](dotnet-build.md) ein Projekt.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-116">For example, [`dotnet build`](dotnet-build.md) builds a project.</span></span> <span data-ttu-id="4e6b0-117">Jeder Befehl definiert seine eigenen Optionen und Argumente.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-117">Each command defines its own options and arguments.</span></span> <span data-ttu-id="4e6b0-118">Alle Befehle unterstützen die Option `--help` zum Ausdrucken einer kurzen Dokumentation über die Verwendung des Befehls.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-118">All commands support the `--help` option for printing out brief documentation about how to use the command.</span></span>

- <span data-ttu-id="4e6b0-119">Sie führt .NET Core-Anwendungen aus.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-119">It runs .NET Core applications.</span></span>

  <span data-ttu-id="4e6b0-120">Sie geben den Pfad zu einer `.dll`-Datei einer Anwendung zur Ausführung der Anwendung an.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-120">You specify the path to an application `.dll` file to run the application.</span></span>  <span data-ttu-id="4e6b0-121">Das Ausführen der Anwendung bedeutet, den Einstiegspunkt zu finden und auszuführen. Im Falle von Konsolen-Apps ist dies die `Main`-Methode.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-121">To run the application means to find and execute the entry point, which in the case of console apps is the `Main` method.</span></span> <span data-ttu-id="4e6b0-122">Beispiel: `dotnet myapp.dll` führt die Anwendung `myapp` aus.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-122">For example, `dotnet myapp.dll` runs the `myapp` application.</span></span> <span data-ttu-id="4e6b0-123">Weitere Informationen über Bereitstellungsoptionen finden Sie unter [.NET Core-Anwendungsbereitstellung](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="4e6b0-123">See [.NET Core application deployment](../deploying/index.md) to learn about deployment options.</span></span>

## <a name="options"></a><span data-ttu-id="4e6b0-124">Optionen</span><span class="sxs-lookup"><span data-stu-id="4e6b0-124">Options</span></span>

<span data-ttu-id="4e6b0-125">Es gibt verschiedene Optionen für `dotnet` allein, für die Ausführung eines Befehls und für die Ausführung einer Anwendung.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-125">Different options are available for `dotnet` by itself, for running a command, and for running an application.</span></span>

### <a name="options-for-dotnet-by-itself"></a><span data-ttu-id="4e6b0-126">Optionen für dotnet</span><span class="sxs-lookup"><span data-stu-id="4e6b0-126">Options for dotnet by itself</span></span>

<span data-ttu-id="4e6b0-127">Die folgenden Optionen gelten für `dotnet` allein.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-127">The following options are for `dotnet` by itself.</span></span> <span data-ttu-id="4e6b0-128">Beispielsweise `dotnet --info`.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-128">For example, `dotnet --info`.</span></span> <span data-ttu-id="4e6b0-129">Sie drucken Informationen über die Umgebung aus.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-129">They print out information about the environment.</span></span>

- **`--info`**

  <span data-ttu-id="4e6b0-130">Gibt ausführliche Informationen über eine .NET Core-Installation und die Computerumgebung aus, z.B. das aktuelle Betriebssystem und den Commit-SHA für die .NET Core-Version.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-130">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

- **`--version`**

  <span data-ttu-id="4e6b0-131">Druckt die Version des verwendeten .NET Core-SDK aus.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-131">Prints out the version of the .NET Core SDK in use.</span></span>

- **`--list-runtimes`**

  <span data-ttu-id="4e6b0-132">Druckt eine Liste der installierten .NET Core-Runtimes aus.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-132">Prints out a list of the installed .NET Core runtimes.</span></span> <span data-ttu-id="4e6b0-133">Eine x86-Version des SDK listet nur x86-Runtimes auf, und eine x64-Version des SDK listet nur x64-Runtimes auf.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-133">An x86 version of the SDK lists only x86 runtimes, and an x64 version of the SDK lists only x64 runtimes.</span></span>

- **`--list-sdks`**

  <span data-ttu-id="4e6b0-134">Druckt eine Liste der installierten .NET Core-SDKs aus.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-134">Prints out a list of the installed .NET Core SDKs.</span></span>

- **`-h|--help`**

  <span data-ttu-id="4e6b0-135">Druckt eine Liste der verfügbaren Befehle aus.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-135">Prints out a list of available commands.</span></span>

### <a name="sdk-options-for-running-a-command"></a><span data-ttu-id="4e6b0-136">SDK-Optionen zum Ausführen eines Befehls</span><span class="sxs-lookup"><span data-stu-id="4e6b0-136">SDK options for running a command</span></span>

<span data-ttu-id="4e6b0-137">Die folgenden Optionen gelten für `dotnet` mit einem Befehl.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-137">The following options are for `dotnet` with a command.</span></span> <span data-ttu-id="4e6b0-138">Beispielsweise `dotnet build --help`.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-138">For example, `dotnet build --help`.</span></span>

- **`-d|--diagnostics`**

  <span data-ttu-id="4e6b0-139">Ermöglicht die diagnostische Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-139">Enables diagnostic output.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="4e6b0-140">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-140">Sets the verbosity level of the command.</span></span> <span data-ttu-id="4e6b0-141">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-141">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="4e6b0-142">Nicht in jedem Befehl unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-142">Not supported in every command.</span></span> <span data-ttu-id="4e6b0-143">Auf der Seite der einzelnen Befehle finden Sie heraus, ob diese Option verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-143">See specific command page to determine if this option is available.</span></span>

- **`-h|--help`**

  <span data-ttu-id="4e6b0-144">Gibt Dokumentation für einen bestimmten Befehl aus, z.B. `dotnet build --help`.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-144">Prints out documentation for a given command, such as `dotnet build --help`.</span></span>

- **`command options`**

  <span data-ttu-id="4e6b0-145">Jeder Befehl definiert Optionen, die für diesen Befehl spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-145">Each command defines options specific to that command.</span></span> <span data-ttu-id="4e6b0-146">Eine Liste der verfügbaren Optionen finden Sie auf einer speziellen Befehlsseite.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-146">See specific command page for a list of available options.</span></span>

### <a name="runtime-options"></a><span data-ttu-id="4e6b0-147">Laufzeitoptionen</span><span class="sxs-lookup"><span data-stu-id="4e6b0-147">Runtime options</span></span>

<span data-ttu-id="4e6b0-148">Die folgenden Optionen sind verfügbar, wenn `dotnet` eine Anwendung ausführt.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-148">The following options are available when `dotnet` runs an application.</span></span> <span data-ttu-id="4e6b0-149">Beispielsweise `dotnet myapp.dll --fx-version 3.1.1`.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-149">For example, `dotnet myapp.dll --fx-version 3.1.1`.</span></span>

- **`--additionalprobingpath <PATH>`**

  <span data-ttu-id="4e6b0-150">Pfad, der die Suchrichtlinie und die zu suchenden Assemblys enthält.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-150">Path containing probing policy and assemblies to probe.</span></span>

- **`--additional-deps <PATH>`**

  <span data-ttu-id="4e6b0-151">Pfad zu einer zusätzlichen *.deps.json*-Datei.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-151">Path to an additional *.deps.json* file.</span></span> <span data-ttu-id="4e6b0-152">Eine *deps.json*-Datei enthält eine Liste mit Abhängigkeiten, Kompilierungsabhängigkeiten und Versionsinformationen, die verwendet werden, um Assemblykonflikte zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-152">A *deps.json* file contains a list of dependencies, compilation dependencies, and version information used to address assembly conflicts.</span></span> <span data-ttu-id="4e6b0-153">Weitere Informationen finden Sie auf GitHub unter [Laufzeitkonfigurationsdateien](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="4e6b0-153">For more information, see [Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) on GitHub.</span></span>

- **`--fx-version <VERSION>`**

  <span data-ttu-id="4e6b0-154">Version der .NET Core-Runtime, die zum Ausführen der Anwendung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-154">Version of the .NET Core runtime to use to run the application.</span></span>

- **`--runtimeconfig`**

  <span data-ttu-id="4e6b0-155">Der Pfad zu einer *runtimeconfig.json*-Datei.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-155">Path to a *runtimeconfig.json* file.</span></span> <span data-ttu-id="4e6b0-156">Eine *runtimeconfig.json*-Datei ist eine Konfigurationsdatei mit Einstellungen für die Runtime.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-156">A *runtimeconfig.json* file is a configuration file that contains run-time settings.</span></span> <span data-ttu-id="4e6b0-157">Weitere Informationen finden Sie unter [Konfigurationseinstellungen für die .NET Core-Runtime](../run-time-config/index.md#runtimeconfigjson).</span><span class="sxs-lookup"><span data-stu-id="4e6b0-157">For more information, see [.NET Core run-time configuration settings](../run-time-config/index.md#runtimeconfigjson).</span></span>

- <span data-ttu-id="4e6b0-158">**`--roll-forward-on-no-candidate-fx <N>`** **Verfügbar im .NET Core 2.x SDK.**</span><span class="sxs-lookup"><span data-stu-id="4e6b0-158">**`--roll-forward-on-no-candidate-fx <N>`** **Available in .NET Core 2.x SDK.**</span></span>

  <span data-ttu-id="4e6b0-159">Definiert ein Verhalten, wenn das erforderliche freigegebene Framework nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-159">Defines behavior when the required shared framework is not available.</span></span> <span data-ttu-id="4e6b0-160">`N` kann Folgendes sein:</span><span class="sxs-lookup"><span data-stu-id="4e6b0-160">`N` can be:</span></span>

  - <span data-ttu-id="4e6b0-161">`0` - Das Ausführen von Rollforward ist auch für die Nebenversion deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-161">`0` - Disable even minor version roll forward.</span></span>
  - <span data-ttu-id="4e6b0-162">`1` - Rollforward wird in der Nebenversion, nicht aber in der Hauptversion, ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-162">`1` - Roll forward on minor version, but not on major version.</span></span> <span data-ttu-id="4e6b0-163">Dies ist das Standardverhalten.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-163">This is the default behavior.</span></span>
  - <span data-ttu-id="4e6b0-164">`2` - Rollforward wird in Neben- und Hauptversionen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-164">`2` - Roll forward on minor and major versions.</span></span>

   <span data-ttu-id="4e6b0-165">Weitere Informationen finden Sie unter [Rollforward](../whats-new/dotnet-core-2-1.md#roll-forward).</span><span class="sxs-lookup"><span data-stu-id="4e6b0-165">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

- <span data-ttu-id="4e6b0-166">**`--roll-forward <SETTING>`** **Verfügbar ab .NET Core SDK 3.0.**</span><span class="sxs-lookup"><span data-stu-id="4e6b0-166">**`--roll-forward <SETTING>`** **Available starting with .NET Core SDK 3.0.**</span></span>

  <span data-ttu-id="4e6b0-167">Steuert, wie der Rollforward auf die App angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-167">Controls how roll forward is applied to the app.</span></span> <span data-ttu-id="4e6b0-168">`SETTING` kann einer der folgenden Werte sein.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-168">The `SETTING` can be one of the following values.</span></span> <span data-ttu-id="4e6b0-169">Wenn nichts anderes angegeben wird, wird als Standard `Minor` verwendet.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-169">If not specified, `Minor` is the default.</span></span>

  - <span data-ttu-id="4e6b0-170">`LatestPatch`: Rollforward zur höchsten Patchversion.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-170">`LatestPatch` - Roll forward to the highest patch version.</span></span> <span data-ttu-id="4e6b0-171">Dies deaktiviert ein Rollforward zur Nebenversion.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-171">This disables minor version roll forward.</span></span>
  - <span data-ttu-id="4e6b0-172">`Minor`: Rollforward zur niedrigsten höheren Nebenversion, wenn die angeforderte Nebenversion nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-172">`Minor` - Roll forward to the lowest higher minor version, if requested minor version is missing.</span></span> <span data-ttu-id="4e6b0-173">Wenn die angeforderte Nebenversion vorhanden ist, wird die LatestPatch-Richtlinie verwendet.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-173">If the requested minor version is present, then the LatestPatch policy is used.</span></span>
  - <span data-ttu-id="4e6b0-174">`Major`: Rollforward zur niedrigsten höheren Hauptversion – und niedrigsten Nebenversion, wenn die angeforderte Hauptversion nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-174">`Major` - Roll forward to lowest higher major version, and lowest minor version, if requested major version is missing.</span></span> <span data-ttu-id="4e6b0-175">Wenn die angeforderte Hauptversion vorhanden ist, wird die Minor-Richtlinie verwendet.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-175">If the requested major version is present, then the Minor policy is used.</span></span>
  - <span data-ttu-id="4e6b0-176">`LatestMinor`: Rollforward zur höchsten Nebenversion – auch dann, wenn die angeforderte Nebenversion vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-176">`LatestMinor` - Roll forward to highest minor version, even if requested minor version is present.</span></span> <span data-ttu-id="4e6b0-177">Für Komponentenhostingszenarien vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-177">Intended for component hosting scenarios.</span></span>
  - <span data-ttu-id="4e6b0-178">`LatestMajor`: Rollforward zur höchsten Hauptversion und höchsten Nebenversion – auch dann, wenn die angeforderte Hauptversion vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-178">`LatestMajor` - Roll forward to highest major and highest minor version, even if requested major is present.</span></span> <span data-ttu-id="4e6b0-179">Für Komponentenhostingszenarien vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-179">Intended for component hosting scenarios.</span></span>
  - <span data-ttu-id="4e6b0-180">`Disable`: Kein Rollforward.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-180">`Disable` - Don't roll forward.</span></span> <span data-ttu-id="4e6b0-181">Nur Binden an angegebene Version.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-181">Only bind to specified version.</span></span> <span data-ttu-id="4e6b0-182">Diese Richtlinie wird nicht zur allgemeinen Verwendung empfohlen, da sie die Möglichkeit eines Rollforwards zu den neuesten Patches ausschließt.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-182">This policy isn't recommended for general use because it disables the ability to roll forward to the latest patches.</span></span> <span data-ttu-id="4e6b0-183">Dieser Wert wird nur zu Testzwecken empfohlen.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-183">This value is only recommended for testing.</span></span>

<span data-ttu-id="4e6b0-184">Mit Ausnahme von `Disable` wird für alle Einstellungen die höchste verfügbare Patchversion verwendet.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-184">With the exception of `Disable`, all settings will use the highest available patch version.</span></span>

<span data-ttu-id="4e6b0-185">Das Rollforwardverhalten kann auch in einer Projektdateieigenschaft, einer Runtime-Konfigurationsdateieigenschaft und einer Umgebungsvariablen konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-185">Roll forward behavior can also be configured in a project file property, a run-time configuration file property, and an environment variable.</span></span> <span data-ttu-id="4e6b0-186">Weitere Informationen finden Sie unter [Runtimerollforward der Hauptversion](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward).</span><span class="sxs-lookup"><span data-stu-id="4e6b0-186">For more information, see [Major-version runtime roll forward](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward).</span></span>

## <a name="dotnet-commands"></a><span data-ttu-id="4e6b0-187">dotnet-Befehle</span><span class="sxs-lookup"><span data-stu-id="4e6b0-187">dotnet commands</span></span>

### <a name="general"></a><span data-ttu-id="4e6b0-188">Allgemein</span><span class="sxs-lookup"><span data-stu-id="4e6b0-188">General</span></span>

| <span data-ttu-id="4e6b0-189">Befehl</span><span class="sxs-lookup"><span data-stu-id="4e6b0-189">Command</span></span>                                       | <span data-ttu-id="4e6b0-190">Funktion</span><span class="sxs-lookup"><span data-stu-id="4e6b0-190">Function</span></span>                                                            |
| --------------------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="4e6b0-191">dotnet build</span><span class="sxs-lookup"><span data-stu-id="4e6b0-191">dotnet build</span></span>](dotnet-build.md)               | <span data-ttu-id="4e6b0-192">Erstellt eine .NET Core-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-192">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="4e6b0-193">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="4e6b0-193">dotnet build-server</span></span>](dotnet-build-server.md) | <span data-ttu-id="4e6b0-194">Interagiert mit Servern, die von einem Build gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-194">Interacts with servers started by a build.</span></span>                          |
| [<span data-ttu-id="4e6b0-195">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="4e6b0-195">dotnet clean</span></span>](dotnet-clean.md)               | <span data-ttu-id="4e6b0-196">Bereinigen von Buildausgaben.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-196">Clean build outputs.</span></span>                                                |
| [<span data-ttu-id="4e6b0-197">dotnet help</span><span class="sxs-lookup"><span data-stu-id="4e6b0-197">dotnet help</span></span>](dotnet-help.md)                 | <span data-ttu-id="4e6b0-198">Zeigt eine ausführlichere Onlinedokumentation für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-198">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="4e6b0-199">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="4e6b0-199">dotnet migrate</span></span>](dotnet-migrate.md)           | <span data-ttu-id="4e6b0-200">Migriert ein gültiges Preview 2-Projekt in ein .NET Core SDK 1.0-Projekt.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-200">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="4e6b0-201">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="4e6b0-201">dotnet msbuild</span></span>](dotnet-msbuild.md)           | <span data-ttu-id="4e6b0-202">Ermöglicht den Zugriff auf die MSBuild-Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="4e6b0-202">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="4e6b0-203">dotnet new</span><span class="sxs-lookup"><span data-stu-id="4e6b0-203">dotnet new</span></span>](dotnet-new.md)                   | <span data-ttu-id="4e6b0-204">Initialisiert ein C#- oder F#-Projekt für eine bestimmte Vorlage.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-204">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="4e6b0-205">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="4e6b0-205">dotnet pack</span></span>](dotnet-pack.md)                 | <span data-ttu-id="4e6b0-206">Erstellt ein NuGet-Paket aus Ihrem Code.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-206">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="4e6b0-207">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="4e6b0-207">dotnet publish</span></span>](dotnet-publish.md)           | <span data-ttu-id="4e6b0-208">Veröffentlicht eine .NET Framework-abhängige oder eigenständige Anwendung.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-208">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="4e6b0-209">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="4e6b0-209">dotnet restore</span></span>](dotnet-restore.md)           | <span data-ttu-id="4e6b0-210">Stellt die Abhängigkeiten für eine bestimmte Anwendung wieder her.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-210">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="4e6b0-211">dotnet run</span><span class="sxs-lookup"><span data-stu-id="4e6b0-211">dotnet run</span></span>](dotnet-run.md)                   | <span data-ttu-id="4e6b0-212">Führt die Anwendung aus der Quelle aus.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-212">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="4e6b0-213">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="4e6b0-213">dotnet sln</span></span>](dotnet-sln.md)                   | <span data-ttu-id="4e6b0-214">Optionen zum Hinzufügen, Entfernen und Listen von Projekten in einer Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-214">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="4e6b0-215">dotnet store</span><span class="sxs-lookup"><span data-stu-id="4e6b0-215">dotnet store</span></span>](dotnet-store.md)               | <span data-ttu-id="4e6b0-216">Speichert Assemblys im Laufzeitpaketspeicher.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-216">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="4e6b0-217">dotnet test</span><span class="sxs-lookup"><span data-stu-id="4e6b0-217">dotnet test</span></span>](dotnet-test.md)                 | <span data-ttu-id="4e6b0-218">Führt Tests mit einem Test Runner aus.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-218">Runs tests using a test runner.</span></span>                                     |

### <a name="project-references"></a><span data-ttu-id="4e6b0-219">Projektverweise</span><span class="sxs-lookup"><span data-stu-id="4e6b0-219">Project references</span></span>

<span data-ttu-id="4e6b0-220">Befehl</span><span class="sxs-lookup"><span data-stu-id="4e6b0-220">Command</span></span> | <span data-ttu-id="4e6b0-221">Funktion</span><span class="sxs-lookup"><span data-stu-id="4e6b0-221">Function</span></span>
--- | ---
[<span data-ttu-id="4e6b0-222">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="4e6b0-222">dotnet add reference</span></span>](dotnet-add-reference.md) | <span data-ttu-id="4e6b0-223">Fügt einen Projektverweis hinzu.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-223">Adds a project reference.</span></span>
[<span data-ttu-id="4e6b0-224">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="4e6b0-224">dotnet list reference</span></span>](dotnet-list-reference.md) | <span data-ttu-id="4e6b0-225">Listet Projektverweise auf.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-225">Lists project references.</span></span>
[<span data-ttu-id="4e6b0-226">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="4e6b0-226">dotnet remove reference</span></span>](dotnet-remove-reference.md) | <span data-ttu-id="4e6b0-227">Entfernt einen Projektverweis.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-227">Removes a project reference.</span></span>

### <a name="nuget-packages"></a><span data-ttu-id="4e6b0-228">NuGet-Pakete</span><span class="sxs-lookup"><span data-stu-id="4e6b0-228">NuGet packages</span></span>

<span data-ttu-id="4e6b0-229">Befehl</span><span class="sxs-lookup"><span data-stu-id="4e6b0-229">Command</span></span> | <span data-ttu-id="4e6b0-230">Funktion</span><span class="sxs-lookup"><span data-stu-id="4e6b0-230">Function</span></span>
--- | ---
[<span data-ttu-id="4e6b0-231">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="4e6b0-231">dotnet add package</span></span>](dotnet-add-package.md) | <span data-ttu-id="4e6b0-232">Fügt ein NuGet-Paket hinzu.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-232">Adds a NuGet package.</span></span>
[<span data-ttu-id="4e6b0-233">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="4e6b0-233">dotnet remove package</span></span>](dotnet-remove-package.md) | <span data-ttu-id="4e6b0-234">Entfernt ein NuGet-Paket.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-234">Removes a NuGet package.</span></span>

### <a name="nuget-commands"></a><span data-ttu-id="4e6b0-235">NuGet-Befehle</span><span class="sxs-lookup"><span data-stu-id="4e6b0-235">NuGet commands</span></span>

<span data-ttu-id="4e6b0-236">Befehl</span><span class="sxs-lookup"><span data-stu-id="4e6b0-236">Command</span></span> | <span data-ttu-id="4e6b0-237">Funktion</span><span class="sxs-lookup"><span data-stu-id="4e6b0-237">Function</span></span>
--- | ---
[<span data-ttu-id="4e6b0-238">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="4e6b0-238">dotnet nuget delete</span></span>](dotnet-nuget-delete.md) | <span data-ttu-id="4e6b0-239">Löscht ein Paket vom Server oder hebt dessen Auflistung auf.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-239">Deletes or unlists a package from the server.</span></span>
[<span data-ttu-id="4e6b0-240">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="4e6b0-240">dotnet nuget push</span></span>](dotnet-nuget-push.md) | <span data-ttu-id="4e6b0-241">Überträgt ein Paket auf den Server und veröffentlicht es.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-241">Pushes a package to the server and publishes it.</span></span>
[<span data-ttu-id="4e6b0-242">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="4e6b0-242">dotnet nuget locals</span></span>](dotnet-nuget-locals.md) | <span data-ttu-id="4e6b0-243">Löscht lokale NuGet-Ressourcen, z.B. den http-Anforderungscache, den temporären Cache oder den Ordner mit globalen Paketen auf dem Computer, oder listet diese Ressourcen auf.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-243">Clears or lists local NuGet resources such as http-request cache, temporary cache, or machine-wide global packages folder.</span></span>
[<span data-ttu-id="4e6b0-244">dotnet nuget add source</span><span class="sxs-lookup"><span data-stu-id="4e6b0-244">dotnet nuget add source</span></span>](dotnet-nuget-add-source.md) | <span data-ttu-id="4e6b0-245">Hiermit fügen Sie eine NuGet-Quelle hinzu.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-245">Adds a NuGet source.</span></span>
[<span data-ttu-id="4e6b0-246">dotnet nuget disable source</span><span class="sxs-lookup"><span data-stu-id="4e6b0-246">dotnet nuget disable source</span></span>](dotnet-nuget-disable-source.md) | <span data-ttu-id="4e6b0-247">Hiermit deaktivieren Sie eine NuGet-Quelle.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-247">Disables a NuGet source.</span></span>
[<span data-ttu-id="4e6b0-248">dotnet nuget enable source</span><span class="sxs-lookup"><span data-stu-id="4e6b0-248">dotnet nuget enable source</span></span>](dotnet-nuget-enable-source.md) | <span data-ttu-id="4e6b0-249">Hiermit aktivieren Sie eine NuGet-Quelle.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-249">Enables a NuGet source.</span></span>
[<span data-ttu-id="4e6b0-250">dotnet nuget list source</span><span class="sxs-lookup"><span data-stu-id="4e6b0-250">dotnet nuget list source</span></span>](dotnet-nuget-list-source.md) | <span data-ttu-id="4e6b0-251">Hiermit werden alle konfigurierten NuGet-Quellen aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-251">Lists all configured NuGet sources.</span></span>
[<span data-ttu-id="4e6b0-252">dotnet nuget remove source</span><span class="sxs-lookup"><span data-stu-id="4e6b0-252">dotnet nuget remove source</span></span>](dotnet-nuget-remove-source.md) | <span data-ttu-id="4e6b0-253">Hiermit entfernen Sie eine NuGet-Quelle.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-253">Removes a NuGet source.</span></span>
[<span data-ttu-id="4e6b0-254">dotnet nuget update source</span><span class="sxs-lookup"><span data-stu-id="4e6b0-254">dotnet nuget update source</span></span>](dotnet-nuget-update-source.md) | <span data-ttu-id="4e6b0-255">Hiermit aktualisieren Sie eine NuGet-Quelle.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-255">Updates a NuGet source.</span></span>

### <a name="global-tool-path-and-local-tools-commands"></a><span data-ttu-id="4e6b0-256">Befehle für globale, Toolpfad- und lokale Tools</span><span class="sxs-lookup"><span data-stu-id="4e6b0-256">Global, tool-path, and local tools commands</span></span>

<span data-ttu-id="4e6b0-257">Tools sind Konsolenanwendungen, die über NuGet-Pakete installiert und über die Eingabeaufforderung aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-257">Tools are console applications that are installed from NuGet packages and are invoked from the command prompt.</span></span> <span data-ttu-id="4e6b0-258">Sie können Tools selbst schreiben oder Drittanbietertools installieren.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-258">You can write tools yourself or install tools written by third parties.</span></span> <span data-ttu-id="4e6b0-259">Tools werden auch als globale Tools, Toolpfadtools und lokale Tools bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-259">Tools are also known as global tools, tool-path tools, and local tools.</span></span> <span data-ttu-id="4e6b0-260">Weitere Informationen finden Sie unter [Übersicht über .NET Core-Tools](global-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4e6b0-260">For more information, see [.NET Core tools overview](global-tools.md).</span></span> <span data-ttu-id="4e6b0-261">Globale und Toolpfadtools sind ab .NET Core SDK 2.1 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-261">Global and tool-path tools are available starting with .NET Core SDK 2.1.</span></span> <span data-ttu-id="4e6b0-262">Lokale Tools sind ab .NET Core SDK 3.0 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-262">Local tools are available starting with .NET Core SDK 3.0.</span></span>

<span data-ttu-id="4e6b0-263">Befehl</span><span class="sxs-lookup"><span data-stu-id="4e6b0-263">Command</span></span> | <span data-ttu-id="4e6b0-264">Funktion</span><span class="sxs-lookup"><span data-stu-id="4e6b0-264">Function</span></span>
--- | ---
[<span data-ttu-id="4e6b0-265">dotnet tool install</span><span class="sxs-lookup"><span data-stu-id="4e6b0-265">dotnet tool install</span></span>](dotnet-tool-install.md) | <span data-ttu-id="4e6b0-266">Installiert ein Tool auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-266">Installs a tool on your machine.</span></span>
[<span data-ttu-id="4e6b0-267">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="4e6b0-267">dotnet tool list</span></span>](dotnet-tool-list.md) | <span data-ttu-id="4e6b0-268">Listet alle globalen, Toolpfad- und lokalen Tools auf, die derzeit auf Ihrem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-268">Lists all global, tool-path, or local tools currently installed on your machine.</span></span>
[<span data-ttu-id="4e6b0-269">dotnet tool uninstall</span><span class="sxs-lookup"><span data-stu-id="4e6b0-269">dotnet tool uninstall</span></span>](dotnet-tool-uninstall.md) | <span data-ttu-id="4e6b0-270">Deinstalliert ein Tool von Ihrem Computer.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-270">Uninstalls a tool from your machine.</span></span>
[<span data-ttu-id="4e6b0-271">dotnet tool update</span><span class="sxs-lookup"><span data-stu-id="4e6b0-271">dotnet tool update</span></span>](dotnet-tool-update.md) | <span data-ttu-id="4e6b0-272">Aktualisiert ein Tool, das auf Ihrem Computer installiert ist.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-272">Updates a tool that is installed on your machine.</span></span>

### <a name="additional-tools"></a><span data-ttu-id="4e6b0-273">Weitere Tools</span><span class="sxs-lookup"><span data-stu-id="4e6b0-273">Additional tools</span></span>

<span data-ttu-id="4e6b0-274">Beginnend mit .NET Core SDK 2.1.300 steht eine Reihe von Tools, die nur auf Projektbasis unter Verwendung von `DotnetCliToolReference` verfügbar waren, jetzt als Teil des .NET Core SDK zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-274">Starting with .NET Core SDK 2.1.300, a number of tools that were available only on a per project basis using `DotnetCliToolReference` are now available as part of the .NET Core SDK.</span></span> <span data-ttu-id="4e6b0-275">Diese Tools werden in der folgenden Tabelle aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="4e6b0-275">These tools are listed in the following table:</span></span>

| <span data-ttu-id="4e6b0-276">Tool</span><span class="sxs-lookup"><span data-stu-id="4e6b0-276">Tool</span></span>                                              | <span data-ttu-id="4e6b0-277">Funktion</span><span class="sxs-lookup"><span data-stu-id="4e6b0-277">Function</span></span>                                                     |
| ------------------------------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="4e6b0-278">dev-certs</span><span class="sxs-lookup"><span data-stu-id="4e6b0-278">dev-certs</span></span>                                         | <span data-ttu-id="4e6b0-279">Erstellt und verwaltet Entwicklungszertifikate.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-279">Creates and manages development certificates.</span></span>                |
| [<span data-ttu-id="4e6b0-280">ef</span><span class="sxs-lookup"><span data-stu-id="4e6b0-280">ef</span></span>](/ef/core/miscellaneous/cli/dotnet)           | <span data-ttu-id="4e6b0-281">Entity Framework Core-Befehlszeilentools.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-281">Entity Framework Core command-line tools.</span></span>                    |
| <span data-ttu-id="4e6b0-282">sql-cache</span><span class="sxs-lookup"><span data-stu-id="4e6b0-282">sql-cache</span></span>                                         | <span data-ttu-id="4e6b0-283">SQL Server-Cache-Befehlszeilentools.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-283">SQL Server cache command-line tools.</span></span>                         |
| [<span data-ttu-id="4e6b0-284">user-secrets</span><span class="sxs-lookup"><span data-stu-id="4e6b0-284">user-secrets</span></span>](/aspnet/core/security/app-secrets) | <span data-ttu-id="4e6b0-285">Verwaltet die Entwicklung von Benutzergeheimnissen.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-285">Manages development user secrets.</span></span>                            |
| [<span data-ttu-id="4e6b0-286">watch</span><span class="sxs-lookup"><span data-stu-id="4e6b0-286">watch</span></span>](/aspnet/core/tutorials/dotnet-watch)      | <span data-ttu-id="4e6b0-287">Startet einen Datei-Watcher, der einen Befehl ausführt, wenn sich Dateien ändern.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-287">Starts a file watcher that runs a command when files change.</span></span> |

<span data-ttu-id="4e6b0-288">Geben Sie `dotnet <tool-name> --help` ein, um weitere Informationen zu den einzelnen Tools zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-288">For more information about each tool, type `dotnet <tool-name> --help`.</span></span>

## <a name="examples"></a><span data-ttu-id="4e6b0-289">Beispiele</span><span class="sxs-lookup"><span data-stu-id="4e6b0-289">Examples</span></span>

<span data-ttu-id="4e6b0-290">Erstellen einer neuen .NET Core-Konsolenanwendung:</span><span class="sxs-lookup"><span data-stu-id="4e6b0-290">Create a new .NET Core console application:</span></span>

```dotnetcli
dotnet new console
```

<span data-ttu-id="4e6b0-291">Erstellen eines Projekts und seiner Abhängigkeiten in einem vorgegebenen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="4e6b0-291">Build a project and its dependencies in a given directory:</span></span>

```dotnetcli
dotnet build
```

<span data-ttu-id="4e6b0-292">Ausführen einer Anwendung:</span><span class="sxs-lookup"><span data-stu-id="4e6b0-292">Run an application:</span></span>

```dotnetcli
dotnet myapp.dll
```

## <a name="environment-variables"></a><span data-ttu-id="4e6b0-293">Umgebungsvariablen</span><span class="sxs-lookup"><span data-stu-id="4e6b0-293">Environment variables</span></span>

- <span data-ttu-id="4e6b0-294">`DOTNET_ROOT`, `DOTNET_ROOT(x86)`</span><span class="sxs-lookup"><span data-stu-id="4e6b0-294">`DOTNET_ROOT`, `DOTNET_ROOT(x86)`</span></span>

  <span data-ttu-id="4e6b0-295">Gibt den Speicherort der .NET Core-Runtimes an, wenn sie nicht am Standardspeicherort installiert sind.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-295">Specifies the location of the .NET Core runtimes, if they are not installed in the default location.</span></span> <span data-ttu-id="4e6b0-296">Der Standardspeicherort unter Windows ist `C:\Program Files\dotnet`.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-296">The default location on Windows is `C:\Program Files\dotnet`.</span></span> <span data-ttu-id="4e6b0-297">Der Standardspeicherort unter Linux und macOS ist `/usr/share/dotnet`.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-297">The default location on Linux and macOS is `/usr/share/dotnet`.</span></span> <span data-ttu-id="4e6b0-298">Diese Umgebungsvariable wird nur beim Ausführen von Anwendungen über generierte ausführbare Dateien (Apphosts) verwendet.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-298">This environment variable is used only when running apps via generated executables (apphosts).</span></span> <span data-ttu-id="4e6b0-299">`DOTNET_ROOT(x86)` wird stattdessen verwendet, wenn eine ausführbare 32-Bit-Datei auf einem 64-Bit-Betriebssystem ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-299">`DOTNET_ROOT(x86)` is used instead when running a 32-bit executable on a 64-bit OS.</span></span>

- `DOTNET_PACKAGES`

  <span data-ttu-id="4e6b0-300">Der Ordner für globale Pakete.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-300">The global packages folder.</span></span> <span data-ttu-id="4e6b0-301">Wenn er nicht festgelegt wird, wird standardmäßig `~/.nuget/packages` unter Unix oder `%userprofile%\.nuget\packages` unter Windows verwendet.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-301">If not set, it defaults to `~/.nuget/packages` on Unix or `%userprofile%\.nuget\packages` on Windows.</span></span>

- `DOTNET_SERVICING`

  <span data-ttu-id="4e6b0-302">Gibt den Speicherort des Wartungsindex an, der vom freigegebenen Host verwendet wird, wenn die Laufzeit geladen wird.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-302">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

- `DOTNET_NOLOGO`

  <span data-ttu-id="4e6b0-303">Gibt an, ob bei der ersten Ausführung .NET Core-Willkommens- und Telemetriemeldungen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-303">Specifies whether .NET Core welcome and telemetry messages are displayed on first run.</span></span> <span data-ttu-id="4e6b0-304">Bei Festlegung auf `true` werden diese Meldungen unterdrückt (akzeptierte Werte: `true`, `1` oder `yes`), bei Festlegung auf `false` werden die Meldungen zugelassen (akzeptierte Werte: `false`, `0` oder `no`).</span><span class="sxs-lookup"><span data-stu-id="4e6b0-304">Set to `true` to mute these messages (values `true`, `1`, or `yes` accepted) or set to `false` to allow (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="4e6b0-305">Sofern nicht festgelegt, lautet der Standardwert `false`, und die Meldungen werden bei der ersten Ausführung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-305">If not set, the default is `false` and the messages will be displayed on first run.</span></span> <span data-ttu-id="4e6b0-306">Dieses Flag besitzt keine Auswirkung auf die Telemetrie (siehe `DOTNET_CLI_TELEMETRY_OPTOUT` zum Deaktivieren der Übermittlung von Telemetriedaten).</span><span class="sxs-lookup"><span data-stu-id="4e6b0-306">This flag has no effect on telemetry (see `DOTNET_CLI_TELEMETRY_OPTOUT` for opting out of sending telemetry).</span></span>

- `DOTNET_CLI_TELEMETRY_OPTOUT`

  <span data-ttu-id="4e6b0-307">Gibt an, ob Daten zur Nutzung von .NET Core-Tools gesammelt und an Microsoft gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-307">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="4e6b0-308">Legen Sie `true` fest, um die Telemetriefunktion zu deaktivieren (Wert `true`, `1` oder `yes` wird akzeptiert).</span><span class="sxs-lookup"><span data-stu-id="4e6b0-308">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="4e6b0-309">Legen Sie andernfalls `false` fest, um die Telemetriefunktionen zu aktivieren (Wert `false`, `0` oder `no` wird akzeptiert).</span><span class="sxs-lookup"><span data-stu-id="4e6b0-309">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="4e6b0-310">Ohne Festlegung ist der Standardwert `false`, und die Telemetriefunktion ist aktiviert.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-310">If not set, the default is `false` and the telemetry feature is active.</span></span>

- `DOTNET_MULTILEVEL_LOOKUP`

  <span data-ttu-id="4e6b0-311">Gibt an, ob die .NET Core-Runtime, das freigegebene Framework oder das SDK vom globalen Speicherort aus aufgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-311">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="4e6b0-312">Ohne Festlegung ist der Standardwert 1 (logisch `true`).</span><span class="sxs-lookup"><span data-stu-id="4e6b0-312">If not set, it defaults to 1 (logical `true`).</span></span> <span data-ttu-id="4e6b0-313">Auf 0 (logisch `false`) festgelegt, um nicht vom globalen Speicherort aus aufzulösen und isolierte .NET Core-Installationen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-313">Set to 0 (logical `false`) to not resolve from the global location and have isolated .NET Core installations.</span></span> <span data-ttu-id="4e6b0-314">Weitere Informationen zu Lookup mit mehreren Ebenen finden Sie unter [Multi-level SharedFX lookup (SharedFX-Lookup mit mehreren Ebenen)](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span><span class="sxs-lookup"><span data-stu-id="4e6b0-314">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

- <span data-ttu-id="4e6b0-315">`DOTNET_ROLL_FORWARD` **Verfügbar ab .NET Core 3.x SDK.**</span><span class="sxs-lookup"><span data-stu-id="4e6b0-315">`DOTNET_ROLL_FORWARD` **Available starting with .NET Core 3.x SDK.**</span></span>

  <span data-ttu-id="4e6b0-316">Bestimmt das Rollforwardverhalten.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-316">Determines roll forward behavior.</span></span> <span data-ttu-id="4e6b0-317">Weitere Informationen finden Sie unter der Option `--roll-forward` weiter oben in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-317">For more information, see the `--roll-forward` option earlier in this article.</span></span>

- <span data-ttu-id="4e6b0-318">`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX` **Verfügbar im .NET Core 2.x SDK.**</span><span class="sxs-lookup"><span data-stu-id="4e6b0-318">`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX` **Available in .NET Core 2.x SDK.**</span></span>

  <span data-ttu-id="4e6b0-319">Deaktiviert Rollforward der Nebenversion, wenn `0` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-319">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="4e6b0-320">Weitere Informationen finden Sie unter [Rollforward](../whats-new/dotnet-core-2-1.md#roll-forward).</span><span class="sxs-lookup"><span data-stu-id="4e6b0-320">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

- `DOTNET_CLI_UI_LANGUAGE`

  <span data-ttu-id="4e6b0-321">Legt die Sprache der CLI-Benutzeroberfläche mit einem Gebietsschemawert wie `en-us` fest.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-321">Sets the language of the CLI UI using a locale value such as `en-us`.</span></span> <span data-ttu-id="4e6b0-322">Die unterstützten Werte sind identisch mit denen für Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-322">The supported values are the same as for Visual Studio.</span></span> <span data-ttu-id="4e6b0-323">Weitere Informationen finden Sie im Abschnitt zum Ändern der Sprache des Installationsprogramms in der [Visual Studio-Installationsdokumentation](https://docs.microsoft.com/visualstudio/install/install-visual-studio?view=vs-2019).</span><span class="sxs-lookup"><span data-stu-id="4e6b0-323">For more information, see the section on changing the installer language in the [Visual Studio installation documentation](https://docs.microsoft.com/visualstudio/install/install-visual-studio?view=vs-2019).</span></span> <span data-ttu-id="4e6b0-324">Es gelten die Regeln des .NET-Ressourcen-Managers, sodass Sie keine genaue Übereinstimmung auswählen müssen, sondern auch Nachfolger in der `CultureInfo`-Struktur auswählen können.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-324">The .NET resource manager rules apply, so you don't have to pick an exact match&mdash;you can also pick descendants in the `CultureInfo` tree.</span></span> <span data-ttu-id="4e6b0-325">Bei einer Festlegung auf `fr-CA` findet und verwendet die Befehlszeilenschnittstelle z. B. die `fr`-Übersetzungen.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-325">For example, if you set it to `fr-CA`, the CLI will find and use the `fr` translations.</span></span> <span data-ttu-id="4e6b0-326">Wenn Sie eine nicht unterstützte Sprache festlegen, greift die Befehlszeilenschnittstelle auf Englisch zurück.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-326">If you set it to a language that is not supported, the CLI falls back to English.</span></span>

- `DOTNET_DISABLE_GUI_ERRORS`

  <span data-ttu-id="4e6b0-327">Für generierte ausführbare Dateien mit aktivierter Benutzeroberfläche – deaktiviert das Dialogfeld-Popupfenster, das normalerweise bei bestimmten Fehlerklassen angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-327">For GUI-enabled generated executables - disables dialog popup, which normally shows for certain classes of errors.</span></span> <span data-ttu-id="4e6b0-328">Es schreibt nur an `stderr` und beendet sich nur in diesen Fällen.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-328">It only writes to `stderr` and exits in those cases.</span></span>
  
- `DOTNET_ADDITIONAL_DEPS`

  <span data-ttu-id="4e6b0-329">Entspricht der CLI-Option `--additional-deps`.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-329">Equivalent to CLI option `--additional-deps`.</span></span>

- `DOTNET_RUNTIME_ID`

  <span data-ttu-id="4e6b0-330">Setzt die erkannte RID außer Kraft.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-330">Overrides the detected RID.</span></span>

- `DOTNET_SHARED_STORE`

  <span data-ttu-id="4e6b0-331">Speicherort des „gemeinsamen Speichers“, auf den die Assemblyauflösung in einigen Fällen zurückgreift.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-331">Location of the "shared store" which assembly resolution falls back to in some cases.</span></span>

- `DOTNET_STARTUP_HOOKS`

  <span data-ttu-id="4e6b0-332">Liste der Assemblys zum Laden und Ausführen von Startuphooks.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-332">List of assemblies to load and execute startup hooks from.</span></span>

- <span data-ttu-id="4e6b0-333">`COREHOST_TRACE`, `COREHOST_TRACEFILE`, `COREHOST_TRACE_VERBOSITY`</span><span class="sxs-lookup"><span data-stu-id="4e6b0-333">`COREHOST_TRACE`, `COREHOST_TRACEFILE`, `COREHOST_TRACE_VERBOSITY`</span></span>

  <span data-ttu-id="4e6b0-334">Steuert die Diagnoseablaufverfolgung von den Hostingkomponenten wie `dotnet.exe`, `hostfxr` und `hostpolicy`.</span><span class="sxs-lookup"><span data-stu-id="4e6b0-334">Controls diagnostics tracing from the hosting components, such as `dotnet.exe`, `hostfxr`, and `hostpolicy`.</span></span>

## <a name="see-also"></a><span data-ttu-id="4e6b0-335">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4e6b0-335">See also</span></span>

- [<span data-ttu-id="4e6b0-336">Laufzeitkonfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="4e6b0-336">Runtime Configuration Files</span></span>](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)
- [<span data-ttu-id="4e6b0-337">Konfigurationseinstellungen für die .NET Core-Runtime</span><span class="sxs-lookup"><span data-stu-id="4e6b0-337">.NET Core run-time configuration settings</span></span>](../run-time-config/index.md)
