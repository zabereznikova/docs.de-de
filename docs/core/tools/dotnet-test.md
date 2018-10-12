---
title: dotnet test-Befehl – .NET Core-CLI
description: Der Befehl „dotnet test“ wird zum Ausführen von Unittests in einem bestimmten Projekt verwendet.
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: 7946196b27489870da1c16b15cbf5f078ae89c61
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2018
ms.locfileid: "44137199"
---
# <a name="dotnet-test"></a><span data-ttu-id="eac09-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="eac09-103">dotnet test</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="eac09-104">name</span><span class="sxs-lookup"><span data-stu-id="eac09-104">Name</span></span>

<span data-ttu-id="eac09-105">`dotnet test`: .NET-Testtreiber, der verwendet wird, um Komponententests auszuführen.</span><span class="sxs-lookup"><span data-stu-id="eac09-105">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="eac09-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="eac09-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="eac09-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="eac09-107">.NET Core 2.1</span></span>](#tab/netcore21)

```console
dotnet test [<PROJECT>] [-a|--test-adapter-path] [--blame] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter]
    [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] [-v|--verbosity]
dotnet test [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="eac09-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="eac09-108">.NET Core 2.0</span></span>](#tab/netcore20)

```console
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter]
    [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] [-v|--verbosity]
dotnet test [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="eac09-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="eac09-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [-d|--diag] [-f|--framework] [--filter] [-l|--logger] [--no-build] [-o|--output] [-s|--settings] [-t|--list-tests]  [-v|--verbosity]
dotnet test [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="eac09-110">Beschreibung </span><span class="sxs-lookup"><span data-stu-id="eac09-110">Description</span></span>

<span data-ttu-id="eac09-111">Der Befehl `dotnet test` wird zum Ausführen von Komponententests in einem bestimmten Projekt verwendet.</span><span class="sxs-lookup"><span data-stu-id="eac09-111">The `dotnet test` command is used to execute unit tests in a given project.</span></span> <span data-ttu-id="eac09-112">Mit dem `dotnet test`-Befehl wird die Testlauf-Konsolenanwendung gestartet, die für ein Projekt angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="eac09-112">The `dotnet test` command launches the test runner console application specified for a project.</span></span> <span data-ttu-id="eac09-113">Durch den Testlauf werden Tests ausgeführt, die für ein Komponententestframework (z.B. MSTest, NUnit oder xUnit) definiert wurden, und der Erfolg oder Misserfolg der einzelnen Testausführungen wird gemeldet.</span><span class="sxs-lookup"><span data-stu-id="eac09-113">The test runner executes the tests defined for a unit test framework (for example, MSTest, NUnit, or xUnit) and reports the success or failure of each test.</span></span> <span data-ttu-id="eac09-114">Der Testlauf und die Komponententestbibliothek werden als NuGet-Pakete gepackt und als gewöhnliche Abhängigkeiten für das Projekt wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="eac09-114">The test runner and the unit test library are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="eac09-115">In Testprojekten wird der Testlauf mittels eines normalen `<PackageReference>`-Elements angegeben, wie in der folgenden Beispielprojektdatei gezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="eac09-115">Test projects specify the test runner using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

## <a name="arguments"></a><span data-ttu-id="eac09-116">Argumente</span><span class="sxs-lookup"><span data-stu-id="eac09-116">Arguments</span></span>

`PROJECT`

<span data-ttu-id="eac09-117">Der Pfad zum Testprojekt.</span><span class="sxs-lookup"><span data-stu-id="eac09-117">Path to the test project.</span></span> <span data-ttu-id="eac09-118">Wenn er nicht angegeben ist, wird standardmäßig das aktuelle Verzeichnis ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="eac09-118">If not specified, it defaults to current directory.</span></span>

## <a name="options"></a><span data-ttu-id="eac09-119">Optionen</span><span class="sxs-lookup"><span data-stu-id="eac09-119">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="eac09-120">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="eac09-120">.NET Core 2.1</span></span>](#tab/netcore21)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="eac09-121">Verwenden Sie die benutzerdefinierten Testadapter aus dem angegebenen Pfad im Testlauf.</span><span class="sxs-lookup"><span data-stu-id="eac09-121">Use the custom test adapters from the specified path in the test run.</span></span>

`--blame`

<span data-ttu-id="eac09-122">Führt die Tests im blame-Modus aus.</span><span class="sxs-lookup"><span data-stu-id="eac09-122">Runs the tests in blame mode.</span></span> <span data-ttu-id="eac09-123">Diese Option hilft beim Isolieren der fehlerhaften Tests, die den Absturz des Testhosts verursachen.</span><span class="sxs-lookup"><span data-stu-id="eac09-123">This option is helpful in isolating the problematic tests causing test host to crash.</span></span> <span data-ttu-id="eac09-124">In dem aktuellen Verzeichnis wird eine Ausgabedatei als *Sequence.xml* erstellt, die die Reihenfolge der ausgeführten Tests vor dem Absturz erfasst.</span><span class="sxs-lookup"><span data-stu-id="eac09-124">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="eac09-125">Legt die Buildkonfiguration fest.</span><span class="sxs-lookup"><span data-stu-id="eac09-125">Defines the build configuration.</span></span> <span data-ttu-id="eac09-126">Der Standardwert ist `Debug`, aber die Konfiguration des Projekts könnte diese SDK-Standardeinstellung überschreiben.</span><span class="sxs-lookup"><span data-stu-id="eac09-126">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

<span data-ttu-id="eac09-127">Aktiviert den Datensammler für den Testlauf.</span><span class="sxs-lookup"><span data-stu-id="eac09-127">Enables data collector for the test run.</span></span> <span data-ttu-id="eac09-128">Weitere Informationen finden Sie unter [Monitor and analyze test run (Überwachen und Analysieren eines Testlaufs)](https://aka.ms/vstest-collect).</span><span class="sxs-lookup"><span data-stu-id="eac09-128">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="eac09-129">Aktiviert den Diagnosemodus für die Testplattform und schreibt Diagnosemeldungen in die angegebene Datei.</span><span class="sxs-lookup"><span data-stu-id="eac09-129">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="eac09-130">Sucht nach Testbinärdateien für ein bestimmtes [Framework](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="eac09-130">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="eac09-131">Filtert Tests im aktuellen Projekt mithilfe des angegebenen Ausdrucks heraus.</span><span class="sxs-lookup"><span data-stu-id="eac09-131">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="eac09-132">Weitere Informationen finden Sie im Abschnitt [Details zu Filteroptionen](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="eac09-132">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="eac09-133">Weitere Informationen und Beispiele zur Verwendung von selektiven Komponententestfiltern finden Sie unter [Ausführen von selektiven Komponententests](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="eac09-133">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="eac09-134">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="eac09-134">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="eac09-135">Gibt eine Protokollierung für die Testergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="eac09-135">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="eac09-136">Erstellt das Projekt nicht vor der Ausführung.</span><span class="sxs-lookup"><span data-stu-id="eac09-136">Doesn't build the test project before running it.</span></span> <span data-ttu-id="eac09-137">Das `--no-restore`-Flag wird implizit festgelegt.</span><span class="sxs-lookup"><span data-stu-id="eac09-137">It also implicit sets the `--no-restore` flag.</span></span>

`--no-restore`

<span data-ttu-id="eac09-138">Führt keine implizite Wiederherstellung aus, wenn der Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="eac09-138">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="eac09-139">Verzeichnis, in dem die auszuführenden Binärdateien zu finden sind.</span><span class="sxs-lookup"><span data-stu-id="eac09-139">Directory in which to find the binaries to run.</span></span>

`-r|--results-directory <PATH>`

<span data-ttu-id="eac09-140">Das Verzeichnis, in dem die Testergebnisse gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="eac09-140">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="eac09-141">Wenn das Verzeichnis noch nicht vorhanden ist, wird es erstellt.</span><span class="sxs-lookup"><span data-stu-id="eac09-141">If the specified directory doesn't exist, it's created.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="eac09-142">Einstellungen, die beim Ausführen von Tests verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="eac09-142">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="eac09-143">Listen Sie alle ermittelten Tests im aktuellen Projekt auf.</span><span class="sxs-lookup"><span data-stu-id="eac09-143">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="eac09-144">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="eac09-144">Sets the verbosity level of the command.</span></span> <span data-ttu-id="eac09-145">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="eac09-145">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="eac09-146">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="eac09-146">.NET Core 2.0</span></span>](#tab/netcore20)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="eac09-147">Verwenden Sie die benutzerdefinierten Testadapter aus dem angegebenen Pfad im Testlauf.</span><span class="sxs-lookup"><span data-stu-id="eac09-147">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="eac09-148">Legt die Buildkonfiguration fest.</span><span class="sxs-lookup"><span data-stu-id="eac09-148">Defines the build configuration.</span></span> <span data-ttu-id="eac09-149">Der Standardwert ist `Debug`, aber die Konfiguration des Projekts könnte diese SDK-Standardeinstellung überschreiben.</span><span class="sxs-lookup"><span data-stu-id="eac09-149">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

<span data-ttu-id="eac09-150">Aktiviert den Datensammler für den Testlauf.</span><span class="sxs-lookup"><span data-stu-id="eac09-150">Enables data collector for the test run.</span></span> <span data-ttu-id="eac09-151">Weitere Informationen finden Sie unter [Monitor and analyze test run (Überwachen und Analysieren eines Testlaufs)](https://aka.ms/vstest-collect).</span><span class="sxs-lookup"><span data-stu-id="eac09-151">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="eac09-152">Aktiviert den Diagnosemodus für die Testplattform und schreibt Diagnosemeldungen in die angegebene Datei.</span><span class="sxs-lookup"><span data-stu-id="eac09-152">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="eac09-153">Sucht nach Testbinärdateien für ein bestimmtes [Framework](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="eac09-153">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="eac09-154">Filtert Tests im aktuellen Projekt mithilfe des angegebenen Ausdrucks heraus.</span><span class="sxs-lookup"><span data-stu-id="eac09-154">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="eac09-155">Weitere Informationen finden Sie im Abschnitt [Details zu Filteroptionen](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="eac09-155">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="eac09-156">Weitere Informationen und Beispiele zur Verwendung von selektiven Komponententestfiltern finden Sie unter [Ausführen von selektiven Komponententests](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="eac09-156">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="eac09-157">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="eac09-157">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="eac09-158">Gibt eine Protokollierung für die Testergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="eac09-158">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="eac09-159">Erstellt das Projekt nicht vor der Ausführung.</span><span class="sxs-lookup"><span data-stu-id="eac09-159">Doesn't build the test project before running it.</span></span> <span data-ttu-id="eac09-160">Das `--no-restore`-Flag wird implizit festgelegt.</span><span class="sxs-lookup"><span data-stu-id="eac09-160">It also implicit sets the `--no-restore` flag.</span></span>

`--no-restore`

<span data-ttu-id="eac09-161">Führt keine implizite Wiederherstellung aus, wenn der Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="eac09-161">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="eac09-162">Verzeichnis, in dem die auszuführenden Binärdateien zu finden sind.</span><span class="sxs-lookup"><span data-stu-id="eac09-162">Directory in which to find the binaries to run.</span></span>

`-r|--results-directory <PATH>`

<span data-ttu-id="eac09-163">Das Verzeichnis, in dem die Testergebnisse gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="eac09-163">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="eac09-164">Wenn das Verzeichnis noch nicht vorhanden ist, wird es erstellt.</span><span class="sxs-lookup"><span data-stu-id="eac09-164">If the specified directory doesn't exist, it's created.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="eac09-165">Einstellungen, die beim Ausführen von Tests verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="eac09-165">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="eac09-166">Listen Sie alle ermittelten Tests im aktuellen Projekt auf.</span><span class="sxs-lookup"><span data-stu-id="eac09-166">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="eac09-167">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="eac09-167">Sets the verbosity level of the command.</span></span> <span data-ttu-id="eac09-168">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="eac09-168">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="eac09-169">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="eac09-169">.NET Core 1.x</span></span>](#tab/netcore1x)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="eac09-170">Verwenden Sie die benutzerdefinierten Testadapter aus dem angegebenen Pfad im Testlauf.</span><span class="sxs-lookup"><span data-stu-id="eac09-170">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="eac09-171">Legt die Buildkonfiguration fest.</span><span class="sxs-lookup"><span data-stu-id="eac09-171">Defines the build configuration.</span></span> <span data-ttu-id="eac09-172">Der Standardwert ist `Debug`, aber die Konfiguration des Projekts könnte diese SDK-Standardeinstellung überschreiben.</span><span class="sxs-lookup"><span data-stu-id="eac09-172">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="eac09-173">Aktiviert den Diagnosemodus für die Testplattform und schreibt Diagnosemeldungen in die angegebene Datei.</span><span class="sxs-lookup"><span data-stu-id="eac09-173">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="eac09-174">Sucht nach Testbinärdateien für ein bestimmtes [Framework](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="eac09-174">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="eac09-175">Filtert Tests im aktuellen Projekt mithilfe des angegebenen Ausdrucks heraus.</span><span class="sxs-lookup"><span data-stu-id="eac09-175">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="eac09-176">Weitere Informationen finden Sie im Abschnitt [Details zu Filteroptionen](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="eac09-176">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="eac09-177">Weitere Informationen und Beispiele zur Verwendung von selektiven Komponententestfiltern finden Sie unter [Ausführen von selektiven Komponententests](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="eac09-177">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="eac09-178">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="eac09-178">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="eac09-179">Gibt eine Protokollierung für die Testergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="eac09-179">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="eac09-180">Erstellt das Projekt nicht vor der Ausführung.</span><span class="sxs-lookup"><span data-stu-id="eac09-180">Doesn't build the test project before running it.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="eac09-181">Verzeichnis, in dem die auszuführenden Binärdateien zu finden sind.</span><span class="sxs-lookup"><span data-stu-id="eac09-181">Directory in which to find the binaries to run.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="eac09-182">Einstellungen, die beim Ausführen von Tests verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="eac09-182">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="eac09-183">Listen Sie alle ermittelten Tests im aktuellen Projekt auf.</span><span class="sxs-lookup"><span data-stu-id="eac09-183">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="eac09-184">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="eac09-184">Sets the verbosity level of the command.</span></span> <span data-ttu-id="eac09-185">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="eac09-185">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="eac09-186">Beispiele</span><span class="sxs-lookup"><span data-stu-id="eac09-186">Examples</span></span>

<span data-ttu-id="eac09-187">Führen Sie die Tests im Projekt im aktuellen Verzeichnis durch:</span><span class="sxs-lookup"><span data-stu-id="eac09-187">Run the tests in the project in the current directory:</span></span>

`dotnet test`

<span data-ttu-id="eac09-188">Führen Sie die Tests im Projekt `test1` durch:</span><span class="sxs-lookup"><span data-stu-id="eac09-188">Run the tests in the `test1` project:</span></span>

`dotnet test ~/projects/test1/test1.csproj`

<span data-ttu-id="eac09-189">Führen Sie die Tests im aktuellen Verzeichnis aus, und generieren Sie eine Testergebnisdatei im TRX-Format:</span><span class="sxs-lookup"><span data-stu-id="eac09-189">Run the tests in the project in the current directory and generate a test results file in the trx format:</span></span>

`dotnet test --logger:trx`

## <a name="filter-option-details"></a><span data-ttu-id="eac09-190">Details zu Filteroptionen</span><span class="sxs-lookup"><span data-stu-id="eac09-190">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="eac09-191">`<Expression>` weist das Format `<property><operator><value>[|&<Expression>]` auf.</span><span class="sxs-lookup"><span data-stu-id="eac09-191">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="eac09-192">`<property>` ist ein Attribut von `Test Case`.</span><span class="sxs-lookup"><span data-stu-id="eac09-192">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="eac09-193">Im Folgenden werden die Eigenschaften aufgeführt, die von gängigen Frameworks für Komponententests unterstützt werden:</span><span class="sxs-lookup"><span data-stu-id="eac09-193">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="eac09-194">Testframework</span><span class="sxs-lookup"><span data-stu-id="eac09-194">Test Framework</span></span> | <span data-ttu-id="eac09-195">Unterstützte Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="eac09-195">Supported properties</span></span>                                                                                      |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="eac09-196">MSTest</span><span class="sxs-lookup"><span data-stu-id="eac09-196">MSTest</span></span>         | <ul><li><span data-ttu-id="eac09-197">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="eac09-197">FullyQualifiedName</span></span></li><li><span data-ttu-id="eac09-198">name</span><span class="sxs-lookup"><span data-stu-id="eac09-198">Name</span></span></li><li><span data-ttu-id="eac09-199">ClassName</span><span class="sxs-lookup"><span data-stu-id="eac09-199">ClassName</span></span></li><li><span data-ttu-id="eac09-200">Priorität</span><span class="sxs-lookup"><span data-stu-id="eac09-200">Priority</span></span></li><li><span data-ttu-id="eac09-201">TestCategory</span><span class="sxs-lookup"><span data-stu-id="eac09-201">TestCategory</span></span></li></ul> |
| <span data-ttu-id="eac09-202">xUnit</span><span class="sxs-lookup"><span data-stu-id="eac09-202">xUnit</span></span>          | <ul><li><span data-ttu-id="eac09-203">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="eac09-203">FullyQualifiedName</span></span></li><li><span data-ttu-id="eac09-204">DisplayName</span><span class="sxs-lookup"><span data-stu-id="eac09-204">DisplayName</span></span></li><li><span data-ttu-id="eac09-205">Merkmale</span><span class="sxs-lookup"><span data-stu-id="eac09-205">Traits</span></span></li></ul>                                   |

<span data-ttu-id="eac09-206">`<operator>` beschreibt die Beziehung zwischen der Eigenschaft und dem Wert:</span><span class="sxs-lookup"><span data-stu-id="eac09-206">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="eac09-207">Operator</span><span class="sxs-lookup"><span data-stu-id="eac09-207">Operator</span></span> | <span data-ttu-id="eac09-208">Funktion</span><span class="sxs-lookup"><span data-stu-id="eac09-208">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="eac09-209">Genaue Übereinstimmung</span><span class="sxs-lookup"><span data-stu-id="eac09-209">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="eac09-210">Keine genaue Übereinstimmung</span><span class="sxs-lookup"><span data-stu-id="eac09-210">Not exact match</span></span> |
| `~`      | <span data-ttu-id="eac09-211">Enthält</span><span class="sxs-lookup"><span data-stu-id="eac09-211">Contains</span></span>        |

<span data-ttu-id="eac09-212">`<value>` ist eine Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="eac09-212">`<value>` is a string.</span></span> <span data-ttu-id="eac09-213">Bei allen Suchvorgängen ist die Groß-/Kleinschreibung nicht relevant.</span><span class="sxs-lookup"><span data-stu-id="eac09-213">All the lookups are case insensitive.</span></span>

<span data-ttu-id="eac09-214">Ein Ausdruck ohne `<operator>` gilt automatisch als `contains` für die `FullyQualifiedName`-Eigenschaft (`dotnet test --filter xyz` ist beispielsweise identisch mit `dotnet test --filter FullyQualifiedName~xyz`).</span><span class="sxs-lookup"><span data-stu-id="eac09-214">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="eac09-215">Ausdrücke können mit bedingten Operatoren verknüpft werden:</span><span class="sxs-lookup"><span data-stu-id="eac09-215">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="eac09-216">Operator</span><span class="sxs-lookup"><span data-stu-id="eac09-216">Operator</span></span>            | <span data-ttu-id="eac09-217">Funktion</span><span class="sxs-lookup"><span data-stu-id="eac09-217">Function</span></span> |
| ------------------- | -------- |
| <code>&#124;</code> | <span data-ttu-id="eac09-218">ODER</span><span class="sxs-lookup"><span data-stu-id="eac09-218">OR</span></span>       |
| `&`                 | <span data-ttu-id="eac09-219">UND</span><span class="sxs-lookup"><span data-stu-id="eac09-219">AND</span></span>      |

<span data-ttu-id="eac09-220">Sie können Ausdrücke in Klammern einschließen, wenn Sie bedingte Operatoren verwenden (z.B. `(Name~TestMethod1) | (Name~TestMethod2)`).</span><span class="sxs-lookup"><span data-stu-id="eac09-220">You can enclose expressions in parenthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="eac09-221">Weitere Informationen und Beispiele zur Verwendung von selektiven Komponententestfiltern finden Sie unter [Ausführen von selektiven Komponententests](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="eac09-221">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="eac09-222">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eac09-222">See also</span></span>

* [<span data-ttu-id="eac09-223">Frameworks und Ziele</span><span class="sxs-lookup"><span data-stu-id="eac09-223">Frameworks and Targets</span></span>](../../standard/frameworks.md)  
* [<span data-ttu-id="eac09-224">.NET Core Runtime-ID (RID)-Katalog</span><span class="sxs-lookup"><span data-stu-id="eac09-224">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
