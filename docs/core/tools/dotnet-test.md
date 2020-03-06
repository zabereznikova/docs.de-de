---
title: Befehl „dotnet test“
description: Der Befehl „dotnet test“ wird zum Ausführen von Unittests in einem bestimmten Projekt verwendet.
ms.date: 02/27/2020
ms.openlocfilehash: 6e906ab396a788905c99f50e73390b765b240efc
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2020
ms.locfileid: "78157010"
---
# <a name="dotnet-test"></a><span data-ttu-id="9af5d-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="9af5d-103">dotnet test</span></span>

<span data-ttu-id="9af5d-104">**Dieser Artikel gilt für:** ✔️ .NET Core 2.1 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="9af5d-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="9af5d-105">name</span><span class="sxs-lookup"><span data-stu-id="9af5d-105">Name</span></span>

<span data-ttu-id="9af5d-106">`dotnet test`: .NET-Testtreiber, der verwendet wird, um Komponententests auszuführen.</span><span class="sxs-lookup"><span data-stu-id="9af5d-106">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="9af5d-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="9af5d-107">Synopsis</span></span>

```dotnetcli
dotnet test [<PROJECT>] [-a|--test-adapter-path] [--blame]
    [-c|--configuration] [--collect] [-d|--diag] [-f|--framework]
    [--filter] [-l|--logger] [--no-build] [--no-restore]
    [-o|--output] [-r|--results-directory] [-s|--settings]
    [-t|--list-tests] [-v|--verbosity] [-- <RunSettings arguments>]

dotnet test [-h|--help]
```

## <a name="description"></a><span data-ttu-id="9af5d-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9af5d-108">Description</span></span>

<span data-ttu-id="9af5d-109">Der Befehl `dotnet test` wird zum Ausführen von Komponententests in einem bestimmten Projekt verwendet.</span><span class="sxs-lookup"><span data-stu-id="9af5d-109">The `dotnet test` command is used to execute unit tests in a given project.</span></span> <span data-ttu-id="9af5d-110">Mit dem `dotnet test`-Befehl wird die Testlauf-Konsolenanwendung gestartet, die für ein Projekt angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="9af5d-110">The `dotnet test` command launches the test runner console application specified for a project.</span></span> <span data-ttu-id="9af5d-111">Durch den Testlauf werden Tests ausgeführt, die für ein Komponententestframework (z.B. MSTest, NUnit oder xUnit) definiert wurden, und der Erfolg oder Misserfolg der einzelnen Testausführungen wird gemeldet.</span><span class="sxs-lookup"><span data-stu-id="9af5d-111">The test runner executes the tests defined for a unit test framework (for example, MSTest, NUnit, or xUnit) and reports the success or failure of each test.</span></span> <span data-ttu-id="9af5d-112">Wenn alle Tests erfolgreich sind, gibt der Test Runner 0 (null) als Exitcode zurück. Wenn jedoch ein Test fehlschlägt, wird 1 zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9af5d-112">If all tests are successful, the test runner returns 0 as an exit code; otherwise if any test fails, it returns 1.</span></span> <span data-ttu-id="9af5d-113">Der Testlauf und die Komponententestbibliothek werden als NuGet-Pakete gepackt und als gewöhnliche Abhängigkeiten für das Projekt wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="9af5d-113">The test runner and the unit test library are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="9af5d-114">In Testprojekten wird der Testlauf mittels eines normalen `<PackageReference>`-Elements angegeben, wie in der folgenden Beispielprojektdatei gezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="9af5d-114">Test projects specify the test runner using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

## <a name="arguments"></a><span data-ttu-id="9af5d-115">Argumente</span><span class="sxs-lookup"><span data-stu-id="9af5d-115">Arguments</span></span>

- **`PROJECT`**

  <span data-ttu-id="9af5d-116">Der Pfad zum Testprojekt.</span><span class="sxs-lookup"><span data-stu-id="9af5d-116">Path to the test project.</span></span> <span data-ttu-id="9af5d-117">Wenn er nicht angegeben ist, wird standardmäßig das aktuelle Verzeichnis ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="9af5d-117">If not specified, it defaults to current directory.</span></span>

## <a name="options"></a><span data-ttu-id="9af5d-118">Optionen</span><span class="sxs-lookup"><span data-stu-id="9af5d-118">Options</span></span>

- **`a|--test-adapter-path <PATH_TO_ADAPTER>`**

  <span data-ttu-id="9af5d-119">Verwenden Sie die benutzerdefinierten Testadapter aus dem angegebenen Pfad im Testlauf.</span><span class="sxs-lookup"><span data-stu-id="9af5d-119">Use the custom test adapters from the specified path in the test run.</span></span>

- **`-blame`**

  <span data-ttu-id="9af5d-120">Führt die Tests im blame-Modus aus.</span><span class="sxs-lookup"><span data-stu-id="9af5d-120">Runs the tests in blame mode.</span></span> <span data-ttu-id="9af5d-121">Diese Option hilft beim Isolieren von fehlerhaften Tests, die den Absturz des Testhosts verursachen.</span><span class="sxs-lookup"><span data-stu-id="9af5d-121">This option is helpful in isolating problematic tests that cause the test host to crash.</span></span> <span data-ttu-id="9af5d-122">In dem aktuellen Verzeichnis wird eine Ausgabedatei als *Sequence.xml* erstellt, die die Reihenfolge der ausgeführten Tests vor dem Absturz erfasst.</span><span class="sxs-lookup"><span data-stu-id="9af5d-122">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

- **`c|--configuration {Debug|Release}`**

  <span data-ttu-id="9af5d-123">Legt die Buildkonfiguration fest.</span><span class="sxs-lookup"><span data-stu-id="9af5d-123">Defines the build configuration.</span></span> <span data-ttu-id="9af5d-124">Der Standardwert ist `Debug`, aber die Konfiguration des Projekts könnte diese SDK-Standardeinstellung überschreiben.</span><span class="sxs-lookup"><span data-stu-id="9af5d-124">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

- **`-collect <DATA_COLLECTOR_FRIENDLY_NAME>`**

  <span data-ttu-id="9af5d-125">Aktiviert den Datensammler für den Testlauf.</span><span class="sxs-lookup"><span data-stu-id="9af5d-125">Enables data collector for the test run.</span></span> <span data-ttu-id="9af5d-126">Weitere Informationen finden Sie unter [Monitor and analyze test run (Überwachen und Analysieren eines Testlaufs)](https://aka.ms/vstest-collect).</span><span class="sxs-lookup"><span data-stu-id="9af5d-126">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

- **`d|--diag <PATH_TO_DIAGNOSTICS_FILE>`**

  <span data-ttu-id="9af5d-127">Aktiviert den Diagnosemodus für die Testplattform und schreibt Diagnosemeldungen in die angegebene Datei.</span><span class="sxs-lookup"><span data-stu-id="9af5d-127">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

- **`f|--framework <FRAMEWORK>`**

  <span data-ttu-id="9af5d-128">Sucht nach Testbinärdateien für ein bestimmtes [Framework](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="9af5d-128">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

- **`--filter <EXPRESSION>`**

  <span data-ttu-id="9af5d-129">Filtert Tests im aktuellen Projekt mithilfe des angegebenen Ausdrucks heraus.</span><span class="sxs-lookup"><span data-stu-id="9af5d-129">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="9af5d-130">Weitere Informationen finden Sie im Abschnitt [Details zu Filteroptionen](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="9af5d-130">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="9af5d-131">Weitere Informationen und Beispiele zur Verwendung von selektiven Komponententestfiltern finden Sie unter [Ausführen von selektiven Komponententests](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="9af5d-131">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

- **`h|--help`**

  <span data-ttu-id="9af5d-132">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="9af5d-132">Prints out a short help for the command.</span></span>

- **`l|--logger <LoggerUri/FriendlyName>`**

  <span data-ttu-id="9af5d-133">Gibt eine Protokollierung für die Testergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="9af5d-133">Specifies a logger for test results.</span></span>

- **`--no-build`**

  <span data-ttu-id="9af5d-134">Erstellt das Projekt nicht vor der Ausführung.</span><span class="sxs-lookup"><span data-stu-id="9af5d-134">Doesn't build the test project before running it.</span></span> <span data-ttu-id="9af5d-135">Zudem wird das Flag `--no-restore` implizit festgelegt.</span><span class="sxs-lookup"><span data-stu-id="9af5d-135">It also implicitly sets the - `--no-restore` flag.</span></span>

- **`--no-restore`**

  <span data-ttu-id="9af5d-136">Führt keine implizite Wiederherstellung aus, wenn der Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9af5d-136">Doesn't execute an implicit restore when running the command.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="9af5d-137">Verzeichnis, in dem die auszuführenden Binärdateien zu finden sind.</span><span class="sxs-lookup"><span data-stu-id="9af5d-137">Directory in which to find the binaries to run.</span></span>

- **`-r|--results-directory <PATH>`**

  <span data-ttu-id="9af5d-138">Das Verzeichnis, in dem die Testergebnisse gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="9af5d-138">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="9af5d-139">Wenn das Verzeichnis noch nicht vorhanden ist, wird es erstellt.</span><span class="sxs-lookup"><span data-stu-id="9af5d-139">If the specified directory doesn't exist, it's created.</span></span>

- **`-s|--settings <SETTINGS_FILE>`**

  <span data-ttu-id="9af5d-140">Die `.runsettings`-Datei, die zum Ausführen der Tests verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9af5d-140">The `.runsettings` file to use for running the tests.</span></span> [<span data-ttu-id="9af5d-141">Konfigurieren von Komponententests mithilfe einer `.runsettings`-Datei.</span><span class="sxs-lookup"><span data-stu-id="9af5d-141">Configure unit tests by using a `.runsettings` file.</span></span>](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file)

- **`-t|--list-tests`**

  <span data-ttu-id="9af5d-142">Listen Sie alle ermittelten Tests im aktuellen Projekt auf.</span><span class="sxs-lookup"><span data-stu-id="9af5d-142">List all of the discovered tests in the current project.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="9af5d-143">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="9af5d-143">Sets the verbosity level of the command.</span></span> <span data-ttu-id="9af5d-144">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="9af5d-144">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

- <span data-ttu-id="9af5d-145">`RunSettings`-Argumente</span><span class="sxs-lookup"><span data-stu-id="9af5d-145">`RunSettings` arguments</span></span>

  <span data-ttu-id="9af5d-146">Argumente werden als `RunSettings`-Konfigurationen für den Test übergeben.</span><span class="sxs-lookup"><span data-stu-id="9af5d-146">Arguments are passed as `RunSettings` configurations for the test.</span></span> <span data-ttu-id="9af5d-147">Argumente werden als `[name]=[value]`-Paaren nach „-- “ angegeben (Beachten Sie das Leerzeichen nach --).</span><span class="sxs-lookup"><span data-stu-id="9af5d-147">Arguments are specified as `[name]=[value]` pairs after "-- " (note the space after --).</span></span> <span data-ttu-id="9af5d-148">Ein Leerzeichen wird verwendet, um mehrere `[name]=[value]`-Paare voneinander zu trennen.</span><span class="sxs-lookup"><span data-stu-id="9af5d-148">A space is used to separate multiple `[name]=[value]` pairs.</span></span>

  <span data-ttu-id="9af5d-149">Ein Beispiel: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span><span class="sxs-lookup"><span data-stu-id="9af5d-149">Example: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span></span>

  <span data-ttu-id="9af5d-150">Weitere Informationen finden Sie unter [vstest.console.exe: Passing RunSettings args](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md) (Übergeben von RunSettings-Argumenten).</span><span class="sxs-lookup"><span data-stu-id="9af5d-150">For more information, see [vstest.console.exe: Passing RunSettings args](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).</span></span>

## <a name="examples"></a><span data-ttu-id="9af5d-151">Beispiele</span><span class="sxs-lookup"><span data-stu-id="9af5d-151">Examples</span></span>

- <span data-ttu-id="9af5d-152">Führen Sie die Tests im Projekt im aktuellen Verzeichnis durch:</span><span class="sxs-lookup"><span data-stu-id="9af5d-152">Run the tests in the project in the current directory:</span></span>

  ```dotnetcli
  dotnet test
  ```

- <span data-ttu-id="9af5d-153">Führen Sie die Tests im Projekt `test1` durch:</span><span class="sxs-lookup"><span data-stu-id="9af5d-153">Run the tests in the `test1` project:</span></span>

  ```dotnetcli
  dotnet test ~/projects/test1/test1.csproj
  ```

- <span data-ttu-id="9af5d-154">Führen Sie die Tests im aktuellen Verzeichnis aus, und generieren Sie eine Testergebnisdatei im TRX-Format:</span><span class="sxs-lookup"><span data-stu-id="9af5d-154">Run the tests in the project in the current directory and generate a test results file in the trx format:</span></span>

  ```dotnetcli
  dotnet test --logger trx
  ```

## <a name="filter-option-details"></a><span data-ttu-id="9af5d-155">Details zu Filteroptionen</span><span class="sxs-lookup"><span data-stu-id="9af5d-155">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="9af5d-156">`<Expression>` weist das Format `<property><operator><value>[|&<Expression>]` auf.</span><span class="sxs-lookup"><span data-stu-id="9af5d-156">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="9af5d-157">`<property>` ist ein Attribut von `Test Case`.</span><span class="sxs-lookup"><span data-stu-id="9af5d-157">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="9af5d-158">Im Folgenden werden die Eigenschaften aufgeführt, die von gängigen Frameworks für Komponententests unterstützt werden:</span><span class="sxs-lookup"><span data-stu-id="9af5d-158">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="9af5d-159">Testframework</span><span class="sxs-lookup"><span data-stu-id="9af5d-159">Test Framework</span></span> | <span data-ttu-id="9af5d-160">Unterstützte Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="9af5d-160">Supported properties</span></span>                                                                                      |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="9af5d-161">MSTest</span><span class="sxs-lookup"><span data-stu-id="9af5d-161">MSTest</span></span>         | <ul><li><span data-ttu-id="9af5d-162">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="9af5d-162">FullyQualifiedName</span></span></li><li><span data-ttu-id="9af5d-163">name</span><span class="sxs-lookup"><span data-stu-id="9af5d-163">Name</span></span></li><li><span data-ttu-id="9af5d-164">ClassName</span><span class="sxs-lookup"><span data-stu-id="9af5d-164">ClassName</span></span></li><li><span data-ttu-id="9af5d-165">Priorität</span><span class="sxs-lookup"><span data-stu-id="9af5d-165">Priority</span></span></li><li><span data-ttu-id="9af5d-166">TestCategory</span><span class="sxs-lookup"><span data-stu-id="9af5d-166">TestCategory</span></span></li></ul> |
| <span data-ttu-id="9af5d-167">xUnit</span><span class="sxs-lookup"><span data-stu-id="9af5d-167">xUnit</span></span>          | <ul><li><span data-ttu-id="9af5d-168">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="9af5d-168">FullyQualifiedName</span></span></li><li><span data-ttu-id="9af5d-169">DisplayName</span><span class="sxs-lookup"><span data-stu-id="9af5d-169">DisplayName</span></span></li><li><span data-ttu-id="9af5d-170">Merkmale</span><span class="sxs-lookup"><span data-stu-id="9af5d-170">Traits</span></span></li></ul>                                   |

<span data-ttu-id="9af5d-171">`<operator>` beschreibt die Beziehung zwischen der Eigenschaft und dem Wert:</span><span class="sxs-lookup"><span data-stu-id="9af5d-171">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="9af5d-172">Operator</span><span class="sxs-lookup"><span data-stu-id="9af5d-172">Operator</span></span> | <span data-ttu-id="9af5d-173">Funktion</span><span class="sxs-lookup"><span data-stu-id="9af5d-173">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="9af5d-174">Genaue Übereinstimmung</span><span class="sxs-lookup"><span data-stu-id="9af5d-174">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="9af5d-175">Keine genaue Übereinstimmung</span><span class="sxs-lookup"><span data-stu-id="9af5d-175">Not exact match</span></span> |
| `~`      | <span data-ttu-id="9af5d-176">Enthält</span><span class="sxs-lookup"><span data-stu-id="9af5d-176">Contains</span></span>        |
| `!~`     | <span data-ttu-id="9af5d-177">Enthält nicht</span><span class="sxs-lookup"><span data-stu-id="9af5d-177">Not contains</span></span>    |

<span data-ttu-id="9af5d-178">`<value>` ist eine Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="9af5d-178">`<value>` is a string.</span></span> <span data-ttu-id="9af5d-179">Bei allen Suchvorgängen ist die Groß-/Kleinschreibung nicht relevant.</span><span class="sxs-lookup"><span data-stu-id="9af5d-179">All the lookups are case insensitive.</span></span>

<span data-ttu-id="9af5d-180">Ein Ausdruck ohne `<operator>` gilt automatisch als `contains` für die `FullyQualifiedName`-Eigenschaft (`dotnet test --filter xyz` ist beispielsweise identisch mit `dotnet test --filter FullyQualifiedName~xyz`).</span><span class="sxs-lookup"><span data-stu-id="9af5d-180">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="9af5d-181">Ausdrücke können mit bedingten Operatoren verknüpft werden:</span><span class="sxs-lookup"><span data-stu-id="9af5d-181">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="9af5d-182">Operator</span><span class="sxs-lookup"><span data-stu-id="9af5d-182">Operator</span></span>            | <span data-ttu-id="9af5d-183">Funktion</span><span class="sxs-lookup"><span data-stu-id="9af5d-183">Function</span></span> |
| ------------------- | -------- |
| <code>&#124;</code> | <span data-ttu-id="9af5d-184">ODER</span><span class="sxs-lookup"><span data-stu-id="9af5d-184">OR</span></span>       |
| `&`                 | <span data-ttu-id="9af5d-185">UND</span><span class="sxs-lookup"><span data-stu-id="9af5d-185">AND</span></span>      |

<span data-ttu-id="9af5d-186">Sie können Ausdrücke in Klammern einschließen, wenn Sie bedingte Operatoren verwenden (z.B. `(Name~TestMethod1) | (Name~TestMethod2)`).</span><span class="sxs-lookup"><span data-stu-id="9af5d-186">You can enclose expressions in parenthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="9af5d-187">Weitere Informationen und Beispiele zur Verwendung von selektiven Komponententestfiltern finden Sie unter [Ausführen von selektiven Komponententests](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="9af5d-187">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9af5d-188">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9af5d-188">See also</span></span>

- [<span data-ttu-id="9af5d-189">Frameworks und Ziele</span><span class="sxs-lookup"><span data-stu-id="9af5d-189">Frameworks and Targets</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="9af5d-190">.NET Core Runtime-ID (RID)-Katalog</span><span class="sxs-lookup"><span data-stu-id="9af5d-190">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
