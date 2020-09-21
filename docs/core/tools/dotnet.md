---
title: dotnet-Befehl
description: Erfahren Sie mehr über den dotnet-Befehl (den generischen Treiber für die .NET Core-CLI) und dessen Verwendung.
ms.date: 02/13/2020
ms.openlocfilehash: 4476dcf36455e0dc1b89712409818cf7e0352f2c
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90537664"
---
# <a name="dotnet-command"></a><span data-ttu-id="e8cde-103">dotnet-Befehl</span><span class="sxs-lookup"><span data-stu-id="e8cde-103">dotnet command</span></span>

<span data-ttu-id="e8cde-104">**Dieser Artikel gilt für:** ✔️ .NET Core 2.1 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="e8cde-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="e8cde-105">name</span><span class="sxs-lookup"><span data-stu-id="e8cde-105">Name</span></span>

<span data-ttu-id="e8cde-106">`dotnet`: Der generische Treiber für die .NET Core-CLI.</span><span class="sxs-lookup"><span data-stu-id="e8cde-106">`dotnet` - The generic driver for the .NET Core CLI.</span></span>

## <a name="synopsis"></a><span data-ttu-id="e8cde-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="e8cde-107">Synopsis</span></span>

<span data-ttu-id="e8cde-108">So erhalten Sie Informationen über die verfügbaren Befehle und die Umgebung</span><span class="sxs-lookup"><span data-stu-id="e8cde-108">To get information about the available commands and the environment:</span></span>

```dotnetcli
dotnet [--version] [--info] [--list-runtimes] [--list-sdks]

dotnet -h|--help
```

<span data-ttu-id="e8cde-109">So führen Sie einen Befehl aus (erfordert eine SDK-Installation)</span><span class="sxs-lookup"><span data-stu-id="e8cde-109">To run a command (requires SDK installation):</span></span>

```dotnetcli
dotnet <COMMAND> [-d|--diagnostics] [-h|--help] [--verbosity <LEVEL>]
    [command-options] [arguments]
```

<span data-ttu-id="e8cde-110">So führen Sie eine Anwendung aus</span><span class="sxs-lookup"><span data-stu-id="e8cde-110">To run an application:</span></span>

```dotnetcli
dotnet [--additionalprobingpath <PATH>] [--additional-deps <PATH>]
    [--fx-version <VERSION>]  [--roll-forward <SETTING>]
    <PATH_TO_APPLICATION> [arguments]

dotnet exec [--additionalprobingpath] [--additional-deps <PATH>]
    [--fx-version <VERSION>]  [--roll-forward <SETTING>]
    <PATH_TO_APPLICATION> [arguments]
```

<span data-ttu-id="e8cde-111">`--roll-forward` ist seit .NET Core 3.x verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e8cde-111">`--roll-forward` is available since .NET Core 3.x.</span></span> <span data-ttu-id="e8cde-112">Verwenden Sie `--roll-forward-on-no-candidate-fx` für .NET Core 2.x.</span><span class="sxs-lookup"><span data-stu-id="e8cde-112">Use `--roll-forward-on-no-candidate-fx` for .NET Core 2.x.</span></span>

## <a name="description"></a><span data-ttu-id="e8cde-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e8cde-113">Description</span></span>

<span data-ttu-id="e8cde-114">Der Befehl `dotnet` hat zwei Funktionen:</span><span class="sxs-lookup"><span data-stu-id="e8cde-114">The `dotnet` command has two functions:</span></span>

- <span data-ttu-id="e8cde-115">Es stellt Befehle für die Arbeit mit .NET Core-Projekten bereit.</span><span class="sxs-lookup"><span data-stu-id="e8cde-115">It provides commands for working with .NET Core projects.</span></span>

  <span data-ttu-id="e8cde-116">Beispielsweise erstellt [`dotnet build`](dotnet-build.md) ein Projekt.</span><span class="sxs-lookup"><span data-stu-id="e8cde-116">For example, [`dotnet build`](dotnet-build.md) builds a project.</span></span> <span data-ttu-id="e8cde-117">Jeder Befehl definiert seine eigenen Optionen und Argumente.</span><span class="sxs-lookup"><span data-stu-id="e8cde-117">Each command defines its own options and arguments.</span></span> <span data-ttu-id="e8cde-118">Alle Befehle unterstützen die Option `--help` zum Ausdrucken einer kurzen Dokumentation über die Verwendung des Befehls.</span><span class="sxs-lookup"><span data-stu-id="e8cde-118">All commands support the `--help` option for printing out brief documentation about how to use the command.</span></span>

- <span data-ttu-id="e8cde-119">Sie führt .NET Core-Anwendungen aus.</span><span class="sxs-lookup"><span data-stu-id="e8cde-119">It runs .NET Core applications.</span></span>

  <span data-ttu-id="e8cde-120">Sie geben den Pfad zu einer `.dll`-Datei einer Anwendung zur Ausführung der Anwendung an.</span><span class="sxs-lookup"><span data-stu-id="e8cde-120">You specify the path to an application `.dll` file to run the application.</span></span>  <span data-ttu-id="e8cde-121">Das Ausführen der Anwendung bedeutet, den Einstiegspunkt zu finden und auszuführen. Im Falle von Konsolen-Apps ist dies die `Main`-Methode.</span><span class="sxs-lookup"><span data-stu-id="e8cde-121">To run the application means to find and execute the entry point, which in the case of console apps is the `Main` method.</span></span> <span data-ttu-id="e8cde-122">Beispiel: `dotnet myapp.dll` führt die Anwendung `myapp` aus.</span><span class="sxs-lookup"><span data-stu-id="e8cde-122">For example, `dotnet myapp.dll` runs the `myapp` application.</span></span> <span data-ttu-id="e8cde-123">Weitere Informationen über Bereitstellungsoptionen finden Sie unter [.NET Core-Anwendungsbereitstellung](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="e8cde-123">See [.NET Core application deployment](../deploying/index.md) to learn about deployment options.</span></span>

## <a name="options"></a><span data-ttu-id="e8cde-124">Optionen</span><span class="sxs-lookup"><span data-stu-id="e8cde-124">Options</span></span>

<span data-ttu-id="e8cde-125">Es gibt verschiedene Optionen für `dotnet` allein, für die Ausführung eines Befehls und für die Ausführung einer Anwendung.</span><span class="sxs-lookup"><span data-stu-id="e8cde-125">Different options are available for `dotnet` by itself, for running a command, and for running an application.</span></span>

### <a name="options-for-dotnet-by-itself"></a><span data-ttu-id="e8cde-126">Optionen für dotnet</span><span class="sxs-lookup"><span data-stu-id="e8cde-126">Options for dotnet by itself</span></span>

<span data-ttu-id="e8cde-127">Die folgenden Optionen gelten für `dotnet` allein.</span><span class="sxs-lookup"><span data-stu-id="e8cde-127">The following options are for `dotnet` by itself.</span></span> <span data-ttu-id="e8cde-128">Beispielsweise `dotnet --info`.</span><span class="sxs-lookup"><span data-stu-id="e8cde-128">For example, `dotnet --info`.</span></span> <span data-ttu-id="e8cde-129">Sie drucken Informationen über die Umgebung aus.</span><span class="sxs-lookup"><span data-stu-id="e8cde-129">They print out information about the environment.</span></span>

- **`--info`**

  <span data-ttu-id="e8cde-130">Gibt ausführliche Informationen über eine .NET Core-Installation und die Computerumgebung aus, z.B. das aktuelle Betriebssystem und den Commit-SHA für die .NET Core-Version.</span><span class="sxs-lookup"><span data-stu-id="e8cde-130">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

- **`--version`**

  <span data-ttu-id="e8cde-131">Druckt die Version des verwendeten .NET Core-SDK aus.</span><span class="sxs-lookup"><span data-stu-id="e8cde-131">Prints out the version of the .NET Core SDK in use.</span></span>

- **`--list-runtimes`**

  <span data-ttu-id="e8cde-132">Druckt eine Liste der installierten .NET Core-Runtimes aus.</span><span class="sxs-lookup"><span data-stu-id="e8cde-132">Prints out a list of the installed .NET Core runtimes.</span></span> <span data-ttu-id="e8cde-133">Eine x86-Version des SDK listet nur x86-Runtimes auf, und eine x64-Version des SDK listet nur x64-Runtimes auf.</span><span class="sxs-lookup"><span data-stu-id="e8cde-133">An x86 version of the SDK lists only x86 runtimes, and an x64 version of the SDK lists only x64 runtimes.</span></span>

- **`--list-sdks`**

  <span data-ttu-id="e8cde-134">Druckt eine Liste der installierten .NET Core-SDKs aus.</span><span class="sxs-lookup"><span data-stu-id="e8cde-134">Prints out a list of the installed .NET Core SDKs.</span></span>

- **`-h|--help`**

  <span data-ttu-id="e8cde-135">Druckt eine Liste der verfügbaren Befehle aus.</span><span class="sxs-lookup"><span data-stu-id="e8cde-135">Prints out a list of available commands.</span></span>

### <a name="sdk-options-for-running-a-command"></a><span data-ttu-id="e8cde-136">SDK-Optionen zum Ausführen eines Befehls</span><span class="sxs-lookup"><span data-stu-id="e8cde-136">SDK options for running a command</span></span>

<span data-ttu-id="e8cde-137">Die folgenden Optionen gelten für `dotnet` mit einem Befehl.</span><span class="sxs-lookup"><span data-stu-id="e8cde-137">The following options are for `dotnet` with a command.</span></span> <span data-ttu-id="e8cde-138">Beispielsweise `dotnet build --help`.</span><span class="sxs-lookup"><span data-stu-id="e8cde-138">For example, `dotnet build --help`.</span></span>

- **`-d|--diagnostics`**

  <span data-ttu-id="e8cde-139">Ermöglicht die diagnostische Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="e8cde-139">Enables diagnostic output.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="e8cde-140">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="e8cde-140">Sets the verbosity level of the command.</span></span> <span data-ttu-id="e8cde-141">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="e8cde-141">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="e8cde-142">Nicht in jedem Befehl unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e8cde-142">Not supported in every command.</span></span> <span data-ttu-id="e8cde-143">Auf der Seite der einzelnen Befehle finden Sie heraus, ob diese Option verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="e8cde-143">See specific command page to determine if this option is available.</span></span>

- **`-h|--help`**

  <span data-ttu-id="e8cde-144">Gibt Dokumentation für einen bestimmten Befehl aus, z.B. `dotnet build --help`.</span><span class="sxs-lookup"><span data-stu-id="e8cde-144">Prints out documentation for a given command, such as `dotnet build --help`.</span></span>

- **`command options`**

  <span data-ttu-id="e8cde-145">Jeder Befehl definiert Optionen, die für diesen Befehl spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="e8cde-145">Each command defines options specific to that command.</span></span> <span data-ttu-id="e8cde-146">Eine Liste der verfügbaren Optionen finden Sie auf einer speziellen Befehlsseite.</span><span class="sxs-lookup"><span data-stu-id="e8cde-146">See specific command page for a list of available options.</span></span>

### <a name="runtime-options"></a><span data-ttu-id="e8cde-147">Laufzeitoptionen</span><span class="sxs-lookup"><span data-stu-id="e8cde-147">Runtime options</span></span>

<span data-ttu-id="e8cde-148">Die folgenden Optionen sind verfügbar, wenn `dotnet` eine Anwendung ausführt.</span><span class="sxs-lookup"><span data-stu-id="e8cde-148">The following options are available when `dotnet` runs an application.</span></span> <span data-ttu-id="e8cde-149">Beispielsweise `dotnet myapp.dll --roll-forward Major`.</span><span class="sxs-lookup"><span data-stu-id="e8cde-149">For example, `dotnet myapp.dll --roll-forward Major`.</span></span>

- **`--additionalprobingpath <PATH>`**

  <span data-ttu-id="e8cde-150">Pfad, der die Suchrichtlinie und die zu suchenden Assemblys enthält.</span><span class="sxs-lookup"><span data-stu-id="e8cde-150">Path containing probing policy and assemblies to probe.</span></span>

- **`--additional-deps <PATH>`**

  <span data-ttu-id="e8cde-151">Pfad zu einer zusätzlichen *.deps.json*-Datei.</span><span class="sxs-lookup"><span data-stu-id="e8cde-151">Path to an additional *.deps.json* file.</span></span> <span data-ttu-id="e8cde-152">Eine *deps.json*-Datei enthält eine Liste mit Abhängigkeiten, Kompilierungsabhängigkeiten und Versionsinformationen, die verwendet werden, um Assemblykonflikte zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="e8cde-152">A *deps.json* file contains a list of dependencies, compilation dependencies, and version information used to address assembly conflicts.</span></span> <span data-ttu-id="e8cde-153">Weitere Informationen finden Sie auf GitHub unter [Laufzeitkonfigurationsdateien](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="e8cde-153">For more information, see [Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) on GitHub.</span></span>

- **`--depsfile <PATH_TO_DEPSFILE>`**

  <span data-ttu-id="e8cde-154">Pfad zur *deps.json*-Datei.</span><span class="sxs-lookup"><span data-stu-id="e8cde-154">Path to the *deps.json* file.</span></span> <span data-ttu-id="e8cde-155">Eine Datei mit Namen *deps.json* ist eine Konfigurationsdatei, die Informationen zu Abhängigkeiten enthält, die zum Ausführen der Anwendung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="e8cde-155">A *deps.json* file is a configuration file that contains information about dependencies necessary to run the application.</span></span> <span data-ttu-id="e8cde-156">Diese Datei wird vom .NET Core SDK generiert.</span><span class="sxs-lookup"><span data-stu-id="e8cde-156">This file is generated by the .NET Core SDK.</span></span>

- **`--runtimeconfig`**

  <span data-ttu-id="e8cde-157">Der Pfad zu einer *runtimeconfig.json*-Datei.</span><span class="sxs-lookup"><span data-stu-id="e8cde-157">Path to a *runtimeconfig.json* file.</span></span> <span data-ttu-id="e8cde-158">Eine *runtimeconfig.json*-Datei ist eine Konfigurationsdatei mit Einstellungen für die Runtime.</span><span class="sxs-lookup"><span data-stu-id="e8cde-158">A *runtimeconfig.json* file is a configuration file that contains run-time settings.</span></span> <span data-ttu-id="e8cde-159">Weitere Informationen finden Sie unter [Konfigurationseinstellungen für die .NET Core-Runtime](../run-time-config/index.md#runtimeconfigjson).</span><span class="sxs-lookup"><span data-stu-id="e8cde-159">For more information, see [.NET Core run-time configuration settings](../run-time-config/index.md#runtimeconfigjson).</span></span>

- <span data-ttu-id="e8cde-160">**`--roll-forward <SETTING>`** **Verfügbar ab .NET Core SDK 3.0.**</span><span class="sxs-lookup"><span data-stu-id="e8cde-160">**`--roll-forward <SETTING>`** **Available starting with .NET Core SDK 3.0.**</span></span>

  <span data-ttu-id="e8cde-161">Steuert, wie der Rollforward auf die App angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="e8cde-161">Controls how roll forward is applied to the app.</span></span> <span data-ttu-id="e8cde-162">`SETTING` kann einer der folgenden Werte sein.</span><span class="sxs-lookup"><span data-stu-id="e8cde-162">The `SETTING` can be one of the following values.</span></span> <span data-ttu-id="e8cde-163">Wenn nichts anderes angegeben wird, wird als Standard `Minor` verwendet.</span><span class="sxs-lookup"><span data-stu-id="e8cde-163">If not specified, `Minor` is the default.</span></span>

  - <span data-ttu-id="e8cde-164">`LatestPatch`: Rollforward zur höchsten Patchversion.</span><span class="sxs-lookup"><span data-stu-id="e8cde-164">`LatestPatch` - Roll forward to the highest patch version.</span></span> <span data-ttu-id="e8cde-165">Dies deaktiviert ein Rollforward zur Nebenversion.</span><span class="sxs-lookup"><span data-stu-id="e8cde-165">This disables minor version roll forward.</span></span>
  - <span data-ttu-id="e8cde-166">`Minor`: Rollforward zur niedrigsten höheren Nebenversion, wenn die angeforderte Nebenversion nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="e8cde-166">`Minor` - Roll forward to the lowest higher minor version, if requested minor version is missing.</span></span> <span data-ttu-id="e8cde-167">Wenn die angeforderte Nebenversion vorhanden ist, wird die LatestPatch-Richtlinie verwendet.</span><span class="sxs-lookup"><span data-stu-id="e8cde-167">If the requested minor version is present, then the LatestPatch policy is used.</span></span>
  - <span data-ttu-id="e8cde-168">`Major`: Rollforward zur niedrigsten höheren Hauptversion – und niedrigsten Nebenversion, wenn die angeforderte Hauptversion nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="e8cde-168">`Major` - Roll forward to lowest higher major version, and lowest minor version, if requested major version is missing.</span></span> <span data-ttu-id="e8cde-169">Wenn die angeforderte Hauptversion vorhanden ist, wird die Minor-Richtlinie verwendet.</span><span class="sxs-lookup"><span data-stu-id="e8cde-169">If the requested major version is present, then the Minor policy is used.</span></span>
  - <span data-ttu-id="e8cde-170">`LatestMinor`: Rollforward zur höchsten Nebenversion – auch dann, wenn die angeforderte Nebenversion vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="e8cde-170">`LatestMinor` - Roll forward to highest minor version, even if requested minor version is present.</span></span> <span data-ttu-id="e8cde-171">Für Komponentenhostingszenarien vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="e8cde-171">Intended for component hosting scenarios.</span></span>
  - <span data-ttu-id="e8cde-172">`LatestMajor`: Rollforward zur höchsten Hauptversion und höchsten Nebenversion – auch dann, wenn die angeforderte Hauptversion vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="e8cde-172">`LatestMajor` - Roll forward to highest major and highest minor version, even if requested major is present.</span></span> <span data-ttu-id="e8cde-173">Für Komponentenhostingszenarien vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="e8cde-173">Intended for component hosting scenarios.</span></span>
  - <span data-ttu-id="e8cde-174">`Disable`: Kein Rollforward.</span><span class="sxs-lookup"><span data-stu-id="e8cde-174">`Disable` - Don't roll forward.</span></span> <span data-ttu-id="e8cde-175">Nur Binden an angegebene Version.</span><span class="sxs-lookup"><span data-stu-id="e8cde-175">Only bind to specified version.</span></span> <span data-ttu-id="e8cde-176">Diese Richtlinie wird nicht zur allgemeinen Verwendung empfohlen, da sie die Möglichkeit eines Rollforwards zu den neuesten Patches ausschließt.</span><span class="sxs-lookup"><span data-stu-id="e8cde-176">This policy isn't recommended for general use because it disables the ability to roll forward to the latest patches.</span></span> <span data-ttu-id="e8cde-177">Dieser Wert wird nur zu Testzwecken empfohlen.</span><span class="sxs-lookup"><span data-stu-id="e8cde-177">This value is only recommended for testing.</span></span>

  <span data-ttu-id="e8cde-178">Mit Ausnahme von `Disable` wird für alle Einstellungen die höchste verfügbare Patchversion verwendet.</span><span class="sxs-lookup"><span data-stu-id="e8cde-178">With the exception of `Disable`, all settings will use the highest available patch version.</span></span>

  <span data-ttu-id="e8cde-179">Das Rollforwardverhalten kann auch in einer Projektdateieigenschaft, einer Runtime-Konfigurationsdateieigenschaft und einer Umgebungsvariablen konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="e8cde-179">Roll forward behavior can also be configured in a project file property, a run-time configuration file property, and an environment variable.</span></span> <span data-ttu-id="e8cde-180">Weitere Informationen finden Sie unter [Runtimerollforward der Hauptversion](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward).</span><span class="sxs-lookup"><span data-stu-id="e8cde-180">For more information, see [Major-version runtime roll forward](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward).</span></span>

- <span data-ttu-id="e8cde-181">**`--roll-forward-on-no-candidate-fx <N>`** **Verfügbar im .NET Core 2.x SDK.**</span><span class="sxs-lookup"><span data-stu-id="e8cde-181">**`--roll-forward-on-no-candidate-fx <N>`** **Available in .NET Core 2.x SDK.**</span></span>

  <span data-ttu-id="e8cde-182">Definiert ein Verhalten, wenn das erforderliche freigegebene Framework nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="e8cde-182">Defines behavior when the required shared framework is not available.</span></span> <span data-ttu-id="e8cde-183">`N` kann Folgendes sein:</span><span class="sxs-lookup"><span data-stu-id="e8cde-183">`N` can be:</span></span>

  - <span data-ttu-id="e8cde-184">`0` - Das Ausführen von Rollforward ist auch für die Nebenversion deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="e8cde-184">`0` - Disable even minor version roll forward.</span></span>
  - <span data-ttu-id="e8cde-185">`1` - Rollforward wird in der Nebenversion, nicht aber in der Hauptversion, ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e8cde-185">`1` - Roll forward on minor version, but not on major version.</span></span> <span data-ttu-id="e8cde-186">Dies ist das Standardverhalten.</span><span class="sxs-lookup"><span data-stu-id="e8cde-186">This is the default behavior.</span></span>
  - <span data-ttu-id="e8cde-187">`2` - Rollforward wird in Neben- und Hauptversionen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e8cde-187">`2` - Roll forward on minor and major versions.</span></span>

  <span data-ttu-id="e8cde-188">Weitere Informationen finden Sie unter [Rollforward](../whats-new/dotnet-core-2-1.md#roll-forward).</span><span class="sxs-lookup"><span data-stu-id="e8cde-188">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

  <span data-ttu-id="e8cde-189">Ab .NET Core 3.0 wird diese Option durch `--roll-forward` abgelöst, und diese Option sollte stattdessen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e8cde-189">Starting with .NET Core 3.0, this option is superseded by `--roll-forward`, and that option should be used instead.</span></span>

- **`--fx-version <VERSION>`**

  <span data-ttu-id="e8cde-190">Version der .NET Core-Runtime, die zum Ausführen der Anwendung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e8cde-190">Version of the .NET Core runtime to use to run the application.</span></span>

  <span data-ttu-id="e8cde-191">Diese Option überschreibt die Version des ersten Frameworkverweises in der `.runtimeconfig.json`-Datei der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="e8cde-191">This option overrides the version of the first framework reference in the application's `.runtimeconfig.json` file.</span></span> <span data-ttu-id="e8cde-192">Dies bedeutet, dass sie nur dann wie erwartet funktioniert, wenn nur ein Frameworkverweis vorliegt.</span><span class="sxs-lookup"><span data-stu-id="e8cde-192">This means it only works as expected if there's just one framework reference.</span></span> <span data-ttu-id="e8cde-193">Wenn die Anwendung über mehrere Frameworkverweise verfügt, kann die Verwendung dieser Option zu Fehlern führen.</span><span class="sxs-lookup"><span data-stu-id="e8cde-193">If the application has more than one framework reference, using this option may cause errors.</span></span>

## <a name="dotnet-commands"></a><span data-ttu-id="e8cde-194">dotnet-Befehle</span><span class="sxs-lookup"><span data-stu-id="e8cde-194">dotnet commands</span></span>

### <a name="general"></a><span data-ttu-id="e8cde-195">Allgemein</span><span class="sxs-lookup"><span data-stu-id="e8cde-195">General</span></span>

| <span data-ttu-id="e8cde-196">Befehl</span><span class="sxs-lookup"><span data-stu-id="e8cde-196">Command</span></span>                                       | <span data-ttu-id="e8cde-197">Funktion</span><span class="sxs-lookup"><span data-stu-id="e8cde-197">Function</span></span>                                                            |
| --------------------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="e8cde-198">dotnet build</span><span class="sxs-lookup"><span data-stu-id="e8cde-198">dotnet build</span></span>](dotnet-build.md)               | <span data-ttu-id="e8cde-199">Erstellt eine .NET Core-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="e8cde-199">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="e8cde-200">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="e8cde-200">dotnet build-server</span></span>](dotnet-build-server.md) | <span data-ttu-id="e8cde-201">Interagiert mit Servern, die von einem Build gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="e8cde-201">Interacts with servers started by a build.</span></span>                          |
| [<span data-ttu-id="e8cde-202">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="e8cde-202">dotnet clean</span></span>](dotnet-clean.md)               | <span data-ttu-id="e8cde-203">Bereinigen von Buildausgaben.</span><span class="sxs-lookup"><span data-stu-id="e8cde-203">Clean build outputs.</span></span>                                                |
| [<span data-ttu-id="e8cde-204">dotnet help</span><span class="sxs-lookup"><span data-stu-id="e8cde-204">dotnet help</span></span>](dotnet-help.md)                 | <span data-ttu-id="e8cde-205">Zeigt eine ausführlichere Onlinedokumentation für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="e8cde-205">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="e8cde-206">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="e8cde-206">dotnet migrate</span></span>](dotnet-migrate.md)           | <span data-ttu-id="e8cde-207">Migriert ein gültiges Preview 2-Projekt in ein .NET Core SDK 1.0-Projekt.</span><span class="sxs-lookup"><span data-stu-id="e8cde-207">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="e8cde-208">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="e8cde-208">dotnet msbuild</span></span>](dotnet-msbuild.md)           | <span data-ttu-id="e8cde-209">Ermöglicht den Zugriff auf die MSBuild-Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="e8cde-209">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="e8cde-210">dotnet new</span><span class="sxs-lookup"><span data-stu-id="e8cde-210">dotnet new</span></span>](dotnet-new.md)                   | <span data-ttu-id="e8cde-211">Initialisiert ein C#- oder F#-Projekt für eine bestimmte Vorlage.</span><span class="sxs-lookup"><span data-stu-id="e8cde-211">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="e8cde-212">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="e8cde-212">dotnet pack</span></span>](dotnet-pack.md)                 | <span data-ttu-id="e8cde-213">Erstellt ein NuGet-Paket aus Ihrem Code.</span><span class="sxs-lookup"><span data-stu-id="e8cde-213">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="e8cde-214">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="e8cde-214">dotnet publish</span></span>](dotnet-publish.md)           | <span data-ttu-id="e8cde-215">Veröffentlicht eine .NET Framework-abhängige oder eigenständige Anwendung.</span><span class="sxs-lookup"><span data-stu-id="e8cde-215">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="e8cde-216">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="e8cde-216">dotnet restore</span></span>](dotnet-restore.md)           | <span data-ttu-id="e8cde-217">Stellt die Abhängigkeiten für eine bestimmte Anwendung wieder her.</span><span class="sxs-lookup"><span data-stu-id="e8cde-217">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="e8cde-218">dotnet run</span><span class="sxs-lookup"><span data-stu-id="e8cde-218">dotnet run</span></span>](dotnet-run.md)                   | <span data-ttu-id="e8cde-219">Führt die Anwendung aus der Quelle aus.</span><span class="sxs-lookup"><span data-stu-id="e8cde-219">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="e8cde-220">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="e8cde-220">dotnet sln</span></span>](dotnet-sln.md)                   | <span data-ttu-id="e8cde-221">Optionen zum Hinzufügen, Entfernen und Listen von Projekten in einer Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="e8cde-221">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="e8cde-222">dotnet store</span><span class="sxs-lookup"><span data-stu-id="e8cde-222">dotnet store</span></span>](dotnet-store.md)               | <span data-ttu-id="e8cde-223">Speichert Assemblys im Laufzeitpaketspeicher.</span><span class="sxs-lookup"><span data-stu-id="e8cde-223">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="e8cde-224">dotnet test</span><span class="sxs-lookup"><span data-stu-id="e8cde-224">dotnet test</span></span>](dotnet-test.md)                 | <span data-ttu-id="e8cde-225">Führt Tests mit einem Test Runner aus.</span><span class="sxs-lookup"><span data-stu-id="e8cde-225">Runs tests using a test runner.</span></span>                                     |

### <a name="project-references"></a><span data-ttu-id="e8cde-226">Projektverweise</span><span class="sxs-lookup"><span data-stu-id="e8cde-226">Project references</span></span>

<span data-ttu-id="e8cde-227">Befehl</span><span class="sxs-lookup"><span data-stu-id="e8cde-227">Command</span></span> | <span data-ttu-id="e8cde-228">Funktion</span><span class="sxs-lookup"><span data-stu-id="e8cde-228">Function</span></span>
--- | ---
[<span data-ttu-id="e8cde-229">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="e8cde-229">dotnet add reference</span></span>](dotnet-add-reference.md) | <span data-ttu-id="e8cde-230">Fügt einen Projektverweis hinzu.</span><span class="sxs-lookup"><span data-stu-id="e8cde-230">Adds a project reference.</span></span>
[<span data-ttu-id="e8cde-231">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="e8cde-231">dotnet list reference</span></span>](dotnet-list-reference.md) | <span data-ttu-id="e8cde-232">Listet Projektverweise auf.</span><span class="sxs-lookup"><span data-stu-id="e8cde-232">Lists project references.</span></span>
[<span data-ttu-id="e8cde-233">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="e8cde-233">dotnet remove reference</span></span>](dotnet-remove-reference.md) | <span data-ttu-id="e8cde-234">Entfernt einen Projektverweis.</span><span class="sxs-lookup"><span data-stu-id="e8cde-234">Removes a project reference.</span></span>

### <a name="nuget-packages"></a><span data-ttu-id="e8cde-235">NuGet-Pakete</span><span class="sxs-lookup"><span data-stu-id="e8cde-235">NuGet packages</span></span>

<span data-ttu-id="e8cde-236">Befehl</span><span class="sxs-lookup"><span data-stu-id="e8cde-236">Command</span></span> | <span data-ttu-id="e8cde-237">Funktion</span><span class="sxs-lookup"><span data-stu-id="e8cde-237">Function</span></span>
--- | ---
[<span data-ttu-id="e8cde-238">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="e8cde-238">dotnet add package</span></span>](dotnet-add-package.md) | <span data-ttu-id="e8cde-239">Fügt ein NuGet-Paket hinzu.</span><span class="sxs-lookup"><span data-stu-id="e8cde-239">Adds a NuGet package.</span></span>
[<span data-ttu-id="e8cde-240">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="e8cde-240">dotnet remove package</span></span>](dotnet-remove-package.md) | <span data-ttu-id="e8cde-241">Entfernt ein NuGet-Paket.</span><span class="sxs-lookup"><span data-stu-id="e8cde-241">Removes a NuGet package.</span></span>

### <a name="nuget-commands"></a><span data-ttu-id="e8cde-242">NuGet-Befehle</span><span class="sxs-lookup"><span data-stu-id="e8cde-242">NuGet commands</span></span>

<span data-ttu-id="e8cde-243">Befehl</span><span class="sxs-lookup"><span data-stu-id="e8cde-243">Command</span></span> | <span data-ttu-id="e8cde-244">Funktion</span><span class="sxs-lookup"><span data-stu-id="e8cde-244">Function</span></span>
--- | ---
[<span data-ttu-id="e8cde-245">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="e8cde-245">dotnet nuget delete</span></span>](dotnet-nuget-delete.md) | <span data-ttu-id="e8cde-246">Löscht ein Paket vom Server oder hebt dessen Auflistung auf.</span><span class="sxs-lookup"><span data-stu-id="e8cde-246">Deletes or unlists a package from the server.</span></span>
[<span data-ttu-id="e8cde-247">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="e8cde-247">dotnet nuget push</span></span>](dotnet-nuget-push.md) | <span data-ttu-id="e8cde-248">Überträgt ein Paket auf den Server und veröffentlicht es.</span><span class="sxs-lookup"><span data-stu-id="e8cde-248">Pushes a package to the server and publishes it.</span></span>
[<span data-ttu-id="e8cde-249">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="e8cde-249">dotnet nuget locals</span></span>](dotnet-nuget-locals.md) | <span data-ttu-id="e8cde-250">Löscht lokale NuGet-Ressourcen, z.B. den http-Anforderungscache, den temporären Cache oder den Ordner mit globalen Paketen auf dem Computer, oder listet diese Ressourcen auf.</span><span class="sxs-lookup"><span data-stu-id="e8cde-250">Clears or lists local NuGet resources such as http-request cache, temporary cache, or machine-wide global packages folder.</span></span>
[<span data-ttu-id="e8cde-251">dotnet nuget add source</span><span class="sxs-lookup"><span data-stu-id="e8cde-251">dotnet nuget add source</span></span>](dotnet-nuget-add-source.md) | <span data-ttu-id="e8cde-252">Hiermit fügen Sie eine NuGet-Quelle hinzu.</span><span class="sxs-lookup"><span data-stu-id="e8cde-252">Adds a NuGet source.</span></span>
[<span data-ttu-id="e8cde-253">dotnet nuget disable source</span><span class="sxs-lookup"><span data-stu-id="e8cde-253">dotnet nuget disable source</span></span>](dotnet-nuget-disable-source.md) | <span data-ttu-id="e8cde-254">Hiermit deaktivieren Sie eine NuGet-Quelle.</span><span class="sxs-lookup"><span data-stu-id="e8cde-254">Disables a NuGet source.</span></span>
[<span data-ttu-id="e8cde-255">dotnet nuget enable source</span><span class="sxs-lookup"><span data-stu-id="e8cde-255">dotnet nuget enable source</span></span>](dotnet-nuget-enable-source.md) | <span data-ttu-id="e8cde-256">Hiermit aktivieren Sie eine NuGet-Quelle.</span><span class="sxs-lookup"><span data-stu-id="e8cde-256">Enables a NuGet source.</span></span>
[<span data-ttu-id="e8cde-257">dotnet nuget list source</span><span class="sxs-lookup"><span data-stu-id="e8cde-257">dotnet nuget list source</span></span>](dotnet-nuget-list-source.md) | <span data-ttu-id="e8cde-258">Hiermit werden alle konfigurierten NuGet-Quellen aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="e8cde-258">Lists all configured NuGet sources.</span></span>
[<span data-ttu-id="e8cde-259">dotnet nuget remove source</span><span class="sxs-lookup"><span data-stu-id="e8cde-259">dotnet nuget remove source</span></span>](dotnet-nuget-remove-source.md) | <span data-ttu-id="e8cde-260">Hiermit entfernen Sie eine NuGet-Quelle.</span><span class="sxs-lookup"><span data-stu-id="e8cde-260">Removes a NuGet source.</span></span>
[<span data-ttu-id="e8cde-261">dotnet nuget update source</span><span class="sxs-lookup"><span data-stu-id="e8cde-261">dotnet nuget update source</span></span>](dotnet-nuget-update-source.md) | <span data-ttu-id="e8cde-262">Hiermit aktualisieren Sie eine NuGet-Quelle.</span><span class="sxs-lookup"><span data-stu-id="e8cde-262">Updates a NuGet source.</span></span>

### <a name="global-tool-path-and-local-tools-commands"></a><span data-ttu-id="e8cde-263">Befehle für globale, Toolpfad- und lokale Tools</span><span class="sxs-lookup"><span data-stu-id="e8cde-263">Global, tool-path, and local tools commands</span></span>

<span data-ttu-id="e8cde-264">Tools sind Konsolenanwendungen, die über NuGet-Pakete installiert und über die Eingabeaufforderung aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="e8cde-264">Tools are console applications that are installed from NuGet packages and are invoked from the command prompt.</span></span> <span data-ttu-id="e8cde-265">Sie können Tools selbst schreiben oder Drittanbietertools installieren.</span><span class="sxs-lookup"><span data-stu-id="e8cde-265">You can write tools yourself or install tools written by third parties.</span></span> <span data-ttu-id="e8cde-266">Tools werden auch als globale Tools, Toolpfadtools und lokale Tools bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="e8cde-266">Tools are also known as global tools, tool-path tools, and local tools.</span></span> <span data-ttu-id="e8cde-267">Weitere Informationen finden Sie unter [Übersicht über .NET Core-Tools](global-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e8cde-267">For more information, see [.NET Core tools overview](global-tools.md).</span></span> <span data-ttu-id="e8cde-268">Globale und Toolpfadtools sind ab .NET Core SDK 2.1 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e8cde-268">Global and tool-path tools are available starting with .NET Core SDK 2.1.</span></span> <span data-ttu-id="e8cde-269">Lokale Tools sind ab .NET Core SDK 3.0 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e8cde-269">Local tools are available starting with .NET Core SDK 3.0.</span></span>

<span data-ttu-id="e8cde-270">Befehl</span><span class="sxs-lookup"><span data-stu-id="e8cde-270">Command</span></span> | <span data-ttu-id="e8cde-271">Funktion</span><span class="sxs-lookup"><span data-stu-id="e8cde-271">Function</span></span>
--- | ---
[<span data-ttu-id="e8cde-272">dotnet tool install</span><span class="sxs-lookup"><span data-stu-id="e8cde-272">dotnet tool install</span></span>](dotnet-tool-install.md) | <span data-ttu-id="e8cde-273">Installiert ein Tool auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="e8cde-273">Installs a tool on your machine.</span></span>
[<span data-ttu-id="e8cde-274">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="e8cde-274">dotnet tool list</span></span>](dotnet-tool-list.md) | <span data-ttu-id="e8cde-275">Listet alle globalen, Toolpfad- und lokalen Tools auf, die derzeit auf Ihrem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="e8cde-275">Lists all global, tool-path, or local tools currently installed on your machine.</span></span>
[<span data-ttu-id="e8cde-276">dotnet tool uninstall</span><span class="sxs-lookup"><span data-stu-id="e8cde-276">dotnet tool uninstall</span></span>](dotnet-tool-uninstall.md) | <span data-ttu-id="e8cde-277">Deinstalliert ein Tool von Ihrem Computer.</span><span class="sxs-lookup"><span data-stu-id="e8cde-277">Uninstalls a tool from your machine.</span></span>
[<span data-ttu-id="e8cde-278">dotnet tool update</span><span class="sxs-lookup"><span data-stu-id="e8cde-278">dotnet tool update</span></span>](dotnet-tool-update.md) | <span data-ttu-id="e8cde-279">Aktualisiert ein Tool, das auf Ihrem Computer installiert ist.</span><span class="sxs-lookup"><span data-stu-id="e8cde-279">Updates a tool that is installed on your machine.</span></span>

### <a name="additional-tools"></a><span data-ttu-id="e8cde-280">Weitere Tools</span><span class="sxs-lookup"><span data-stu-id="e8cde-280">Additional tools</span></span>

<span data-ttu-id="e8cde-281">Beginnend mit .NET Core SDK 2.1.300 steht eine Reihe von Tools, die nur auf Projektbasis unter Verwendung von `DotnetCliToolReference` verfügbar waren, jetzt als Teil des .NET Core SDK zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="e8cde-281">Starting with .NET Core SDK 2.1.300, a number of tools that were available only on a per project basis using `DotnetCliToolReference` are now available as part of the .NET Core SDK.</span></span> <span data-ttu-id="e8cde-282">Diese Tools werden in der folgenden Tabelle aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="e8cde-282">These tools are listed in the following table:</span></span>

| <span data-ttu-id="e8cde-283">Tool</span><span class="sxs-lookup"><span data-stu-id="e8cde-283">Tool</span></span>                                              | <span data-ttu-id="e8cde-284">Funktion</span><span class="sxs-lookup"><span data-stu-id="e8cde-284">Function</span></span>                                                     |
| ------------------------------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="e8cde-285">dev-certs</span><span class="sxs-lookup"><span data-stu-id="e8cde-285">dev-certs</span></span>                                         | <span data-ttu-id="e8cde-286">Erstellt und verwaltet Entwicklungszertifikate.</span><span class="sxs-lookup"><span data-stu-id="e8cde-286">Creates and manages development certificates.</span></span>                |
| [<span data-ttu-id="e8cde-287">ef</span><span class="sxs-lookup"><span data-stu-id="e8cde-287">ef</span></span>](/ef/core/miscellaneous/cli/dotnet)           | <span data-ttu-id="e8cde-288">Entity Framework Core-Befehlszeilentools.</span><span class="sxs-lookup"><span data-stu-id="e8cde-288">Entity Framework Core command-line tools.</span></span>                    |
| <span data-ttu-id="e8cde-289">sql-cache</span><span class="sxs-lookup"><span data-stu-id="e8cde-289">sql-cache</span></span>                                         | <span data-ttu-id="e8cde-290">SQL Server-Cache-Befehlszeilentools.</span><span class="sxs-lookup"><span data-stu-id="e8cde-290">SQL Server cache command-line tools.</span></span>                         |
| [<span data-ttu-id="e8cde-291">user-secrets</span><span class="sxs-lookup"><span data-stu-id="e8cde-291">user-secrets</span></span>](/aspnet/core/security/app-secrets) | <span data-ttu-id="e8cde-292">Verwaltet die Entwicklung von Benutzergeheimnissen.</span><span class="sxs-lookup"><span data-stu-id="e8cde-292">Manages development user secrets.</span></span>                            |
| [<span data-ttu-id="e8cde-293">watch</span><span class="sxs-lookup"><span data-stu-id="e8cde-293">watch</span></span>](/aspnet/core/tutorials/dotnet-watch)      | <span data-ttu-id="e8cde-294">Startet einen Datei-Watcher, der einen Befehl ausführt, wenn sich Dateien ändern.</span><span class="sxs-lookup"><span data-stu-id="e8cde-294">Starts a file watcher that runs a command when files change.</span></span> |

<span data-ttu-id="e8cde-295">Geben Sie `dotnet <tool-name> --help` ein, um weitere Informationen zu den einzelnen Tools zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="e8cde-295">For more information about each tool, type `dotnet <tool-name> --help`.</span></span>

## <a name="examples"></a><span data-ttu-id="e8cde-296">Beispiele</span><span class="sxs-lookup"><span data-stu-id="e8cde-296">Examples</span></span>

<span data-ttu-id="e8cde-297">Erstellen einer neuen .NET Core-Konsolenanwendung:</span><span class="sxs-lookup"><span data-stu-id="e8cde-297">Create a new .NET Core console application:</span></span>

```dotnetcli
dotnet new console
```

<span data-ttu-id="e8cde-298">Erstellen eines Projekts und seiner Abhängigkeiten in einem vorgegebenen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="e8cde-298">Build a project and its dependencies in a given directory:</span></span>

```dotnetcli
dotnet build
```

<span data-ttu-id="e8cde-299">Ausführen einer Anwendung:</span><span class="sxs-lookup"><span data-stu-id="e8cde-299">Run an application:</span></span>

```dotnetcli
dotnet myapp.dll
```

## <a name="environment-variables"></a><span data-ttu-id="e8cde-300">Umgebungsvariablen</span><span class="sxs-lookup"><span data-stu-id="e8cde-300">Environment variables</span></span>

- <span data-ttu-id="e8cde-301">`DOTNET_ROOT`, `DOTNET_ROOT(x86)`</span><span class="sxs-lookup"><span data-stu-id="e8cde-301">`DOTNET_ROOT`, `DOTNET_ROOT(x86)`</span></span>

  <span data-ttu-id="e8cde-302">Gibt den Speicherort der .NET Core-Runtimes an, wenn sie nicht am Standardspeicherort installiert sind.</span><span class="sxs-lookup"><span data-stu-id="e8cde-302">Specifies the location of the .NET Core runtimes, if they are not installed in the default location.</span></span> <span data-ttu-id="e8cde-303">Der Standardspeicherort unter Windows ist `C:\Program Files\dotnet`.</span><span class="sxs-lookup"><span data-stu-id="e8cde-303">The default location on Windows is `C:\Program Files\dotnet`.</span></span> <span data-ttu-id="e8cde-304">Der Standardspeicherort unter Linux und macOS ist `/usr/share/dotnet`.</span><span class="sxs-lookup"><span data-stu-id="e8cde-304">The default location on Linux and macOS is `/usr/share/dotnet`.</span></span> <span data-ttu-id="e8cde-305">Diese Umgebungsvariable wird nur beim Ausführen von Anwendungen über generierte ausführbare Dateien (Apphosts) verwendet.</span><span class="sxs-lookup"><span data-stu-id="e8cde-305">This environment variable is used only when running apps via generated executables (apphosts).</span></span> <span data-ttu-id="e8cde-306">`DOTNET_ROOT(x86)` wird stattdessen verwendet, wenn eine ausführbare 32-Bit-Datei auf einem 64-Bit-Betriebssystem ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e8cde-306">`DOTNET_ROOT(x86)` is used instead when running a 32-bit executable on a 64-bit OS.</span></span>

- `DOTNET_PACKAGES`

  <span data-ttu-id="e8cde-307">Der Ordner für globale Pakete.</span><span class="sxs-lookup"><span data-stu-id="e8cde-307">The global packages folder.</span></span> <span data-ttu-id="e8cde-308">Wenn er nicht festgelegt wird, wird standardmäßig `~/.nuget/packages` unter Unix oder `%userprofile%\.nuget\packages` unter Windows verwendet.</span><span class="sxs-lookup"><span data-stu-id="e8cde-308">If not set, it defaults to `~/.nuget/packages` on Unix or `%userprofile%\.nuget\packages` on Windows.</span></span>

- `DOTNET_SERVICING`

  <span data-ttu-id="e8cde-309">Gibt den Speicherort des Wartungsindex an, der vom freigegebenen Host verwendet wird, wenn die Laufzeit geladen wird.</span><span class="sxs-lookup"><span data-stu-id="e8cde-309">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

- `DOTNET_NOLOGO`

  <span data-ttu-id="e8cde-310">Gibt an, ob bei der ersten Ausführung .NET Core-Willkommens- und Telemetriemeldungen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="e8cde-310">Specifies whether .NET Core welcome and telemetry messages are displayed on first run.</span></span> <span data-ttu-id="e8cde-311">Bei Festlegung auf `true` werden diese Meldungen unterdrückt (akzeptierte Werte: `true`, `1` oder `yes`), bei Festlegung auf `false` werden die Meldungen zugelassen (akzeptierte Werte: `false`, `0` oder `no`).</span><span class="sxs-lookup"><span data-stu-id="e8cde-311">Set to `true` to mute these messages (values `true`, `1`, or `yes` accepted) or set to `false` to allow (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="e8cde-312">Sofern nicht festgelegt, lautet der Standardwert `false`, und die Meldungen werden bei der ersten Ausführung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e8cde-312">If not set, the default is `false` and the messages will be displayed on first run.</span></span> <span data-ttu-id="e8cde-313">Dieses Flag besitzt keine Auswirkung auf die Telemetrie (siehe `DOTNET_CLI_TELEMETRY_OPTOUT` zum Deaktivieren der Übermittlung von Telemetriedaten).</span><span class="sxs-lookup"><span data-stu-id="e8cde-313">This flag has no effect on telemetry (see `DOTNET_CLI_TELEMETRY_OPTOUT` for opting out of sending telemetry).</span></span>

- `DOTNET_CLI_TELEMETRY_OPTOUT`

  <span data-ttu-id="e8cde-314">Gibt an, ob Daten zur Nutzung von .NET Core-Tools gesammelt und an Microsoft gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="e8cde-314">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="e8cde-315">Legen Sie `true` fest, um die Telemetriefunktion zu deaktivieren (Wert `true`, `1` oder `yes` wird akzeptiert).</span><span class="sxs-lookup"><span data-stu-id="e8cde-315">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="e8cde-316">Legen Sie andernfalls `false` fest, um die Telemetriefunktionen zu aktivieren (Wert `false`, `0` oder `no` wird akzeptiert).</span><span class="sxs-lookup"><span data-stu-id="e8cde-316">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="e8cde-317">Ohne Festlegung ist der Standardwert `false`, und die Telemetriefunktion ist aktiviert.</span><span class="sxs-lookup"><span data-stu-id="e8cde-317">If not set, the default is `false` and the telemetry feature is active.</span></span>

- `DOTNET_MULTILEVEL_LOOKUP`

  <span data-ttu-id="e8cde-318">Gibt an, ob die .NET Core-Runtime, das freigegebene Framework oder das SDK vom globalen Speicherort aus aufgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="e8cde-318">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="e8cde-319">Ohne Festlegung ist der Standardwert 1 (logisch `true`).</span><span class="sxs-lookup"><span data-stu-id="e8cde-319">If not set, it defaults to 1 (logical `true`).</span></span> <span data-ttu-id="e8cde-320">Auf 0 (logisch `false`) festgelegt, um nicht vom globalen Speicherort aus aufzulösen und isolierte .NET Core-Installationen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="e8cde-320">Set to 0 (logical `false`) to not resolve from the global location and have isolated .NET Core installations.</span></span> <span data-ttu-id="e8cde-321">Weitere Informationen zu Lookup mit mehreren Ebenen finden Sie unter [Multi-level SharedFX lookup (SharedFX-Lookup mit mehreren Ebenen)](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span><span class="sxs-lookup"><span data-stu-id="e8cde-321">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

- <span data-ttu-id="e8cde-322">`DOTNET_ROLL_FORWARD` **Verfügbar ab .NET Core 3.x.**</span><span class="sxs-lookup"><span data-stu-id="e8cde-322">`DOTNET_ROLL_FORWARD` **Available starting with .NET Core 3.x.**</span></span>

  <span data-ttu-id="e8cde-323">Bestimmt das Rollforwardverhalten.</span><span class="sxs-lookup"><span data-stu-id="e8cde-323">Determines roll forward behavior.</span></span> <span data-ttu-id="e8cde-324">Weitere Informationen finden Sie unter der Option `--roll-forward` weiter oben in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="e8cde-324">For more information, see the `--roll-forward` option earlier in this article.</span></span>

- <span data-ttu-id="e8cde-325">`DOTNET_ROLL_FORWARD_TO_PRERELEASE` **Verfügbar ab .NET Core 3.x.**</span><span class="sxs-lookup"><span data-stu-id="e8cde-325">`DOTNET_ROLL_FORWARD_TO_PRERELEASE` **Available starting with .NET Core 3.x.**</span></span>

  <span data-ttu-id="e8cde-326">Wenn diese Option auf `1` (aktiviert) festgelegt ist, wird das Rollforward von einer endgültigen Produktversion zu einer Vorabversion aktiviert.</span><span class="sxs-lookup"><span data-stu-id="e8cde-326">If set to `1` (enabled), enables rolling forward to a pre-release version from a release version.</span></span> <span data-ttu-id="e8cde-327">Wenn eine endgültige Produktversion der .NET Core-Runtime angefordert wird, werden standardmäßig (`0` – deaktiviert) nur installierte endgültige Produktversionen beim Rollforward berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="e8cde-327">By default (`0` - disabled), when a release version of .NET Core runtime is requested, roll-forward will only consider installed release versions.</span></span>

  <span data-ttu-id="e8cde-328">Weitere Informationen finden Sie unter [Rollforward](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward).</span><span class="sxs-lookup"><span data-stu-id="e8cde-328">For more information, see [Roll forward](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward).</span></span>

- <span data-ttu-id="e8cde-329">`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX` **Verfügbar in .NET Core 2.x.**</span><span class="sxs-lookup"><span data-stu-id="e8cde-329">`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX` **Available in .NET Core 2.x.**</span></span>

  <span data-ttu-id="e8cde-330">Deaktiviert Rollforward der Nebenversion, wenn `0` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="e8cde-330">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="e8cde-331">Weitere Informationen finden Sie unter [Rollforward](../whats-new/dotnet-core-2-1.md#roll-forward).</span><span class="sxs-lookup"><span data-stu-id="e8cde-331">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

  <span data-ttu-id="e8cde-332">Diese Einstellung wird in .NET Core 3.0 durch `DOTNET_ROLL_FORWARD` abgelöst.</span><span class="sxs-lookup"><span data-stu-id="e8cde-332">This setting is superseded in .NET Core 3.0 by `DOTNET_ROLL_FORWARD`.</span></span> <span data-ttu-id="e8cde-333">Stattdessen sollten die neuen Einstellungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e8cde-333">The new settings should be used instead.</span></span>

- `DOTNET_CLI_UI_LANGUAGE`

  <span data-ttu-id="e8cde-334">Legt die Sprache der CLI-Benutzeroberfläche mit einem Gebietsschemawert wie `en-us` fest.</span><span class="sxs-lookup"><span data-stu-id="e8cde-334">Sets the language of the CLI UI using a locale value such as `en-us`.</span></span> <span data-ttu-id="e8cde-335">Die unterstützten Werte sind identisch mit denen für Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e8cde-335">The supported values are the same as for Visual Studio.</span></span> <span data-ttu-id="e8cde-336">Weitere Informationen finden Sie im Abschnitt zum Ändern der Sprache des Installationsprogramms in der [Visual Studio-Installationsdokumentation](/visualstudio/install/install-visual-studio?view=vs-2019).</span><span class="sxs-lookup"><span data-stu-id="e8cde-336">For more information, see the section on changing the installer language in the [Visual Studio installation documentation](/visualstudio/install/install-visual-studio?view=vs-2019).</span></span> <span data-ttu-id="e8cde-337">Es gelten die Regeln des .NET-Ressourcen-Managers, sodass Sie keine genaue Übereinstimmung auswählen müssen, sondern auch Nachfolger in der `CultureInfo`-Struktur auswählen können.</span><span class="sxs-lookup"><span data-stu-id="e8cde-337">The .NET resource manager rules apply, so you don't have to pick an exact match&mdash;you can also pick descendants in the `CultureInfo` tree.</span></span> <span data-ttu-id="e8cde-338">Bei einer Festlegung auf `fr-CA` findet und verwendet die Befehlszeilenschnittstelle z. B. die `fr`-Übersetzungen.</span><span class="sxs-lookup"><span data-stu-id="e8cde-338">For example, if you set it to `fr-CA`, the CLI will find and use the `fr` translations.</span></span> <span data-ttu-id="e8cde-339">Wenn Sie eine nicht unterstützte Sprache festlegen, greift die Befehlszeilenschnittstelle auf Englisch zurück.</span><span class="sxs-lookup"><span data-stu-id="e8cde-339">If you set it to a language that is not supported, the CLI falls back to English.</span></span>

- `DOTNET_DISABLE_GUI_ERRORS`

  <span data-ttu-id="e8cde-340">Für generierte ausführbare Dateien mit aktivierter Benutzeroberfläche – deaktiviert das Dialogfeld-Popupfenster, das normalerweise bei bestimmten Fehlerklassen angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="e8cde-340">For GUI-enabled generated executables - disables dialog popup, which normally shows for certain classes of errors.</span></span> <span data-ttu-id="e8cde-341">Es schreibt nur an `stderr` und beendet sich nur in diesen Fällen.</span><span class="sxs-lookup"><span data-stu-id="e8cde-341">It only writes to `stderr` and exits in those cases.</span></span>
  
- `DOTNET_ADDITIONAL_DEPS`

  <span data-ttu-id="e8cde-342">Entspricht der CLI-Option `--additional-deps`.</span><span class="sxs-lookup"><span data-stu-id="e8cde-342">Equivalent to CLI option `--additional-deps`.</span></span>

- `DOTNET_RUNTIME_ID`

  <span data-ttu-id="e8cde-343">Setzt die erkannte RID außer Kraft.</span><span class="sxs-lookup"><span data-stu-id="e8cde-343">Overrides the detected RID.</span></span>

- `DOTNET_SHARED_STORE`

  <span data-ttu-id="e8cde-344">Speicherort des „gemeinsamen Speichers“, auf den die Assemblyauflösung in einigen Fällen zurückgreift.</span><span class="sxs-lookup"><span data-stu-id="e8cde-344">Location of the "shared store" which assembly resolution falls back to in some cases.</span></span>

- `DOTNET_STARTUP_HOOKS`

  <span data-ttu-id="e8cde-345">Liste der Assemblys zum Laden und Ausführen von Startuphooks.</span><span class="sxs-lookup"><span data-stu-id="e8cde-345">List of assemblies to load and execute startup hooks from.</span></span>

- <span data-ttu-id="e8cde-346">`DOTNET_BUNDLE_EXTRACT_BASE_DIR` **Verfügbar ab .NET Core 3.x.**</span><span class="sxs-lookup"><span data-stu-id="e8cde-346">`DOTNET_BUNDLE_EXTRACT_BASE_DIR` **Available starting with .NET Core 3.x.**</span></span>

  <span data-ttu-id="e8cde-347">Gibt ein Verzeichnis an, in das eine Einzeldateianwendung vor der Ausführung extrahiert wird.</span><span class="sxs-lookup"><span data-stu-id="e8cde-347">Specifies a directory to which a single-file application is extracted before it is executed.</span></span>

  <span data-ttu-id="e8cde-348">Weitere Informationen finden Sie unter [Ausführbare Einzeldateien](../whats-new/dotnet-core-3-0.md#single-file-executables).</span><span class="sxs-lookup"><span data-stu-id="e8cde-348">For more information, see [Single-file executables](../whats-new/dotnet-core-3-0.md#single-file-executables).</span></span>

- <span data-ttu-id="e8cde-349">`COREHOST_TRACE`, `COREHOST_TRACEFILE`, `COREHOST_TRACE_VERBOSITY`</span><span class="sxs-lookup"><span data-stu-id="e8cde-349">`COREHOST_TRACE`, `COREHOST_TRACEFILE`, `COREHOST_TRACE_VERBOSITY`</span></span>

  <span data-ttu-id="e8cde-350">Steuert die Diagnoseablaufverfolgung von den Hostingkomponenten wie `dotnet.exe`, `hostfxr` und `hostpolicy`.</span><span class="sxs-lookup"><span data-stu-id="e8cde-350">Controls diagnostics tracing from the hosting components, such as `dotnet.exe`, `hostfxr`, and `hostpolicy`.</span></span>

  * <span data-ttu-id="e8cde-351">`COREHOST_TRACE=[0/1]` – Standardwert ist `0` – Ablaufverfolgung deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="e8cde-351">`COREHOST_TRACE=[0/1]` - default is `0` - tracing disabled.</span></span> <span data-ttu-id="e8cde-352">Wenn auf `1` festgelegt, ist die Diagnoseablaufverfolgung aktiviert.</span><span class="sxs-lookup"><span data-stu-id="e8cde-352">If set to `1`, diagnostics tracing is enabled.</span></span>
  * <span data-ttu-id="e8cde-353">`COREHOST_TRACEFILE=<file path>` – ist nur wirksam, wenn die Ablaufverfolgung über `COREHOST_TRACE=1` aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="e8cde-353">`COREHOST_TRACEFILE=<file path>` - only has effect if tracing is enabled via `COREHOST_TRACE=1`.</span></span> <span data-ttu-id="e8cde-354">Wenn festgelegt, werden die Ablaufverfolgungsinformationen in die angegebene Datei geschrieben, andernfalls in `stderr`.</span><span class="sxs-lookup"><span data-stu-id="e8cde-354">When set, the tracing information is written to the specified file, otherwise the tracing information is written to `stderr`.</span></span> <span data-ttu-id="e8cde-355">**Verfügbar ab .NET Core 3.x.**</span><span class="sxs-lookup"><span data-stu-id="e8cde-355">**Available starting with .NET Core 3.x.**</span></span>
  * <span data-ttu-id="e8cde-356">`COREHOST_TRACE_VERBOSITY=[1/2/3/4]` – Standardwert ist `4`.</span><span class="sxs-lookup"><span data-stu-id="e8cde-356">`COREHOST_TRACE_VERBOSITY=[1/2/3/4]` - default is `4`.</span></span> <span data-ttu-id="e8cde-357">Die Einstellung wird nur verwendet, wenn die Ablaufverfolgung über `COREHOST_TRACE=1` aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="e8cde-357">The setting is used only when tracing is enabled via `COREHOST_TRACE=1`.</span></span> <span data-ttu-id="e8cde-358">**Verfügbar ab .NET Core 3.x.**</span><span class="sxs-lookup"><span data-stu-id="e8cde-358">**Available starting with .NET Core 3.x.**</span></span>
    * <span data-ttu-id="e8cde-359">`4` – alle Ablaufverfolgungsinformationen werden geschrieben</span><span class="sxs-lookup"><span data-stu-id="e8cde-359">`4` - all tracing information is written</span></span>
    * <span data-ttu-id="e8cde-360">`3` – nur Informationen, Warn- und Fehlermeldungen werden geschrieben</span><span class="sxs-lookup"><span data-stu-id="e8cde-360">`3` - only informational, warning and error messages are written</span></span>
    * <span data-ttu-id="e8cde-361">`2` – nur Warn- und Fehlermeldungen werden geschrieben</span><span class="sxs-lookup"><span data-stu-id="e8cde-361">`2` - only warning and error messages are written</span></span>
    * <span data-ttu-id="e8cde-362">`1` – nur Fehlermeldungen werden geschrieben</span><span class="sxs-lookup"><span data-stu-id="e8cde-362">`1` - only error messages are written</span></span>

  <span data-ttu-id="e8cde-363">Die übliche Methode, ausführliche Ablaufverfolgungsinformationen zum Starten der Anwendung zu erhalten, besteht darin, vor der Ausführung der Anwendung `COREHOST_TRACE=1` und `COREHOST_TRACEFILE=host_trace.txt` festzulegen.</span><span class="sxs-lookup"><span data-stu-id="e8cde-363">The typical way to get detailed trace information about application startup is to set `COREHOST_TRACE=1` and `COREHOST_TRACEFILE=host_trace.txt` and then run the application.</span></span> <span data-ttu-id="e8cde-364">Im aktuellen Verzeichnis wird eine neue Datei `host_trace.txt` mit detaillierten Informationen erstellt.</span><span class="sxs-lookup"><span data-stu-id="e8cde-364">A new file `host_trace.txt` will be created in the current directory with the detailed information.</span></span>

## <a name="see-also"></a><span data-ttu-id="e8cde-365">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e8cde-365">See also</span></span>

- [<span data-ttu-id="e8cde-366">Laufzeitkonfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="e8cde-366">Runtime Configuration Files</span></span>](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)
- [<span data-ttu-id="e8cde-367">Konfigurationseinstellungen für die .NET Core-Runtime</span><span class="sxs-lookup"><span data-stu-id="e8cde-367">.NET Core run-time configuration settings</span></span>](../run-time-config/index.md)
