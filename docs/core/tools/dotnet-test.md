---
title: Befehl „dotnet test“
description: Der Befehl „dotnet test“ wird zum Ausführen von Unittests in einem bestimmten Projekt verwendet.
ms.date: 02/27/2020
ms.openlocfilehash: a11814f9fdc6326e681a09d7d2654b968014f318
ms.sourcegitcommit: 2514f4e3655081dcfe1b22470c0c28500f952c42
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/18/2020
ms.locfileid: "79507307"
---
# <a name="dotnet-test"></a><span data-ttu-id="117e5-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="117e5-103">dotnet test</span></span>

<span data-ttu-id="117e5-104">**Dieser Artikel gilt für:** ✔️ .NET Core 2.1 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="117e5-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="117e5-105">name</span><span class="sxs-lookup"><span data-stu-id="117e5-105">Name</span></span>

<span data-ttu-id="117e5-106">`dotnet test`: .NET-Testtreiber, der verwendet wird, um Komponententests auszuführen.</span><span class="sxs-lookup"><span data-stu-id="117e5-106">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="117e5-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="117e5-107">Synopsis</span></span>

```dotnetcli
dotnet test [<PROJECT> | <SOLUTION>]
    [-a|--test-adapter-path] [--blame] [-c|--configuration]
    [--collect] [-d|--diag] [-f|--framework] [--filter]
    [--interactive] [-l|--logger] [--no-build] [--nologo]
    [--no-restore] [-o|--output] [-r|--results-directory]
    [--runtime] [-s|--settings] [-t|--list-tests]
    [-v|--verbosity] [[--] <RunSettings arguments>]

dotnet test [-h|--help]
```

## <a name="description"></a><span data-ttu-id="117e5-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="117e5-108">Description</span></span>

<span data-ttu-id="117e5-109">Der Befehl `dotnet test` wird zum Ausführen von Komponententests in einem bestimmten Projekt verwendet.</span><span class="sxs-lookup"><span data-stu-id="117e5-109">The `dotnet test` command is used to execute unit tests in a given project.</span></span> <span data-ttu-id="117e5-110">Mit dem `dotnet test`-Befehl wird die Testlauf-Konsolenanwendung gestartet, die für ein Projekt angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="117e5-110">The `dotnet test` command launches the test runner console application specified for a project.</span></span> <span data-ttu-id="117e5-111">Durch den Testlauf werden Tests ausgeführt, die für ein Komponententestframework (z.B. MSTest, NUnit oder xUnit) definiert wurden, und der Erfolg oder Misserfolg der einzelnen Testausführungen wird gemeldet.</span><span class="sxs-lookup"><span data-stu-id="117e5-111">The test runner executes the tests defined for a unit test framework (for example, MSTest, NUnit, or xUnit) and reports the success or failure of each test.</span></span> <span data-ttu-id="117e5-112">Wenn alle Tests erfolgreich sind, gibt der Test Runner 0 (null) als Exitcode zurück. Wenn jedoch ein Test fehlschlägt, wird 1 zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="117e5-112">If all tests are successful, the test runner returns 0 as an exit code; otherwise if any test fails, it returns 1.</span></span> <span data-ttu-id="117e5-113">Der Testlauf und die Komponententestbibliothek werden als NuGet-Pakete gepackt und als gewöhnliche Abhängigkeiten für das Projekt wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="117e5-113">The test runner and the unit test library are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="117e5-114">In Testprojekten wird der Testlauf mittels eines normalen `<PackageReference>`-Elements angegeben, wie in der folgenden Beispielprojektdatei gezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="117e5-114">Test projects specify the test runner using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

## <a name="arguments"></a><span data-ttu-id="117e5-115">Argumente</span><span class="sxs-lookup"><span data-stu-id="117e5-115">Arguments</span></span>

- **`PROJECT | SOLUTION`**

  <span data-ttu-id="117e5-116">Pfad zum Testprojekt oder zur Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="117e5-116">Path to the test project or solution.</span></span> <span data-ttu-id="117e5-117">Wenn er nicht angegeben ist, wird standardmäßig das aktuelle Verzeichnis ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="117e5-117">If not specified, it defaults to current directory.</span></span>

## <a name="options"></a><span data-ttu-id="117e5-118">Optionen</span><span class="sxs-lookup"><span data-stu-id="117e5-118">Options</span></span>

- **`a|--test-adapter-path <PATH_TO_ADAPTER>`**

  <span data-ttu-id="117e5-119">Verwenden Sie die benutzerdefinierten Testadapter aus dem angegebenen Pfad im Testlauf.</span><span class="sxs-lookup"><span data-stu-id="117e5-119">Use the custom test adapters from the specified path in the test run.</span></span>

- **`--blame`**

  <span data-ttu-id="117e5-120">Führt die Tests im blame-Modus aus.</span><span class="sxs-lookup"><span data-stu-id="117e5-120">Runs the tests in blame mode.</span></span> <span data-ttu-id="117e5-121">Diese Option hilft beim Isolieren von fehlerhaften Tests, die den Absturz des Testhosts verursachen.</span><span class="sxs-lookup"><span data-stu-id="117e5-121">This option is helpful in isolating problematic tests that cause the test host to crash.</span></span> <span data-ttu-id="117e5-122">In dem aktuellen Verzeichnis wird eine Ausgabedatei als *Sequence.xml* erstellt, die die Reihenfolge der ausgeführten Tests vor dem Absturz erfasst.</span><span class="sxs-lookup"><span data-stu-id="117e5-122">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

- **`c|--configuration <CONFIGURATION>`**

  <span data-ttu-id="117e5-123">Legt die Buildkonfiguration fest.</span><span class="sxs-lookup"><span data-stu-id="117e5-123">Defines the build configuration.</span></span> <span data-ttu-id="117e5-124">Der Standardwert ist `Debug`, aber die Konfiguration des Projekts könnte diese SDK-Standardeinstellung überschreiben.</span><span class="sxs-lookup"><span data-stu-id="117e5-124">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

- **`-collect <DATA_COLLECTOR_FRIENDLY_NAME>`**

  <span data-ttu-id="117e5-125">Aktiviert den Datensammler für den Testlauf.</span><span class="sxs-lookup"><span data-stu-id="117e5-125">Enables data collector for the test run.</span></span> <span data-ttu-id="117e5-126">Weitere Informationen finden Sie unter [Monitor and analyze test run (Überwachen und Analysieren eines Testlaufs)](https://aka.ms/vstest-collect).</span><span class="sxs-lookup"><span data-stu-id="117e5-126">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

- **`d|--diag <PATH_TO_DIAGNOSTICS_FILE>`**

  <span data-ttu-id="117e5-127">Aktiviert den Diagnosemodus für die Testplattform und schreibt Diagnosemeldungen in die angegebene Datei.</span><span class="sxs-lookup"><span data-stu-id="117e5-127">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

- **`f|--framework <FRAMEWORK>`**

  <span data-ttu-id="117e5-128">Sucht nach Testbinärdateien für ein bestimmtes [Framework](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="117e5-128">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

- **`--filter <EXPRESSION>`**

  <span data-ttu-id="117e5-129">Filtert Tests im aktuellen Projekt mithilfe des angegebenen Ausdrucks heraus.</span><span class="sxs-lookup"><span data-stu-id="117e5-129">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="117e5-130">Weitere Informationen finden Sie im Abschnitt [Details zu Filteroptionen](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="117e5-130">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="117e5-131">Weitere Informationen und Beispiele zur Verwendung von selektiven Komponententestfiltern finden Sie unter [Ausführen von selektiven Komponententests](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="117e5-131">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

- **`h|--help`**

  <span data-ttu-id="117e5-132">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="117e5-132">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="117e5-133">Ermöglicht dem Befehl, anzuhalten und auf Benutzereingaben oder Aktionen zu warten.</span><span class="sxs-lookup"><span data-stu-id="117e5-133">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="117e5-134">Beispielsweise, um die Authentifizierung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="117e5-134">For example, to complete authentication.</span></span> <span data-ttu-id="117e5-135">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="117e5-135">Available since .NET Core 3.0 SDK.</span></span>

- **`l|--logger <LoggerUri/FriendlyName>`**

  <span data-ttu-id="117e5-136">Gibt eine Protokollierung für die Testergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="117e5-136">Specifies a logger for test results.</span></span>

- **`--no-build`**

  <span data-ttu-id="117e5-137">Erstellt das Projekt nicht vor der Ausführung.</span><span class="sxs-lookup"><span data-stu-id="117e5-137">Doesn't build the test project before running it.</span></span> <span data-ttu-id="117e5-138">Zudem wird das Flag `--no-restore` implizit festgelegt.</span><span class="sxs-lookup"><span data-stu-id="117e5-138">It also implicitly sets the - `--no-restore` flag.</span></span>

- **`--nologo`**

  <span data-ttu-id="117e5-139">Führen Sie Tests aus, ohne das Microsoft TestPlatform-Banner anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="117e5-139">Run tests without displaying the Microsoft TestPlatform banner.</span></span> <span data-ttu-id="117e5-140">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="117e5-140">Available since .NET Core 3.0 SDK.</span></span>

- **`--no-restore`**

  <span data-ttu-id="117e5-141">Führt keine implizite Wiederherstellung aus, wenn der Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="117e5-141">Doesn't execute an implicit restore when running the command.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="117e5-142">Verzeichnis, in dem die auszuführenden Binärdateien zu finden sind.</span><span class="sxs-lookup"><span data-stu-id="117e5-142">Directory in which to find the binaries to run.</span></span>

- **`-r|--results-directory <PATH>`**

  <span data-ttu-id="117e5-143">Das Verzeichnis, in dem die Testergebnisse gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="117e5-143">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="117e5-144">Wenn das Verzeichnis noch nicht vorhanden ist, wird es erstellt.</span><span class="sxs-lookup"><span data-stu-id="117e5-144">If the specified directory doesn't exist, it's created.</span></span>

- **`--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="117e5-145">Die Zielruntime, für die Tests ausgeführt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="117e5-145">The target runtime to test for.</span></span>

- **`-s|--settings <SETTINGS_FILE>`**

  <span data-ttu-id="117e5-146">Die `.runsettings`-Datei, die zum Ausführen der Tests verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="117e5-146">The `.runsettings` file to use for running the tests.</span></span> [<span data-ttu-id="117e5-147">Konfigurieren von Komponententests mithilfe einer `.runsettings`-Datei.</span><span class="sxs-lookup"><span data-stu-id="117e5-147">Configure unit tests by using a `.runsettings` file.</span></span>](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file)

- **`-t|--list-tests`**

  <span data-ttu-id="117e5-148">Listen Sie alle ermittelten Tests im aktuellen Projekt auf.</span><span class="sxs-lookup"><span data-stu-id="117e5-148">List all of the discovered tests in the current project.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="117e5-149">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="117e5-149">Sets the verbosity level of the command.</span></span> <span data-ttu-id="117e5-150">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="117e5-150">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

- <span data-ttu-id="117e5-151">`RunSettings`-Argumente</span><span class="sxs-lookup"><span data-stu-id="117e5-151">`RunSettings` arguments</span></span>

  <span data-ttu-id="117e5-152">Argumente werden als `RunSettings`-Konfigurationen für den Test übergeben.</span><span class="sxs-lookup"><span data-stu-id="117e5-152">Arguments are passed as `RunSettings` configurations for the test.</span></span> <span data-ttu-id="117e5-153">Argumente werden als `[name]=[value]`-Paaren nach „-- “ angegeben (Beachten Sie das Leerzeichen nach --).</span><span class="sxs-lookup"><span data-stu-id="117e5-153">Arguments are specified as `[name]=[value]` pairs after "-- " (note the space after --).</span></span> <span data-ttu-id="117e5-154">Ein Leerzeichen wird verwendet, um mehrere `[name]=[value]`-Paare voneinander zu trennen.</span><span class="sxs-lookup"><span data-stu-id="117e5-154">A space is used to separate multiple `[name]=[value]` pairs.</span></span>

  <span data-ttu-id="117e5-155">Ein Beispiel: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span><span class="sxs-lookup"><span data-stu-id="117e5-155">Example: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span></span>

  <span data-ttu-id="117e5-156">Weitere Informationen finden Sie unter [vstest.console.exe: Passing RunSettings args](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md) (Übergeben von RunSettings-Argumenten).</span><span class="sxs-lookup"><span data-stu-id="117e5-156">For more information, see [vstest.console.exe: Passing RunSettings args](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).</span></span>

## <a name="examples"></a><span data-ttu-id="117e5-157">Beispiele</span><span class="sxs-lookup"><span data-stu-id="117e5-157">Examples</span></span>

- <span data-ttu-id="117e5-158">Führen Sie die Tests im Projekt im aktuellen Verzeichnis durch:</span><span class="sxs-lookup"><span data-stu-id="117e5-158">Run the tests in the project in the current directory:</span></span>

  ```dotnetcli
  dotnet test
  ```

- <span data-ttu-id="117e5-159">Führen Sie die Tests im Projekt `test1` durch:</span><span class="sxs-lookup"><span data-stu-id="117e5-159">Run the tests in the `test1` project:</span></span>

  ```dotnetcli
  dotnet test ~/projects/test1/test1.csproj
  ```

- <span data-ttu-id="117e5-160">Führen Sie die Tests im aktuellen Verzeichnis aus, und generieren Sie eine Testergebnisdatei im TRX-Format:</span><span class="sxs-lookup"><span data-stu-id="117e5-160">Run the tests in the project in the current directory and generate a test results file in the trx format:</span></span>

  ```dotnetcli
  dotnet test --logger trx
  ```

## <a name="filter-option-details"></a><span data-ttu-id="117e5-161">Details zu Filteroptionen</span><span class="sxs-lookup"><span data-stu-id="117e5-161">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="117e5-162">`<Expression>` weist das Format `<property><operator><value>[|&<Expression>]` auf.</span><span class="sxs-lookup"><span data-stu-id="117e5-162">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="117e5-163">`<property>` ist ein Attribut von `Test Case`.</span><span class="sxs-lookup"><span data-stu-id="117e5-163">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="117e5-164">Im Folgenden werden die Eigenschaften aufgeführt, die von gängigen Frameworks für Komponententests unterstützt werden:</span><span class="sxs-lookup"><span data-stu-id="117e5-164">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="117e5-165">Testframework</span><span class="sxs-lookup"><span data-stu-id="117e5-165">Test Framework</span></span> | <span data-ttu-id="117e5-166">Unterstützte Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="117e5-166">Supported properties</span></span>                                                                                      |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="117e5-167">MSTest</span><span class="sxs-lookup"><span data-stu-id="117e5-167">MSTest</span></span>         | <ul><li><span data-ttu-id="117e5-168">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="117e5-168">FullyQualifiedName</span></span></li><li><span data-ttu-id="117e5-169">name</span><span class="sxs-lookup"><span data-stu-id="117e5-169">Name</span></span></li><li><span data-ttu-id="117e5-170">ClassName</span><span class="sxs-lookup"><span data-stu-id="117e5-170">ClassName</span></span></li><li><span data-ttu-id="117e5-171">Priorität</span><span class="sxs-lookup"><span data-stu-id="117e5-171">Priority</span></span></li><li><span data-ttu-id="117e5-172">TestCategory</span><span class="sxs-lookup"><span data-stu-id="117e5-172">TestCategory</span></span></li></ul> |
| <span data-ttu-id="117e5-173">xUnit</span><span class="sxs-lookup"><span data-stu-id="117e5-173">xUnit</span></span>          | <ul><li><span data-ttu-id="117e5-174">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="117e5-174">FullyQualifiedName</span></span></li><li><span data-ttu-id="117e5-175">DisplayName</span><span class="sxs-lookup"><span data-stu-id="117e5-175">DisplayName</span></span></li><li><span data-ttu-id="117e5-176">Merkmale</span><span class="sxs-lookup"><span data-stu-id="117e5-176">Traits</span></span></li></ul>                                   |

<span data-ttu-id="117e5-177">`<operator>` beschreibt die Beziehung zwischen der Eigenschaft und dem Wert:</span><span class="sxs-lookup"><span data-stu-id="117e5-177">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="117e5-178">Operator</span><span class="sxs-lookup"><span data-stu-id="117e5-178">Operator</span></span> | <span data-ttu-id="117e5-179">Funktion</span><span class="sxs-lookup"><span data-stu-id="117e5-179">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="117e5-180">Genaue Übereinstimmung</span><span class="sxs-lookup"><span data-stu-id="117e5-180">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="117e5-181">Keine genaue Übereinstimmung</span><span class="sxs-lookup"><span data-stu-id="117e5-181">Not exact match</span></span> |
| `~`      | <span data-ttu-id="117e5-182">Enthält</span><span class="sxs-lookup"><span data-stu-id="117e5-182">Contains</span></span>        |
| `!~`     | <span data-ttu-id="117e5-183">Enthält nicht</span><span class="sxs-lookup"><span data-stu-id="117e5-183">Not contains</span></span>    |

<span data-ttu-id="117e5-184">`<value>` ist eine Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="117e5-184">`<value>` is a string.</span></span> <span data-ttu-id="117e5-185">Bei allen Suchvorgängen ist die Groß-/Kleinschreibung nicht relevant.</span><span class="sxs-lookup"><span data-stu-id="117e5-185">All the lookups are case insensitive.</span></span>

<span data-ttu-id="117e5-186">Ein Ausdruck ohne `<operator>` gilt automatisch als `contains` für die `FullyQualifiedName`-Eigenschaft (`dotnet test --filter xyz` ist beispielsweise identisch mit `dotnet test --filter FullyQualifiedName~xyz`).</span><span class="sxs-lookup"><span data-stu-id="117e5-186">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="117e5-187">Ausdrücke können mit bedingten Operatoren verknüpft werden:</span><span class="sxs-lookup"><span data-stu-id="117e5-187">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="117e5-188">Operator</span><span class="sxs-lookup"><span data-stu-id="117e5-188">Operator</span></span>            | <span data-ttu-id="117e5-189">Funktion</span><span class="sxs-lookup"><span data-stu-id="117e5-189">Function</span></span> |
| ------------------- | -------- |
| <code>&#124;</code> | <span data-ttu-id="117e5-190">ODER</span><span class="sxs-lookup"><span data-stu-id="117e5-190">OR</span></span>       |
| `&`                 | <span data-ttu-id="117e5-191">UND</span><span class="sxs-lookup"><span data-stu-id="117e5-191">AND</span></span>      |

<span data-ttu-id="117e5-192">Sie können Ausdrücke in Klammern einschließen, wenn Sie bedingte Operatoren verwenden (z.B. `(Name~TestMethod1) | (Name~TestMethod2)`).</span><span class="sxs-lookup"><span data-stu-id="117e5-192">You can enclose expressions in parenthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="117e5-193">Weitere Informationen und Beispiele zur Verwendung von selektiven Komponententestfiltern finden Sie unter [Ausführen von selektiven Komponententests](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="117e5-193">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="117e5-194">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="117e5-194">See also</span></span>

- [<span data-ttu-id="117e5-195">Frameworks und Ziele</span><span class="sxs-lookup"><span data-stu-id="117e5-195">Frameworks and Targets</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="117e5-196">.NET Core Runtime-ID (RID)-Katalog</span><span class="sxs-lookup"><span data-stu-id="117e5-196">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
