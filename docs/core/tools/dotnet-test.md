---
title: Befehl „dotnet test“
description: Der Befehl „dotnet test“ wird zum Ausführen von Unittests in einem bestimmten Projekt verwendet.
ms.date: 05/29/2018
ms.openlocfilehash: 49926b35b418e93237a159758903c535ec6c4006
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2019
ms.locfileid: "70988547"
---
# <a name="dotnet-test"></a><span data-ttu-id="ef399-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="ef399-103">dotnet test</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="ef399-104">name</span><span class="sxs-lookup"><span data-stu-id="ef399-104">Name</span></span>

<span data-ttu-id="ef399-105">`dotnet test`: .NET-Testtreiber, der verwendet wird, um Komponententests auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ef399-105">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="ef399-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="ef399-106">Synopsis</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="ef399-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="ef399-107">.NET Core 2.1</span></span>](#tab/netcore21)

```console
dotnet test [<PROJECT>] [-a|--test-adapter-path] [--blame] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter]
    [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] 
    [-v|--verbosity] [-- <RunSettings arguments>]

dotnet test [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="ef399-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="ef399-108">.NET Core 2.0</span></span>](#tab/netcore20)

```console
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter]
    [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] [-v|--verbosity]

dotnet test [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="ef399-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="ef399-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [-d|--diag] [-f|--framework] [--filter] [-l|--logger] [--no-build] [-o|--output] [-s|--settings] [-t|--list-tests]  [-v|--verbosity]

dotnet test [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="ef399-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ef399-110">Description</span></span>

<span data-ttu-id="ef399-111">Der Befehl `dotnet test` wird zum Ausführen von Komponententests in einem bestimmten Projekt verwendet.</span><span class="sxs-lookup"><span data-stu-id="ef399-111">The `dotnet test` command is used to execute unit tests in a given project.</span></span> <span data-ttu-id="ef399-112">Mit dem `dotnet test`-Befehl wird die Testlauf-Konsolenanwendung gestartet, die für ein Projekt angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="ef399-112">The `dotnet test` command launches the test runner console application specified for a project.</span></span> <span data-ttu-id="ef399-113">Durch den Testlauf werden Tests ausgeführt, die für ein Komponententestframework (z.B. MSTest, NUnit oder xUnit) definiert wurden, und der Erfolg oder Misserfolg der einzelnen Testausführungen wird gemeldet.</span><span class="sxs-lookup"><span data-stu-id="ef399-113">The test runner executes the tests defined for a unit test framework (for example, MSTest, NUnit, or xUnit) and reports the success or failure of each test.</span></span> <span data-ttu-id="ef399-114">Wenn alle Tests erfolgreich sind, gibt der Test Runner 0 (null) als Exitcode zurück. Wenn jedoch ein Test fehlschlägt, wird 1 zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ef399-114">If all tests are successful, the test runner returns 0 as an exit code; otherwise if any test fails, it returns 1.</span></span> <span data-ttu-id="ef399-115">Der Testlauf und die Komponententestbibliothek werden als NuGet-Pakete gepackt und als gewöhnliche Abhängigkeiten für das Projekt wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="ef399-115">The test runner and the unit test library are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="ef399-116">In Testprojekten wird der Testlauf mittels eines normalen `<PackageReference>`-Elements angegeben, wie in der folgenden Beispielprojektdatei gezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="ef399-116">Test projects specify the test runner using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

## <a name="arguments"></a><span data-ttu-id="ef399-117">Argumente</span><span class="sxs-lookup"><span data-stu-id="ef399-117">Arguments</span></span>

`PROJECT`

<span data-ttu-id="ef399-118">Der Pfad zum Testprojekt.</span><span class="sxs-lookup"><span data-stu-id="ef399-118">Path to the test project.</span></span> <span data-ttu-id="ef399-119">Wenn er nicht angegeben ist, wird standardmäßig das aktuelle Verzeichnis ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="ef399-119">If not specified, it defaults to current directory.</span></span>

## <a name="options"></a><span data-ttu-id="ef399-120">Optionen</span><span class="sxs-lookup"><span data-stu-id="ef399-120">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="ef399-121">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="ef399-121">.NET Core 2.1</span></span>](#tab/netcore21)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="ef399-122">Verwenden Sie die benutzerdefinierten Testadapter aus dem angegebenen Pfad im Testlauf.</span><span class="sxs-lookup"><span data-stu-id="ef399-122">Use the custom test adapters from the specified path in the test run.</span></span>

`--blame`

<span data-ttu-id="ef399-123">Führt die Tests im blame-Modus aus.</span><span class="sxs-lookup"><span data-stu-id="ef399-123">Runs the tests in blame mode.</span></span> <span data-ttu-id="ef399-124">Diese Option hilft beim Isolieren der fehlerhaften Tests, die den Absturz des Testhosts verursachen.</span><span class="sxs-lookup"><span data-stu-id="ef399-124">This option is helpful in isolating the problematic tests causing test host to crash.</span></span> <span data-ttu-id="ef399-125">In dem aktuellen Verzeichnis wird eine Ausgabedatei als *Sequence.xml* erstellt, die die Reihenfolge der ausgeführten Tests vor dem Absturz erfasst.</span><span class="sxs-lookup"><span data-stu-id="ef399-125">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="ef399-126">Legt die Buildkonfiguration fest.</span><span class="sxs-lookup"><span data-stu-id="ef399-126">Defines the build configuration.</span></span> <span data-ttu-id="ef399-127">Der Standardwert ist `Debug`, aber die Konfiguration des Projekts könnte diese SDK-Standardeinstellung überschreiben.</span><span class="sxs-lookup"><span data-stu-id="ef399-127">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

<span data-ttu-id="ef399-128">Aktiviert den Datensammler für den Testlauf.</span><span class="sxs-lookup"><span data-stu-id="ef399-128">Enables data collector for the test run.</span></span> <span data-ttu-id="ef399-129">Weitere Informationen finden Sie unter [Monitor and analyze test run (Überwachen und Analysieren eines Testlaufs)](https://aka.ms/vstest-collect).</span><span class="sxs-lookup"><span data-stu-id="ef399-129">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="ef399-130">Aktiviert den Diagnosemodus für die Testplattform und schreibt Diagnosemeldungen in die angegebene Datei.</span><span class="sxs-lookup"><span data-stu-id="ef399-130">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="ef399-131">Sucht nach Testbinärdateien für ein bestimmtes [Framework](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="ef399-131">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="ef399-132">Filtert Tests im aktuellen Projekt mithilfe des angegebenen Ausdrucks heraus.</span><span class="sxs-lookup"><span data-stu-id="ef399-132">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="ef399-133">Weitere Informationen finden Sie im Abschnitt [Details zu Filteroptionen](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="ef399-133">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="ef399-134">Weitere Informationen und Beispiele zur Verwendung von selektiven Komponententestfiltern finden Sie unter [Ausführen von selektiven Komponententests](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="ef399-134">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="ef399-135">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="ef399-135">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="ef399-136">Gibt eine Protokollierung für die Testergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="ef399-136">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="ef399-137">Erstellt das Projekt nicht vor der Ausführung.</span><span class="sxs-lookup"><span data-stu-id="ef399-137">Doesn't build the test project before running it.</span></span> <span data-ttu-id="ef399-138">Das `--no-restore`-Flag wird implizit festgelegt.</span><span class="sxs-lookup"><span data-stu-id="ef399-138">It also implicit sets the `--no-restore` flag.</span></span>

`--no-restore`

<span data-ttu-id="ef399-139">Führt keine implizite Wiederherstellung aus, wenn der Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ef399-139">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="ef399-140">Verzeichnis, in dem die auszuführenden Binärdateien zu finden sind.</span><span class="sxs-lookup"><span data-stu-id="ef399-140">Directory in which to find the binaries to run.</span></span>

`-r|--results-directory <PATH>`

<span data-ttu-id="ef399-141">Das Verzeichnis, in dem die Testergebnisse gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="ef399-141">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="ef399-142">Wenn das Verzeichnis noch nicht vorhanden ist, wird es erstellt.</span><span class="sxs-lookup"><span data-stu-id="ef399-142">If the specified directory doesn't exist, it's created.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="ef399-143">Die `.runsettings`-Datei, die zum Ausführen der Tests verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ef399-143">The `.runsettings` file to use for running the tests.</span></span> [<span data-ttu-id="ef399-144">Konfigurieren von Komponententests mithilfe einer `.runsettings`-Datei.</span><span class="sxs-lookup"><span data-stu-id="ef399-144">Configure unit tests by using a `.runsettings` file.</span></span>](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file?view=vs-2019)

`-t|--list-tests`

<span data-ttu-id="ef399-145">Listen Sie alle ermittelten Tests im aktuellen Projekt auf.</span><span class="sxs-lookup"><span data-stu-id="ef399-145">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="ef399-146">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="ef399-146">Sets the verbosity level of the command.</span></span> <span data-ttu-id="ef399-147">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="ef399-147">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`RunSettings arguments`

<span data-ttu-id="ef399-148">Argumente, die als RunSettings-Konfigurationen für den Test übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="ef399-148">Arguments passed as RunSettings configurations for the test.</span></span> <span data-ttu-id="ef399-149">Argumente werden als `[name]=[value]`-Paaren nach „-- “ angegeben (Beachten Sie das Leerzeichen nach --).</span><span class="sxs-lookup"><span data-stu-id="ef399-149">Arguments are specified as `[name]=[value]` pairs after "-- " (note the space after --).</span></span> <span data-ttu-id="ef399-150">Ein Leerzeichen wird verwendet, um mehrere `[name]=[value]`-Paare voneinander zu trennen.</span><span class="sxs-lookup"><span data-stu-id="ef399-150">A space is used to separate multiple `[name]=[value]` pairs.</span></span>

<span data-ttu-id="ef399-151">Ein Beispiel: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span><span class="sxs-lookup"><span data-stu-id="ef399-151">Example: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span></span>

<span data-ttu-id="ef399-152">Weitere Informationen zu RunSettings finden Sie unter [vstest.console.exe: Passing RunSettings args](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md) (Übergeben von RunSettings-Argumenten).</span><span class="sxs-lookup"><span data-stu-id="ef399-152">For more information about RunSettings, see [vstest.console.exe: Passing RunSettings args](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="ef399-153">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="ef399-153">.NET Core 2.0</span></span>](#tab/netcore20)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="ef399-154">Verwenden Sie die benutzerdefinierten Testadapter aus dem angegebenen Pfad im Testlauf.</span><span class="sxs-lookup"><span data-stu-id="ef399-154">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="ef399-155">Legt die Buildkonfiguration fest.</span><span class="sxs-lookup"><span data-stu-id="ef399-155">Defines the build configuration.</span></span> <span data-ttu-id="ef399-156">Der Standardwert ist `Debug`, aber die Konfiguration des Projekts könnte diese SDK-Standardeinstellung überschreiben.</span><span class="sxs-lookup"><span data-stu-id="ef399-156">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

<span data-ttu-id="ef399-157">Aktiviert den Datensammler für den Testlauf.</span><span class="sxs-lookup"><span data-stu-id="ef399-157">Enables data collector for the test run.</span></span> <span data-ttu-id="ef399-158">Weitere Informationen finden Sie unter [Monitor and analyze test run (Überwachen und Analysieren eines Testlaufs)](https://aka.ms/vstest-collect).</span><span class="sxs-lookup"><span data-stu-id="ef399-158">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="ef399-159">Aktiviert den Diagnosemodus für die Testplattform und schreibt Diagnosemeldungen in die angegebene Datei.</span><span class="sxs-lookup"><span data-stu-id="ef399-159">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="ef399-160">Sucht nach Testbinärdateien für ein bestimmtes [Framework](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="ef399-160">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="ef399-161">Filtert Tests im aktuellen Projekt mithilfe des angegebenen Ausdrucks heraus.</span><span class="sxs-lookup"><span data-stu-id="ef399-161">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="ef399-162">Weitere Informationen finden Sie im Abschnitt [Details zu Filteroptionen](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="ef399-162">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="ef399-163">Weitere Informationen und Beispiele zur Verwendung von selektiven Komponententestfiltern finden Sie unter [Ausführen von selektiven Komponententests](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="ef399-163">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="ef399-164">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="ef399-164">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="ef399-165">Gibt eine Protokollierung für die Testergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="ef399-165">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="ef399-166">Erstellt das Projekt nicht vor der Ausführung.</span><span class="sxs-lookup"><span data-stu-id="ef399-166">Doesn't build the test project before running it.</span></span> <span data-ttu-id="ef399-167">Das `--no-restore`-Flag wird implizit festgelegt.</span><span class="sxs-lookup"><span data-stu-id="ef399-167">It also implicit sets the `--no-restore` flag.</span></span>

`--no-restore`

<span data-ttu-id="ef399-168">Führt keine implizite Wiederherstellung aus, wenn der Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ef399-168">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="ef399-169">Verzeichnis, in dem die auszuführenden Binärdateien zu finden sind.</span><span class="sxs-lookup"><span data-stu-id="ef399-169">Directory in which to find the binaries to run.</span></span>

`-r|--results-directory <PATH>`

<span data-ttu-id="ef399-170">Das Verzeichnis, in dem die Testergebnisse gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="ef399-170">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="ef399-171">Wenn das Verzeichnis noch nicht vorhanden ist, wird es erstellt.</span><span class="sxs-lookup"><span data-stu-id="ef399-171">If the specified directory doesn't exist, it's created.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="ef399-172">Die `.runsettings`-Datei, die zum Ausführen der Tests verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ef399-172">The `.runsettings` file to use for running the tests.</span></span> [<span data-ttu-id="ef399-173">Konfigurieren von Komponententests mithilfe einer `.runsettings`-Datei.</span><span class="sxs-lookup"><span data-stu-id="ef399-173">Configure unit tests by using a `.runsettings` file.</span></span>](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file?view=vs-2019)

`-t|--list-tests`

<span data-ttu-id="ef399-174">Listen Sie alle ermittelten Tests im aktuellen Projekt auf.</span><span class="sxs-lookup"><span data-stu-id="ef399-174">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="ef399-175">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="ef399-175">Sets the verbosity level of the command.</span></span> <span data-ttu-id="ef399-176">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="ef399-176">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="ef399-177">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="ef399-177">.NET Core 1.x</span></span>](#tab/netcore1x)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="ef399-178">Verwenden Sie die benutzerdefinierten Testadapter aus dem angegebenen Pfad im Testlauf.</span><span class="sxs-lookup"><span data-stu-id="ef399-178">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="ef399-179">Legt die Buildkonfiguration fest.</span><span class="sxs-lookup"><span data-stu-id="ef399-179">Defines the build configuration.</span></span> <span data-ttu-id="ef399-180">Der Standardwert ist `Debug`, aber die Konfiguration des Projekts könnte diese SDK-Standardeinstellung überschreiben.</span><span class="sxs-lookup"><span data-stu-id="ef399-180">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="ef399-181">Aktiviert den Diagnosemodus für die Testplattform und schreibt Diagnosemeldungen in die angegebene Datei.</span><span class="sxs-lookup"><span data-stu-id="ef399-181">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="ef399-182">Sucht nach Testbinärdateien für ein bestimmtes [Framework](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="ef399-182">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="ef399-183">Filtert Tests im aktuellen Projekt mithilfe des angegebenen Ausdrucks heraus.</span><span class="sxs-lookup"><span data-stu-id="ef399-183">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="ef399-184">Weitere Informationen finden Sie im Abschnitt [Details zu Filteroptionen](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="ef399-184">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="ef399-185">Weitere Informationen und Beispiele zur Verwendung von selektiven Komponententestfiltern finden Sie unter [Ausführen von selektiven Komponententests](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="ef399-185">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="ef399-186">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="ef399-186">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="ef399-187">Gibt eine Protokollierung für die Testergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="ef399-187">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="ef399-188">Erstellt das Projekt nicht vor der Ausführung.</span><span class="sxs-lookup"><span data-stu-id="ef399-188">Doesn't build the test project before running it.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="ef399-189">Verzeichnis, in dem die auszuführenden Binärdateien zu finden sind.</span><span class="sxs-lookup"><span data-stu-id="ef399-189">Directory in which to find the binaries to run.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="ef399-190">Die `.runsettings`-Datei, die zum Ausführen der Tests verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ef399-190">The `.runsettings` file to use for running the tests.</span></span> [<span data-ttu-id="ef399-191">Konfigurieren von Komponententests mithilfe einer `.runsettings`-Datei.</span><span class="sxs-lookup"><span data-stu-id="ef399-191">Configure unit tests by using a `.runsettings` file.</span></span>](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file?view=vs-2019)

`-t|--list-tests`

<span data-ttu-id="ef399-192">Listen Sie alle ermittelten Tests im aktuellen Projekt auf.</span><span class="sxs-lookup"><span data-stu-id="ef399-192">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="ef399-193">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="ef399-193">Sets the verbosity level of the command.</span></span> <span data-ttu-id="ef399-194">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="ef399-194">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="ef399-195">Beispiele</span><span class="sxs-lookup"><span data-stu-id="ef399-195">Examples</span></span>

<span data-ttu-id="ef399-196">Führen Sie die Tests im Projekt im aktuellen Verzeichnis durch:</span><span class="sxs-lookup"><span data-stu-id="ef399-196">Run the tests in the project in the current directory:</span></span>

`dotnet test`

<span data-ttu-id="ef399-197">Führen Sie die Tests im Projekt `test1` durch:</span><span class="sxs-lookup"><span data-stu-id="ef399-197">Run the tests in the `test1` project:</span></span>

`dotnet test ~/projects/test1/test1.csproj`

<span data-ttu-id="ef399-198">Führen Sie die Tests im aktuellen Verzeichnis aus, und generieren Sie eine Testergebnisdatei im TRX-Format:</span><span class="sxs-lookup"><span data-stu-id="ef399-198">Run the tests in the project in the current directory and generate a test results file in the trx format:</span></span>

`dotnet test --logger trx`

## <a name="filter-option-details"></a><span data-ttu-id="ef399-199">Details zu Filteroptionen</span><span class="sxs-lookup"><span data-stu-id="ef399-199">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="ef399-200">`<Expression>` weist das Format `<property><operator><value>[|&<Expression>]` auf.</span><span class="sxs-lookup"><span data-stu-id="ef399-200">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="ef399-201">`<property>` ist ein Attribut von `Test Case`.</span><span class="sxs-lookup"><span data-stu-id="ef399-201">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="ef399-202">Im Folgenden werden die Eigenschaften aufgeführt, die von gängigen Frameworks für Komponententests unterstützt werden:</span><span class="sxs-lookup"><span data-stu-id="ef399-202">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="ef399-203">Testframework</span><span class="sxs-lookup"><span data-stu-id="ef399-203">Test Framework</span></span> | <span data-ttu-id="ef399-204">Unterstützte Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="ef399-204">Supported properties</span></span>                                                                                      |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="ef399-205">MSTest</span><span class="sxs-lookup"><span data-stu-id="ef399-205">MSTest</span></span>         | <ul><li><span data-ttu-id="ef399-206">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="ef399-206">FullyQualifiedName</span></span></li><li><span data-ttu-id="ef399-207">name</span><span class="sxs-lookup"><span data-stu-id="ef399-207">Name</span></span></li><li><span data-ttu-id="ef399-208">ClassName</span><span class="sxs-lookup"><span data-stu-id="ef399-208">ClassName</span></span></li><li><span data-ttu-id="ef399-209">Priorität</span><span class="sxs-lookup"><span data-stu-id="ef399-209">Priority</span></span></li><li><span data-ttu-id="ef399-210">TestCategory</span><span class="sxs-lookup"><span data-stu-id="ef399-210">TestCategory</span></span></li></ul> |
| <span data-ttu-id="ef399-211">xUnit</span><span class="sxs-lookup"><span data-stu-id="ef399-211">xUnit</span></span>          | <ul><li><span data-ttu-id="ef399-212">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="ef399-212">FullyQualifiedName</span></span></li><li><span data-ttu-id="ef399-213">DisplayName</span><span class="sxs-lookup"><span data-stu-id="ef399-213">DisplayName</span></span></li><li><span data-ttu-id="ef399-214">Merkmale</span><span class="sxs-lookup"><span data-stu-id="ef399-214">Traits</span></span></li></ul>                                   |

<span data-ttu-id="ef399-215">`<operator>` beschreibt die Beziehung zwischen der Eigenschaft und dem Wert:</span><span class="sxs-lookup"><span data-stu-id="ef399-215">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="ef399-216">Operator</span><span class="sxs-lookup"><span data-stu-id="ef399-216">Operator</span></span> | <span data-ttu-id="ef399-217">Funktion</span><span class="sxs-lookup"><span data-stu-id="ef399-217">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="ef399-218">Genaue Übereinstimmung</span><span class="sxs-lookup"><span data-stu-id="ef399-218">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="ef399-219">Keine genaue Übereinstimmung</span><span class="sxs-lookup"><span data-stu-id="ef399-219">Not exact match</span></span> |
| `~`      | <span data-ttu-id="ef399-220">Enthält</span><span class="sxs-lookup"><span data-stu-id="ef399-220">Contains</span></span>        |

<span data-ttu-id="ef399-221">`<value>` ist eine Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="ef399-221">`<value>` is a string.</span></span> <span data-ttu-id="ef399-222">Bei allen Suchvorgängen ist die Groß-/Kleinschreibung nicht relevant.</span><span class="sxs-lookup"><span data-stu-id="ef399-222">All the lookups are case insensitive.</span></span>

<span data-ttu-id="ef399-223">Ein Ausdruck ohne `<operator>` gilt automatisch als `contains` für die `FullyQualifiedName`-Eigenschaft (`dotnet test --filter xyz` ist beispielsweise identisch mit `dotnet test --filter FullyQualifiedName~xyz`).</span><span class="sxs-lookup"><span data-stu-id="ef399-223">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="ef399-224">Ausdrücke können mit bedingten Operatoren verknüpft werden:</span><span class="sxs-lookup"><span data-stu-id="ef399-224">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="ef399-225">Operator</span><span class="sxs-lookup"><span data-stu-id="ef399-225">Operator</span></span>            | <span data-ttu-id="ef399-226">Funktion</span><span class="sxs-lookup"><span data-stu-id="ef399-226">Function</span></span> |
| ------------------- | -------- |
| <code>&#124;</code> | <span data-ttu-id="ef399-227">ODER</span><span class="sxs-lookup"><span data-stu-id="ef399-227">OR</span></span>       |
| `&`                 | <span data-ttu-id="ef399-228">UND</span><span class="sxs-lookup"><span data-stu-id="ef399-228">AND</span></span>      |

<span data-ttu-id="ef399-229">Sie können Ausdrücke in Klammern einschließen, wenn Sie bedingte Operatoren verwenden (z.B. `(Name~TestMethod1) | (Name~TestMethod2)`).</span><span class="sxs-lookup"><span data-stu-id="ef399-229">You can enclose expressions in parenthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="ef399-230">Weitere Informationen und Beispiele zur Verwendung von selektiven Komponententestfiltern finden Sie unter [Ausführen von selektiven Komponententests](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="ef399-230">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ef399-231">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ef399-231">See also</span></span>

- [<span data-ttu-id="ef399-232">Frameworks und Ziele</span><span class="sxs-lookup"><span data-stu-id="ef399-232">Frameworks and Targets</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="ef399-233">.NET Core Runtime-ID (RID)-Katalog</span><span class="sxs-lookup"><span data-stu-id="ef399-233">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
