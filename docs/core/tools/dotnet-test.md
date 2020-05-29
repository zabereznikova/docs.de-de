---
title: Befehl „dotnet test“
description: Der Befehl „dotnet test“ wird zum Ausführen von Unittests in einem bestimmten Projekt verwendet.
ms.date: 04/29/2020
ms.openlocfilehash: 22b27007d26c98cff40733ef8d449ce334f87848
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2020
ms.locfileid: "83802677"
---
# <a name="dotnet-test"></a><span data-ttu-id="dbf3d-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="dbf3d-103">dotnet test</span></span>

<span data-ttu-id="dbf3d-104">**Dieser Artikel gilt für:** ✔️ .NET Core 2.1 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="dbf3d-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="dbf3d-105">name</span><span class="sxs-lookup"><span data-stu-id="dbf3d-105">Name</span></span>

<span data-ttu-id="dbf3d-106">`dotnet test`: .NET-Testtreiber, der verwendet wird, um Komponententests auszuführen.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-106">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="dbf3d-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="dbf3d-107">Synopsis</span></span>

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

## <a name="description"></a><span data-ttu-id="dbf3d-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dbf3d-108">Description</span></span>

<span data-ttu-id="dbf3d-109">Der Befehl `dotnet test` wird zum Ausführen von Komponententests in einer bestimmten Projektmappe verwendet.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-109">The `dotnet test` command is used to execute unit tests in a given solution.</span></span> <span data-ttu-id="dbf3d-110">Mit dem Befehl `dotnet test` wird die Projektmappe erstellt und für jedes Testprojekt in der Projektmappe eine Testhostanwendung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-110">The `dotnet test` command builds the solution and runs a test host application for each test project in the solution.</span></span> <span data-ttu-id="dbf3d-111">Der Testhost führt Tests im angegebenen Projekt mithilfe eines Testframeworks aus, z. B. MSTest, NUnit oder xUnit, und meldet den Erfolg oder Fehler jedes Tests.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-111">The test host executes tests in the given project using a test framework, for example: MSTest, NUnit, or xUnit, and reports the success or failure of each test.</span></span> <span data-ttu-id="dbf3d-112">Wenn alle Tests erfolgreich sind, gibt der Test Runner 0 (null) als Exitcode zurück. Wenn jedoch ein Test fehlschlägt, wird 1 zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-112">If all tests are successful, the test runner returns 0 as an exit code; otherwise if any test fails, it returns 1.</span></span>

<span data-ttu-id="dbf3d-113">Bei Projekten mit mehreren Zielen werden Tests für jedes Zielframework ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-113">For multi-targeted projects, tests are run for each targeted framework.</span></span> <span data-ttu-id="dbf3d-114">Der Testhost und das Komponententest-Framework werden als NuGet-Pakete gepackt und als gewöhnliche Abhängigkeiten für das Projekt wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-114">The test host and the unit test framework are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="dbf3d-115">In Testprojekten wird der Testlauf mittels eines normalen `<PackageReference>`-Elements angegeben, wie in der folgenden Beispielprojektdatei gezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="dbf3d-115">Test projects specify the test runner using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

<span data-ttu-id="dbf3d-116">Wobei `Microsoft.NET.Test.Sdk` der Testhost und `xunit` das Testframework ist.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-116">Where `Microsoft.NET.Test.Sdk` is the test host, `xunit` is the test framework.</span></span> <span data-ttu-id="dbf3d-117">Und `xunit.runner.visualstudio` ist ein Testadapter, der es dem xUnit-Framework ermöglicht, mit dem Testhost zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-117">And `xunit.runner.visualstudio` is a test adapter, which allows the xUnit framework to work with the test host.</span></span>

### <a name="implicit-restore"></a><span data-ttu-id="dbf3d-118">Implizite Wiederherstellung</span><span class="sxs-lookup"><span data-stu-id="dbf3d-118">Implicit restore</span></span>

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a><span data-ttu-id="dbf3d-119">Argumente</span><span class="sxs-lookup"><span data-stu-id="dbf3d-119">Arguments</span></span>

- **`PROJECT | SOLUTION | DIRECTORY | DLL`**

  - <span data-ttu-id="dbf3d-120">Der Pfad zum Testprojekt.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-120">Path to the test project.</span></span>
  - <span data-ttu-id="dbf3d-121">Der Pfad zur Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-121">Path to the solution.</span></span>
  - <span data-ttu-id="dbf3d-122">Der Pfad zu einem Verzeichnis, das ein Projekt oder eine Projektmappe enthält.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-122">Path to a directory that contains a project or a solution.</span></span>
  - <span data-ttu-id="dbf3d-123">Der Pfad zur *DLL*-Datei eines Testprojekts.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-123">Path to a test project *.dll* file.</span></span>

  <span data-ttu-id="dbf3d-124">Ist dieses Argument nicht angegeben, wird nach einem Projekt oder einer Projektmappe im aktuellen Verzeichnis gesucht.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-124">If not specified, it searches for a project or a solution in the current directory.</span></span>

## <a name="options"></a><span data-ttu-id="dbf3d-125">Optionen</span><span class="sxs-lookup"><span data-stu-id="dbf3d-125">Options</span></span>

- **`-a|--test-adapter-path <PATH_TO_ADAPTER>`**

  <span data-ttu-id="dbf3d-126">Der Pfad zu einem Verzeichnis, das nach zusätzlichen Testadaptern durchsucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-126">Path to a directory to be searched for additional test adapters.</span></span> <span data-ttu-id="dbf3d-127">Nur *DLL*-Dateien mit dem Suffix `.TestAdapter.dll` werden untersucht.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-127">Only *.dll* files with suffix `.TestAdapter.dll` are inspected.</span></span> <span data-ttu-id="dbf3d-128">Wenn nichts angegeben ist, wird das Verzeichnis der Test-*DLL* durchsucht.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-128">If not specified, the directory of the test *.dll* is searched.</span></span>

- **`--blame`**

  <span data-ttu-id="dbf3d-129">Führt die Tests im blame-Modus aus.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-129">Runs the tests in blame mode.</span></span> <span data-ttu-id="dbf3d-130">Diese Option hilft beim Isolieren von fehlerhaften Tests, die den Absturz des Testhosts verursachen.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-130">This option is helpful in isolating problematic tests that cause the test host to crash.</span></span> <span data-ttu-id="dbf3d-131">Wenn ei Absturz erkannt wird, wird in `TestResults/<Guid>/<Guid>_Sequence.xml` eine Sequenzdatei erstellt, die die Reihenfolge der Tests erfasst, die vor dem Absturz ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-131">When a crash is detected, it creates an sequence file in `TestResults/<Guid>/<Guid>_Sequence.xml` that captures the order of tests that were run before the crash.</span></span>

- **`-c|--configuration <CONFIGURATION>`**

  <span data-ttu-id="dbf3d-132">Legt die Buildkonfiguration fest.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-132">Defines the build configuration.</span></span> <span data-ttu-id="dbf3d-133">Der Standardwert ist `Debug`, aber die Konfiguration des Projekts könnte diese SDK-Standardeinstellung überschreiben.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-133">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

- **`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`**

  <span data-ttu-id="dbf3d-134">Aktiviert den Datensammler für den Testlauf.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-134">Enables data collector for the test run.</span></span> <span data-ttu-id="dbf3d-135">Weitere Informationen finden Sie unter [Monitor and analyze test run (Überwachen und Analysieren eines Testlaufs)](https://aka.ms/vstest-collect).</span><span class="sxs-lookup"><span data-stu-id="dbf3d-135">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

- **`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`**

  <span data-ttu-id="dbf3d-136">Aktiviert den Diagnosemodus für die Testplattform und schreibt Diagnosemeldungen in die angegebene Datei sowie in benachbarte Dateien.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-136">Enables diagnostic mode for the test platform and writes diagnostic messages to the specified file and to files next to it.</span></span> <span data-ttu-id="dbf3d-137">Der Prozess, der die Meldungen protokolliert, bestimmt, welche Dateien erstellt werden, z. B. `*.host_<date>.txt` für das Testhostprotokoll und `*.datacollector_<date>.txt` für das Datensammlerprotokoll.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-137">The process that is logging the messages determines which files are created, such as `*.host_<date>.txt` for test host log, and `*.datacollector_<date>.txt` for data collector log.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="dbf3d-138">Erzwingt die Verwendung von `dotnet` oder des .NET Framework-Testhosts für die Testbinärdateien.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-138">Forces the use of `dotnet` or .NET Framework test host for the test binaries.</span></span> <span data-ttu-id="dbf3d-139">Mit dieser Option wird nur der zu verwendende Hosttyp bestimmt.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-139">This option only determines which type of host to use.</span></span> <span data-ttu-id="dbf3d-140">Die tatsächliche zu verwendende Frameworkversion wird durch die *runtimeconfig.json* des Testprojekts bestimmt.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-140">The actual framework version to be used is determined by the *runtimeconfig.json* of the test project.</span></span> <span data-ttu-id="dbf3d-141">Wenn nichts angegeben ist, wird das [TargetFramework-Assemblyattribut](/dotnet/api/system.runtime.versioning.targetframeworkattribute) verwendet, um den Hosttyp zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-141">When not specified, the [TargetFramework assembly attribute](/dotnet/api/system.runtime.versioning.targetframeworkattribute) is used to determine the type of host.</span></span> <span data-ttu-id="dbf3d-142">Wenn dieses Attribut von der *DLL* entfernt wird, wird der .NET Framework-Host verwendet.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-142">When that attribute is stripped from the *.dll*, the .NET Framework host is used.</span></span>

- **`--filter <EXPRESSION>`**

  <span data-ttu-id="dbf3d-143">Filtert Tests im aktuellen Projekt mithilfe des angegebenen Ausdrucks heraus.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-143">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="dbf3d-144">Weitere Informationen finden Sie im Abschnitt [Details zu Filteroptionen](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="dbf3d-144">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="dbf3d-145">Weitere Informationen und Beispiele zur Verwendung von selektiven Komponententestfiltern finden Sie unter [Ausführen von selektiven Komponententests](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="dbf3d-145">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

- **`-h|--help`**

  <span data-ttu-id="dbf3d-146">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-146">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="dbf3d-147">Ermöglicht dem Befehl, anzuhalten und auf Benutzereingaben oder Aktionen zu warten.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-147">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="dbf3d-148">Beispielsweise, um die Authentifizierung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-148">For example, to complete authentication.</span></span> <span data-ttu-id="dbf3d-149">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-149">Available since .NET Core 3.0 SDK.</span></span>

- **`-l|--logger <LOGGER_URI/FRIENDLY_NAME>`**

  <span data-ttu-id="dbf3d-150">Gibt eine Protokollierung für die Testergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-150">Specifies a logger for test results.</span></span> <span data-ttu-id="dbf3d-151">Im Gegensatz zu MSBuild akzeptiert der Befehl „dotnet test“ keine Abkürzungen: verwenden Sie `-l "console;verbosity=detailed"` anstelle von `-l "console;v=d"`.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-151">Unlike MSBuild, dotnet test doesn't accept abbreviations: instead of `-l "console;v=d"` use `-l "console;verbosity=detailed"`.</span></span>

- **`--no-build`**

  <span data-ttu-id="dbf3d-152">Erstellt das Projekt nicht vor der Ausführung.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-152">Doesn't build the test project before running it.</span></span> <span data-ttu-id="dbf3d-153">Zudem wird das Flag `--no-restore` implizit festgelegt.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-153">It also implicitly sets the - `--no-restore` flag.</span></span>

- **`--nologo`**

  <span data-ttu-id="dbf3d-154">Führen Sie Tests aus, ohne das Microsoft TestPlatform-Banner anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-154">Run tests without displaying the Microsoft TestPlatform banner.</span></span> <span data-ttu-id="dbf3d-155">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-155">Available since .NET Core 3.0 SDK.</span></span>

- **`--no-restore`**

  <span data-ttu-id="dbf3d-156">Führt keine implizite Wiederherstellung aus, wenn der Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-156">Doesn't execute an implicit restore when running the command.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="dbf3d-157">Verzeichnis, in dem die auszuführenden Binärdateien zu finden sind.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-157">Directory in which to find the binaries to run.</span></span> <span data-ttu-id="dbf3d-158">Wenn nicht angegeben, ist der Standardpfad `./bin/<configuration>/<framework>/`.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-158">If not specified, the default path is `./bin/<configuration>/<framework>/`.</span></span>  <span data-ttu-id="dbf3d-159">Bei Projekten mit mehreren Zielframeworks (über die `TargetFrameworks`-Eigenschaft) müssen Sie auch `--framework` definieren, wenn Sie diese Option angeben.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-159">For projects with multiple target frameworks (via the `TargetFrameworks` property), you also need to define `--framework` when you specify this option.</span></span> <span data-ttu-id="dbf3d-160">`dotnet test` führt Tests immer über das Ausgabeverzeichnis aus.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-160">`dotnet test` always runs tests from the output directory.</span></span> <span data-ttu-id="dbf3d-161">Sie können <xref:System.AppDomain.BaseDirectory%2A?displayProperty=nameWithType> verwenden, um die Testobjekte im Ausgabeverzeichnis zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-161">You can use <xref:System.AppDomain.BaseDirectory%2A?displayProperty=nameWithType> to consume test assets in the output directory.</span></span>

- **`-r|--results-directory <PATH>`**

  <span data-ttu-id="dbf3d-162">Das Verzeichnis, in dem die Testergebnisse gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-162">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="dbf3d-163">Wenn das Verzeichnis noch nicht vorhanden ist, wird es erstellt.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-163">If the specified directory doesn't exist, it's created.</span></span> <span data-ttu-id="dbf3d-164">Der Standardwert ist `TestResults` in dem Verzeichnis, das die Projektdatei enthält.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-164">The default is `TestResults` in the directory that contains the project file.</span></span>

- **`--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="dbf3d-165">Die Zielruntime, für die Tests ausgeführt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-165">The target runtime to test for.</span></span>

- **`-s|--settings <SETTINGS_FILE>`**

  <span data-ttu-id="dbf3d-166">Die `.runsettings`-Datei, die zum Ausführen der Tests verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-166">The `.runsettings` file to use for running the tests.</span></span> <span data-ttu-id="dbf3d-167">Beachten Sie, dass das `TargetPlatform`-Element (x86|x64) keine Auswirkung auf `dotnet test` hat.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-167">Note that the `TargetPlatform` element (x86|x64) has no effect for `dotnet test`.</span></span> <span data-ttu-id="dbf3d-168">Installieren Sie die x86-Version von .NET Core, um x86-Tests auszuführen.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-168">To run tests that target x86, install the x86 version of .NET Core.</span></span> <span data-ttu-id="dbf3d-169">Die Bitanzahl der Datei *dotnet.exe*, die sich in diesem Pfad befindet, wird zum Ausführen von Tests verwendet.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-169">The bitness of the *dotnet.exe* that is on the path is what will be used for running tests.</span></span> <span data-ttu-id="dbf3d-170">Weitere Informationen finden Sie in den folgenden Ressourcen:</span><span class="sxs-lookup"><span data-stu-id="dbf3d-170">For more information, see the following resources:</span></span>

  - [<span data-ttu-id="dbf3d-171">Konfigurieren von Komponententests mithilfe einer `.runsettings`-Datei.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-171">Configure unit tests by using a `.runsettings` file.</span></span>](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file)
  - [<span data-ttu-id="dbf3d-172">Konfigurieren eines Testlaufs</span><span class="sxs-lookup"><span data-stu-id="dbf3d-172">Configure a test run</span></span>](https://github.com/Microsoft/vstest-docs/blob/master/docs/configure.md)

- **`-t|--list-tests`**

  <span data-ttu-id="dbf3d-173">Listen Sie alle ermittelten Tests im aktuellen Projekt auf.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-173">List all of the discovered tests in the current project.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="dbf3d-174">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-174">Sets the verbosity level of the command.</span></span> <span data-ttu-id="dbf3d-175">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-175">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="dbf3d-176">Der Standardwert ist `minimal`.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-176">The default is `minimal`.</span></span> <span data-ttu-id="dbf3d-177">Weitere Informationen finden Sie unter <xref:Microsoft.Build.Framework.LoggerVerbosity>.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-177">For more information, see <xref:Microsoft.Build.Framework.LoggerVerbosity>.</span></span>

- <span data-ttu-id="dbf3d-178">**`RunSettings`** -Argumente</span><span class="sxs-lookup"><span data-stu-id="dbf3d-178">**`RunSettings`** arguments</span></span>

 <span data-ttu-id="dbf3d-179">Inline-`RunSettings` werden als die letzten Argumente auf der Befehlszeile nach „-- “ (beachten Sie das Leerzeichen hinter „--“) übergeben.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-179">Inline `RunSettings` are passed as the last arguments on the command line after "-- " (note the space after --).</span></span> <span data-ttu-id="dbf3d-180">Inline-`RunSettings` werden als `[name]=[value]`-Paare angegeben.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-180">Inline `RunSettings` are specified as `[name]=[value]` pairs.</span></span> <span data-ttu-id="dbf3d-181">Ein Leerzeichen wird verwendet, um mehrere `[name]=[value]`-Paare voneinander zu trennen.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-181">A space is used to separate multiple `[name]=[value]` pairs.</span></span>

  <span data-ttu-id="dbf3d-182">Ein Beispiel: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span><span class="sxs-lookup"><span data-stu-id="dbf3d-182">Example: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span></span>

  <span data-ttu-id="dbf3d-183">Weitere Informationen finden Sie unter [Übergeben von RunSettings-Argumenten über die Befehlszeile](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).</span><span class="sxs-lookup"><span data-stu-id="dbf3d-183">For more information, see [Passing RunSettings arguments through command line](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).</span></span>

## <a name="examples"></a><span data-ttu-id="dbf3d-184">Beispiele</span><span class="sxs-lookup"><span data-stu-id="dbf3d-184">Examples</span></span>

- <span data-ttu-id="dbf3d-185">Führen Sie die Tests im Projekt im aktuellen Verzeichnis durch:</span><span class="sxs-lookup"><span data-stu-id="dbf3d-185">Run the tests in the project in the current directory:</span></span>

  ```dotnetcli
  dotnet test
  ```

- <span data-ttu-id="dbf3d-186">Führen Sie die Tests im Projekt `test1` durch:</span><span class="sxs-lookup"><span data-stu-id="dbf3d-186">Run the tests in the `test1` project:</span></span>

  ```dotnetcli
  dotnet test ~/projects/test1/test1.csproj
  ```

- <span data-ttu-id="dbf3d-187">Mit dem folgenden Befehl führen Sie die Tests im aktuellen Verzeichnis aus und generieren eine Testergebnisdatei im TRX-Format:</span><span class="sxs-lookup"><span data-stu-id="dbf3d-187">Run the tests in the project in the current directory, and generate a test results file in the trx format:</span></span>

  ```dotnetcli
  dotnet test --logger trx
  ```

- <span data-ttu-id="dbf3d-188">Mit dem folgenden Befehl führen Sie die Tests im aktuellen Verzeichnis aus und erstellen ein ausführliches Protokoll in der Konsole:</span><span class="sxs-lookup"><span data-stu-id="dbf3d-188">Run the tests in the project in the current directory, and log with detailed verbosity to the console:</span></span>

  ```dotnetcli
  dotnet test --logger "console;verbosity=detailed"
  ```
  
  - <span data-ttu-id="dbf3d-189">Mit dem folgenden Befehl führen Sie die Tests in dem Projekt im aktuellen Verzeichnis aus und melden Tests, die während des Absturzes des Testhosts in Arbeit waren:</span><span class="sxs-lookup"><span data-stu-id="dbf3d-189">Run the tests in the project in the current directory, and report tests that were in progress when the test host crashed:</span></span>

  ```dotnetcli
  dotnet test --blame
  ```

## <a name="filter-option-details"></a><span data-ttu-id="dbf3d-190">Details zu Filteroptionen</span><span class="sxs-lookup"><span data-stu-id="dbf3d-190">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="dbf3d-191">`<Expression>` weist das Format `<property><operator><value>[|&<Expression>]` auf.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-191">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="dbf3d-192">`<property>` ist ein Attribut von `Test Case`.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-192">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="dbf3d-193">Im Folgenden werden die Eigenschaften aufgeführt, die von gängigen Frameworks für Komponententests unterstützt werden:</span><span class="sxs-lookup"><span data-stu-id="dbf3d-193">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="dbf3d-194">Testframework</span><span class="sxs-lookup"><span data-stu-id="dbf3d-194">Test Framework</span></span> | <span data-ttu-id="dbf3d-195">Unterstützte Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="dbf3d-195">Supported properties</span></span>                                                                                      |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="dbf3d-196">MSTest</span><span class="sxs-lookup"><span data-stu-id="dbf3d-196">MSTest</span></span>         | <ul><li><span data-ttu-id="dbf3d-197">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="dbf3d-197">FullyQualifiedName</span></span></li><li><span data-ttu-id="dbf3d-198">name</span><span class="sxs-lookup"><span data-stu-id="dbf3d-198">Name</span></span></li><li><span data-ttu-id="dbf3d-199">ClassName</span><span class="sxs-lookup"><span data-stu-id="dbf3d-199">ClassName</span></span></li><li><span data-ttu-id="dbf3d-200">Priorität</span><span class="sxs-lookup"><span data-stu-id="dbf3d-200">Priority</span></span></li><li><span data-ttu-id="dbf3d-201">TestCategory</span><span class="sxs-lookup"><span data-stu-id="dbf3d-201">TestCategory</span></span></li></ul> |
| <span data-ttu-id="dbf3d-202">xUnit</span><span class="sxs-lookup"><span data-stu-id="dbf3d-202">xUnit</span></span>          | <ul><li><span data-ttu-id="dbf3d-203">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="dbf3d-203">FullyQualifiedName</span></span></li><li><span data-ttu-id="dbf3d-204">DisplayName</span><span class="sxs-lookup"><span data-stu-id="dbf3d-204">DisplayName</span></span></li><li><span data-ttu-id="dbf3d-205">Merkmale</span><span class="sxs-lookup"><span data-stu-id="dbf3d-205">Traits</span></span></li></ul>                                   |

<span data-ttu-id="dbf3d-206">`<operator>` beschreibt die Beziehung zwischen der Eigenschaft und dem Wert:</span><span class="sxs-lookup"><span data-stu-id="dbf3d-206">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="dbf3d-207">Operator</span><span class="sxs-lookup"><span data-stu-id="dbf3d-207">Operator</span></span> | <span data-ttu-id="dbf3d-208">Funktion</span><span class="sxs-lookup"><span data-stu-id="dbf3d-208">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="dbf3d-209">Genaue Übereinstimmung</span><span class="sxs-lookup"><span data-stu-id="dbf3d-209">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="dbf3d-210">Keine genaue Übereinstimmung</span><span class="sxs-lookup"><span data-stu-id="dbf3d-210">Not exact match</span></span> |
| `~`      | <span data-ttu-id="dbf3d-211">Enthält</span><span class="sxs-lookup"><span data-stu-id="dbf3d-211">Contains</span></span>        |
| `!~`     | <span data-ttu-id="dbf3d-212">Enthält nicht</span><span class="sxs-lookup"><span data-stu-id="dbf3d-212">Not contains</span></span>    |

<span data-ttu-id="dbf3d-213">`<value>` ist eine Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-213">`<value>` is a string.</span></span> <span data-ttu-id="dbf3d-214">Bei allen Suchvorgängen ist die Groß-/Kleinschreibung nicht relevant.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-214">All the lookups are case insensitive.</span></span>

<span data-ttu-id="dbf3d-215">Ein Ausdruck ohne `<operator>` gilt automatisch als `contains` für die `FullyQualifiedName`-Eigenschaft (`dotnet test --filter xyz` ist beispielsweise identisch mit `dotnet test --filter FullyQualifiedName~xyz`).</span><span class="sxs-lookup"><span data-stu-id="dbf3d-215">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="dbf3d-216">Ausdrücke können mit bedingten Operatoren verknüpft werden:</span><span class="sxs-lookup"><span data-stu-id="dbf3d-216">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="dbf3d-217">Operator</span><span class="sxs-lookup"><span data-stu-id="dbf3d-217">Operator</span></span>            | <span data-ttu-id="dbf3d-218">Funktion</span><span class="sxs-lookup"><span data-stu-id="dbf3d-218">Function</span></span> |
| ------------------- | -------- |
| <code>&#124;</code> | <span data-ttu-id="dbf3d-219">ODER</span><span class="sxs-lookup"><span data-stu-id="dbf3d-219">OR</span></span>       |
| `&`                 | <span data-ttu-id="dbf3d-220">UND</span><span class="sxs-lookup"><span data-stu-id="dbf3d-220">AND</span></span>      |

<span data-ttu-id="dbf3d-221">Sie können Ausdrücke in Klammern einschließen, wenn Sie bedingte Operatoren verwenden (z.B. `(Name~TestMethod1) | (Name~TestMethod2)`).</span><span class="sxs-lookup"><span data-stu-id="dbf3d-221">You can enclose expressions in parenthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="dbf3d-222">Weitere Informationen und Beispiele zur Verwendung von selektiven Komponententestfiltern finden Sie unter [Ausführen von selektiven Komponententests](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="dbf3d-222">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="dbf3d-223">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dbf3d-223">See also</span></span>

- [<span data-ttu-id="dbf3d-224">Frameworks und Ziele</span><span class="sxs-lookup"><span data-stu-id="dbf3d-224">Frameworks and Targets</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="dbf3d-225">.NET Core Runtime-ID (RID)-Katalog</span><span class="sxs-lookup"><span data-stu-id="dbf3d-225">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
- [<span data-ttu-id="dbf3d-226">Übergeben von runsettings-Argumenten über die Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="dbf3d-226">Passing runsettings arguments through commandline</span></span>](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md)
