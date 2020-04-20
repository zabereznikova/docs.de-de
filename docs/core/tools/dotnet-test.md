---
title: Befehl „dotnet test“
description: Der Befehl „dotnet test“ wird zum Ausführen von Unittests in einem bestimmten Projekt verwendet.
ms.date: 02/27/2020
ms.openlocfilehash: f9df03cda01bdaf649394a58e96903e764193338
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463375"
---
# <a name="dotnet-test"></a><span data-ttu-id="1b074-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="1b074-103">dotnet test</span></span>

<span data-ttu-id="1b074-104">**Dieser Artikel gilt für:** ✔️ .NET Core 2.1 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="1b074-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="1b074-105">name</span><span class="sxs-lookup"><span data-stu-id="1b074-105">Name</span></span>

<span data-ttu-id="1b074-106">`dotnet test`: .NET-Testtreiber, der verwendet wird, um Komponententests auszuführen.</span><span class="sxs-lookup"><span data-stu-id="1b074-106">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="1b074-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="1b074-107">Synopsis</span></span>

```dotnetcli
dotnet test [<PROJECT> | <SOLUTION>]
    [-a|--test-adapter-path <PATH_TO_ADAPTER>] [--blame]
    [-c|--configuration <CONFIGURATION>]
    [--collect <DATA_COLLECTOR_FRIENDLY_NAME>]
    [-d|--diag <PATH_TO_DIAGNOSTICS_FILE>] [-f|--framework <FRAMEWORK>]
    [--filter <EXPRESSION>] [--interactive]
    [-l|--logger <LOGGER_URI/FRIENDLY_NAME>] [--no-build]
    [--nologo] [--no-restore] [-o|--output <OUTPUT_DIRECTORY>]
    [-r|--results-directory <PATH>] [--runtime <RUNTIME_IDENTIFIER>]
    [-s|--settings <SETTINGS_FILE>] [-t|--list-tests]
    [-v|--verbosity <LEVEL>] [[--] <RunSettings arguments>]

dotnet test -h|--help
```

## <a name="description"></a><span data-ttu-id="1b074-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1b074-108">Description</span></span>

<span data-ttu-id="1b074-109">Der Befehl `dotnet test` wird zum Ausführen von Komponententests in einem bestimmten Projekt verwendet.</span><span class="sxs-lookup"><span data-stu-id="1b074-109">The `dotnet test` command is used to execute unit tests in a given project.</span></span> <span data-ttu-id="1b074-110">Mit dem `dotnet test`-Befehl wird die Testlauf-Konsolenanwendung gestartet, die für ein Projekt angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="1b074-110">The `dotnet test` command launches the test runner console application specified for a project.</span></span> <span data-ttu-id="1b074-111">Durch den Testlauf werden Tests ausgeführt, die für ein Komponententestframework (z.B. MSTest, NUnit oder xUnit) definiert wurden, und der Erfolg oder Misserfolg der einzelnen Testausführungen wird gemeldet.</span><span class="sxs-lookup"><span data-stu-id="1b074-111">The test runner executes the tests defined for a unit test framework (for example, MSTest, NUnit, or xUnit) and reports the success or failure of each test.</span></span> <span data-ttu-id="1b074-112">Wenn alle Tests erfolgreich sind, gibt der Test Runner 0 (null) als Exitcode zurück. Wenn jedoch ein Test fehlschlägt, wird 1 zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="1b074-112">If all tests are successful, the test runner returns 0 as an exit code; otherwise if any test fails, it returns 1.</span></span> <span data-ttu-id="1b074-113">Der Testlauf und die Komponententestbibliothek werden als NuGet-Pakete gepackt und als gewöhnliche Abhängigkeiten für das Projekt wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="1b074-113">The test runner and the unit test library are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="1b074-114">In Testprojekten wird der Testlauf mittels eines normalen `<PackageReference>`-Elements angegeben, wie in der folgenden Beispielprojektdatei gezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="1b074-114">Test projects specify the test runner using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

## <a name="arguments"></a><span data-ttu-id="1b074-115">Argumente</span><span class="sxs-lookup"><span data-stu-id="1b074-115">Arguments</span></span>

- **`PROJECT | SOLUTION`**

  <span data-ttu-id="1b074-116">Pfad zum Testprojekt oder zur Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="1b074-116">Path to the test project or solution.</span></span> <span data-ttu-id="1b074-117">Wenn er nicht angegeben ist, wird standardmäßig das aktuelle Verzeichnis ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="1b074-117">If not specified, it defaults to current directory.</span></span>

## <a name="options"></a><span data-ttu-id="1b074-118">Optionen</span><span class="sxs-lookup"><span data-stu-id="1b074-118">Options</span></span>

- **`a|--test-adapter-path <PATH_TO_ADAPTER>`**

  <span data-ttu-id="1b074-119">Verwenden Sie die benutzerdefinierten Testadapter aus dem angegebenen Pfad im Testlauf.</span><span class="sxs-lookup"><span data-stu-id="1b074-119">Use the custom test adapters from the specified path in the test run.</span></span>

- **`--blame`**

  <span data-ttu-id="1b074-120">Führt die Tests im blame-Modus aus.</span><span class="sxs-lookup"><span data-stu-id="1b074-120">Runs the tests in blame mode.</span></span> <span data-ttu-id="1b074-121">Diese Option hilft beim Isolieren von fehlerhaften Tests, die den Absturz des Testhosts verursachen.</span><span class="sxs-lookup"><span data-stu-id="1b074-121">This option is helpful in isolating problematic tests that cause the test host to crash.</span></span> <span data-ttu-id="1b074-122">In dem aktuellen Verzeichnis wird eine Ausgabedatei als *Sequence.xml* erstellt, die die Reihenfolge der ausgeführten Tests vor dem Absturz erfasst.</span><span class="sxs-lookup"><span data-stu-id="1b074-122">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

- **`c|--configuration <CONFIGURATION>`**

  <span data-ttu-id="1b074-123">Legt die Buildkonfiguration fest.</span><span class="sxs-lookup"><span data-stu-id="1b074-123">Defines the build configuration.</span></span> <span data-ttu-id="1b074-124">Der Standardwert ist `Debug`, aber die Konfiguration des Projekts könnte diese SDK-Standardeinstellung überschreiben.</span><span class="sxs-lookup"><span data-stu-id="1b074-124">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

- **`-collect <DATA_COLLECTOR_FRIENDLY_NAME>`**

  <span data-ttu-id="1b074-125">Aktiviert den Datensammler für den Testlauf.</span><span class="sxs-lookup"><span data-stu-id="1b074-125">Enables data collector for the test run.</span></span> <span data-ttu-id="1b074-126">Weitere Informationen finden Sie unter [Monitor and analyze test run (Überwachen und Analysieren eines Testlaufs)](https://aka.ms/vstest-collect).</span><span class="sxs-lookup"><span data-stu-id="1b074-126">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

- **`d|--diag <PATH_TO_DIAGNOSTICS_FILE>`**

  <span data-ttu-id="1b074-127">Aktiviert den Diagnosemodus für die Testplattform und schreibt Diagnosemeldungen in die angegebene Datei.</span><span class="sxs-lookup"><span data-stu-id="1b074-127">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

- **`f|--framework <FRAMEWORK>`**

  <span data-ttu-id="1b074-128">Sucht nach Testbinärdateien für ein bestimmtes [Framework](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="1b074-128">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

- **`--filter <EXPRESSION>`**

  <span data-ttu-id="1b074-129">Filtert Tests im aktuellen Projekt mithilfe des angegebenen Ausdrucks heraus.</span><span class="sxs-lookup"><span data-stu-id="1b074-129">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="1b074-130">Weitere Informationen finden Sie im Abschnitt [Details zu Filteroptionen](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="1b074-130">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="1b074-131">Weitere Informationen und Beispiele zur Verwendung von selektiven Komponententestfiltern finden Sie unter [Ausführen von selektiven Komponententests](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="1b074-131">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

- **`h|--help`**

  <span data-ttu-id="1b074-132">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="1b074-132">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="1b074-133">Ermöglicht dem Befehl, anzuhalten und auf Benutzereingaben oder Aktionen zu warten.</span><span class="sxs-lookup"><span data-stu-id="1b074-133">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="1b074-134">Beispielsweise, um die Authentifizierung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="1b074-134">For example, to complete authentication.</span></span> <span data-ttu-id="1b074-135">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="1b074-135">Available since .NET Core 3.0 SDK.</span></span>

- **`l|--logger <LOGGER_URI/FRIENDLY_NAME>`**

  <span data-ttu-id="1b074-136">Gibt eine Protokollierung für die Testergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="1b074-136">Specifies a logger for test results.</span></span> <span data-ttu-id="1b074-137">Im Gegensatz zu MSBuild akzeptiert der Befehl „dotnet test“ keine Abkürzungen: verwenden Sie `-l "console;verbosity=detailed"` anstelle von `-l "console;v=d"`.</span><span class="sxs-lookup"><span data-stu-id="1b074-137">Unlike MSBuild, dotnet test doesn't accept abbreviations: instead of `-l "console;v=d"` use `-l "console;verbosity=detailed"`.</span></span>

- **`--no-build`**

  <span data-ttu-id="1b074-138">Erstellt das Projekt nicht vor der Ausführung.</span><span class="sxs-lookup"><span data-stu-id="1b074-138">Doesn't build the test project before running it.</span></span> <span data-ttu-id="1b074-139">Zudem wird das Flag `--no-restore` implizit festgelegt.</span><span class="sxs-lookup"><span data-stu-id="1b074-139">It also implicitly sets the - `--no-restore` flag.</span></span>

- **`--nologo`**

  <span data-ttu-id="1b074-140">Führen Sie Tests aus, ohne das Microsoft TestPlatform-Banner anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="1b074-140">Run tests without displaying the Microsoft TestPlatform banner.</span></span> <span data-ttu-id="1b074-141">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="1b074-141">Available since .NET Core 3.0 SDK.</span></span>

- **`--no-restore`**

  <span data-ttu-id="1b074-142">Führt keine implizite Wiederherstellung aus, wenn der Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1b074-142">Doesn't execute an implicit restore when running the command.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="1b074-143">Verzeichnis, in dem die auszuführenden Binärdateien zu finden sind.</span><span class="sxs-lookup"><span data-stu-id="1b074-143">Directory in which to find the binaries to run.</span></span>

- **`-r|--results-directory <PATH>`**

  <span data-ttu-id="1b074-144">Das Verzeichnis, in dem die Testergebnisse gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="1b074-144">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="1b074-145">Wenn das Verzeichnis noch nicht vorhanden ist, wird es erstellt.</span><span class="sxs-lookup"><span data-stu-id="1b074-145">If the specified directory doesn't exist, it's created.</span></span>

- **`--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="1b074-146">Die Zielruntime, für die Tests ausgeführt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="1b074-146">The target runtime to test for.</span></span>

- **`-s|--settings <SETTINGS_FILE>`**

  <span data-ttu-id="1b074-147">Die `.runsettings`-Datei, die zum Ausführen der Tests verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="1b074-147">The `.runsettings` file to use for running the tests.</span></span> [<span data-ttu-id="1b074-148">Konfigurieren von Komponententests mithilfe einer `.runsettings`-Datei.</span><span class="sxs-lookup"><span data-stu-id="1b074-148">Configure unit tests by using a `.runsettings` file.</span></span>](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file)

- **`-t|--list-tests`**

  <span data-ttu-id="1b074-149">Listen Sie alle ermittelten Tests im aktuellen Projekt auf.</span><span class="sxs-lookup"><span data-stu-id="1b074-149">List all of the discovered tests in the current project.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="1b074-150">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="1b074-150">Sets the verbosity level of the command.</span></span> <span data-ttu-id="1b074-151">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="1b074-151">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="1b074-152">Der Standardwert ist `minimal`.</span><span class="sxs-lookup"><span data-stu-id="1b074-152">The default is `minimal`.</span></span> <span data-ttu-id="1b074-153">Weitere Informationen finden Sie unter <xref:Microsoft.Build.Framework.LoggerVerbosity>.</span><span class="sxs-lookup"><span data-stu-id="1b074-153">For more information, see <xref:Microsoft.Build.Framework.LoggerVerbosity>.</span></span>

- <span data-ttu-id="1b074-154">`RunSettings`-Argumente</span><span class="sxs-lookup"><span data-stu-id="1b074-154">`RunSettings` arguments</span></span>

  <span data-ttu-id="1b074-155">Argumente werden als `RunSettings`-Konfigurationen für den Test übergeben.</span><span class="sxs-lookup"><span data-stu-id="1b074-155">Arguments are passed as `RunSettings` configurations for the test.</span></span> <span data-ttu-id="1b074-156">Argumente werden als `[name]=[value]`-Paaren nach „-- “ angegeben (Beachten Sie das Leerzeichen nach --).</span><span class="sxs-lookup"><span data-stu-id="1b074-156">Arguments are specified as `[name]=[value]` pairs after "-- " (note the space after --).</span></span> <span data-ttu-id="1b074-157">Ein Leerzeichen wird verwendet, um mehrere `[name]=[value]`-Paare voneinander zu trennen.</span><span class="sxs-lookup"><span data-stu-id="1b074-157">A space is used to separate multiple `[name]=[value]` pairs.</span></span>

  <span data-ttu-id="1b074-158">Ein Beispiel: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span><span class="sxs-lookup"><span data-stu-id="1b074-158">Example: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span></span>

  <span data-ttu-id="1b074-159">Weitere Informationen finden Sie unter [vstest.console.exe: Passing RunSettings args](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md) (Übergeben von RunSettings-Argumenten).</span><span class="sxs-lookup"><span data-stu-id="1b074-159">For more information, see [vstest.console.exe: Passing RunSettings args](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).</span></span>

## <a name="examples"></a><span data-ttu-id="1b074-160">Beispiele</span><span class="sxs-lookup"><span data-stu-id="1b074-160">Examples</span></span>

- <span data-ttu-id="1b074-161">Führen Sie die Tests im Projekt im aktuellen Verzeichnis durch:</span><span class="sxs-lookup"><span data-stu-id="1b074-161">Run the tests in the project in the current directory:</span></span>

  ```dotnetcli
  dotnet test
  ```

- <span data-ttu-id="1b074-162">Führen Sie die Tests im Projekt `test1` durch:</span><span class="sxs-lookup"><span data-stu-id="1b074-162">Run the tests in the `test1` project:</span></span>

  ```dotnetcli
  dotnet test ~/projects/test1/test1.csproj
  ```

- <span data-ttu-id="1b074-163">Mit dem folgenden Befehl führen Sie die Tests im aktuellen Verzeichnis aus und generieren eine Testergebnisdatei im TRX-Format:</span><span class="sxs-lookup"><span data-stu-id="1b074-163">Run the tests in the project in the current directory, and generate a test results file in the trx format:</span></span>

  ```dotnetcli
  dotnet test --logger trx
  ```

- <span data-ttu-id="1b074-164">Mit dem folgenden Befehl führen Sie die Tests im aktuellen Verzeichnis aus und erstellen ein ausführliches Protokoll in der Konsole:</span><span class="sxs-lookup"><span data-stu-id="1b074-164">Run the tests in the project in the current directory, and log with detailed verbosity to the console:</span></span>

  ```dotnetcli
  dotnet test --logger "console;verbosity=detailed"
  ```

## <a name="filter-option-details"></a><span data-ttu-id="1b074-165">Details zu Filteroptionen</span><span class="sxs-lookup"><span data-stu-id="1b074-165">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="1b074-166">`<Expression>` weist das Format `<property><operator><value>[|&<Expression>]` auf.</span><span class="sxs-lookup"><span data-stu-id="1b074-166">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="1b074-167">`<property>` ist ein Attribut von `Test Case`.</span><span class="sxs-lookup"><span data-stu-id="1b074-167">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="1b074-168">Im Folgenden werden die Eigenschaften aufgeführt, die von gängigen Frameworks für Komponententests unterstützt werden:</span><span class="sxs-lookup"><span data-stu-id="1b074-168">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="1b074-169">Testframework</span><span class="sxs-lookup"><span data-stu-id="1b074-169">Test Framework</span></span> | <span data-ttu-id="1b074-170">Unterstützte Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="1b074-170">Supported properties</span></span>                                                                                      |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="1b074-171">MSTest</span><span class="sxs-lookup"><span data-stu-id="1b074-171">MSTest</span></span>         | <ul><li><span data-ttu-id="1b074-172">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="1b074-172">FullyQualifiedName</span></span></li><li><span data-ttu-id="1b074-173">name</span><span class="sxs-lookup"><span data-stu-id="1b074-173">Name</span></span></li><li><span data-ttu-id="1b074-174">ClassName</span><span class="sxs-lookup"><span data-stu-id="1b074-174">ClassName</span></span></li><li><span data-ttu-id="1b074-175">Priorität</span><span class="sxs-lookup"><span data-stu-id="1b074-175">Priority</span></span></li><li><span data-ttu-id="1b074-176">TestCategory</span><span class="sxs-lookup"><span data-stu-id="1b074-176">TestCategory</span></span></li></ul> |
| <span data-ttu-id="1b074-177">xUnit</span><span class="sxs-lookup"><span data-stu-id="1b074-177">xUnit</span></span>          | <ul><li><span data-ttu-id="1b074-178">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="1b074-178">FullyQualifiedName</span></span></li><li><span data-ttu-id="1b074-179">DisplayName</span><span class="sxs-lookup"><span data-stu-id="1b074-179">DisplayName</span></span></li><li><span data-ttu-id="1b074-180">Merkmale</span><span class="sxs-lookup"><span data-stu-id="1b074-180">Traits</span></span></li></ul>                                   |

<span data-ttu-id="1b074-181">`<operator>` beschreibt die Beziehung zwischen der Eigenschaft und dem Wert:</span><span class="sxs-lookup"><span data-stu-id="1b074-181">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="1b074-182">Operator</span><span class="sxs-lookup"><span data-stu-id="1b074-182">Operator</span></span> | <span data-ttu-id="1b074-183">Funktion</span><span class="sxs-lookup"><span data-stu-id="1b074-183">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="1b074-184">Genaue Übereinstimmung</span><span class="sxs-lookup"><span data-stu-id="1b074-184">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="1b074-185">Keine genaue Übereinstimmung</span><span class="sxs-lookup"><span data-stu-id="1b074-185">Not exact match</span></span> |
| `~`      | <span data-ttu-id="1b074-186">Enthält</span><span class="sxs-lookup"><span data-stu-id="1b074-186">Contains</span></span>        |
| `!~`     | <span data-ttu-id="1b074-187">Enthält nicht</span><span class="sxs-lookup"><span data-stu-id="1b074-187">Not contains</span></span>    |

<span data-ttu-id="1b074-188">`<value>` ist eine Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="1b074-188">`<value>` is a string.</span></span> <span data-ttu-id="1b074-189">Bei allen Suchvorgängen ist die Groß-/Kleinschreibung nicht relevant.</span><span class="sxs-lookup"><span data-stu-id="1b074-189">All the lookups are case insensitive.</span></span>

<span data-ttu-id="1b074-190">Ein Ausdruck ohne `<operator>` gilt automatisch als `contains` für die `FullyQualifiedName`-Eigenschaft (`dotnet test --filter xyz` ist beispielsweise identisch mit `dotnet test --filter FullyQualifiedName~xyz`).</span><span class="sxs-lookup"><span data-stu-id="1b074-190">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="1b074-191">Ausdrücke können mit bedingten Operatoren verknüpft werden:</span><span class="sxs-lookup"><span data-stu-id="1b074-191">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="1b074-192">Operator</span><span class="sxs-lookup"><span data-stu-id="1b074-192">Operator</span></span>            | <span data-ttu-id="1b074-193">Funktion</span><span class="sxs-lookup"><span data-stu-id="1b074-193">Function</span></span> |
| ------------------- | -------- |
| <code>&#124;</code> | <span data-ttu-id="1b074-194">ODER</span><span class="sxs-lookup"><span data-stu-id="1b074-194">OR</span></span>       |
| `&`                 | <span data-ttu-id="1b074-195">UND</span><span class="sxs-lookup"><span data-stu-id="1b074-195">AND</span></span>      |

<span data-ttu-id="1b074-196">Sie können Ausdrücke in Klammern einschließen, wenn Sie bedingte Operatoren verwenden (z.B. `(Name~TestMethod1) | (Name~TestMethod2)`).</span><span class="sxs-lookup"><span data-stu-id="1b074-196">You can enclose expressions in parenthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="1b074-197">Weitere Informationen und Beispiele zur Verwendung von selektiven Komponententestfiltern finden Sie unter [Ausführen von selektiven Komponententests](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="1b074-197">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1b074-198">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1b074-198">See also</span></span>

- [<span data-ttu-id="1b074-199">Frameworks und Ziele</span><span class="sxs-lookup"><span data-stu-id="1b074-199">Frameworks and Targets</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="1b074-200">.NET Core Runtime-ID (RID)-Katalog</span><span class="sxs-lookup"><span data-stu-id="1b074-200">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
- [<span data-ttu-id="1b074-201">Übergeben von runsettings-Argumenten über die Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="1b074-201">Passing runsettings arguments through commandline</span></span>](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md)
