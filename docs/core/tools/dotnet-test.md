---
title: dotnet test-Befehl – .NET Core-CLI
description: Der Befehl „dotnet test“ wird zum Ausführen von Unittests in einem bestimmten Projekt verwendet.
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: e80ba874ec8d0fbc49858719dc3b9b6e02254c78
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2018
ms.locfileid: "46696455"
---
# <a name="dotnet-test"></a><span data-ttu-id="92ee2-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="92ee2-103">dotnet test</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="92ee2-104">name</span><span class="sxs-lookup"><span data-stu-id="92ee2-104">Name</span></span>

<span data-ttu-id="92ee2-105">`dotnet test`: .NET-Testtreiber, der verwendet wird, um Komponententests auszuführen.</span><span class="sxs-lookup"><span data-stu-id="92ee2-105">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="92ee2-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="92ee2-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="92ee2-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="92ee2-107">.NET Core 2.1</span></span>](#tab/netcore21)

```console
dotnet test [<PROJECT>] [-a|--test-adapter-path] [--blame] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter]
    [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] [-v|--verbosity]
dotnet test [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="92ee2-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="92ee2-108">.NET Core 2.0</span></span>](#tab/netcore20)

```console
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter]
    [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] [-v|--verbosity]
dotnet test [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="92ee2-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="92ee2-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [-d|--diag] [-f|--framework] [--filter] [-l|--logger] [--no-build] [-o|--output] [-s|--settings] [-t|--list-tests]  [-v|--verbosity]
dotnet test [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="92ee2-110">Beschreibung </span><span class="sxs-lookup"><span data-stu-id="92ee2-110">Description</span></span>

<span data-ttu-id="92ee2-111">Der Befehl `dotnet test` wird zum Ausführen von Komponententests in einem bestimmten Projekt verwendet.</span><span class="sxs-lookup"><span data-stu-id="92ee2-111">The `dotnet test` command is used to execute unit tests in a given project.</span></span> <span data-ttu-id="92ee2-112">Mit dem `dotnet test`-Befehl wird die Testlauf-Konsolenanwendung gestartet, die für ein Projekt angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="92ee2-112">The `dotnet test` command launches the test runner console application specified for a project.</span></span> <span data-ttu-id="92ee2-113">Durch den Testlauf werden Tests ausgeführt, die für ein Komponententestframework (z.B. MSTest, NUnit oder xUnit) definiert wurden, und der Erfolg oder Misserfolg der einzelnen Testausführungen wird gemeldet.</span><span class="sxs-lookup"><span data-stu-id="92ee2-113">The test runner executes the tests defined for a unit test framework (for example, MSTest, NUnit, or xUnit) and reports the success or failure of each test.</span></span> <span data-ttu-id="92ee2-114">Wenn alle Tests erfolgreich sind, gibt der Test Runner 0 (null) als Exitcode zurück. Wenn jedoch ein Test fehlschlägt, wird 1 zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="92ee2-114">If all tests are successful, the test runner returns 0 as an exit code; otherwise if any test fails, it returns 1.</span></span> <span data-ttu-id="92ee2-115">Der Testlauf und die Komponententestbibliothek werden als NuGet-Pakete gepackt und als gewöhnliche Abhängigkeiten für das Projekt wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="92ee2-115">The test runner and the unit test library are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="92ee2-116">In Testprojekten wird der Testlauf mittels eines normalen `<PackageReference>`-Elements angegeben, wie in der folgenden Beispielprojektdatei gezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="92ee2-116">Test projects specify the test runner using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

## <a name="arguments"></a><span data-ttu-id="92ee2-117">Argumente</span><span class="sxs-lookup"><span data-stu-id="92ee2-117">Arguments</span></span>

`PROJECT`

<span data-ttu-id="92ee2-118">Der Pfad zum Testprojekt.</span><span class="sxs-lookup"><span data-stu-id="92ee2-118">Path to the test project.</span></span> <span data-ttu-id="92ee2-119">Wenn er nicht angegeben ist, wird standardmäßig das aktuelle Verzeichnis ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="92ee2-119">If not specified, it defaults to current directory.</span></span>

## <a name="options"></a><span data-ttu-id="92ee2-120">Optionen</span><span class="sxs-lookup"><span data-stu-id="92ee2-120">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="92ee2-121">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="92ee2-121">.NET Core 2.1</span></span>](#tab/netcore21)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="92ee2-122">Verwenden Sie die benutzerdefinierten Testadapter aus dem angegebenen Pfad im Testlauf.</span><span class="sxs-lookup"><span data-stu-id="92ee2-122">Use the custom test adapters from the specified path in the test run.</span></span>

`--blame`

<span data-ttu-id="92ee2-123">Führt die Tests im blame-Modus aus.</span><span class="sxs-lookup"><span data-stu-id="92ee2-123">Runs the tests in blame mode.</span></span> <span data-ttu-id="92ee2-124">Diese Option hilft beim Isolieren der fehlerhaften Tests, die den Absturz des Testhosts verursachen.</span><span class="sxs-lookup"><span data-stu-id="92ee2-124">This option is helpful in isolating the problematic tests causing test host to crash.</span></span> <span data-ttu-id="92ee2-125">In dem aktuellen Verzeichnis wird eine Ausgabedatei als *Sequence.xml* erstellt, die die Reihenfolge der ausgeführten Tests vor dem Absturz erfasst.</span><span class="sxs-lookup"><span data-stu-id="92ee2-125">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="92ee2-126">Legt die Buildkonfiguration fest.</span><span class="sxs-lookup"><span data-stu-id="92ee2-126">Defines the build configuration.</span></span> <span data-ttu-id="92ee2-127">Der Standardwert ist `Debug`, aber die Konfiguration des Projekts könnte diese SDK-Standardeinstellung überschreiben.</span><span class="sxs-lookup"><span data-stu-id="92ee2-127">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

<span data-ttu-id="92ee2-128">Aktiviert den Datensammler für den Testlauf.</span><span class="sxs-lookup"><span data-stu-id="92ee2-128">Enables data collector for the test run.</span></span> <span data-ttu-id="92ee2-129">Weitere Informationen finden Sie unter [Monitor and analyze test run (Überwachen und Analysieren eines Testlaufs)](https://aka.ms/vstest-collect).</span><span class="sxs-lookup"><span data-stu-id="92ee2-129">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="92ee2-130">Aktiviert den Diagnosemodus für die Testplattform und schreibt Diagnosemeldungen in die angegebene Datei.</span><span class="sxs-lookup"><span data-stu-id="92ee2-130">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="92ee2-131">Sucht nach Testbinärdateien für ein bestimmtes [Framework](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="92ee2-131">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="92ee2-132">Filtert Tests im aktuellen Projekt mithilfe des angegebenen Ausdrucks heraus.</span><span class="sxs-lookup"><span data-stu-id="92ee2-132">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="92ee2-133">Weitere Informationen finden Sie im Abschnitt [Details zu Filteroptionen](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="92ee2-133">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="92ee2-134">Weitere Informationen und Beispiele zur Verwendung von selektiven Komponententestfiltern finden Sie unter [Ausführen von selektiven Komponententests](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="92ee2-134">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="92ee2-135">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="92ee2-135">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="92ee2-136">Gibt eine Protokollierung für die Testergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="92ee2-136">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="92ee2-137">Erstellt das Projekt nicht vor der Ausführung.</span><span class="sxs-lookup"><span data-stu-id="92ee2-137">Doesn't build the test project before running it.</span></span> <span data-ttu-id="92ee2-138">Das `--no-restore`-Flag wird implizit festgelegt.</span><span class="sxs-lookup"><span data-stu-id="92ee2-138">It also implicit sets the `--no-restore` flag.</span></span>

`--no-restore`

<span data-ttu-id="92ee2-139">Führt keine implizite Wiederherstellung aus, wenn der Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="92ee2-139">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="92ee2-140">Verzeichnis, in dem die auszuführenden Binärdateien zu finden sind.</span><span class="sxs-lookup"><span data-stu-id="92ee2-140">Directory in which to find the binaries to run.</span></span>

`-r|--results-directory <PATH>`

<span data-ttu-id="92ee2-141">Das Verzeichnis, in dem die Testergebnisse gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="92ee2-141">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="92ee2-142">Wenn das Verzeichnis noch nicht vorhanden ist, wird es erstellt.</span><span class="sxs-lookup"><span data-stu-id="92ee2-142">If the specified directory doesn't exist, it's created.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="92ee2-143">Einstellungen, die beim Ausführen von Tests verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="92ee2-143">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="92ee2-144">Listen Sie alle ermittelten Tests im aktuellen Projekt auf.</span><span class="sxs-lookup"><span data-stu-id="92ee2-144">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="92ee2-145">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="92ee2-145">Sets the verbosity level of the command.</span></span> <span data-ttu-id="92ee2-146">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="92ee2-146">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="92ee2-147">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="92ee2-147">.NET Core 2.0</span></span>](#tab/netcore20)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="92ee2-148">Verwenden Sie die benutzerdefinierten Testadapter aus dem angegebenen Pfad im Testlauf.</span><span class="sxs-lookup"><span data-stu-id="92ee2-148">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="92ee2-149">Legt die Buildkonfiguration fest.</span><span class="sxs-lookup"><span data-stu-id="92ee2-149">Defines the build configuration.</span></span> <span data-ttu-id="92ee2-150">Der Standardwert ist `Debug`, aber die Konfiguration des Projekts könnte diese SDK-Standardeinstellung überschreiben.</span><span class="sxs-lookup"><span data-stu-id="92ee2-150">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

<span data-ttu-id="92ee2-151">Aktiviert den Datensammler für den Testlauf.</span><span class="sxs-lookup"><span data-stu-id="92ee2-151">Enables data collector for the test run.</span></span> <span data-ttu-id="92ee2-152">Weitere Informationen finden Sie unter [Monitor and analyze test run (Überwachen und Analysieren eines Testlaufs)](https://aka.ms/vstest-collect).</span><span class="sxs-lookup"><span data-stu-id="92ee2-152">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="92ee2-153">Aktiviert den Diagnosemodus für die Testplattform und schreibt Diagnosemeldungen in die angegebene Datei.</span><span class="sxs-lookup"><span data-stu-id="92ee2-153">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="92ee2-154">Sucht nach Testbinärdateien für ein bestimmtes [Framework](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="92ee2-154">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="92ee2-155">Filtert Tests im aktuellen Projekt mithilfe des angegebenen Ausdrucks heraus.</span><span class="sxs-lookup"><span data-stu-id="92ee2-155">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="92ee2-156">Weitere Informationen finden Sie im Abschnitt [Details zu Filteroptionen](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="92ee2-156">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="92ee2-157">Weitere Informationen und Beispiele zur Verwendung von selektiven Komponententestfiltern finden Sie unter [Ausführen von selektiven Komponententests](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="92ee2-157">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="92ee2-158">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="92ee2-158">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="92ee2-159">Gibt eine Protokollierung für die Testergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="92ee2-159">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="92ee2-160">Erstellt das Projekt nicht vor der Ausführung.</span><span class="sxs-lookup"><span data-stu-id="92ee2-160">Doesn't build the test project before running it.</span></span> <span data-ttu-id="92ee2-161">Das `--no-restore`-Flag wird implizit festgelegt.</span><span class="sxs-lookup"><span data-stu-id="92ee2-161">It also implicit sets the `--no-restore` flag.</span></span>

`--no-restore`

<span data-ttu-id="92ee2-162">Führt keine implizite Wiederherstellung aus, wenn der Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="92ee2-162">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="92ee2-163">Verzeichnis, in dem die auszuführenden Binärdateien zu finden sind.</span><span class="sxs-lookup"><span data-stu-id="92ee2-163">Directory in which to find the binaries to run.</span></span>

`-r|--results-directory <PATH>`

<span data-ttu-id="92ee2-164">Das Verzeichnis, in dem die Testergebnisse gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="92ee2-164">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="92ee2-165">Wenn das Verzeichnis noch nicht vorhanden ist, wird es erstellt.</span><span class="sxs-lookup"><span data-stu-id="92ee2-165">If the specified directory doesn't exist, it's created.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="92ee2-166">Einstellungen, die beim Ausführen von Tests verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="92ee2-166">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="92ee2-167">Listen Sie alle ermittelten Tests im aktuellen Projekt auf.</span><span class="sxs-lookup"><span data-stu-id="92ee2-167">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="92ee2-168">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="92ee2-168">Sets the verbosity level of the command.</span></span> <span data-ttu-id="92ee2-169">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="92ee2-169">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="92ee2-170">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="92ee2-170">.NET Core 1.x</span></span>](#tab/netcore1x)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="92ee2-171">Verwenden Sie die benutzerdefinierten Testadapter aus dem angegebenen Pfad im Testlauf.</span><span class="sxs-lookup"><span data-stu-id="92ee2-171">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="92ee2-172">Legt die Buildkonfiguration fest.</span><span class="sxs-lookup"><span data-stu-id="92ee2-172">Defines the build configuration.</span></span> <span data-ttu-id="92ee2-173">Der Standardwert ist `Debug`, aber die Konfiguration des Projekts könnte diese SDK-Standardeinstellung überschreiben.</span><span class="sxs-lookup"><span data-stu-id="92ee2-173">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="92ee2-174">Aktiviert den Diagnosemodus für die Testplattform und schreibt Diagnosemeldungen in die angegebene Datei.</span><span class="sxs-lookup"><span data-stu-id="92ee2-174">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="92ee2-175">Sucht nach Testbinärdateien für ein bestimmtes [Framework](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="92ee2-175">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="92ee2-176">Filtert Tests im aktuellen Projekt mithilfe des angegebenen Ausdrucks heraus.</span><span class="sxs-lookup"><span data-stu-id="92ee2-176">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="92ee2-177">Weitere Informationen finden Sie im Abschnitt [Details zu Filteroptionen](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="92ee2-177">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="92ee2-178">Weitere Informationen und Beispiele zur Verwendung von selektiven Komponententestfiltern finden Sie unter [Ausführen von selektiven Komponententests](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="92ee2-178">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="92ee2-179">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="92ee2-179">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="92ee2-180">Gibt eine Protokollierung für die Testergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="92ee2-180">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="92ee2-181">Erstellt das Projekt nicht vor der Ausführung.</span><span class="sxs-lookup"><span data-stu-id="92ee2-181">Doesn't build the test project before running it.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="92ee2-182">Verzeichnis, in dem die auszuführenden Binärdateien zu finden sind.</span><span class="sxs-lookup"><span data-stu-id="92ee2-182">Directory in which to find the binaries to run.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="92ee2-183">Einstellungen, die beim Ausführen von Tests verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="92ee2-183">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="92ee2-184">Listen Sie alle ermittelten Tests im aktuellen Projekt auf.</span><span class="sxs-lookup"><span data-stu-id="92ee2-184">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="92ee2-185">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="92ee2-185">Sets the verbosity level of the command.</span></span> <span data-ttu-id="92ee2-186">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="92ee2-186">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="92ee2-187">Beispiele</span><span class="sxs-lookup"><span data-stu-id="92ee2-187">Examples</span></span>

<span data-ttu-id="92ee2-188">Führen Sie die Tests im Projekt im aktuellen Verzeichnis durch:</span><span class="sxs-lookup"><span data-stu-id="92ee2-188">Run the tests in the project in the current directory:</span></span>

`dotnet test`

<span data-ttu-id="92ee2-189">Führen Sie die Tests im Projekt `test1` durch:</span><span class="sxs-lookup"><span data-stu-id="92ee2-189">Run the tests in the `test1` project:</span></span>

`dotnet test ~/projects/test1/test1.csproj`

<span data-ttu-id="92ee2-190">Führen Sie die Tests im aktuellen Verzeichnis aus, und generieren Sie eine Testergebnisdatei im TRX-Format:</span><span class="sxs-lookup"><span data-stu-id="92ee2-190">Run the tests in the project in the current directory and generate a test results file in the trx format:</span></span>

`dotnet test --logger:trx`

## <a name="filter-option-details"></a><span data-ttu-id="92ee2-191">Details zu Filteroptionen</span><span class="sxs-lookup"><span data-stu-id="92ee2-191">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="92ee2-192">`<Expression>` weist das Format `<property><operator><value>[|&<Expression>]` auf.</span><span class="sxs-lookup"><span data-stu-id="92ee2-192">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="92ee2-193">`<property>` ist ein Attribut von `Test Case`.</span><span class="sxs-lookup"><span data-stu-id="92ee2-193">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="92ee2-194">Im Folgenden werden die Eigenschaften aufgeführt, die von gängigen Frameworks für Komponententests unterstützt werden:</span><span class="sxs-lookup"><span data-stu-id="92ee2-194">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="92ee2-195">Testframework</span><span class="sxs-lookup"><span data-stu-id="92ee2-195">Test Framework</span></span> | <span data-ttu-id="92ee2-196">Unterstützte Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="92ee2-196">Supported properties</span></span>                                                                                      |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="92ee2-197">MSTest</span><span class="sxs-lookup"><span data-stu-id="92ee2-197">MSTest</span></span>         | <ul><li><span data-ttu-id="92ee2-198">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="92ee2-198">FullyQualifiedName</span></span></li><li><span data-ttu-id="92ee2-199">name</span><span class="sxs-lookup"><span data-stu-id="92ee2-199">Name</span></span></li><li><span data-ttu-id="92ee2-200">ClassName</span><span class="sxs-lookup"><span data-stu-id="92ee2-200">ClassName</span></span></li><li><span data-ttu-id="92ee2-201">Priorität</span><span class="sxs-lookup"><span data-stu-id="92ee2-201">Priority</span></span></li><li><span data-ttu-id="92ee2-202">TestCategory</span><span class="sxs-lookup"><span data-stu-id="92ee2-202">TestCategory</span></span></li></ul> |
| <span data-ttu-id="92ee2-203">xUnit</span><span class="sxs-lookup"><span data-stu-id="92ee2-203">xUnit</span></span>          | <ul><li><span data-ttu-id="92ee2-204">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="92ee2-204">FullyQualifiedName</span></span></li><li><span data-ttu-id="92ee2-205">DisplayName</span><span class="sxs-lookup"><span data-stu-id="92ee2-205">DisplayName</span></span></li><li><span data-ttu-id="92ee2-206">Merkmale</span><span class="sxs-lookup"><span data-stu-id="92ee2-206">Traits</span></span></li></ul>                                   |

<span data-ttu-id="92ee2-207">`<operator>` beschreibt die Beziehung zwischen der Eigenschaft und dem Wert:</span><span class="sxs-lookup"><span data-stu-id="92ee2-207">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="92ee2-208">Operator</span><span class="sxs-lookup"><span data-stu-id="92ee2-208">Operator</span></span> | <span data-ttu-id="92ee2-209">Funktion</span><span class="sxs-lookup"><span data-stu-id="92ee2-209">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="92ee2-210">Genaue Übereinstimmung</span><span class="sxs-lookup"><span data-stu-id="92ee2-210">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="92ee2-211">Keine genaue Übereinstimmung</span><span class="sxs-lookup"><span data-stu-id="92ee2-211">Not exact match</span></span> |
| `~`      | <span data-ttu-id="92ee2-212">Enthält</span><span class="sxs-lookup"><span data-stu-id="92ee2-212">Contains</span></span>        |

<span data-ttu-id="92ee2-213">`<value>` ist eine Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="92ee2-213">`<value>` is a string.</span></span> <span data-ttu-id="92ee2-214">Bei allen Suchvorgängen ist die Groß-/Kleinschreibung nicht relevant.</span><span class="sxs-lookup"><span data-stu-id="92ee2-214">All the lookups are case insensitive.</span></span>

<span data-ttu-id="92ee2-215">Ein Ausdruck ohne `<operator>` gilt automatisch als `contains` für die `FullyQualifiedName`-Eigenschaft (`dotnet test --filter xyz` ist beispielsweise identisch mit `dotnet test --filter FullyQualifiedName~xyz`).</span><span class="sxs-lookup"><span data-stu-id="92ee2-215">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="92ee2-216">Ausdrücke können mit bedingten Operatoren verknüpft werden:</span><span class="sxs-lookup"><span data-stu-id="92ee2-216">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="92ee2-217">Operator</span><span class="sxs-lookup"><span data-stu-id="92ee2-217">Operator</span></span>            | <span data-ttu-id="92ee2-218">Funktion</span><span class="sxs-lookup"><span data-stu-id="92ee2-218">Function</span></span> |
| ------------------- | -------- |
| <code>&#124;</code> | <span data-ttu-id="92ee2-219">ODER</span><span class="sxs-lookup"><span data-stu-id="92ee2-219">OR</span></span>       |
| `&`                 | <span data-ttu-id="92ee2-220">UND</span><span class="sxs-lookup"><span data-stu-id="92ee2-220">AND</span></span>      |

<span data-ttu-id="92ee2-221">Sie können Ausdrücke in Klammern einschließen, wenn Sie bedingte Operatoren verwenden (z.B. `(Name~TestMethod1) | (Name~TestMethod2)`).</span><span class="sxs-lookup"><span data-stu-id="92ee2-221">You can enclose expressions in parenthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="92ee2-222">Weitere Informationen und Beispiele zur Verwendung von selektiven Komponententestfiltern finden Sie unter [Ausführen von selektiven Komponententests](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="92ee2-222">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="92ee2-223">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="92ee2-223">See also</span></span>

* [<span data-ttu-id="92ee2-224">Frameworks und Ziele</span><span class="sxs-lookup"><span data-stu-id="92ee2-224">Frameworks and Targets</span></span>](../../standard/frameworks.md)  
* [<span data-ttu-id="92ee2-225">.NET Core Runtime-ID (RID)-Katalog</span><span class="sxs-lookup"><span data-stu-id="92ee2-225">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
