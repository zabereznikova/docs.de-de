---
title: Befehl „dotnet test“
description: Der Befehl „dotnet test“ wird zum Ausführen von Unittests in einem bestimmten Projekt verwendet.
ms.date: 04/29/2020
ms.openlocfilehash: a8218b6596601069b89a60ad018adf89a1f47cf6
ms.sourcegitcommit: e09dbff13f0b21b569a101f3b3c5efa174aec204
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/01/2020
ms.locfileid: "82624890"
---
# <a name="dotnet-test"></a><span data-ttu-id="cc285-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="cc285-103">dotnet test</span></span>

<span data-ttu-id="cc285-104">**Dieser Artikel gilt für:** ✔️ .NET Core 2.1 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="cc285-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="cc285-105">name</span><span class="sxs-lookup"><span data-stu-id="cc285-105">Name</span></span>

<span data-ttu-id="cc285-106">`dotnet test`: .NET-Testtreiber, der verwendet wird, um Komponententests auszuführen.</span><span class="sxs-lookup"><span data-stu-id="cc285-106">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="cc285-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="cc285-107">Synopsis</span></span>

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

## <a name="description"></a><span data-ttu-id="cc285-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cc285-108">Description</span></span>

<span data-ttu-id="cc285-109">Der Befehl `dotnet test` wird zum Ausführen von Komponententests in einem bestimmten Projekt verwendet.</span><span class="sxs-lookup"><span data-stu-id="cc285-109">The `dotnet test` command is used to execute unit tests in a given project.</span></span> <span data-ttu-id="cc285-110">Mit dem `dotnet test`-Befehl wird die Testlauf-Konsolenanwendung gestartet, die für ein Projekt angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="cc285-110">The `dotnet test` command launches the test runner console application specified for a project.</span></span> <span data-ttu-id="cc285-111">Durch den Testlauf werden Tests ausgeführt, die für ein Komponententestframework (z.B. MSTest, NUnit oder xUnit) definiert wurden, und der Erfolg oder Misserfolg der einzelnen Testausführungen wird gemeldet.</span><span class="sxs-lookup"><span data-stu-id="cc285-111">The test runner executes the tests defined for a unit test framework (for example, MSTest, NUnit, or xUnit) and reports the success or failure of each test.</span></span> <span data-ttu-id="cc285-112">Wenn alle Tests erfolgreich sind, gibt der Test Runner 0 (null) als Exitcode zurück. Wenn jedoch ein Test fehlschlägt, wird 1 zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="cc285-112">If all tests are successful, the test runner returns 0 as an exit code; otherwise if any test fails, it returns 1.</span></span> <span data-ttu-id="cc285-113">Bei Projekten mit mehreren Zielen werden Tests für jedes Zielframework ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="cc285-113">For multi-targeted projects, tests are run for each targeted framework.</span></span> <span data-ttu-id="cc285-114">Der Testlauf und die Komponententestbibliothek werden als NuGet-Pakete gepackt und als gewöhnliche Abhängigkeiten für das Projekt wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="cc285-114">The test runner and the unit test library are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="cc285-115">In Testprojekten wird der Testlauf mittels eines normalen `<PackageReference>`-Elements angegeben, wie in der folgenden Beispielprojektdatei gezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="cc285-115">Test projects specify the test runner using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

### <a name="implicit-restore"></a><span data-ttu-id="cc285-116">Implizite Wiederherstellung</span><span class="sxs-lookup"><span data-stu-id="cc285-116">Implicit restore</span></span>

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a><span data-ttu-id="cc285-117">Argumente</span><span class="sxs-lookup"><span data-stu-id="cc285-117">Arguments</span></span>

- **`PROJECT | SOLUTION`**

  <span data-ttu-id="cc285-118">Pfad zum Testprojekt oder zur Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="cc285-118">Path to the test project or solution.</span></span> <span data-ttu-id="cc285-119">Wenn er nicht angegeben ist, wird standardmäßig das aktuelle Verzeichnis ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="cc285-119">If not specified, it defaults to current directory.</span></span>

## <a name="options"></a><span data-ttu-id="cc285-120">Optionen</span><span class="sxs-lookup"><span data-stu-id="cc285-120">Options</span></span>

- **`-a|--test-adapter-path <PATH_TO_ADAPTER>`**

  <span data-ttu-id="cc285-121">Verwenden Sie die benutzerdefinierten Testadapter aus dem angegebenen Pfad im Testlauf.</span><span class="sxs-lookup"><span data-stu-id="cc285-121">Use the custom test adapters from the specified path in the test run.</span></span>

- **`--blame`**

  <span data-ttu-id="cc285-122">Führt die Tests im blame-Modus aus.</span><span class="sxs-lookup"><span data-stu-id="cc285-122">Runs the tests in blame mode.</span></span> <span data-ttu-id="cc285-123">Diese Option hilft beim Isolieren von fehlerhaften Tests, die den Absturz des Testhosts verursachen.</span><span class="sxs-lookup"><span data-stu-id="cc285-123">This option is helpful in isolating problematic tests that cause the test host to crash.</span></span> <span data-ttu-id="cc285-124">In dem aktuellen Verzeichnis wird eine Ausgabedatei als *Sequence.xml* erstellt, die die Reihenfolge der ausgeführten Tests vor dem Absturz erfasst.</span><span class="sxs-lookup"><span data-stu-id="cc285-124">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

- **`-c|--configuration <CONFIGURATION>`**

  <span data-ttu-id="cc285-125">Legt die Buildkonfiguration fest.</span><span class="sxs-lookup"><span data-stu-id="cc285-125">Defines the build configuration.</span></span> <span data-ttu-id="cc285-126">Der Standardwert ist `Debug`, aber die Konfiguration des Projekts könnte diese SDK-Standardeinstellung überschreiben.</span><span class="sxs-lookup"><span data-stu-id="cc285-126">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

- **`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`**

  <span data-ttu-id="cc285-127">Aktiviert den Datensammler für den Testlauf.</span><span class="sxs-lookup"><span data-stu-id="cc285-127">Enables data collector for the test run.</span></span> <span data-ttu-id="cc285-128">Weitere Informationen finden Sie unter [Monitor and analyze test run (Überwachen und Analysieren eines Testlaufs)](https://aka.ms/vstest-collect).</span><span class="sxs-lookup"><span data-stu-id="cc285-128">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

- **`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`**

  <span data-ttu-id="cc285-129">Aktiviert den Diagnosemodus für die Testplattform und schreibt Diagnosemeldungen in die angegebene Datei.</span><span class="sxs-lookup"><span data-stu-id="cc285-129">Enables diagnostic mode for the test platform and writes diagnostic messages to the specified file.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="cc285-130">Sucht nach Testbinärdateien für ein bestimmtes [Framework](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="cc285-130">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

- **`--filter <EXPRESSION>`**

  <span data-ttu-id="cc285-131">Filtert Tests im aktuellen Projekt mithilfe des angegebenen Ausdrucks heraus.</span><span class="sxs-lookup"><span data-stu-id="cc285-131">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="cc285-132">Weitere Informationen finden Sie im Abschnitt [Details zu Filteroptionen](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="cc285-132">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="cc285-133">Weitere Informationen und Beispiele zur Verwendung von selektiven Komponententestfiltern finden Sie unter [Ausführen von selektiven Komponententests](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="cc285-133">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

- **`-h|--help`**

  <span data-ttu-id="cc285-134">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="cc285-134">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="cc285-135">Ermöglicht dem Befehl, anzuhalten und auf Benutzereingaben oder Aktionen zu warten.</span><span class="sxs-lookup"><span data-stu-id="cc285-135">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="cc285-136">Beispielsweise, um die Authentifizierung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="cc285-136">For example, to complete authentication.</span></span> <span data-ttu-id="cc285-137">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="cc285-137">Available since .NET Core 3.0 SDK.</span></span>

- **`-l|--logger <LOGGER_URI/FRIENDLY_NAME>`**

  <span data-ttu-id="cc285-138">Gibt eine Protokollierung für die Testergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="cc285-138">Specifies a logger for test results.</span></span> <span data-ttu-id="cc285-139">Im Gegensatz zu MSBuild akzeptiert der Befehl „dotnet test“ keine Abkürzungen: verwenden Sie `-l "console;verbosity=detailed"` anstelle von `-l "console;v=d"`.</span><span class="sxs-lookup"><span data-stu-id="cc285-139">Unlike MSBuild, dotnet test doesn't accept abbreviations: instead of `-l "console;v=d"` use `-l "console;verbosity=detailed"`.</span></span>

- **`--no-build`**

  <span data-ttu-id="cc285-140">Erstellt das Projekt nicht vor der Ausführung.</span><span class="sxs-lookup"><span data-stu-id="cc285-140">Doesn't build the test project before running it.</span></span> <span data-ttu-id="cc285-141">Zudem wird das Flag `--no-restore` implizit festgelegt.</span><span class="sxs-lookup"><span data-stu-id="cc285-141">It also implicitly sets the - `--no-restore` flag.</span></span>

- **`--nologo`**

  <span data-ttu-id="cc285-142">Führen Sie Tests aus, ohne das Microsoft TestPlatform-Banner anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="cc285-142">Run tests without displaying the Microsoft TestPlatform banner.</span></span> <span data-ttu-id="cc285-143">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="cc285-143">Available since .NET Core 3.0 SDK.</span></span>

- **`--no-restore`**

  <span data-ttu-id="cc285-144">Führt keine implizite Wiederherstellung aus, wenn der Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="cc285-144">Doesn't execute an implicit restore when running the command.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="cc285-145">Verzeichnis, in dem die auszuführenden Binärdateien zu finden sind.</span><span class="sxs-lookup"><span data-stu-id="cc285-145">Directory in which to find the binaries to run.</span></span> <span data-ttu-id="cc285-146">Wenn nicht angegeben, ist der Standardpfad `./bin/<configuration>/<framework>/`.</span><span class="sxs-lookup"><span data-stu-id="cc285-146">If not specified, the default path is `./bin/<configuration>/<framework>/`.</span></span>  <span data-ttu-id="cc285-147">Bei Projekten mit mehreren Zielframeworks (über die `TargetFrameworks`-Eigenschaft) müssen Sie auch `--framework` definieren, wenn Sie diese Option angeben.</span><span class="sxs-lookup"><span data-stu-id="cc285-147">For projects with multiple target frameworks (via the `TargetFrameworks` property), you also need to define `--framework` when you specify this option.</span></span> <span data-ttu-id="cc285-148">`dotnet test` führt Tests immer über das Ausgabeverzeichnis aus.</span><span class="sxs-lookup"><span data-stu-id="cc285-148">`dotnet test` always run tests from the output directory.</span></span> <span data-ttu-id="cc285-149">Sie können <xref:System.AppDomain.BaseDirectory%2A?displayProperty=nameWithType> verwenden, um die Testobjekte im Ausgabeverzeichnis zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="cc285-149">You can use <xref:System.AppDomain.BaseDirectory%2A?displayProperty=nameWithType> to consume test assets in the output directory.</span></span>

- **`-r|--results-directory <PATH>`**

  <span data-ttu-id="cc285-150">Das Verzeichnis, in dem die Testergebnisse gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="cc285-150">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="cc285-151">Wenn das Verzeichnis noch nicht vorhanden ist, wird es erstellt.</span><span class="sxs-lookup"><span data-stu-id="cc285-151">If the specified directory doesn't exist, it's created.</span></span> <span data-ttu-id="cc285-152">Der Standardwert ist `TestResults` in dem Verzeichnis, das die Projektdatei enthält.</span><span class="sxs-lookup"><span data-stu-id="cc285-152">The default is `TestResults` in the directory that contains the project file.</span></span>

- **`--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="cc285-153">Die Zielruntime, für die Tests ausgeführt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="cc285-153">The target runtime to test for.</span></span>

- **`-s|--settings <SETTINGS_FILE>`**

  <span data-ttu-id="cc285-154">Die `.runsettings`-Datei, die zum Ausführen der Tests verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="cc285-154">The `.runsettings` file to use for running the tests.</span></span> <span data-ttu-id="cc285-155">Beachten Sie, dass das `TargetPlatform`-Element (x86|x64) keine Auswirkung auf `dotnet test` hat.</span><span class="sxs-lookup"><span data-stu-id="cc285-155">Note that the `TargetPlatform` element (x86|x64) has no effect for `dotnet test`.</span></span> <span data-ttu-id="cc285-156">Installieren Sie die x86-Version von .NET Core, um x86-Tests auszuführen.</span><span class="sxs-lookup"><span data-stu-id="cc285-156">To run tests that target x86, install the x86 version of .NET Core.</span></span> <span data-ttu-id="cc285-157">Die Bitanzahl der Datei *dotnet.exe*, die sich in diesem Pfad befindet, wird zum Ausführen von Tests verwendet.</span><span class="sxs-lookup"><span data-stu-id="cc285-157">The bitness of the *dotnet.exe* that is on the path is what will be used for running tests.</span></span> <span data-ttu-id="cc285-158">Weitere Informationen finden Sie in den folgenden Ressourcen:</span><span class="sxs-lookup"><span data-stu-id="cc285-158">for more information, see the following resources:</span></span>

  - [<span data-ttu-id="cc285-159">Konfigurieren von Komponententests mithilfe einer `.runsettings`-Datei.</span><span class="sxs-lookup"><span data-stu-id="cc285-159">Configure unit tests by using a `.runsettings` file.</span></span>](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file)
  - [<span data-ttu-id="cc285-160">Konfigurieren eines Testlaufs</span><span class="sxs-lookup"><span data-stu-id="cc285-160">Configure a test run</span></span>](https://github.com/Microsoft/vstest-docs/blob/master/docs/configure.md)

- **`-t|--list-tests`**

  <span data-ttu-id="cc285-161">Listen Sie alle ermittelten Tests im aktuellen Projekt auf.</span><span class="sxs-lookup"><span data-stu-id="cc285-161">List all of the discovered tests in the current project.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="cc285-162">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="cc285-162">Sets the verbosity level of the command.</span></span> <span data-ttu-id="cc285-163">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="cc285-163">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="cc285-164">Der Standardwert ist `minimal`.</span><span class="sxs-lookup"><span data-stu-id="cc285-164">The default is `minimal`.</span></span> <span data-ttu-id="cc285-165">Weitere Informationen finden Sie unter <xref:Microsoft.Build.Framework.LoggerVerbosity>.</span><span class="sxs-lookup"><span data-stu-id="cc285-165">For more information, see <xref:Microsoft.Build.Framework.LoggerVerbosity>.</span></span>

- <span data-ttu-id="cc285-166">**`RunSettings`** -Argumente</span><span class="sxs-lookup"><span data-stu-id="cc285-166">**`RunSettings`** arguments</span></span>

  <span data-ttu-id="cc285-167">Argumente werden als `RunSettings`-Konfigurationen für den Test übergeben.</span><span class="sxs-lookup"><span data-stu-id="cc285-167">Arguments are passed as `RunSettings` configurations for the test.</span></span> <span data-ttu-id="cc285-168">Argumente werden als `[name]=[value]`-Paaren nach „-- “ angegeben (Beachten Sie das Leerzeichen nach --).</span><span class="sxs-lookup"><span data-stu-id="cc285-168">Arguments are specified as `[name]=[value]` pairs after "-- " (note the space after --).</span></span> <span data-ttu-id="cc285-169">Ein Leerzeichen wird verwendet, um mehrere `[name]=[value]`-Paare voneinander zu trennen.</span><span class="sxs-lookup"><span data-stu-id="cc285-169">A space is used to separate multiple `[name]=[value]` pairs.</span></span>

  <span data-ttu-id="cc285-170">Ein Beispiel: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span><span class="sxs-lookup"><span data-stu-id="cc285-170">Example: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span></span>

  <span data-ttu-id="cc285-171">Weitere Informationen finden Sie unter [Übergeben von RunSettings-Argumenten über die Befehlszeile](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).</span><span class="sxs-lookup"><span data-stu-id="cc285-171">For more information, see [Passing RunSettings arguments through command line](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).</span></span>

## <a name="examples"></a><span data-ttu-id="cc285-172">Beispiele</span><span class="sxs-lookup"><span data-stu-id="cc285-172">Examples</span></span>

- <span data-ttu-id="cc285-173">Führen Sie die Tests im Projekt im aktuellen Verzeichnis durch:</span><span class="sxs-lookup"><span data-stu-id="cc285-173">Run the tests in the project in the current directory:</span></span>

  ```dotnetcli
  dotnet test
  ```

- <span data-ttu-id="cc285-174">Führen Sie die Tests im Projekt `test1` durch:</span><span class="sxs-lookup"><span data-stu-id="cc285-174">Run the tests in the `test1` project:</span></span>

  ```dotnetcli
  dotnet test ~/projects/test1/test1.csproj
  ```

- <span data-ttu-id="cc285-175">Mit dem folgenden Befehl führen Sie die Tests im aktuellen Verzeichnis aus und generieren eine Testergebnisdatei im TRX-Format:</span><span class="sxs-lookup"><span data-stu-id="cc285-175">Run the tests in the project in the current directory, and generate a test results file in the trx format:</span></span>

  ```dotnetcli
  dotnet test --logger trx
  ```

- <span data-ttu-id="cc285-176">Mit dem folgenden Befehl führen Sie die Tests im aktuellen Verzeichnis aus und erstellen ein ausführliches Protokoll in der Konsole:</span><span class="sxs-lookup"><span data-stu-id="cc285-176">Run the tests in the project in the current directory, and log with detailed verbosity to the console:</span></span>

  ```dotnetcli
  dotnet test --logger "console;verbosity=detailed"
  ```

## <a name="filter-option-details"></a><span data-ttu-id="cc285-177">Details zu Filteroptionen</span><span class="sxs-lookup"><span data-stu-id="cc285-177">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="cc285-178">`<Expression>` weist das Format `<property><operator><value>[|&<Expression>]` auf.</span><span class="sxs-lookup"><span data-stu-id="cc285-178">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="cc285-179">`<property>` ist ein Attribut von `Test Case`.</span><span class="sxs-lookup"><span data-stu-id="cc285-179">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="cc285-180">Im Folgenden werden die Eigenschaften aufgeführt, die von gängigen Frameworks für Komponententests unterstützt werden:</span><span class="sxs-lookup"><span data-stu-id="cc285-180">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="cc285-181">Testframework</span><span class="sxs-lookup"><span data-stu-id="cc285-181">Test Framework</span></span> | <span data-ttu-id="cc285-182">Unterstützte Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="cc285-182">Supported properties</span></span>                                                                                      |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="cc285-183">MSTest</span><span class="sxs-lookup"><span data-stu-id="cc285-183">MSTest</span></span>         | <ul><li><span data-ttu-id="cc285-184">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="cc285-184">FullyQualifiedName</span></span></li><li><span data-ttu-id="cc285-185">name</span><span class="sxs-lookup"><span data-stu-id="cc285-185">Name</span></span></li><li><span data-ttu-id="cc285-186">ClassName</span><span class="sxs-lookup"><span data-stu-id="cc285-186">ClassName</span></span></li><li><span data-ttu-id="cc285-187">Priorität</span><span class="sxs-lookup"><span data-stu-id="cc285-187">Priority</span></span></li><li><span data-ttu-id="cc285-188">TestCategory</span><span class="sxs-lookup"><span data-stu-id="cc285-188">TestCategory</span></span></li></ul> |
| <span data-ttu-id="cc285-189">xUnit</span><span class="sxs-lookup"><span data-stu-id="cc285-189">xUnit</span></span>          | <ul><li><span data-ttu-id="cc285-190">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="cc285-190">FullyQualifiedName</span></span></li><li><span data-ttu-id="cc285-191">DisplayName</span><span class="sxs-lookup"><span data-stu-id="cc285-191">DisplayName</span></span></li><li><span data-ttu-id="cc285-192">Merkmale</span><span class="sxs-lookup"><span data-stu-id="cc285-192">Traits</span></span></li></ul>                                   |

<span data-ttu-id="cc285-193">`<operator>` beschreibt die Beziehung zwischen der Eigenschaft und dem Wert:</span><span class="sxs-lookup"><span data-stu-id="cc285-193">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="cc285-194">Operator</span><span class="sxs-lookup"><span data-stu-id="cc285-194">Operator</span></span> | <span data-ttu-id="cc285-195">Funktion</span><span class="sxs-lookup"><span data-stu-id="cc285-195">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="cc285-196">Genaue Übereinstimmung</span><span class="sxs-lookup"><span data-stu-id="cc285-196">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="cc285-197">Keine genaue Übereinstimmung</span><span class="sxs-lookup"><span data-stu-id="cc285-197">Not exact match</span></span> |
| `~`      | <span data-ttu-id="cc285-198">Enthält</span><span class="sxs-lookup"><span data-stu-id="cc285-198">Contains</span></span>        |
| `!~`     | <span data-ttu-id="cc285-199">Enthält nicht</span><span class="sxs-lookup"><span data-stu-id="cc285-199">Not contains</span></span>    |

<span data-ttu-id="cc285-200">`<value>` ist eine Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="cc285-200">`<value>` is a string.</span></span> <span data-ttu-id="cc285-201">Bei allen Suchvorgängen ist die Groß-/Kleinschreibung nicht relevant.</span><span class="sxs-lookup"><span data-stu-id="cc285-201">All the lookups are case insensitive.</span></span>

<span data-ttu-id="cc285-202">Ein Ausdruck ohne `<operator>` gilt automatisch als `contains` für die `FullyQualifiedName`-Eigenschaft (`dotnet test --filter xyz` ist beispielsweise identisch mit `dotnet test --filter FullyQualifiedName~xyz`).</span><span class="sxs-lookup"><span data-stu-id="cc285-202">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="cc285-203">Ausdrücke können mit bedingten Operatoren verknüpft werden:</span><span class="sxs-lookup"><span data-stu-id="cc285-203">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="cc285-204">Operator</span><span class="sxs-lookup"><span data-stu-id="cc285-204">Operator</span></span>            | <span data-ttu-id="cc285-205">Funktion</span><span class="sxs-lookup"><span data-stu-id="cc285-205">Function</span></span> |
| ------------------- | -------- |
| <code>&#124;</code> | <span data-ttu-id="cc285-206">ODER</span><span class="sxs-lookup"><span data-stu-id="cc285-206">OR</span></span>       |
| `&`                 | <span data-ttu-id="cc285-207">UND</span><span class="sxs-lookup"><span data-stu-id="cc285-207">AND</span></span>      |

<span data-ttu-id="cc285-208">Sie können Ausdrücke in Klammern einschließen, wenn Sie bedingte Operatoren verwenden (z.B. `(Name~TestMethod1) | (Name~TestMethod2)`).</span><span class="sxs-lookup"><span data-stu-id="cc285-208">You can enclose expressions in parenthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="cc285-209">Weitere Informationen und Beispiele zur Verwendung von selektiven Komponententestfiltern finden Sie unter [Ausführen von selektiven Komponententests](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="cc285-209">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="cc285-210">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cc285-210">See also</span></span>

- [<span data-ttu-id="cc285-211">Frameworks und Ziele</span><span class="sxs-lookup"><span data-stu-id="cc285-211">Frameworks and Targets</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="cc285-212">.NET Core Runtime-ID (RID)-Katalog</span><span class="sxs-lookup"><span data-stu-id="cc285-212">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
- [<span data-ttu-id="cc285-213">Übergeben von runsettings-Argumenten über die Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="cc285-213">Passing runsettings arguments through commandline</span></span>](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md)
