---
title: Befehl „dotnet test“
description: Der Befehl „dotnet test“ wird zum Ausführen von Unittests in einem bestimmten Projekt verwendet.
ms.date: 05/29/2018
ms.openlocfilehash: 1b2a3917a930db0c0a49ebea41f568aaf4a58ee3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54535281"
---
# <a name="dotnet-test"></a><span data-ttu-id="56e65-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="56e65-103">dotnet test</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="56e65-104">name</span><span class="sxs-lookup"><span data-stu-id="56e65-104">Name</span></span>

<span data-ttu-id="56e65-105">`dotnet test`: .NET-Testtreiber, der verwendet wird, um Komponententests auszuführen.</span><span class="sxs-lookup"><span data-stu-id="56e65-105">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="56e65-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="56e65-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="56e65-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="56e65-107">.NET Core 2.1</span></span>](#tab/netcore21)

```console
dotnet test [<PROJECT>] [-a|--test-adapter-path] [--blame] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter]
    [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] 
    [-v|--verbosity] [-- <RunSettings arguments>]

dotnet test [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="56e65-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="56e65-108">.NET Core 2.0</span></span>](#tab/netcore20)

```console
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter]
    [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] [-v|--verbosity]

dotnet test [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="56e65-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="56e65-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [-d|--diag] [-f|--framework] [--filter] [-l|--logger] [--no-build] [-o|--output] [-s|--settings] [-t|--list-tests]  [-v|--verbosity]

dotnet test [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="56e65-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="56e65-110">Description</span></span>

<span data-ttu-id="56e65-111">Der Befehl `dotnet test` wird zum Ausführen von Komponententests in einem bestimmten Projekt verwendet.</span><span class="sxs-lookup"><span data-stu-id="56e65-111">The `dotnet test` command is used to execute unit tests in a given project.</span></span> <span data-ttu-id="56e65-112">Mit dem `dotnet test`-Befehl wird die Testlauf-Konsolenanwendung gestartet, die für ein Projekt angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="56e65-112">The `dotnet test` command launches the test runner console application specified for a project.</span></span> <span data-ttu-id="56e65-113">Durch den Testlauf werden Tests ausgeführt, die für ein Komponententestframework (z.B. MSTest, NUnit oder xUnit) definiert wurden, und der Erfolg oder Misserfolg der einzelnen Testausführungen wird gemeldet.</span><span class="sxs-lookup"><span data-stu-id="56e65-113">The test runner executes the tests defined for a unit test framework (for example, MSTest, NUnit, or xUnit) and reports the success or failure of each test.</span></span> <span data-ttu-id="56e65-114">Wenn alle Tests erfolgreich sind, gibt der Test Runner 0 (null) als Exitcode zurück. Wenn jedoch ein Test fehlschlägt, wird 1 zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="56e65-114">If all tests are successful, the test runner returns 0 as an exit code; otherwise if any test fails, it returns 1.</span></span> <span data-ttu-id="56e65-115">Der Testlauf und die Komponententestbibliothek werden als NuGet-Pakete gepackt und als gewöhnliche Abhängigkeiten für das Projekt wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="56e65-115">The test runner and the unit test library are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="56e65-116">In Testprojekten wird der Testlauf mittels eines normalen `<PackageReference>`-Elements angegeben, wie in der folgenden Beispielprojektdatei gezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="56e65-116">Test projects specify the test runner using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

## <a name="arguments"></a><span data-ttu-id="56e65-117">Argumente</span><span class="sxs-lookup"><span data-stu-id="56e65-117">Arguments</span></span>

`PROJECT`

<span data-ttu-id="56e65-118">Der Pfad zum Testprojekt.</span><span class="sxs-lookup"><span data-stu-id="56e65-118">Path to the test project.</span></span> <span data-ttu-id="56e65-119">Wenn er nicht angegeben ist, wird standardmäßig das aktuelle Verzeichnis ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="56e65-119">If not specified, it defaults to current directory.</span></span>

## <a name="options"></a><span data-ttu-id="56e65-120">Optionen</span><span class="sxs-lookup"><span data-stu-id="56e65-120">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="56e65-121">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="56e65-121">.NET Core 2.1</span></span>](#tab/netcore21)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="56e65-122">Verwenden Sie die benutzerdefinierten Testadapter aus dem angegebenen Pfad im Testlauf.</span><span class="sxs-lookup"><span data-stu-id="56e65-122">Use the custom test adapters from the specified path in the test run.</span></span>

`--blame`

<span data-ttu-id="56e65-123">Führt die Tests im blame-Modus aus.</span><span class="sxs-lookup"><span data-stu-id="56e65-123">Runs the tests in blame mode.</span></span> <span data-ttu-id="56e65-124">Diese Option hilft beim Isolieren der fehlerhaften Tests, die den Absturz des Testhosts verursachen.</span><span class="sxs-lookup"><span data-stu-id="56e65-124">This option is helpful in isolating the problematic tests causing test host to crash.</span></span> <span data-ttu-id="56e65-125">In dem aktuellen Verzeichnis wird eine Ausgabedatei als *Sequence.xml* erstellt, die die Reihenfolge der ausgeführten Tests vor dem Absturz erfasst.</span><span class="sxs-lookup"><span data-stu-id="56e65-125">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="56e65-126">Legt die Buildkonfiguration fest.</span><span class="sxs-lookup"><span data-stu-id="56e65-126">Defines the build configuration.</span></span> <span data-ttu-id="56e65-127">Der Standardwert ist `Debug`, aber die Konfiguration des Projekts könnte diese SDK-Standardeinstellung überschreiben.</span><span class="sxs-lookup"><span data-stu-id="56e65-127">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

<span data-ttu-id="56e65-128">Aktiviert den Datensammler für den Testlauf.</span><span class="sxs-lookup"><span data-stu-id="56e65-128">Enables data collector for the test run.</span></span> <span data-ttu-id="56e65-129">Weitere Informationen finden Sie unter [Monitor and analyze test run (Überwachen und Analysieren eines Testlaufs)](https://aka.ms/vstest-collect).</span><span class="sxs-lookup"><span data-stu-id="56e65-129">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="56e65-130">Aktiviert den Diagnosemodus für die Testplattform und schreibt Diagnosemeldungen in die angegebene Datei.</span><span class="sxs-lookup"><span data-stu-id="56e65-130">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="56e65-131">Sucht nach Testbinärdateien für ein bestimmtes [Framework](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="56e65-131">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="56e65-132">Filtert Tests im aktuellen Projekt mithilfe des angegebenen Ausdrucks heraus.</span><span class="sxs-lookup"><span data-stu-id="56e65-132">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="56e65-133">Weitere Informationen finden Sie im Abschnitt [Details zu Filteroptionen](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="56e65-133">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="56e65-134">Weitere Informationen und Beispiele zur Verwendung von selektiven Komponententestfiltern finden Sie unter [Ausführen von selektiven Komponententests](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="56e65-134">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="56e65-135">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="56e65-135">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="56e65-136">Gibt eine Protokollierung für die Testergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="56e65-136">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="56e65-137">Erstellt das Projekt nicht vor der Ausführung.</span><span class="sxs-lookup"><span data-stu-id="56e65-137">Doesn't build the test project before running it.</span></span> <span data-ttu-id="56e65-138">Das `--no-restore`-Flag wird implizit festgelegt.</span><span class="sxs-lookup"><span data-stu-id="56e65-138">It also implicit sets the `--no-restore` flag.</span></span>

`--no-restore`

<span data-ttu-id="56e65-139">Führt keine implizite Wiederherstellung aus, wenn der Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="56e65-139">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="56e65-140">Verzeichnis, in dem die auszuführenden Binärdateien zu finden sind.</span><span class="sxs-lookup"><span data-stu-id="56e65-140">Directory in which to find the binaries to run.</span></span>

`-r|--results-directory <PATH>`

<span data-ttu-id="56e65-141">Das Verzeichnis, in dem die Testergebnisse gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="56e65-141">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="56e65-142">Wenn das Verzeichnis noch nicht vorhanden ist, wird es erstellt.</span><span class="sxs-lookup"><span data-stu-id="56e65-142">If the specified directory doesn't exist, it's created.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="56e65-143">Einstellungen, die beim Ausführen von Tests verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="56e65-143">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="56e65-144">Listen Sie alle ermittelten Tests im aktuellen Projekt auf.</span><span class="sxs-lookup"><span data-stu-id="56e65-144">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="56e65-145">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="56e65-145">Sets the verbosity level of the command.</span></span> <span data-ttu-id="56e65-146">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="56e65-146">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`RunSettings arguments`

<span data-ttu-id="56e65-147">Argumente, die als RunSettings-Konfigurationen für den Test übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="56e65-147">Arguments passed as RunSettings configurations for the test.</span></span> <span data-ttu-id="56e65-148">Argumente werden als `[name]=[value]`-Paaren nach „-- “ angegeben (Beachten Sie das Leerzeichen nach --).</span><span class="sxs-lookup"><span data-stu-id="56e65-148">Arguments are specified as `[name]=[value]` pairs after "-- " (note the space after --).</span></span> <span data-ttu-id="56e65-149">Ein Leerzeichen wird verwendet, um mehrere `[name]=[value]`-Paare voneinander zu trennen.</span><span class="sxs-lookup"><span data-stu-id="56e65-149">A space is used to separate multiple `[name]=[value]` pairs.</span></span>

<span data-ttu-id="56e65-150">Ein Beispiel: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span><span class="sxs-lookup"><span data-stu-id="56e65-150">Example: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span></span>

<span data-ttu-id="56e65-151">Weitere Informationen zu RunSettings finden Sie unter [vstest.console.exe: Passing RunSettings args](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md) (Übergeben von RunSettings-Argumenten).</span><span class="sxs-lookup"><span data-stu-id="56e65-151">For more information about RunSettings, see [vstest.console.exe: Passing RunSettings args](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="56e65-152">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="56e65-152">.NET Core 2.0</span></span>](#tab/netcore20)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="56e65-153">Verwenden Sie die benutzerdefinierten Testadapter aus dem angegebenen Pfad im Testlauf.</span><span class="sxs-lookup"><span data-stu-id="56e65-153">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="56e65-154">Legt die Buildkonfiguration fest.</span><span class="sxs-lookup"><span data-stu-id="56e65-154">Defines the build configuration.</span></span> <span data-ttu-id="56e65-155">Der Standardwert ist `Debug`, aber die Konfiguration des Projekts könnte diese SDK-Standardeinstellung überschreiben.</span><span class="sxs-lookup"><span data-stu-id="56e65-155">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

<span data-ttu-id="56e65-156">Aktiviert den Datensammler für den Testlauf.</span><span class="sxs-lookup"><span data-stu-id="56e65-156">Enables data collector for the test run.</span></span> <span data-ttu-id="56e65-157">Weitere Informationen finden Sie unter [Monitor and analyze test run (Überwachen und Analysieren eines Testlaufs)](https://aka.ms/vstest-collect).</span><span class="sxs-lookup"><span data-stu-id="56e65-157">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="56e65-158">Aktiviert den Diagnosemodus für die Testplattform und schreibt Diagnosemeldungen in die angegebene Datei.</span><span class="sxs-lookup"><span data-stu-id="56e65-158">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="56e65-159">Sucht nach Testbinärdateien für ein bestimmtes [Framework](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="56e65-159">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="56e65-160">Filtert Tests im aktuellen Projekt mithilfe des angegebenen Ausdrucks heraus.</span><span class="sxs-lookup"><span data-stu-id="56e65-160">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="56e65-161">Weitere Informationen finden Sie im Abschnitt [Details zu Filteroptionen](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="56e65-161">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="56e65-162">Weitere Informationen und Beispiele zur Verwendung von selektiven Komponententestfiltern finden Sie unter [Ausführen von selektiven Komponententests](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="56e65-162">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="56e65-163">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="56e65-163">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="56e65-164">Gibt eine Protokollierung für die Testergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="56e65-164">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="56e65-165">Erstellt das Projekt nicht vor der Ausführung.</span><span class="sxs-lookup"><span data-stu-id="56e65-165">Doesn't build the test project before running it.</span></span> <span data-ttu-id="56e65-166">Das `--no-restore`-Flag wird implizit festgelegt.</span><span class="sxs-lookup"><span data-stu-id="56e65-166">It also implicit sets the `--no-restore` flag.</span></span>

`--no-restore`

<span data-ttu-id="56e65-167">Führt keine implizite Wiederherstellung aus, wenn der Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="56e65-167">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="56e65-168">Verzeichnis, in dem die auszuführenden Binärdateien zu finden sind.</span><span class="sxs-lookup"><span data-stu-id="56e65-168">Directory in which to find the binaries to run.</span></span>

`-r|--results-directory <PATH>`

<span data-ttu-id="56e65-169">Das Verzeichnis, in dem die Testergebnisse gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="56e65-169">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="56e65-170">Wenn das Verzeichnis noch nicht vorhanden ist, wird es erstellt.</span><span class="sxs-lookup"><span data-stu-id="56e65-170">If the specified directory doesn't exist, it's created.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="56e65-171">Einstellungen, die beim Ausführen von Tests verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="56e65-171">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="56e65-172">Listen Sie alle ermittelten Tests im aktuellen Projekt auf.</span><span class="sxs-lookup"><span data-stu-id="56e65-172">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="56e65-173">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="56e65-173">Sets the verbosity level of the command.</span></span> <span data-ttu-id="56e65-174">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="56e65-174">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="56e65-175">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="56e65-175">.NET Core 1.x</span></span>](#tab/netcore1x)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="56e65-176">Verwenden Sie die benutzerdefinierten Testadapter aus dem angegebenen Pfad im Testlauf.</span><span class="sxs-lookup"><span data-stu-id="56e65-176">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="56e65-177">Legt die Buildkonfiguration fest.</span><span class="sxs-lookup"><span data-stu-id="56e65-177">Defines the build configuration.</span></span> <span data-ttu-id="56e65-178">Der Standardwert ist `Debug`, aber die Konfiguration des Projekts könnte diese SDK-Standardeinstellung überschreiben.</span><span class="sxs-lookup"><span data-stu-id="56e65-178">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="56e65-179">Aktiviert den Diagnosemodus für die Testplattform und schreibt Diagnosemeldungen in die angegebene Datei.</span><span class="sxs-lookup"><span data-stu-id="56e65-179">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="56e65-180">Sucht nach Testbinärdateien für ein bestimmtes [Framework](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="56e65-180">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="56e65-181">Filtert Tests im aktuellen Projekt mithilfe des angegebenen Ausdrucks heraus.</span><span class="sxs-lookup"><span data-stu-id="56e65-181">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="56e65-182">Weitere Informationen finden Sie im Abschnitt [Details zu Filteroptionen](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="56e65-182">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="56e65-183">Weitere Informationen und Beispiele zur Verwendung von selektiven Komponententestfiltern finden Sie unter [Ausführen von selektiven Komponententests](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="56e65-183">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="56e65-184">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="56e65-184">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="56e65-185">Gibt eine Protokollierung für die Testergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="56e65-185">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="56e65-186">Erstellt das Projekt nicht vor der Ausführung.</span><span class="sxs-lookup"><span data-stu-id="56e65-186">Doesn't build the test project before running it.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="56e65-187">Verzeichnis, in dem die auszuführenden Binärdateien zu finden sind.</span><span class="sxs-lookup"><span data-stu-id="56e65-187">Directory in which to find the binaries to run.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="56e65-188">Einstellungen, die beim Ausführen von Tests verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="56e65-188">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="56e65-189">Listen Sie alle ermittelten Tests im aktuellen Projekt auf.</span><span class="sxs-lookup"><span data-stu-id="56e65-189">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="56e65-190">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="56e65-190">Sets the verbosity level of the command.</span></span> <span data-ttu-id="56e65-191">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="56e65-191">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="56e65-192">Beispiele</span><span class="sxs-lookup"><span data-stu-id="56e65-192">Examples</span></span>

<span data-ttu-id="56e65-193">Führen Sie die Tests im Projekt im aktuellen Verzeichnis durch:</span><span class="sxs-lookup"><span data-stu-id="56e65-193">Run the tests in the project in the current directory:</span></span>

`dotnet test`

<span data-ttu-id="56e65-194">Führen Sie die Tests im Projekt `test1` durch:</span><span class="sxs-lookup"><span data-stu-id="56e65-194">Run the tests in the `test1` project:</span></span>

`dotnet test ~/projects/test1/test1.csproj`

<span data-ttu-id="56e65-195">Führen Sie die Tests im aktuellen Verzeichnis aus, und generieren Sie eine Testergebnisdatei im TRX-Format:</span><span class="sxs-lookup"><span data-stu-id="56e65-195">Run the tests in the project in the current directory and generate a test results file in the trx format:</span></span>

`dotnet test --logger:trx`

## <a name="filter-option-details"></a><span data-ttu-id="56e65-196">Details zu Filteroptionen</span><span class="sxs-lookup"><span data-stu-id="56e65-196">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="56e65-197">`<Expression>` weist das Format `<property><operator><value>[|&<Expression>]` auf.</span><span class="sxs-lookup"><span data-stu-id="56e65-197">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="56e65-198">`<property>` ist ein Attribut von `Test Case`.</span><span class="sxs-lookup"><span data-stu-id="56e65-198">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="56e65-199">Im Folgenden werden die Eigenschaften aufgeführt, die von gängigen Frameworks für Komponententests unterstützt werden:</span><span class="sxs-lookup"><span data-stu-id="56e65-199">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="56e65-200">Testframework</span><span class="sxs-lookup"><span data-stu-id="56e65-200">Test Framework</span></span> | <span data-ttu-id="56e65-201">Unterstützte Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="56e65-201">Supported properties</span></span>                                                                                      |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="56e65-202">MSTest</span><span class="sxs-lookup"><span data-stu-id="56e65-202">MSTest</span></span>         | <ul><li><span data-ttu-id="56e65-203">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="56e65-203">FullyQualifiedName</span></span></li><li><span data-ttu-id="56e65-204">name</span><span class="sxs-lookup"><span data-stu-id="56e65-204">Name</span></span></li><li><span data-ttu-id="56e65-205">ClassName</span><span class="sxs-lookup"><span data-stu-id="56e65-205">ClassName</span></span></li><li><span data-ttu-id="56e65-206">Priorität</span><span class="sxs-lookup"><span data-stu-id="56e65-206">Priority</span></span></li><li><span data-ttu-id="56e65-207">TestCategory</span><span class="sxs-lookup"><span data-stu-id="56e65-207">TestCategory</span></span></li></ul> |
| <span data-ttu-id="56e65-208">xUnit</span><span class="sxs-lookup"><span data-stu-id="56e65-208">xUnit</span></span>          | <ul><li><span data-ttu-id="56e65-209">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="56e65-209">FullyQualifiedName</span></span></li><li><span data-ttu-id="56e65-210">DisplayName</span><span class="sxs-lookup"><span data-stu-id="56e65-210">DisplayName</span></span></li><li><span data-ttu-id="56e65-211">Merkmale</span><span class="sxs-lookup"><span data-stu-id="56e65-211">Traits</span></span></li></ul>                                   |

<span data-ttu-id="56e65-212">`<operator>` beschreibt die Beziehung zwischen der Eigenschaft und dem Wert:</span><span class="sxs-lookup"><span data-stu-id="56e65-212">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="56e65-213">Operator</span><span class="sxs-lookup"><span data-stu-id="56e65-213">Operator</span></span> | <span data-ttu-id="56e65-214">Funktion</span><span class="sxs-lookup"><span data-stu-id="56e65-214">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="56e65-215">Genaue Übereinstimmung</span><span class="sxs-lookup"><span data-stu-id="56e65-215">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="56e65-216">Keine genaue Übereinstimmung</span><span class="sxs-lookup"><span data-stu-id="56e65-216">Not exact match</span></span> |
| `~`      | <span data-ttu-id="56e65-217">Enthält</span><span class="sxs-lookup"><span data-stu-id="56e65-217">Contains</span></span>        |

<span data-ttu-id="56e65-218">`<value>` ist eine Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="56e65-218">`<value>` is a string.</span></span> <span data-ttu-id="56e65-219">Bei allen Suchvorgängen ist die Groß-/Kleinschreibung nicht relevant.</span><span class="sxs-lookup"><span data-stu-id="56e65-219">All the lookups are case insensitive.</span></span>

<span data-ttu-id="56e65-220">Ein Ausdruck ohne `<operator>` gilt automatisch als `contains` für die `FullyQualifiedName`-Eigenschaft (`dotnet test --filter xyz` ist beispielsweise identisch mit `dotnet test --filter FullyQualifiedName~xyz`).</span><span class="sxs-lookup"><span data-stu-id="56e65-220">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="56e65-221">Ausdrücke können mit bedingten Operatoren verknüpft werden:</span><span class="sxs-lookup"><span data-stu-id="56e65-221">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="56e65-222">Operator</span><span class="sxs-lookup"><span data-stu-id="56e65-222">Operator</span></span>            | <span data-ttu-id="56e65-223">Funktion</span><span class="sxs-lookup"><span data-stu-id="56e65-223">Function</span></span> |
| ------------------- | -------- |
| <code>&#124;</code> | <span data-ttu-id="56e65-224">ODER</span><span class="sxs-lookup"><span data-stu-id="56e65-224">OR</span></span>       |
| `&`                 | <span data-ttu-id="56e65-225">UND</span><span class="sxs-lookup"><span data-stu-id="56e65-225">AND</span></span>      |

<span data-ttu-id="56e65-226">Sie können Ausdrücke in Klammern einschließen, wenn Sie bedingte Operatoren verwenden (z.B. `(Name~TestMethod1) | (Name~TestMethod2)`).</span><span class="sxs-lookup"><span data-stu-id="56e65-226">You can enclose expressions in parenthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="56e65-227">Weitere Informationen und Beispiele zur Verwendung von selektiven Komponententestfiltern finden Sie unter [Ausführen von selektiven Komponententests](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="56e65-227">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="56e65-228">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="56e65-228">See also</span></span>

- [<span data-ttu-id="56e65-229">Frameworks und Ziele</span><span class="sxs-lookup"><span data-stu-id="56e65-229">Frameworks and Targets</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="56e65-230">.NET Core Runtime-ID (RID)-Katalog</span><span class="sxs-lookup"><span data-stu-id="56e65-230">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
