---
title: Befehl „dotnet test“
description: Der Befehl „dotnet test“ wird zum Ausführen von Unittests in einem bestimmten Projekt verwendet.
ms.date: 05/29/2018
ms.openlocfilehash: 6b67273f549edd7712237756a5aba13d5cb59a61
ms.sourcegitcommit: 52e588dc2ee74d484cd07ac60076be25cbf777ab
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2019
ms.locfileid: "67410365"
---
# <a name="dotnet-test"></a><span data-ttu-id="911f9-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="911f9-103">dotnet test</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="911f9-104">name</span><span class="sxs-lookup"><span data-stu-id="911f9-104">Name</span></span>

<span data-ttu-id="911f9-105">`dotnet test`: .NET-Testtreiber, der verwendet wird, um Komponententests auszuführen.</span><span class="sxs-lookup"><span data-stu-id="911f9-105">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="911f9-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="911f9-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="911f9-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="911f9-107">.NET Core 2.1</span></span>](#tab/netcore21)

```console
dotnet test [<PROJECT>] [-a|--test-adapter-path] [--blame] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter]
    [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] 
    [-v|--verbosity] [-- <RunSettings arguments>]

dotnet test [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="911f9-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="911f9-108">.NET Core 2.0</span></span>](#tab/netcore20)

```console
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter]
    [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] [-v|--verbosity]

dotnet test [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="911f9-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="911f9-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [-d|--diag] [-f|--framework] [--filter] [-l|--logger] [--no-build] [-o|--output] [-s|--settings] [-t|--list-tests]  [-v|--verbosity]

dotnet test [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="911f9-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="911f9-110">Description</span></span>

<span data-ttu-id="911f9-111">Der Befehl `dotnet test` wird zum Ausführen von Komponententests in einem bestimmten Projekt verwendet.</span><span class="sxs-lookup"><span data-stu-id="911f9-111">The `dotnet test` command is used to execute unit tests in a given project.</span></span> <span data-ttu-id="911f9-112">Mit dem `dotnet test`-Befehl wird die Testlauf-Konsolenanwendung gestartet, die für ein Projekt angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="911f9-112">The `dotnet test` command launches the test runner console application specified for a project.</span></span> <span data-ttu-id="911f9-113">Durch den Testlauf werden Tests ausgeführt, die für ein Komponententestframework (z.B. MSTest, NUnit oder xUnit) definiert wurden, und der Erfolg oder Misserfolg der einzelnen Testausführungen wird gemeldet.</span><span class="sxs-lookup"><span data-stu-id="911f9-113">The test runner executes the tests defined for a unit test framework (for example, MSTest, NUnit, or xUnit) and reports the success or failure of each test.</span></span> <span data-ttu-id="911f9-114">Wenn alle Tests erfolgreich sind, gibt der Test Runner 0 (null) als Exitcode zurück. Wenn jedoch ein Test fehlschlägt, wird 1 zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="911f9-114">If all tests are successful, the test runner returns 0 as an exit code; otherwise if any test fails, it returns 1.</span></span> <span data-ttu-id="911f9-115">Der Testlauf und die Komponententestbibliothek werden als NuGet-Pakete gepackt und als gewöhnliche Abhängigkeiten für das Projekt wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="911f9-115">The test runner and the unit test library are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="911f9-116">In Testprojekten wird der Testlauf mittels eines normalen `<PackageReference>`-Elements angegeben, wie in der folgenden Beispielprojektdatei gezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="911f9-116">Test projects specify the test runner using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

## <a name="arguments"></a><span data-ttu-id="911f9-117">Argumente</span><span class="sxs-lookup"><span data-stu-id="911f9-117">Arguments</span></span>

`PROJECT`

<span data-ttu-id="911f9-118">Der Pfad zum Testprojekt.</span><span class="sxs-lookup"><span data-stu-id="911f9-118">Path to the test project.</span></span> <span data-ttu-id="911f9-119">Wenn er nicht angegeben ist, wird standardmäßig das aktuelle Verzeichnis ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="911f9-119">If not specified, it defaults to current directory.</span></span>

## <a name="options"></a><span data-ttu-id="911f9-120">Optionen</span><span class="sxs-lookup"><span data-stu-id="911f9-120">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="911f9-121">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="911f9-121">.NET Core 2.1</span></span>](#tab/netcore21)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="911f9-122">Verwenden Sie die benutzerdefinierten Testadapter aus dem angegebenen Pfad im Testlauf.</span><span class="sxs-lookup"><span data-stu-id="911f9-122">Use the custom test adapters from the specified path in the test run.</span></span>

`--blame`

<span data-ttu-id="911f9-123">Führt die Tests im blame-Modus aus.</span><span class="sxs-lookup"><span data-stu-id="911f9-123">Runs the tests in blame mode.</span></span> <span data-ttu-id="911f9-124">Diese Option hilft beim Isolieren der fehlerhaften Tests, die den Absturz des Testhosts verursachen.</span><span class="sxs-lookup"><span data-stu-id="911f9-124">This option is helpful in isolating the problematic tests causing test host to crash.</span></span> <span data-ttu-id="911f9-125">In dem aktuellen Verzeichnis wird eine Ausgabedatei als *Sequence.xml* erstellt, die die Reihenfolge der ausgeführten Tests vor dem Absturz erfasst.</span><span class="sxs-lookup"><span data-stu-id="911f9-125">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="911f9-126">Legt die Buildkonfiguration fest.</span><span class="sxs-lookup"><span data-stu-id="911f9-126">Defines the build configuration.</span></span> <span data-ttu-id="911f9-127">Der Standardwert ist `Debug`, aber die Konfiguration des Projekts könnte diese SDK-Standardeinstellung überschreiben.</span><span class="sxs-lookup"><span data-stu-id="911f9-127">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

<span data-ttu-id="911f9-128">Aktiviert den Datensammler für den Testlauf.</span><span class="sxs-lookup"><span data-stu-id="911f9-128">Enables data collector for the test run.</span></span> <span data-ttu-id="911f9-129">Weitere Informationen finden Sie unter [Monitor and analyze test run (Überwachen und Analysieren eines Testlaufs)](https://aka.ms/vstest-collect).</span><span class="sxs-lookup"><span data-stu-id="911f9-129">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="911f9-130">Aktiviert den Diagnosemodus für die Testplattform und schreibt Diagnosemeldungen in die angegebene Datei.</span><span class="sxs-lookup"><span data-stu-id="911f9-130">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="911f9-131">Sucht nach Testbinärdateien für ein bestimmtes [Framework](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="911f9-131">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="911f9-132">Filtert Tests im aktuellen Projekt mithilfe des angegebenen Ausdrucks heraus.</span><span class="sxs-lookup"><span data-stu-id="911f9-132">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="911f9-133">Weitere Informationen finden Sie im Abschnitt [Details zu Filteroptionen](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="911f9-133">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="911f9-134">Weitere Informationen und Beispiele zur Verwendung von selektiven Komponententestfiltern finden Sie unter [Ausführen von selektiven Komponententests](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="911f9-134">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="911f9-135">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="911f9-135">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="911f9-136">Gibt eine Protokollierung für die Testergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="911f9-136">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="911f9-137">Erstellt das Projekt nicht vor der Ausführung.</span><span class="sxs-lookup"><span data-stu-id="911f9-137">Doesn't build the test project before running it.</span></span> <span data-ttu-id="911f9-138">Das `--no-restore`-Flag wird implizit festgelegt.</span><span class="sxs-lookup"><span data-stu-id="911f9-138">It also implicit sets the `--no-restore` flag.</span></span>

`--no-restore`

<span data-ttu-id="911f9-139">Führt keine implizite Wiederherstellung aus, wenn der Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="911f9-139">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="911f9-140">Verzeichnis, in dem die auszuführenden Binärdateien zu finden sind.</span><span class="sxs-lookup"><span data-stu-id="911f9-140">Directory in which to find the binaries to run.</span></span>

`-r|--results-directory <PATH>`

<span data-ttu-id="911f9-141">Das Verzeichnis, in dem die Testergebnisse gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="911f9-141">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="911f9-142">Wenn das Verzeichnis noch nicht vorhanden ist, wird es erstellt.</span><span class="sxs-lookup"><span data-stu-id="911f9-142">If the specified directory doesn't exist, it's created.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="911f9-143">Die `.runsettings`-Datei, die zum Ausführen der Tests verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="911f9-143">The `.runsettings` file to use for running the tests.</span></span> [<span data-ttu-id="911f9-144">Konfigurieren von Komponententests mithilfe einer `.runsettings`-Datei.</span><span class="sxs-lookup"><span data-stu-id="911f9-144">Configure unit tests by using a `.runsettings` file.</span></span>](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file?view=vs-2019)

`-t|--list-tests`

<span data-ttu-id="911f9-145">Listen Sie alle ermittelten Tests im aktuellen Projekt auf.</span><span class="sxs-lookup"><span data-stu-id="911f9-145">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="911f9-146">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="911f9-146">Sets the verbosity level of the command.</span></span> <span data-ttu-id="911f9-147">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="911f9-147">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`RunSettings arguments`

<span data-ttu-id="911f9-148">Argumente, die als RunSettings-Konfigurationen für den Test übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="911f9-148">Arguments passed as RunSettings configurations for the test.</span></span> <span data-ttu-id="911f9-149">Argumente werden als `[name]=[value]`-Paaren nach „-- “ angegeben (Beachten Sie das Leerzeichen nach --).</span><span class="sxs-lookup"><span data-stu-id="911f9-149">Arguments are specified as `[name]=[value]` pairs after "-- " (note the space after --).</span></span> <span data-ttu-id="911f9-150">Ein Leerzeichen wird verwendet, um mehrere `[name]=[value]`-Paare voneinander zu trennen.</span><span class="sxs-lookup"><span data-stu-id="911f9-150">A space is used to separate multiple `[name]=[value]` pairs.</span></span>

<span data-ttu-id="911f9-151">Ein Beispiel: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span><span class="sxs-lookup"><span data-stu-id="911f9-151">Example: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span></span>

<span data-ttu-id="911f9-152">Weitere Informationen zu RunSettings finden Sie unter [vstest.console.exe: Passing RunSettings args](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md) (Übergeben von RunSettings-Argumenten).</span><span class="sxs-lookup"><span data-stu-id="911f9-152">For more information about RunSettings, see [vstest.console.exe: Passing RunSettings args](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="911f9-153">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="911f9-153">.NET Core 2.0</span></span>](#tab/netcore20)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="911f9-154">Verwenden Sie die benutzerdefinierten Testadapter aus dem angegebenen Pfad im Testlauf.</span><span class="sxs-lookup"><span data-stu-id="911f9-154">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="911f9-155">Legt die Buildkonfiguration fest.</span><span class="sxs-lookup"><span data-stu-id="911f9-155">Defines the build configuration.</span></span> <span data-ttu-id="911f9-156">Der Standardwert ist `Debug`, aber die Konfiguration des Projekts könnte diese SDK-Standardeinstellung überschreiben.</span><span class="sxs-lookup"><span data-stu-id="911f9-156">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

<span data-ttu-id="911f9-157">Aktiviert den Datensammler für den Testlauf.</span><span class="sxs-lookup"><span data-stu-id="911f9-157">Enables data collector for the test run.</span></span> <span data-ttu-id="911f9-158">Weitere Informationen finden Sie unter [Monitor and analyze test run (Überwachen und Analysieren eines Testlaufs)](https://aka.ms/vstest-collect).</span><span class="sxs-lookup"><span data-stu-id="911f9-158">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="911f9-159">Aktiviert den Diagnosemodus für die Testplattform und schreibt Diagnosemeldungen in die angegebene Datei.</span><span class="sxs-lookup"><span data-stu-id="911f9-159">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="911f9-160">Sucht nach Testbinärdateien für ein bestimmtes [Framework](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="911f9-160">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="911f9-161">Filtert Tests im aktuellen Projekt mithilfe des angegebenen Ausdrucks heraus.</span><span class="sxs-lookup"><span data-stu-id="911f9-161">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="911f9-162">Weitere Informationen finden Sie im Abschnitt [Details zu Filteroptionen](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="911f9-162">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="911f9-163">Weitere Informationen und Beispiele zur Verwendung von selektiven Komponententestfiltern finden Sie unter [Ausführen von selektiven Komponententests](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="911f9-163">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="911f9-164">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="911f9-164">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="911f9-165">Gibt eine Protokollierung für die Testergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="911f9-165">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="911f9-166">Erstellt das Projekt nicht vor der Ausführung.</span><span class="sxs-lookup"><span data-stu-id="911f9-166">Doesn't build the test project before running it.</span></span> <span data-ttu-id="911f9-167">Das `--no-restore`-Flag wird implizit festgelegt.</span><span class="sxs-lookup"><span data-stu-id="911f9-167">It also implicit sets the `--no-restore` flag.</span></span>

`--no-restore`

<span data-ttu-id="911f9-168">Führt keine implizite Wiederherstellung aus, wenn der Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="911f9-168">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="911f9-169">Verzeichnis, in dem die auszuführenden Binärdateien zu finden sind.</span><span class="sxs-lookup"><span data-stu-id="911f9-169">Directory in which to find the binaries to run.</span></span>

`-r|--results-directory <PATH>`

<span data-ttu-id="911f9-170">Das Verzeichnis, in dem die Testergebnisse gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="911f9-170">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="911f9-171">Wenn das Verzeichnis noch nicht vorhanden ist, wird es erstellt.</span><span class="sxs-lookup"><span data-stu-id="911f9-171">If the specified directory doesn't exist, it's created.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="911f9-172">Die `.runsettings`-Datei, die zum Ausführen der Tests verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="911f9-172">The `.runsettings` file to use for running the tests.</span></span> [<span data-ttu-id="911f9-173">Konfigurieren von Komponententests mithilfe einer `.runsettings`-Datei.</span><span class="sxs-lookup"><span data-stu-id="911f9-173">Configure unit tests by using a `.runsettings` file.</span></span>](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file?view=vs-2019)

`-t|--list-tests`

<span data-ttu-id="911f9-174">Listen Sie alle ermittelten Tests im aktuellen Projekt auf.</span><span class="sxs-lookup"><span data-stu-id="911f9-174">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="911f9-175">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="911f9-175">Sets the verbosity level of the command.</span></span> <span data-ttu-id="911f9-176">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="911f9-176">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="911f9-177">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="911f9-177">.NET Core 1.x</span></span>](#tab/netcore1x)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="911f9-178">Verwenden Sie die benutzerdefinierten Testadapter aus dem angegebenen Pfad im Testlauf.</span><span class="sxs-lookup"><span data-stu-id="911f9-178">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="911f9-179">Legt die Buildkonfiguration fest.</span><span class="sxs-lookup"><span data-stu-id="911f9-179">Defines the build configuration.</span></span> <span data-ttu-id="911f9-180">Der Standardwert ist `Debug`, aber die Konfiguration des Projekts könnte diese SDK-Standardeinstellung überschreiben.</span><span class="sxs-lookup"><span data-stu-id="911f9-180">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="911f9-181">Aktiviert den Diagnosemodus für die Testplattform und schreibt Diagnosemeldungen in die angegebene Datei.</span><span class="sxs-lookup"><span data-stu-id="911f9-181">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="911f9-182">Sucht nach Testbinärdateien für ein bestimmtes [Framework](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="911f9-182">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="911f9-183">Filtert Tests im aktuellen Projekt mithilfe des angegebenen Ausdrucks heraus.</span><span class="sxs-lookup"><span data-stu-id="911f9-183">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="911f9-184">Weitere Informationen finden Sie im Abschnitt [Details zu Filteroptionen](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="911f9-184">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="911f9-185">Weitere Informationen und Beispiele zur Verwendung von selektiven Komponententestfiltern finden Sie unter [Ausführen von selektiven Komponententests](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="911f9-185">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="911f9-186">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="911f9-186">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="911f9-187">Gibt eine Protokollierung für die Testergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="911f9-187">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="911f9-188">Erstellt das Projekt nicht vor der Ausführung.</span><span class="sxs-lookup"><span data-stu-id="911f9-188">Doesn't build the test project before running it.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="911f9-189">Verzeichnis, in dem die auszuführenden Binärdateien zu finden sind.</span><span class="sxs-lookup"><span data-stu-id="911f9-189">Directory in which to find the binaries to run.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="911f9-190">Die `.runsettings`-Datei, die zum Ausführen der Tests verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="911f9-190">The `.runsettings` file to use for running the tests.</span></span> [<span data-ttu-id="911f9-191">Konfigurieren von Komponententests mithilfe einer `.runsettings`-Datei.</span><span class="sxs-lookup"><span data-stu-id="911f9-191">Configure unit tests by using a `.runsettings` file.</span></span>](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file?view=vs-2019)

`-t|--list-tests`

<span data-ttu-id="911f9-192">Listen Sie alle ermittelten Tests im aktuellen Projekt auf.</span><span class="sxs-lookup"><span data-stu-id="911f9-192">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="911f9-193">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="911f9-193">Sets the verbosity level of the command.</span></span> <span data-ttu-id="911f9-194">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="911f9-194">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="911f9-195">Beispiele</span><span class="sxs-lookup"><span data-stu-id="911f9-195">Examples</span></span>

<span data-ttu-id="911f9-196">Führen Sie die Tests im Projekt im aktuellen Verzeichnis durch:</span><span class="sxs-lookup"><span data-stu-id="911f9-196">Run the tests in the project in the current directory:</span></span>

`dotnet test`

<span data-ttu-id="911f9-197">Führen Sie die Tests im Projekt `test1` durch:</span><span class="sxs-lookup"><span data-stu-id="911f9-197">Run the tests in the `test1` project:</span></span>

`dotnet test ~/projects/test1/test1.csproj`

<span data-ttu-id="911f9-198">Führen Sie die Tests im aktuellen Verzeichnis aus, und generieren Sie eine Testergebnisdatei im TRX-Format:</span><span class="sxs-lookup"><span data-stu-id="911f9-198">Run the tests in the project in the current directory and generate a test results file in the trx format:</span></span>

`dotnet test --logger:trx`

## <a name="filter-option-details"></a><span data-ttu-id="911f9-199">Details zu Filteroptionen</span><span class="sxs-lookup"><span data-stu-id="911f9-199">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="911f9-200">`<Expression>` weist das Format `<property><operator><value>[|&<Expression>]` auf.</span><span class="sxs-lookup"><span data-stu-id="911f9-200">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="911f9-201">`<property>` ist ein Attribut von `Test Case`.</span><span class="sxs-lookup"><span data-stu-id="911f9-201">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="911f9-202">Im Folgenden werden die Eigenschaften aufgeführt, die von gängigen Frameworks für Komponententests unterstützt werden:</span><span class="sxs-lookup"><span data-stu-id="911f9-202">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="911f9-203">Testframework</span><span class="sxs-lookup"><span data-stu-id="911f9-203">Test Framework</span></span> | <span data-ttu-id="911f9-204">Unterstützte Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="911f9-204">Supported properties</span></span>                                                                                      |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="911f9-205">MSTest</span><span class="sxs-lookup"><span data-stu-id="911f9-205">MSTest</span></span>         | <ul><li><span data-ttu-id="911f9-206">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="911f9-206">FullyQualifiedName</span></span></li><li><span data-ttu-id="911f9-207">name</span><span class="sxs-lookup"><span data-stu-id="911f9-207">Name</span></span></li><li><span data-ttu-id="911f9-208">ClassName</span><span class="sxs-lookup"><span data-stu-id="911f9-208">ClassName</span></span></li><li><span data-ttu-id="911f9-209">Priorität</span><span class="sxs-lookup"><span data-stu-id="911f9-209">Priority</span></span></li><li><span data-ttu-id="911f9-210">TestCategory</span><span class="sxs-lookup"><span data-stu-id="911f9-210">TestCategory</span></span></li></ul> |
| <span data-ttu-id="911f9-211">xUnit</span><span class="sxs-lookup"><span data-stu-id="911f9-211">xUnit</span></span>          | <ul><li><span data-ttu-id="911f9-212">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="911f9-212">FullyQualifiedName</span></span></li><li><span data-ttu-id="911f9-213">DisplayName</span><span class="sxs-lookup"><span data-stu-id="911f9-213">DisplayName</span></span></li><li><span data-ttu-id="911f9-214">Merkmale</span><span class="sxs-lookup"><span data-stu-id="911f9-214">Traits</span></span></li></ul>                                   |

<span data-ttu-id="911f9-215">`<operator>` beschreibt die Beziehung zwischen der Eigenschaft und dem Wert:</span><span class="sxs-lookup"><span data-stu-id="911f9-215">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="911f9-216">Operator</span><span class="sxs-lookup"><span data-stu-id="911f9-216">Operator</span></span> | <span data-ttu-id="911f9-217">Funktion</span><span class="sxs-lookup"><span data-stu-id="911f9-217">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="911f9-218">Genaue Übereinstimmung</span><span class="sxs-lookup"><span data-stu-id="911f9-218">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="911f9-219">Keine genaue Übereinstimmung</span><span class="sxs-lookup"><span data-stu-id="911f9-219">Not exact match</span></span> |
| `~`      | <span data-ttu-id="911f9-220">Enthält</span><span class="sxs-lookup"><span data-stu-id="911f9-220">Contains</span></span>        |

<span data-ttu-id="911f9-221">`<value>` ist eine Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="911f9-221">`<value>` is a string.</span></span> <span data-ttu-id="911f9-222">Bei allen Suchvorgängen ist die Groß-/Kleinschreibung nicht relevant.</span><span class="sxs-lookup"><span data-stu-id="911f9-222">All the lookups are case insensitive.</span></span>

<span data-ttu-id="911f9-223">Ein Ausdruck ohne `<operator>` gilt automatisch als `contains` für die `FullyQualifiedName`-Eigenschaft (`dotnet test --filter xyz` ist beispielsweise identisch mit `dotnet test --filter FullyQualifiedName~xyz`).</span><span class="sxs-lookup"><span data-stu-id="911f9-223">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="911f9-224">Ausdrücke können mit bedingten Operatoren verknüpft werden:</span><span class="sxs-lookup"><span data-stu-id="911f9-224">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="911f9-225">Operator</span><span class="sxs-lookup"><span data-stu-id="911f9-225">Operator</span></span>            | <span data-ttu-id="911f9-226">Funktion</span><span class="sxs-lookup"><span data-stu-id="911f9-226">Function</span></span> |
| ------------------- | -------- |
| <code>&#124;</code> | <span data-ttu-id="911f9-227">ODER</span><span class="sxs-lookup"><span data-stu-id="911f9-227">OR</span></span>       |
| `&`                 | <span data-ttu-id="911f9-228">UND</span><span class="sxs-lookup"><span data-stu-id="911f9-228">AND</span></span>      |

<span data-ttu-id="911f9-229">Sie können Ausdrücke in Klammern einschließen, wenn Sie bedingte Operatoren verwenden (z.B. `(Name~TestMethod1) | (Name~TestMethod2)`).</span><span class="sxs-lookup"><span data-stu-id="911f9-229">You can enclose expressions in parenthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="911f9-230">Weitere Informationen und Beispiele zur Verwendung von selektiven Komponententestfiltern finden Sie unter [Ausführen von selektiven Komponententests](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="911f9-230">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="911f9-231">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="911f9-231">See also</span></span>

- [<span data-ttu-id="911f9-232">Frameworks und Ziele</span><span class="sxs-lookup"><span data-stu-id="911f9-232">Frameworks and Targets</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="911f9-233">.NET Core Runtime-ID (RID)-Katalog</span><span class="sxs-lookup"><span data-stu-id="911f9-233">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
