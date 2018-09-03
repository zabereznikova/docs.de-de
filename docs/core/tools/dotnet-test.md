---
title: dotnet test-Befehl – .NET Core-CLI
description: Der Befehl „dotnet test“ wird zum Ausführen von Unittests in einem bestimmten Projekt verwendet.
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: 2bee78ca44026f28c51fac3bcf87d976b53e48a7
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43390689"
---
# <a name="dotnet-test"></a><span data-ttu-id="cdc48-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="cdc48-103">dotnet test</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="cdc48-104">name</span><span class="sxs-lookup"><span data-stu-id="cdc48-104">Name</span></span>

<span data-ttu-id="cdc48-105">`dotnet test`: .NET-Testtreiber, der verwendet wird, um Komponententests auszuführen.</span><span class="sxs-lookup"><span data-stu-id="cdc48-105">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="cdc48-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="cdc48-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="cdc48-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="cdc48-107">.NET Core 2.1</span></span>](#tab/netcore21)

```console
dotnet test [<PROJECT>] [-a|--test-adapter-path] [--blame] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter]
    [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] [-v|--verbosity]
dotnet test [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="cdc48-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="cdc48-108">.NET Core 2.0</span></span>](#tab/netcore20)

```console
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter]
    [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] [-v|--verbosity]
dotnet test [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="cdc48-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="cdc48-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [-d|--diag] [-f|--framework] [--filter] [-l|--logger] [--no-build] [-o|--output] [-s|--settings] [-t|--list-tests]  [-v|--verbosity]
dotnet test [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="cdc48-110">Beschreibung </span><span class="sxs-lookup"><span data-stu-id="cdc48-110">Description</span></span>

<span data-ttu-id="cdc48-111">Der Befehl `dotnet test` wird zum Ausführen von Komponententests in einem bestimmten Projekt verwendet.</span><span class="sxs-lookup"><span data-stu-id="cdc48-111">The `dotnet test` command is used to execute unit tests in a given project.</span></span> <span data-ttu-id="cdc48-112">Mit dem `dotnet test`-Befehl wird die Testlauf-Konsolenanwendung gestartet, die für ein Projekt angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="cdc48-112">The `dotnet test` command launches the test runner console application specified for a project.</span></span> <span data-ttu-id="cdc48-113">Durch den Testlauf werden Tests ausgeführt, die für ein Komponententestframework (z.B. MSTest, NUnit oder xUnit) definiert wurden, und der Erfolg oder Misserfolg der einzelnen Testausführungen wird gemeldet.</span><span class="sxs-lookup"><span data-stu-id="cdc48-113">The test runner executes the tests defined for a unit test framework (for example, MSTest, NUnit, or xUnit) and reports the success or failure of each test.</span></span> <span data-ttu-id="cdc48-114">Der Testlauf und die Komponententestbibliothek werden als NuGet-Pakete gepackt und als gewöhnliche Abhängigkeiten für das Projekt wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="cdc48-114">The test runner and the unit test library are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="cdc48-115">In Testprojekten wird der Testlauf mittels eines normalen `<PackageReference>`-Elements angegeben, wie in der folgenden Beispielprojektdatei gezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="cdc48-115">Test projects specify the test runner using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

## <a name="arguments"></a><span data-ttu-id="cdc48-116">Argumente</span><span class="sxs-lookup"><span data-stu-id="cdc48-116">Arguments</span></span>

`PROJECT`

<span data-ttu-id="cdc48-117">Der Pfad zum Testprojekt.</span><span class="sxs-lookup"><span data-stu-id="cdc48-117">Path to the test project.</span></span> <span data-ttu-id="cdc48-118">Wenn er nicht angegeben ist, wird standardmäßig das aktuelle Verzeichnis ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="cdc48-118">If not specified, it defaults to current directory.</span></span>

## <a name="options"></a><span data-ttu-id="cdc48-119">Optionen</span><span class="sxs-lookup"><span data-stu-id="cdc48-119">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="cdc48-120">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="cdc48-120">.NET Core 2.1</span></span>](#tab/netcore21)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="cdc48-121">Verwenden Sie die benutzerdefinierten Testadapter aus dem angegebenen Pfad im Testlauf.</span><span class="sxs-lookup"><span data-stu-id="cdc48-121">Use the custom test adapters from the specified path in the test run.</span></span>

`--blame`

<span data-ttu-id="cdc48-122">Führt die Tests im blame-Modus aus.</span><span class="sxs-lookup"><span data-stu-id="cdc48-122">Runs the tests in blame mode.</span></span> <span data-ttu-id="cdc48-123">Diese Option hilft beim Isolieren der fehlerhaften Tests, die den Absturz des Testhosts verursachen.</span><span class="sxs-lookup"><span data-stu-id="cdc48-123">This option is helpful in isolating the problematic tests causing test host to crash.</span></span> <span data-ttu-id="cdc48-124">In dem aktuellen Verzeichnis wird eine Ausgabedatei als *Sequence.xml* erstellt, die die Reihenfolge der ausgeführten Tests vor dem Absturz erfasst.</span><span class="sxs-lookup"><span data-stu-id="cdc48-124">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="cdc48-125">Legt die Buildkonfiguration fest.</span><span class="sxs-lookup"><span data-stu-id="cdc48-125">Defines the build configuration.</span></span> <span data-ttu-id="cdc48-126">Der Standardwert ist `Debug`, aber die Konfiguration des Projekts könnte diese SDK-Standardeinstellung überschreiben.</span><span class="sxs-lookup"><span data-stu-id="cdc48-126">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

<span data-ttu-id="cdc48-127">Aktiviert den Datensammler für den Testlauf.</span><span class="sxs-lookup"><span data-stu-id="cdc48-127">Enables data collector for the test run.</span></span> <span data-ttu-id="cdc48-128">Weitere Informationen finden Sie unter [Monitor and analyze test run (Überwachen und Analysieren eines Testlaufs)](https://aka.ms/vstest-collect).</span><span class="sxs-lookup"><span data-stu-id="cdc48-128">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="cdc48-129">Aktiviert den Diagnosemodus für die Testplattform und schreibt Diagnosemeldungen in die angegebene Datei.</span><span class="sxs-lookup"><span data-stu-id="cdc48-129">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="cdc48-130">Sucht nach Testbinärdateien für ein bestimmtes [Framework](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="cdc48-130">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="cdc48-131">Filtert Tests im aktuellen Projekt mithilfe des angegebenen Ausdrucks heraus.</span><span class="sxs-lookup"><span data-stu-id="cdc48-131">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="cdc48-132">Weitere Informationen finden Sie im Abschnitt [Details zu Filteroptionen](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="cdc48-132">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="cdc48-133">Weitere Informationen und Beispiele zur Verwendung von selektiven Komponententestfiltern finden Sie unter [Ausführen von selektiven Komponententests](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="cdc48-133">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="cdc48-134">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="cdc48-134">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="cdc48-135">Gibt eine Protokollierung für die Testergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="cdc48-135">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="cdc48-136">Erstellt das Projekt nicht vor der Ausführung.</span><span class="sxs-lookup"><span data-stu-id="cdc48-136">Doesn't build the test project before running it.</span></span> <span data-ttu-id="cdc48-137">Das `--no-restore`-Flag wird implizit festgelegt.</span><span class="sxs-lookup"><span data-stu-id="cdc48-137">It also implicit sets the `--no-restore` flag.</span></span>

`--no-restore`

<span data-ttu-id="cdc48-138">Führt keine implizite Wiederherstellung aus, wenn der Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="cdc48-138">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="cdc48-139">Verzeichnis, in dem die auszuführenden Binärdateien zu finden sind.</span><span class="sxs-lookup"><span data-stu-id="cdc48-139">Directory in which to find the binaries to run.</span></span>

`-r|--results-directory <PATH>`

<span data-ttu-id="cdc48-140">Das Verzeichnis, in dem die Testergebnisse gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="cdc48-140">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="cdc48-141">Wenn das Verzeichnis noch nicht vorhanden ist, wird es erstellt.</span><span class="sxs-lookup"><span data-stu-id="cdc48-141">If the specified directory doesn't exist, it's created.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="cdc48-142">Einstellungen, die beim Ausführen von Tests verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cdc48-142">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="cdc48-143">Listen Sie alle ermittelten Tests im aktuellen Projekt auf.</span><span class="sxs-lookup"><span data-stu-id="cdc48-143">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="cdc48-144">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="cdc48-144">Sets the verbosity level of the command.</span></span> <span data-ttu-id="cdc48-145">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="cdc48-145">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="cdc48-146">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="cdc48-146">.NET Core 2.0</span></span>](#tab/netcore20)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="cdc48-147">Verwenden Sie die benutzerdefinierten Testadapter aus dem angegebenen Pfad im Testlauf.</span><span class="sxs-lookup"><span data-stu-id="cdc48-147">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="cdc48-148">Legt die Buildkonfiguration fest.</span><span class="sxs-lookup"><span data-stu-id="cdc48-148">Defines the build configuration.</span></span> <span data-ttu-id="cdc48-149">Der Standardwert ist `Debug`, aber die Konfiguration des Projekts könnte diese SDK-Standardeinstellung überschreiben.</span><span class="sxs-lookup"><span data-stu-id="cdc48-149">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

<span data-ttu-id="cdc48-150">Aktiviert den Datensammler für den Testlauf.</span><span class="sxs-lookup"><span data-stu-id="cdc48-150">Enables data collector for the test run.</span></span> <span data-ttu-id="cdc48-151">Weitere Informationen finden Sie unter [Monitor and analyze test run (Überwachen und Analysieren eines Testlaufs)](https://aka.ms/vstest-collect).</span><span class="sxs-lookup"><span data-stu-id="cdc48-151">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="cdc48-152">Aktiviert den Diagnosemodus für die Testplattform und schreibt Diagnosemeldungen in die angegebene Datei.</span><span class="sxs-lookup"><span data-stu-id="cdc48-152">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="cdc48-153">Sucht nach Testbinärdateien für ein bestimmtes [Framework](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="cdc48-153">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="cdc48-154">Filtert Tests im aktuellen Projekt mithilfe des angegebenen Ausdrucks heraus.</span><span class="sxs-lookup"><span data-stu-id="cdc48-154">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="cdc48-155">Weitere Informationen finden Sie im Abschnitt [Details zu Filteroptionen](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="cdc48-155">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="cdc48-156">Weitere Informationen und Beispiele zur Verwendung von selektiven Komponententestfiltern finden Sie unter [Ausführen von selektiven Komponententests](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="cdc48-156">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="cdc48-157">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="cdc48-157">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="cdc48-158">Gibt eine Protokollierung für die Testergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="cdc48-158">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="cdc48-159">Erstellt das Projekt nicht vor der Ausführung.</span><span class="sxs-lookup"><span data-stu-id="cdc48-159">Doesn't build the test project before running it.</span></span> <span data-ttu-id="cdc48-160">Das `--no-restore`-Flag wird implizit festgelegt.</span><span class="sxs-lookup"><span data-stu-id="cdc48-160">It also implicit sets the `--no-restore` flag.</span></span>

`--no-restore`

<span data-ttu-id="cdc48-161">Führt keine implizite Wiederherstellung aus, wenn der Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="cdc48-161">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="cdc48-162">Verzeichnis, in dem die auszuführenden Binärdateien zu finden sind.</span><span class="sxs-lookup"><span data-stu-id="cdc48-162">Directory in which to find the binaries to run.</span></span>

`-r|--results-directory <PATH>`

<span data-ttu-id="cdc48-163">Das Verzeichnis, in dem die Testergebnisse gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="cdc48-163">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="cdc48-164">Wenn das Verzeichnis noch nicht vorhanden ist, wird es erstellt.</span><span class="sxs-lookup"><span data-stu-id="cdc48-164">If the specified directory doesn't exist, it's created.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="cdc48-165">Einstellungen, die beim Ausführen von Tests verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cdc48-165">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="cdc48-166">Listen Sie alle ermittelten Tests im aktuellen Projekt auf.</span><span class="sxs-lookup"><span data-stu-id="cdc48-166">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="cdc48-167">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="cdc48-167">Sets the verbosity level of the command.</span></span> <span data-ttu-id="cdc48-168">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="cdc48-168">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="cdc48-169">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="cdc48-169">.NET Core 1.x</span></span>](#tab/netcore1x)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="cdc48-170">Verwenden Sie die benutzerdefinierten Testadapter aus dem angegebenen Pfad im Testlauf.</span><span class="sxs-lookup"><span data-stu-id="cdc48-170">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="cdc48-171">Legt die Buildkonfiguration fest.</span><span class="sxs-lookup"><span data-stu-id="cdc48-171">Defines the build configuration.</span></span> <span data-ttu-id="cdc48-172">Der Standardwert ist `Debug`, aber die Konfiguration des Projekts könnte diese SDK-Standardeinstellung überschreiben.</span><span class="sxs-lookup"><span data-stu-id="cdc48-172">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="cdc48-173">Aktiviert den Diagnosemodus für die Testplattform und schreibt Diagnosemeldungen in die angegebene Datei.</span><span class="sxs-lookup"><span data-stu-id="cdc48-173">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="cdc48-174">Sucht nach Testbinärdateien für ein bestimmtes [Framework](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="cdc48-174">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="cdc48-175">Filtert Tests im aktuellen Projekt mithilfe des angegebenen Ausdrucks heraus.</span><span class="sxs-lookup"><span data-stu-id="cdc48-175">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="cdc48-176">Weitere Informationen finden Sie im Abschnitt [Details zu Filteroptionen](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="cdc48-176">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="cdc48-177">Weitere Informationen und Beispiele zur Verwendung von selektiven Komponententestfiltern finden Sie unter [Ausführen von selektiven Komponententests](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="cdc48-177">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="cdc48-178">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="cdc48-178">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="cdc48-179">Gibt eine Protokollierung für die Testergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="cdc48-179">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="cdc48-180">Erstellt das Projekt nicht vor der Ausführung.</span><span class="sxs-lookup"><span data-stu-id="cdc48-180">Doesn't build the test project before running it.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="cdc48-181">Verzeichnis, in dem die auszuführenden Binärdateien zu finden sind.</span><span class="sxs-lookup"><span data-stu-id="cdc48-181">Directory in which to find the binaries to run.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="cdc48-182">Einstellungen, die beim Ausführen von Tests verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cdc48-182">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="cdc48-183">Listen Sie alle ermittelten Tests im aktuellen Projekt auf.</span><span class="sxs-lookup"><span data-stu-id="cdc48-183">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="cdc48-184">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="cdc48-184">Sets the verbosity level of the command.</span></span> <span data-ttu-id="cdc48-185">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="cdc48-185">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="cdc48-186">Beispiele</span><span class="sxs-lookup"><span data-stu-id="cdc48-186">Examples</span></span>

<span data-ttu-id="cdc48-187">Führen Sie die Tests im Projekt im aktuellen Verzeichnis durch:</span><span class="sxs-lookup"><span data-stu-id="cdc48-187">Run the tests in the project in the current directory:</span></span>

`dotnet test`

<span data-ttu-id="cdc48-188">Führen Sie die Tests im Projekt `test1` durch:</span><span class="sxs-lookup"><span data-stu-id="cdc48-188">Run the tests in the `test1` project:</span></span>

`dotnet test ~/projects/test1/test1.csproj`

## <a name="filter-option-details"></a><span data-ttu-id="cdc48-189">Details zu Filteroptionen</span><span class="sxs-lookup"><span data-stu-id="cdc48-189">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="cdc48-190">`<Expression>` weist das Format `<property><operator><value>[|&<Expression>]` auf.</span><span class="sxs-lookup"><span data-stu-id="cdc48-190">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="cdc48-191">`<property>` ist ein Attribut von `Test Case`.</span><span class="sxs-lookup"><span data-stu-id="cdc48-191">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="cdc48-192">Im Folgenden werden die Eigenschaften aufgeführt, die von gängigen Frameworks für Komponententests unterstützt werden:</span><span class="sxs-lookup"><span data-stu-id="cdc48-192">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="cdc48-193">Testframework</span><span class="sxs-lookup"><span data-stu-id="cdc48-193">Test Framework</span></span> | <span data-ttu-id="cdc48-194">Unterstützte Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="cdc48-194">Supported properties</span></span>                                                                                      |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="cdc48-195">MSTest</span><span class="sxs-lookup"><span data-stu-id="cdc48-195">MSTest</span></span>         | <ul><li><span data-ttu-id="cdc48-196">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="cdc48-196">FullyQualifiedName</span></span></li><li><span data-ttu-id="cdc48-197">name</span><span class="sxs-lookup"><span data-stu-id="cdc48-197">Name</span></span></li><li><span data-ttu-id="cdc48-198">ClassName</span><span class="sxs-lookup"><span data-stu-id="cdc48-198">ClassName</span></span></li><li><span data-ttu-id="cdc48-199">Priorität</span><span class="sxs-lookup"><span data-stu-id="cdc48-199">Priority</span></span></li><li><span data-ttu-id="cdc48-200">TestCategory</span><span class="sxs-lookup"><span data-stu-id="cdc48-200">TestCategory</span></span></li></ul> |
| <span data-ttu-id="cdc48-201">xUnit</span><span class="sxs-lookup"><span data-stu-id="cdc48-201">xUnit</span></span>          | <ul><li><span data-ttu-id="cdc48-202">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="cdc48-202">FullyQualifiedName</span></span></li><li><span data-ttu-id="cdc48-203">DisplayName</span><span class="sxs-lookup"><span data-stu-id="cdc48-203">DisplayName</span></span></li><li><span data-ttu-id="cdc48-204">Merkmale</span><span class="sxs-lookup"><span data-stu-id="cdc48-204">Traits</span></span></li></ul>                                   |

<span data-ttu-id="cdc48-205">`<operator>` beschreibt die Beziehung zwischen der Eigenschaft und dem Wert:</span><span class="sxs-lookup"><span data-stu-id="cdc48-205">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="cdc48-206">Operator</span><span class="sxs-lookup"><span data-stu-id="cdc48-206">Operator</span></span> | <span data-ttu-id="cdc48-207">Funktion</span><span class="sxs-lookup"><span data-stu-id="cdc48-207">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="cdc48-208">Genaue Übereinstimmung</span><span class="sxs-lookup"><span data-stu-id="cdc48-208">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="cdc48-209">Keine genaue Übereinstimmung</span><span class="sxs-lookup"><span data-stu-id="cdc48-209">Not exact match</span></span> |
| `~`      | <span data-ttu-id="cdc48-210">Enthält</span><span class="sxs-lookup"><span data-stu-id="cdc48-210">Contains</span></span>        |

<span data-ttu-id="cdc48-211">`<value>` ist eine Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="cdc48-211">`<value>` is a string.</span></span> <span data-ttu-id="cdc48-212">Bei allen Suchvorgängen ist die Groß-/Kleinschreibung nicht relevant.</span><span class="sxs-lookup"><span data-stu-id="cdc48-212">All the lookups are case insensitive.</span></span>

<span data-ttu-id="cdc48-213">Ein Ausdruck ohne `<operator>` gilt automatisch als `contains` für die `FullyQualifiedName`-Eigenschaft (`dotnet test --filter xyz` ist beispielsweise identisch mit `dotnet test --filter FullyQualifiedName~xyz`).</span><span class="sxs-lookup"><span data-stu-id="cdc48-213">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="cdc48-214">Ausdrücke können mit bedingten Operatoren verknüpft werden:</span><span class="sxs-lookup"><span data-stu-id="cdc48-214">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="cdc48-215">Operator</span><span class="sxs-lookup"><span data-stu-id="cdc48-215">Operator</span></span>            | <span data-ttu-id="cdc48-216">Funktion</span><span class="sxs-lookup"><span data-stu-id="cdc48-216">Function</span></span> |
| ------------------- | -------- |
| <code>&#124;</code> | <span data-ttu-id="cdc48-217">ODER</span><span class="sxs-lookup"><span data-stu-id="cdc48-217">OR</span></span>       |
| `&`                 | <span data-ttu-id="cdc48-218">UND</span><span class="sxs-lookup"><span data-stu-id="cdc48-218">AND</span></span>      |

<span data-ttu-id="cdc48-219">Sie können Ausdrücke in Klammern einschließen, wenn Sie bedingte Operatoren verwenden (z.B. `(Name~TestMethod1) | (Name~TestMethod2)`).</span><span class="sxs-lookup"><span data-stu-id="cdc48-219">You can enclose expressions in parenthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="cdc48-220">Weitere Informationen und Beispiele zur Verwendung von selektiven Komponententestfiltern finden Sie unter [Ausführen von selektiven Komponententests](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="cdc48-220">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="cdc48-221">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cdc48-221">See also</span></span>

* [<span data-ttu-id="cdc48-222">Frameworks und Ziele</span><span class="sxs-lookup"><span data-stu-id="cdc48-222">Frameworks and Targets</span></span>](../../standard/frameworks.md)  
* [<span data-ttu-id="cdc48-223">.NET Core Runtime-ID (RID)-Katalog</span><span class="sxs-lookup"><span data-stu-id="cdc48-223">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
