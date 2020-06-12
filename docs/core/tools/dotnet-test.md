---
title: Befehl „dotnet test“
description: Der Befehl „dotnet test“ wird zum Ausführen von Unittests in einem bestimmten Projekt verwendet.
ms.date: 04/29/2020
ms.openlocfilehash: 1190ecb75e83c9930c60726e7cd83203b11928cb
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84283935"
---
# <a name="dotnet-test"></a><span data-ttu-id="c21c3-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="c21c3-103">dotnet test</span></span>

<span data-ttu-id="c21c3-104">**Dieser Artikel gilt für:** ✔️ .NET Core 2.1 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="c21c3-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="c21c3-105">name</span><span class="sxs-lookup"><span data-stu-id="c21c3-105">Name</span></span>

<span data-ttu-id="c21c3-106">`dotnet test`: .NET-Testtreiber, der verwendet wird, um Komponententests auszuführen.</span><span class="sxs-lookup"><span data-stu-id="c21c3-106">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="c21c3-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="c21c3-107">Synopsis</span></span>

```dotnetcli
dotnet test [<PROJECT> | <SOLUTION> | <DIRECTORY> | <DLL>]
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

## <a name="description"></a><span data-ttu-id="c21c3-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c21c3-108">Description</span></span>

<span data-ttu-id="c21c3-109">Der Befehl `dotnet test` wird zum Ausführen von Komponententests in einer bestimmten Projektmappe verwendet.</span><span class="sxs-lookup"><span data-stu-id="c21c3-109">The `dotnet test` command is used to execute unit tests in a given solution.</span></span> <span data-ttu-id="c21c3-110">Mit dem Befehl `dotnet test` wird die Projektmappe erstellt und für jedes Testprojekt in der Projektmappe eine Testhostanwendung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c21c3-110">The `dotnet test` command builds the solution and runs a test host application for each test project in the solution.</span></span> <span data-ttu-id="c21c3-111">Der Testhost führt Tests im angegebenen Projekt mithilfe eines Testframeworks aus, z. B. MSTest, NUnit oder xUnit, und meldet den Erfolg oder Fehler jedes Tests.</span><span class="sxs-lookup"><span data-stu-id="c21c3-111">The test host executes tests in the given project using a test framework, for example: MSTest, NUnit, or xUnit, and reports the success or failure of each test.</span></span> <span data-ttu-id="c21c3-112">Wenn alle Tests erfolgreich sind, gibt der Test Runner 0 (null) als Exitcode zurück. Wenn jedoch ein Test fehlschlägt, wird 1 zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c21c3-112">If all tests are successful, the test runner returns 0 as an exit code; otherwise if any test fails, it returns 1.</span></span>

<span data-ttu-id="c21c3-113">Bei Projekten mit mehreren Zielen werden Tests für jedes Zielframework ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c21c3-113">For multi-targeted projects, tests are run for each targeted framework.</span></span> <span data-ttu-id="c21c3-114">Der Testhost und das Komponententest-Framework werden als NuGet-Pakete gepackt und als gewöhnliche Abhängigkeiten für das Projekt wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="c21c3-114">The test host and the unit test framework are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="c21c3-115">In Testprojekten wird der Testlauf mittels eines normalen `<PackageReference>`-Elements angegeben, wie in der folgenden Beispielprojektdatei gezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="c21c3-115">Test projects specify the test runner using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

<span data-ttu-id="c21c3-116">Wobei `Microsoft.NET.Test.Sdk` der Testhost und `xunit` das Testframework ist.</span><span class="sxs-lookup"><span data-stu-id="c21c3-116">Where `Microsoft.NET.Test.Sdk` is the test host, `xunit` is the test framework.</span></span> <span data-ttu-id="c21c3-117">Und `xunit.runner.visualstudio` ist ein Testadapter, der es dem xUnit-Framework ermöglicht, mit dem Testhost zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="c21c3-117">And `xunit.runner.visualstudio` is a test adapter, which allows the xUnit framework to work with the test host.</span></span>

### <a name="implicit-restore"></a><span data-ttu-id="c21c3-118">Implizite Wiederherstellung</span><span class="sxs-lookup"><span data-stu-id="c21c3-118">Implicit restore</span></span>

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a><span data-ttu-id="c21c3-119">Argumente</span><span class="sxs-lookup"><span data-stu-id="c21c3-119">Arguments</span></span>

- **`PROJECT | SOLUTION | DIRECTORY | DLL`**

  - <span data-ttu-id="c21c3-120">Der Pfad zum Testprojekt.</span><span class="sxs-lookup"><span data-stu-id="c21c3-120">Path to the test project.</span></span>
  - <span data-ttu-id="c21c3-121">Der Pfad zur Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="c21c3-121">Path to the solution.</span></span>
  - <span data-ttu-id="c21c3-122">Der Pfad zu einem Verzeichnis, das ein Projekt oder eine Projektmappe enthält.</span><span class="sxs-lookup"><span data-stu-id="c21c3-122">Path to a directory that contains a project or a solution.</span></span>
  - <span data-ttu-id="c21c3-123">Der Pfad zur *DLL*-Datei eines Testprojekts.</span><span class="sxs-lookup"><span data-stu-id="c21c3-123">Path to a test project *.dll* file.</span></span>

  <span data-ttu-id="c21c3-124">Ist dieses Argument nicht angegeben, wird nach einem Projekt oder einer Projektmappe im aktuellen Verzeichnis gesucht.</span><span class="sxs-lookup"><span data-stu-id="c21c3-124">If not specified, it searches for a project or a solution in the current directory.</span></span>

## <a name="options"></a><span data-ttu-id="c21c3-125">Optionen</span><span class="sxs-lookup"><span data-stu-id="c21c3-125">Options</span></span>

- **`-a|--test-adapter-path <PATH_TO_ADAPTER>`**

  <span data-ttu-id="c21c3-126">Der Pfad zu einem Verzeichnis, das nach zusätzlichen Testadaptern durchsucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="c21c3-126">Path to a directory to be searched for additional test adapters.</span></span> <span data-ttu-id="c21c3-127">Nur *DLL*-Dateien mit dem Suffix `.TestAdapter.dll` werden untersucht.</span><span class="sxs-lookup"><span data-stu-id="c21c3-127">Only *.dll* files with suffix `.TestAdapter.dll` are inspected.</span></span> <span data-ttu-id="c21c3-128">Wenn nichts angegeben ist, wird das Verzeichnis der Test-*DLL* durchsucht.</span><span class="sxs-lookup"><span data-stu-id="c21c3-128">If not specified, the directory of the test *.dll* is searched.</span></span>

- **`--blame`**

  <span data-ttu-id="c21c3-129">Führt die Tests im blame-Modus aus.</span><span class="sxs-lookup"><span data-stu-id="c21c3-129">Runs the tests in blame mode.</span></span> <span data-ttu-id="c21c3-130">Diese Option hilft beim Isolieren von fehlerhaften Tests, die den Absturz des Testhosts verursachen.</span><span class="sxs-lookup"><span data-stu-id="c21c3-130">This option is helpful in isolating problematic tests that cause the test host to crash.</span></span> <span data-ttu-id="c21c3-131">Wenn ein Absturz erkannt wird, wird in `TestResults/<Guid>/<Guid>_Sequence.xml` eine Sequenzdatei erstellt, die die Reihenfolge der Tests erfasst, die vor dem Absturz ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="c21c3-131">When a crash is detected, it creates a sequence file in `TestResults/<Guid>/<Guid>_Sequence.xml` that captures the order of tests that were run before the crash.</span></span>

- **`-c|--configuration <CONFIGURATION>`**

  <span data-ttu-id="c21c3-132">Legt die Buildkonfiguration fest.</span><span class="sxs-lookup"><span data-stu-id="c21c3-132">Defines the build configuration.</span></span> <span data-ttu-id="c21c3-133">Der Standardwert ist `Debug`, aber die Konfiguration des Projekts könnte diese SDK-Standardeinstellung überschreiben.</span><span class="sxs-lookup"><span data-stu-id="c21c3-133">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

- **`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`**

  <span data-ttu-id="c21c3-134">Aktiviert den Datensammler für den Testlauf.</span><span class="sxs-lookup"><span data-stu-id="c21c3-134">Enables data collector for the test run.</span></span> <span data-ttu-id="c21c3-135">Weitere Informationen finden Sie unter [Monitor and analyze test run (Überwachen und Analysieren eines Testlaufs)](https://aka.ms/vstest-collect).</span><span class="sxs-lookup"><span data-stu-id="c21c3-135">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>
  
  <span data-ttu-id="c21c3-136">Um Code Coverage auf einer beliebigen Plattform zu erfassen, die von .NET Core unterstützt wird, installieren Sie [Coverlet](https://github.com/coverlet-coverage/coverlet/blob/master/README.md) und verwenden die `--collect:"XPlat Code Coverage"`-Option.</span><span class="sxs-lookup"><span data-stu-id="c21c3-136">To collect code coverage on any platform that is supported by .NET Core, install [Coverlet](https://github.com/coverlet-coverage/coverlet/blob/master/README.md) and use the `--collect:"XPlat Code Coverage"` option.</span></span>

  <span data-ttu-id="c21c3-137">Unter Windows können Sie Code Coverage mithilfe der `--collect "Code Coverage"`-Option erfassen.</span><span class="sxs-lookup"><span data-stu-id="c21c3-137">On Windows, you can collect code coverage by using the `--collect "Code Coverage"` option.</span></span> <span data-ttu-id="c21c3-138">Mit dieser Option wird eine *COVERAGE*-Datei generiert, die in Visual Studio 2019 Enterprise geöffnet werden kann.</span><span class="sxs-lookup"><span data-stu-id="c21c3-138">This option generates a *.coverage* file, which can be opened in Visual Studio 2019 Enterprise.</span></span> <span data-ttu-id="c21c3-139">Weitere Informationen finden Sie unter [Verwenden von Code Coverage](/visualstudio/test/using-code-coverage-to-determine-how-much-code-is-being-tested) und [Anpassen der Code Coverage-Analyse](/visualstudio/test/customizing-code-coverage-analysis).</span><span class="sxs-lookup"><span data-stu-id="c21c3-139">For more information, see [Use code coverage](/visualstudio/test/using-code-coverage-to-determine-how-much-code-is-being-tested) and [Customize code coverage analysis](/visualstudio/test/customizing-code-coverage-analysis).</span></span>

- **`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`**

  <span data-ttu-id="c21c3-140">Aktiviert den Diagnosemodus für die Testplattform und schreibt Diagnosemeldungen in die angegebene Datei sowie in benachbarte Dateien.</span><span class="sxs-lookup"><span data-stu-id="c21c3-140">Enables diagnostic mode for the test platform and writes diagnostic messages to the specified file and to files next to it.</span></span> <span data-ttu-id="c21c3-141">Der Prozess, der die Meldungen protokolliert, bestimmt, welche Dateien erstellt werden, z. B. `*.host_<date>.txt` für das Testhostprotokoll und `*.datacollector_<date>.txt` für das Datensammlerprotokoll.</span><span class="sxs-lookup"><span data-stu-id="c21c3-141">The process that is logging the messages determines which files are created, such as `*.host_<date>.txt` for test host log, and `*.datacollector_<date>.txt` for data collector log.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="c21c3-142">Erzwingt die Verwendung von `dotnet` oder des .NET Framework-Testhosts für die Testbinärdateien.</span><span class="sxs-lookup"><span data-stu-id="c21c3-142">Forces the use of `dotnet` or .NET Framework test host for the test binaries.</span></span> <span data-ttu-id="c21c3-143">Mit dieser Option wird nur der zu verwendende Hosttyp bestimmt.</span><span class="sxs-lookup"><span data-stu-id="c21c3-143">This option only determines which type of host to use.</span></span> <span data-ttu-id="c21c3-144">Die tatsächliche zu verwendende Frameworkversion wird durch die *runtimeconfig.json* des Testprojekts bestimmt.</span><span class="sxs-lookup"><span data-stu-id="c21c3-144">The actual framework version to be used is determined by the *runtimeconfig.json* of the test project.</span></span> <span data-ttu-id="c21c3-145">Wenn nichts angegeben ist, wird das [TargetFramework-Assemblyattribut](/dotnet/api/system.runtime.versioning.targetframeworkattribute) verwendet, um den Hosttyp zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="c21c3-145">When not specified, the [TargetFramework assembly attribute](/dotnet/api/system.runtime.versioning.targetframeworkattribute) is used to determine the type of host.</span></span> <span data-ttu-id="c21c3-146">Wenn dieses Attribut von der *DLL* entfernt wird, wird der .NET Framework-Host verwendet.</span><span class="sxs-lookup"><span data-stu-id="c21c3-146">When that attribute is stripped from the *.dll*, the .NET Framework host is used.</span></span>

- **`--filter <EXPRESSION>`**

  <span data-ttu-id="c21c3-147">Filtert Tests im aktuellen Projekt mithilfe des angegebenen Ausdrucks heraus.</span><span class="sxs-lookup"><span data-stu-id="c21c3-147">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="c21c3-148">Weitere Informationen finden Sie im Abschnitt [Details zu Filteroptionen](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="c21c3-148">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="c21c3-149">Weitere Informationen und Beispiele zur Verwendung von selektiven Komponententestfiltern finden Sie unter [Ausführen von selektiven Komponententests](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="c21c3-149">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

- **`-h|--help`**

  <span data-ttu-id="c21c3-150">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="c21c3-150">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="c21c3-151">Ermöglicht dem Befehl, anzuhalten und auf Benutzereingaben oder Aktionen zu warten.</span><span class="sxs-lookup"><span data-stu-id="c21c3-151">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="c21c3-152">Beispielsweise, um die Authentifizierung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="c21c3-152">For example, to complete authentication.</span></span> <span data-ttu-id="c21c3-153">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="c21c3-153">Available since .NET Core 3.0 SDK.</span></span>

- **`-l|--logger <LOGGER_URI/FRIENDLY_NAME>`**

  <span data-ttu-id="c21c3-154">Gibt eine Protokollierung für die Testergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="c21c3-154">Specifies a logger for test results.</span></span> <span data-ttu-id="c21c3-155">Im Gegensatz zu MSBuild akzeptiert der Befehl „dotnet test“ keine Abkürzungen: verwenden Sie `-l "console;verbosity=detailed"` anstelle von `-l "console;v=d"`.</span><span class="sxs-lookup"><span data-stu-id="c21c3-155">Unlike MSBuild, dotnet test doesn't accept abbreviations: instead of `-l "console;v=d"` use `-l "console;verbosity=detailed"`.</span></span>

- **`--no-build`**

  <span data-ttu-id="c21c3-156">Erstellt das Projekt nicht vor der Ausführung.</span><span class="sxs-lookup"><span data-stu-id="c21c3-156">Doesn't build the test project before running it.</span></span> <span data-ttu-id="c21c3-157">Zudem wird das Flag `--no-restore` implizit festgelegt.</span><span class="sxs-lookup"><span data-stu-id="c21c3-157">It also implicitly sets the - `--no-restore` flag.</span></span>

- **`--nologo`**

  <span data-ttu-id="c21c3-158">Führen Sie Tests aus, ohne das Microsoft TestPlatform-Banner anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="c21c3-158">Run tests without displaying the Microsoft TestPlatform banner.</span></span> <span data-ttu-id="c21c3-159">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="c21c3-159">Available since .NET Core 3.0 SDK.</span></span>

- **`--no-restore`**

  <span data-ttu-id="c21c3-160">Führt keine implizite Wiederherstellung aus, wenn der Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c21c3-160">Doesn't execute an implicit restore when running the command.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="c21c3-161">Verzeichnis, in dem die auszuführenden Binärdateien zu finden sind.</span><span class="sxs-lookup"><span data-stu-id="c21c3-161">Directory in which to find the binaries to run.</span></span> <span data-ttu-id="c21c3-162">Wenn nicht angegeben, ist der Standardpfad `./bin/<configuration>/<framework>/`.</span><span class="sxs-lookup"><span data-stu-id="c21c3-162">If not specified, the default path is `./bin/<configuration>/<framework>/`.</span></span>  <span data-ttu-id="c21c3-163">Bei Projekten mit mehreren Zielframeworks (über die `TargetFrameworks`-Eigenschaft) müssen Sie auch `--framework` definieren, wenn Sie diese Option angeben.</span><span class="sxs-lookup"><span data-stu-id="c21c3-163">For projects with multiple target frameworks (via the `TargetFrameworks` property), you also need to define `--framework` when you specify this option.</span></span> <span data-ttu-id="c21c3-164">`dotnet test` führt Tests immer über das Ausgabeverzeichnis aus.</span><span class="sxs-lookup"><span data-stu-id="c21c3-164">`dotnet test` always runs tests from the output directory.</span></span> <span data-ttu-id="c21c3-165">Sie können <xref:System.AppDomain.BaseDirectory%2A?displayProperty=nameWithType> verwenden, um die Testobjekte im Ausgabeverzeichnis zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="c21c3-165">You can use <xref:System.AppDomain.BaseDirectory%2A?displayProperty=nameWithType> to consume test assets in the output directory.</span></span>

- **`-r|--results-directory <PATH>`**

  <span data-ttu-id="c21c3-166">Das Verzeichnis, in dem die Testergebnisse gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="c21c3-166">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="c21c3-167">Wenn das Verzeichnis noch nicht vorhanden ist, wird es erstellt.</span><span class="sxs-lookup"><span data-stu-id="c21c3-167">If the specified directory doesn't exist, it's created.</span></span> <span data-ttu-id="c21c3-168">Der Standardwert ist `TestResults` in dem Verzeichnis, das die Projektdatei enthält.</span><span class="sxs-lookup"><span data-stu-id="c21c3-168">The default is `TestResults` in the directory that contains the project file.</span></span>

- **`--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="c21c3-169">Die Zielruntime, für die Tests ausgeführt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c21c3-169">The target runtime to test for.</span></span>

- **`-s|--settings <SETTINGS_FILE>`**

  <span data-ttu-id="c21c3-170">Die `.runsettings`-Datei, die zum Ausführen der Tests verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c21c3-170">The `.runsettings` file to use for running the tests.</span></span> <span data-ttu-id="c21c3-171">Das `TargetPlatform`-Element (x86|x64) hat keine Auswirkung auf `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="c21c3-171">The `TargetPlatform` element (x86|x64) has no effect for `dotnet test`.</span></span> <span data-ttu-id="c21c3-172">Installieren Sie die x86-Version von .NET Core, um x86-Tests auszuführen.</span><span class="sxs-lookup"><span data-stu-id="c21c3-172">To run tests that target x86, install the x86 version of .NET Core.</span></span> <span data-ttu-id="c21c3-173">Die Bitanzahl der Datei *dotnet.exe*, die sich in diesem Pfad befindet, wird zum Ausführen von Tests verwendet.</span><span class="sxs-lookup"><span data-stu-id="c21c3-173">The bitness of the *dotnet.exe* that is on the path is what will be used for running tests.</span></span> <span data-ttu-id="c21c3-174">Weitere Informationen finden Sie in den folgenden Ressourcen:</span><span class="sxs-lookup"><span data-stu-id="c21c3-174">For more information, see the following resources:</span></span>

  - [<span data-ttu-id="c21c3-175">Konfigurieren von Komponententests mithilfe einer `.runsettings`-Datei.</span><span class="sxs-lookup"><span data-stu-id="c21c3-175">Configure unit tests by using a `.runsettings` file.</span></span>](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file)
  - [<span data-ttu-id="c21c3-176">Konfigurieren eines Testlaufs</span><span class="sxs-lookup"><span data-stu-id="c21c3-176">Configure a test run</span></span>](https://github.com/Microsoft/vstest-docs/blob/master/docs/configure.md)

- **`-t|--list-tests`**

  <span data-ttu-id="c21c3-177">Listen Sie alle ermittelten Tests im aktuellen Projekt auf.</span><span class="sxs-lookup"><span data-stu-id="c21c3-177">List all of the discovered tests in the current project.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="c21c3-178">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="c21c3-178">Sets the verbosity level of the command.</span></span> <span data-ttu-id="c21c3-179">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="c21c3-179">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="c21c3-180">Der Standardwert ist `minimal`.</span><span class="sxs-lookup"><span data-stu-id="c21c3-180">The default is `minimal`.</span></span> <span data-ttu-id="c21c3-181">Weitere Informationen finden Sie unter <xref:Microsoft.Build.Framework.LoggerVerbosity>.</span><span class="sxs-lookup"><span data-stu-id="c21c3-181">For more information, see <xref:Microsoft.Build.Framework.LoggerVerbosity>.</span></span>

- <span data-ttu-id="c21c3-182">**`RunSettings`** -Argumente</span><span class="sxs-lookup"><span data-stu-id="c21c3-182">**`RunSettings`** arguments</span></span>

 <span data-ttu-id="c21c3-183">Inline-`RunSettings` werden als die letzten Argumente auf der Befehlszeile nach „-- “ (beachten Sie das Leerzeichen hinter „--“) übergeben.</span><span class="sxs-lookup"><span data-stu-id="c21c3-183">Inline `RunSettings` are passed as the last arguments on the command line after "-- " (note the space after --).</span></span> <span data-ttu-id="c21c3-184">Inline-`RunSettings` werden als `[name]=[value]`-Paare angegeben.</span><span class="sxs-lookup"><span data-stu-id="c21c3-184">Inline `RunSettings` are specified as `[name]=[value]` pairs.</span></span> <span data-ttu-id="c21c3-185">Ein Leerzeichen wird verwendet, um mehrere `[name]=[value]`-Paare voneinander zu trennen.</span><span class="sxs-lookup"><span data-stu-id="c21c3-185">A space is used to separate multiple `[name]=[value]` pairs.</span></span>

  <span data-ttu-id="c21c3-186">Ein Beispiel: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span><span class="sxs-lookup"><span data-stu-id="c21c3-186">Example: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span></span>

  <span data-ttu-id="c21c3-187">Weitere Informationen finden Sie unter [Übergeben von RunSettings-Argumenten über die Befehlszeile](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).</span><span class="sxs-lookup"><span data-stu-id="c21c3-187">For more information, see [Passing RunSettings arguments through command line](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).</span></span>

## <a name="examples"></a><span data-ttu-id="c21c3-188">Beispiele</span><span class="sxs-lookup"><span data-stu-id="c21c3-188">Examples</span></span>

- <span data-ttu-id="c21c3-189">Führen Sie die Tests im Projekt im aktuellen Verzeichnis durch:</span><span class="sxs-lookup"><span data-stu-id="c21c3-189">Run the tests in the project in the current directory:</span></span>

  ```dotnetcli
  dotnet test
  ```

- <span data-ttu-id="c21c3-190">Führen Sie die Tests im Projekt `test1` durch:</span><span class="sxs-lookup"><span data-stu-id="c21c3-190">Run the tests in the `test1` project:</span></span>

  ```dotnetcli
  dotnet test ~/projects/test1/test1.csproj
  ```

- <span data-ttu-id="c21c3-191">Mit dem folgenden Befehl führen Sie die Tests im aktuellen Verzeichnis aus und generieren eine Testergebnisdatei im TRX-Format:</span><span class="sxs-lookup"><span data-stu-id="c21c3-191">Run the tests in the project in the current directory, and generate a test results file in the trx format:</span></span>

  ```dotnetcli
  dotnet test --logger trx
  ```

- <span data-ttu-id="c21c3-192">Führen Sie die Tests im Projekt im aktuellen Verzeichnis aus, und generieren Sie eine Code Coverage-Datei (nach der Installation von [Coverlet](https://github.com/tonerdo/coverlet/blob/master/README.md)):</span><span class="sxs-lookup"><span data-stu-id="c21c3-192">Run the tests in the project in the current directory, and generate a code coverage file (after installing [Coverlet](https://github.com/tonerdo/coverlet/blob/master/README.md)):</span></span>

  ```dotnetcli
  dotnet test --collect:"XPlat Code Coverage"
  ```

- <span data-ttu-id="c21c3-193">Führen Sie die Tests im Projekt im aktuellen Verzeichnis aus, und generieren Sie eine Code Coverage-Datei (nur Windows):</span><span class="sxs-lookup"><span data-stu-id="c21c3-193">Run the tests in the project in the current directory, and generate a code coverage file (Windows only):</span></span>

  ```dotnetcli
  dotnet test --collect "Code Coverage"
  ```

- <span data-ttu-id="c21c3-194">Mit dem folgenden Befehl führen Sie die Tests im aktuellen Verzeichnis aus und erstellen ein ausführliches Protokoll in der Konsole:</span><span class="sxs-lookup"><span data-stu-id="c21c3-194">Run the tests in the project in the current directory, and log with detailed verbosity to the console:</span></span>

  ```dotnetcli
  dotnet test --logger "console;verbosity=detailed"
  ```
  
  - <span data-ttu-id="c21c3-195">Mit dem folgenden Befehl führen Sie die Tests in dem Projekt im aktuellen Verzeichnis aus und melden Tests, die während des Absturzes des Testhosts in Arbeit waren:</span><span class="sxs-lookup"><span data-stu-id="c21c3-195">Run the tests in the project in the current directory, and report tests that were in progress when the test host crashed:</span></span>

  ```dotnetcli
  dotnet test --blame
  ```

## <a name="filter-option-details"></a><span data-ttu-id="c21c3-196">Details zu Filteroptionen</span><span class="sxs-lookup"><span data-stu-id="c21c3-196">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="c21c3-197">`<Expression>` weist das Format `<property><operator><value>[|&<Expression>]` auf.</span><span class="sxs-lookup"><span data-stu-id="c21c3-197">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="c21c3-198">`<property>` ist ein Attribut von `Test Case`.</span><span class="sxs-lookup"><span data-stu-id="c21c3-198">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="c21c3-199">Im Folgenden werden die Eigenschaften aufgeführt, die von gängigen Frameworks für Komponententests unterstützt werden:</span><span class="sxs-lookup"><span data-stu-id="c21c3-199">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="c21c3-200">Testframework</span><span class="sxs-lookup"><span data-stu-id="c21c3-200">Test Framework</span></span> | <span data-ttu-id="c21c3-201">Unterstützte Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="c21c3-201">Supported properties</span></span>                                                                                      |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="c21c3-202">MSTest</span><span class="sxs-lookup"><span data-stu-id="c21c3-202">MSTest</span></span>         | <ul><li><span data-ttu-id="c21c3-203">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="c21c3-203">FullyQualifiedName</span></span></li><li><span data-ttu-id="c21c3-204">name</span><span class="sxs-lookup"><span data-stu-id="c21c3-204">Name</span></span></li><li><span data-ttu-id="c21c3-205">ClassName</span><span class="sxs-lookup"><span data-stu-id="c21c3-205">ClassName</span></span></li><li><span data-ttu-id="c21c3-206">Priorität</span><span class="sxs-lookup"><span data-stu-id="c21c3-206">Priority</span></span></li><li><span data-ttu-id="c21c3-207">TestCategory</span><span class="sxs-lookup"><span data-stu-id="c21c3-207">TestCategory</span></span></li></ul> |
| <span data-ttu-id="c21c3-208">xUnit</span><span class="sxs-lookup"><span data-stu-id="c21c3-208">xUnit</span></span>          | <ul><li><span data-ttu-id="c21c3-209">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="c21c3-209">FullyQualifiedName</span></span></li><li><span data-ttu-id="c21c3-210">DisplayName</span><span class="sxs-lookup"><span data-stu-id="c21c3-210">DisplayName</span></span></li><li><span data-ttu-id="c21c3-211">Merkmale</span><span class="sxs-lookup"><span data-stu-id="c21c3-211">Traits</span></span></li></ul>                                   |
| <span data-ttu-id="c21c3-212">NUnit</span><span class="sxs-lookup"><span data-stu-id="c21c3-212">NUnit</span></span>          | <ul><li><span data-ttu-id="c21c3-213">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="c21c3-213">FullyQualifiedName</span></span></li><li><span data-ttu-id="c21c3-214">name</span><span class="sxs-lookup"><span data-stu-id="c21c3-214">Name</span></span></li><li><span data-ttu-id="c21c3-215">TestCategory</span><span class="sxs-lookup"><span data-stu-id="c21c3-215">TestCategory</span></span></li><li><span data-ttu-id="c21c3-216">Priorität</span><span class="sxs-lookup"><span data-stu-id="c21c3-216">Priority</span></span></li></ul>                                   |

<span data-ttu-id="c21c3-217">`<operator>` beschreibt die Beziehung zwischen der Eigenschaft und dem Wert:</span><span class="sxs-lookup"><span data-stu-id="c21c3-217">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="c21c3-218">Operator</span><span class="sxs-lookup"><span data-stu-id="c21c3-218">Operator</span></span> | <span data-ttu-id="c21c3-219">Funktion</span><span class="sxs-lookup"><span data-stu-id="c21c3-219">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="c21c3-220">Genaue Übereinstimmung</span><span class="sxs-lookup"><span data-stu-id="c21c3-220">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="c21c3-221">Keine genaue Übereinstimmung</span><span class="sxs-lookup"><span data-stu-id="c21c3-221">Not exact match</span></span> |
| `~`      | <span data-ttu-id="c21c3-222">Enthält</span><span class="sxs-lookup"><span data-stu-id="c21c3-222">Contains</span></span>        |
| `!~`     | <span data-ttu-id="c21c3-223">Enthält nicht</span><span class="sxs-lookup"><span data-stu-id="c21c3-223">Not contains</span></span>    |

<span data-ttu-id="c21c3-224">`<value>` ist eine Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="c21c3-224">`<value>` is a string.</span></span> <span data-ttu-id="c21c3-225">Bei allen Suchvorgängen ist die Groß-/Kleinschreibung nicht relevant.</span><span class="sxs-lookup"><span data-stu-id="c21c3-225">All the lookups are case insensitive.</span></span>

<span data-ttu-id="c21c3-226">Ein Ausdruck ohne `<operator>` gilt automatisch als `contains` für die `FullyQualifiedName`-Eigenschaft (`dotnet test --filter xyz` ist beispielsweise identisch mit `dotnet test --filter FullyQualifiedName~xyz`).</span><span class="sxs-lookup"><span data-stu-id="c21c3-226">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="c21c3-227">Ausdrücke können mit bedingten Operatoren verknüpft werden:</span><span class="sxs-lookup"><span data-stu-id="c21c3-227">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="c21c3-228">Operator</span><span class="sxs-lookup"><span data-stu-id="c21c3-228">Operator</span></span>            | <span data-ttu-id="c21c3-229">Funktion</span><span class="sxs-lookup"><span data-stu-id="c21c3-229">Function</span></span> |
| ------------------- | -------- |
| <code>&#124;</code> | <span data-ttu-id="c21c3-230">ODER</span><span class="sxs-lookup"><span data-stu-id="c21c3-230">OR</span></span>       |
| `&`                 | <span data-ttu-id="c21c3-231">UND</span><span class="sxs-lookup"><span data-stu-id="c21c3-231">AND</span></span>      |

<span data-ttu-id="c21c3-232">Sie können Ausdrücke in Klammern einschließen, wenn Sie bedingte Operatoren verwenden (z.B. `(Name~TestMethod1) | (Name~TestMethod2)`).</span><span class="sxs-lookup"><span data-stu-id="c21c3-232">You can enclose expressions in parenthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="c21c3-233">Weitere Informationen und Beispiele zur Verwendung von selektiven Komponententestfiltern finden Sie unter [Ausführen von selektiven Komponententests](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="c21c3-233">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c21c3-234">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c21c3-234">See also</span></span>

- [<span data-ttu-id="c21c3-235">Frameworks und Ziele</span><span class="sxs-lookup"><span data-stu-id="c21c3-235">Frameworks and Targets</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="c21c3-236">.NET Core Runtime-ID (RID)-Katalog</span><span class="sxs-lookup"><span data-stu-id="c21c3-236">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
- [<span data-ttu-id="c21c3-237">Übergeben von runsettings-Argumenten über die Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="c21c3-237">Passing runsettings arguments through commandline</span></span>](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md)
