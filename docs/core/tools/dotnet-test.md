---
title: Befehl „dotnet test“
description: Der Befehl „dotnet test“ wird zum Ausführen von Unittests in einem bestimmten Projekt verwendet.
ms.date: 04/29/2020
ms.openlocfilehash: a5666cfe4c09b2b88d77b256fac922154c7d6bd7
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2020
ms.locfileid: "94634382"
---
# <a name="dotnet-test"></a><span data-ttu-id="5ecf6-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="5ecf6-103">dotnet test</span></span>

<span data-ttu-id="5ecf6-104">**Dieser Artikel gilt für:** ✔️ .NET Core 2.1 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="5ecf6-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="5ecf6-105">name</span><span class="sxs-lookup"><span data-stu-id="5ecf6-105">Name</span></span>

<span data-ttu-id="5ecf6-106">`dotnet test`: .NET-Testtreiber, der verwendet wird, um Komponententests auszuführen.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-106">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="5ecf6-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="5ecf6-107">Synopsis</span></span>

```dotnetcli
dotnet test [<PROJECT> | <SOLUTION> | <DIRECTORY> | <DLL>]
    [-a|--test-adapter-path <ADAPTER_PATH>] [--blame] [--blame-crash]
    [--blame-crash-dump-type <DUMP_TYPE>] [--blame-crash-collect-always]
    [--blame-hang] [--blame-hang-dump-type <DUMP_TYPE>]
    [--blame-hang-timeout <TIMESPAN>]
    [-c|--configuration <CONFIGURATION>]
    [--collect <DATA_COLLECTOR_NAME>]
    [-d|--diag <LOG_FILE>] [-f|--framework <FRAMEWORK>]
    [--filter <EXPRESSION>] [--interactive]
    [-l|--logger <LOGGER>] [--no-build]
    [--nologo] [--no-restore] [-o|--output <OUTPUT_DIRECTORY>]
    [-r|--results-directory <RESULTS_DIR>] [--runtime <RUNTIME_IDENTIFIER>]
    [-s|--settings <SETTINGS_FILE>] [-t|--list-tests]
    [-v|--verbosity <LEVEL>] [[--] <RunSettings arguments>]

dotnet test -h|--help
```

## <a name="description"></a><span data-ttu-id="5ecf6-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5ecf6-108">Description</span></span>

<span data-ttu-id="5ecf6-109">Der Befehl `dotnet test` wird zum Ausführen von Komponententests in einer bestimmten Projektmappe verwendet.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-109">The `dotnet test` command is used to execute unit tests in a given solution.</span></span> <span data-ttu-id="5ecf6-110">Mit dem Befehl `dotnet test` wird die Projektmappe erstellt und für jedes Testprojekt in der Projektmappe eine Testhostanwendung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-110">The `dotnet test` command builds the solution and runs a test host application for each test project in the solution.</span></span> <span data-ttu-id="5ecf6-111">Der Testhost führt Tests im angegebenen Projekt mithilfe eines Testframeworks aus, z. B. MSTest, NUnit oder xUnit, und meldet den Erfolg oder Fehler jedes Tests.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-111">The test host executes tests in the given project using a test framework, for example: MSTest, NUnit, or xUnit, and reports the success or failure of each test.</span></span> <span data-ttu-id="5ecf6-112">Wenn alle Tests erfolgreich sind, gibt der Test Runner 0 (null) als Exitcode zurück. Wenn jedoch ein Test fehlschlägt, wird 1 zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-112">If all tests are successful, the test runner returns 0 as an exit code; otherwise if any test fails, it returns 1.</span></span>

<span data-ttu-id="5ecf6-113">Bei Projekten mit mehreren Zielen werden Tests für jedes Zielframework ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-113">For multi-targeted projects, tests are run for each targeted framework.</span></span> <span data-ttu-id="5ecf6-114">Der Testhost und das Komponententest-Framework werden als NuGet-Pakete gepackt und als gewöhnliche Abhängigkeiten für das Projekt wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-114">The test host and the unit test framework are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="5ecf6-115">In Testprojekten wird der Testlauf mittels eines normalen `<PackageReference>`-Elements angegeben, wie in der folgenden Beispielprojektdatei gezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="5ecf6-115">Test projects specify the test runner using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

<span data-ttu-id="5ecf6-116">Wobei `Microsoft.NET.Test.Sdk` der Testhost und `xunit` das Testframework ist.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-116">Where `Microsoft.NET.Test.Sdk` is the test host, `xunit` is the test framework.</span></span> <span data-ttu-id="5ecf6-117">Und `xunit.runner.visualstudio` ist ein Testadapter, der es dem xUnit-Framework ermöglicht, mit dem Testhost zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-117">And `xunit.runner.visualstudio` is a test adapter, which allows the xUnit framework to work with the test host.</span></span>

### <a name="implicit-restore"></a><span data-ttu-id="5ecf6-118">Implizite Wiederherstellung</span><span class="sxs-lookup"><span data-stu-id="5ecf6-118">Implicit restore</span></span>

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a><span data-ttu-id="5ecf6-119">Argumente</span><span class="sxs-lookup"><span data-stu-id="5ecf6-119">Arguments</span></span>

- **`PROJECT | SOLUTION | DIRECTORY | DLL`**

  - <span data-ttu-id="5ecf6-120">Der Pfad zum Testprojekt.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-120">Path to the test project.</span></span>
  - <span data-ttu-id="5ecf6-121">Der Pfad zur Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-121">Path to the solution.</span></span>
  - <span data-ttu-id="5ecf6-122">Der Pfad zu einem Verzeichnis, das ein Projekt oder eine Projektmappe enthält.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-122">Path to a directory that contains a project or a solution.</span></span>
  - <span data-ttu-id="5ecf6-123">Der Pfad zur *DLL*-Datei eines Testprojekts.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-123">Path to a test project *.dll* file.</span></span>

  <span data-ttu-id="5ecf6-124">Ist dieses Argument nicht angegeben, wird nach einem Projekt oder einer Projektmappe im aktuellen Verzeichnis gesucht.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-124">If not specified, it searches for a project or a solution in the current directory.</span></span>

## <a name="options"></a><span data-ttu-id="5ecf6-125">Optionen</span><span class="sxs-lookup"><span data-stu-id="5ecf6-125">Options</span></span>

- **`-a|--test-adapter-path <ADAPTER_PATH>`**

  <span data-ttu-id="5ecf6-126">Der Pfad zu einem Verzeichnis, das nach zusätzlichen Testadaptern durchsucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-126">Path to a directory to be searched for additional test adapters.</span></span> <span data-ttu-id="5ecf6-127">Nur *DLL*-Dateien mit dem Suffix `.TestAdapter.dll` werden untersucht.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-127">Only *.dll* files with suffix `.TestAdapter.dll` are inspected.</span></span> <span data-ttu-id="5ecf6-128">Wenn nichts angegeben ist, wird das Verzeichnis der Test-*DLL* durchsucht.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-128">If not specified, the directory of the test *.dll* is searched.</span></span>

- **`--blame`**

  <span data-ttu-id="5ecf6-129">Führt die Tests im blame-Modus aus.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-129">Runs the tests in blame mode.</span></span> <span data-ttu-id="5ecf6-130">Diese Option hilft beim Isolieren von fehlerhaften Tests, die den Absturz des Testhosts verursachen.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-130">This option is helpful in isolating problematic tests that cause the test host to crash.</span></span> <span data-ttu-id="5ecf6-131">Wenn ein Absturz erkannt wird, wird in `TestResults/<Guid>/<Guid>_Sequence.xml` eine Sequenzdatei erstellt, die die Reihenfolge der Tests erfasst, die vor dem Absturz ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-131">When a crash is detected, it creates a sequence file in `TestResults/<Guid>/<Guid>_Sequence.xml` that captures the order of tests that were run before the crash.</span></span>

- <span data-ttu-id="5ecf6-132">**`--blame-crash`** (Verfügbar seit .NET 5.0 Preview SDK)</span><span class="sxs-lookup"><span data-stu-id="5ecf6-132">**`--blame-crash`** (Available since .NET 5.0 preview SDK)</span></span>

  <span data-ttu-id="5ecf6-133">Führt die Tests im Modus „Verantwortung zuweisen“ aus und erfasst ein Absturzabbild, wenn der Testhost unerwartet beendet wird.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-133">Runs the tests in blame mode and collects a crash dump when the test host exits unexpectedly.</span></span> <span data-ttu-id="5ecf6-134">Diese Option hängt von der verwendeten Version von .NET, dem Fehlertyp und Betriebssystem ab.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-134">This option depends on the version of .NET used, the type of error, and the operating system.</span></span>
  
  <span data-ttu-id="5ecf6-135">Für Ausnahmen in verwaltetem Code wird ab NET 5.0 automatisch ein Absturzabbild erfasst.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-135">For exceptions in managed code, a dump will be automatically collected on .NET 5.0 and later versions.</span></span> <span data-ttu-id="5ecf6-136">Es wird ein Absturzabbild für den Testhost oder jegliche untergeordneten Prozesse generiert, die ebenfalls unter .NET 5.0 liefen und abgestürzt sind.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-136">It will generate a dump for testhost or any child process that also ran on .NET 5.0 and crashed.</span></span> <span data-ttu-id="5ecf6-137">Abstürze in nativem Code generieren keine Absturzabbild.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-137">Crashes in native code will not generate a dump.</span></span> <span data-ttu-id="5ecf6-138">Diese Option funktioniert unter Windows, macOS und Linux.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-138">This option works on Windows, macOS, and Linux.</span></span>
  
  <span data-ttu-id="5ecf6-139">Absturzabbilder in nativem Code oder bei Verwendung von .NET Core 3.1 oder früheren Versionen können unter Windows nur mithilfe von Procdump erfasst werden.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-139">Crash dumps in native code, or when using .NET Core 3.1 or earlier versions, can only be collected on Windows, by using Procdump.</span></span> <span data-ttu-id="5ecf6-140">Ein Verzeichnis, das *procdump.exe* und *procdump64.exe* enthält, muss in der PATH- oder PROCDUMP_PATH-Umgebungsvariablen enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-140">A directory that contains *procdump.exe* and *procdump64.exe* must be in the PATH or PROCDUMP_PATH environment variable.</span></span> <span data-ttu-id="5ecf6-141">[Tools herunterladen](/sysinternals/downloads/procdump).</span><span class="sxs-lookup"><span data-stu-id="5ecf6-141">[Download the tools](/sysinternals/downloads/procdump).</span></span> <span data-ttu-id="5ecf6-142">Impliziert `--blame`.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-142">Implies `--blame`.</span></span>
  
  <span data-ttu-id="5ecf6-143">Um ein Absturzabbild aus einer nativen Anwendung zu erfassen, die unter .NET 5.0 oder höher läuft, kann die Verwendung von Procdump erzwungen werden, indem die Umgebungsvariable `VSTEST_DUMP_FORCEPROCDUMP` auf `1` festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-143">To collect a crash dump from a native application running on .NET 5.0 or later, the usage of Procdump can be forced by setting the `VSTEST_DUMP_FORCEPROCDUMP` environment variable to `1`.</span></span>

- <span data-ttu-id="5ecf6-144">**`--blame-crash-dump-type <DUMP_TYPE>`** (Verfügbar seit .NET 5.0 Preview SDK)</span><span class="sxs-lookup"><span data-stu-id="5ecf6-144">**`--blame-crash-dump-type <DUMP_TYPE>`** (Available since .NET 5.0 preview SDK)</span></span>

  <span data-ttu-id="5ecf6-145">Der Typ des zu erfassenden Absturzspeicherabbilds.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-145">The type of crash dump to be collected.</span></span> <span data-ttu-id="5ecf6-146">Impliziert `--blame-crash`.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-146">Implies `--blame-crash`.</span></span>

- <span data-ttu-id="5ecf6-147">**`--blame-crash-collect-always`** (Verfügbar seit .NET 5.0 Preview SDK)</span><span class="sxs-lookup"><span data-stu-id="5ecf6-147">**`--blame-crash-collect-always`** (Available since .NET 5.0 preview SDK)</span></span>

  <span data-ttu-id="5ecf6-148">Erfasst ein Absturzabbild bei einer erwarteten und einer unerwarteten Beendigung des Testhosts.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-148">Collects a crash dump on expected as well as unexpected test host exit.</span></span>

- <span data-ttu-id="5ecf6-149">**`--blame-hang`** (Verfügbar seit .NET 5.0 Preview SDK)</span><span class="sxs-lookup"><span data-stu-id="5ecf6-149">**`--blame-hang`** (Available since .NET 5.0 preview SDK)</span></span>

  <span data-ttu-id="5ecf6-150">Hiermit werden Tests im Modus „Verantwortung zuweisen“ ausgeführt, und ein Blockadeabbild wird erfasst, wenn der Test länger als angegeben dauert.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-150">Run the tests in blame mode and collects a hang dump when a test exceeds the given timeout.</span></span>

- <span data-ttu-id="5ecf6-151">**`--blame-hang-dump-type <DUMP_TYPE>`** (Verfügbar seit .NET 5.0 Preview SDK)</span><span class="sxs-lookup"><span data-stu-id="5ecf6-151">**`--blame-hang-dump-type <DUMP_TYPE>`** (Available since .NET 5.0 preview SDK)</span></span>

  <span data-ttu-id="5ecf6-152">Der Typ des zu erfassenden Absturzspeicherabbilds.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-152">The type of crash dump to be collected.</span></span> <span data-ttu-id="5ecf6-153">Möglich sind `full`, `mini` oder `none`.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-153">It should be `full`, `mini`, or `none`.</span></span> <span data-ttu-id="5ecf6-154">Wenn `none` angegeben wird, wird der Testhost bei einem Timeout beendet, es wird jedoch kein Abbild erfasst.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-154">When `none` is specified, test host is terminated on timeout, but no dump is collected.</span></span> <span data-ttu-id="5ecf6-155">Impliziert `--blame-hang`.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-155">Implies `--blame-hang`.</span></span>

- <span data-ttu-id="5ecf6-156">**`--blame-hang-timeout <TIMESPAN>`** (Verfügbar seit .NET 5.0 Preview SDK)</span><span class="sxs-lookup"><span data-stu-id="5ecf6-156">**`--blame-hang-timeout <TIMESPAN>`** (Available since .NET 5.0 preview SDK)</span></span>

  <span data-ttu-id="5ecf6-157">Testspezifisches Timeout, nach dem ein Blockadeabbild ausgelöst und der Testhostprozess und alle dessen untergeordneten Prozesse gesichert und beendet werden.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-157">Per-test timeout, after which a hang dump is triggered and the test host process and all of its child processes are dumped and terminated.</span></span> <span data-ttu-id="5ecf6-158">Der Timeoutwert wird in einem der folgenden Formate angegeben:</span><span class="sxs-lookup"><span data-stu-id="5ecf6-158">The timeout value is specified in one of the following formats:</span></span>
  
  - <span data-ttu-id="5ecf6-159">1.5h, 1.5hour, 1.5hours</span><span class="sxs-lookup"><span data-stu-id="5ecf6-159">1.5h, 1.5hour, 1.5hours</span></span>
  - <span data-ttu-id="5ecf6-160">90m, 90min, 90minute, 90minutes</span><span class="sxs-lookup"><span data-stu-id="5ecf6-160">90m, 90min, 90minute, 90minutes</span></span>
  - <span data-ttu-id="5ecf6-161">5400s, 5400sec, 5400second, 5400seconds</span><span class="sxs-lookup"><span data-stu-id="5ecf6-161">5400s, 5400sec, 5400second, 5400seconds</span></span>
  - <span data-ttu-id="5ecf6-162">5400000ms, 5400000mil, 5400000millisecond, 5400000milliseconds</span><span class="sxs-lookup"><span data-stu-id="5ecf6-162">5400000ms, 5400000mil, 5400000millisecond, 5400000milliseconds</span></span>

  <span data-ttu-id="5ecf6-163">Wenn keine Einheit verwendet wird (z. B. 5.400.000), wird angenommen, dass der Wert in Millisekunden angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-163">When no unit is used (for example, 5400000), the value is assumed to be in milliseconds.</span></span> <span data-ttu-id="5ecf6-164">Bei Verwendung in Verbindung mit datenorientierten Tests hängt das Timeoutverhalten vom verwendeten Testadapter ab.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-164">When used together with data driven tests, the timeout behavior depends on the test adapter used.</span></span> <span data-ttu-id="5ecf6-165">Bei xUnit und NUnit wird das Timeout nach jedem Testfall erneuert.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-165">For xUnit and NUnit the timeout is renewed after every test case.</span></span> <span data-ttu-id="5ecf6-166">Für MSTest wird das Timeout für alle Testfälle verwendet.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-166">For MSTest, the timeout is used for all test cases.</span></span> <span data-ttu-id="5ecf6-167">Diese Option wird unter Windows mit netcoreapp2.1 und höher, unter Linux mit netcoreapp3.1 und höher und unter macOS mit net5.0 und höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-167">This option is supported on Windows with netcoreapp2.1 and later, on Linux with netcoreapp3.1 and later, and on macOS with net5.0 or later.</span></span> <span data-ttu-id="5ecf6-168">Impliziert `--blame` und `--blame-hang`.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-168">Implies `--blame` and `--blame-hang`.</span></span>

- **`-c|--configuration <CONFIGURATION>`**

  <span data-ttu-id="5ecf6-169">Legt die Buildkonfiguration fest.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-169">Defines the build configuration.</span></span> <span data-ttu-id="5ecf6-170">Der Standardwert ist `Debug`, aber die Konfiguration des Projekts könnte diese SDK-Standardeinstellung überschreiben.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-170">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

- **`--collect <DATA_COLLECTOR_NAME>`**

  <span data-ttu-id="5ecf6-171">Aktiviert den Datensammler für den Testlauf.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-171">Enables data collector for the test run.</span></span> <span data-ttu-id="5ecf6-172">Weitere Informationen finden Sie unter [Monitor and analyze test run (Überwachen und Analysieren eines Testlaufs)](https://aka.ms/vstest-collect).</span><span class="sxs-lookup"><span data-stu-id="5ecf6-172">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>
  
  <span data-ttu-id="5ecf6-173">Um Code Coverage auf einer beliebigen Plattform zu erfassen, die von .NET Core unterstützt wird, installieren Sie [Coverlet](https://github.com/coverlet-coverage/coverlet/blob/master/README.md) und verwenden die `--collect:"XPlat Code Coverage"`-Option.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-173">To collect code coverage on any platform that is supported by .NET Core, install [Coverlet](https://github.com/coverlet-coverage/coverlet/blob/master/README.md) and use the `--collect:"XPlat Code Coverage"` option.</span></span>

  <span data-ttu-id="5ecf6-174">Unter Windows können Sie Code Coverage mithilfe der `--collect "Code Coverage"`-Option erfassen.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-174">On Windows, you can collect code coverage by using the `--collect "Code Coverage"` option.</span></span> <span data-ttu-id="5ecf6-175">Mit dieser Option wird eine *COVERAGE*-Datei generiert, die in Visual Studio 2019 Enterprise geöffnet werden kann.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-175">This option generates a *.coverage* file, which can be opened in Visual Studio 2019 Enterprise.</span></span> <span data-ttu-id="5ecf6-176">Weitere Informationen finden Sie unter [Verwenden von Code Coverage](/visualstudio/test/using-code-coverage-to-determine-how-much-code-is-being-tested) und [Anpassen der Code Coverage-Analyse](/visualstudio/test/customizing-code-coverage-analysis).</span><span class="sxs-lookup"><span data-stu-id="5ecf6-176">For more information, see [Use code coverage](/visualstudio/test/using-code-coverage-to-determine-how-much-code-is-being-tested) and [Customize code coverage analysis](/visualstudio/test/customizing-code-coverage-analysis).</span></span>

- **`-d|--diag <LOG_FILE>`**

  <span data-ttu-id="5ecf6-177">Aktiviert den Diagnosemodus für die Testplattform und schreibt Diagnosemeldungen in die angegebene Datei sowie in benachbarte Dateien.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-177">Enables diagnostic mode for the test platform and writes diagnostic messages to the specified file and to files next to it.</span></span> <span data-ttu-id="5ecf6-178">Der Prozess, der die Meldungen protokolliert, bestimmt, welche Dateien erstellt werden, z. B. `*.host_<date>.txt` für das Testhostprotokoll und `*.datacollector_<date>.txt` für das Datensammlerprotokoll.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-178">The process that is logging the messages determines which files are created, such as `*.host_<date>.txt` for test host log, and `*.datacollector_<date>.txt` for data collector log.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="5ecf6-179">Erzwingt die Verwendung von `dotnet` oder des .NET Framework-Testhosts für die Testbinärdateien.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-179">Forces the use of `dotnet` or .NET Framework test host for the test binaries.</span></span> <span data-ttu-id="5ecf6-180">Mit dieser Option wird nur der zu verwendende Hosttyp bestimmt.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-180">This option only determines which type of host to use.</span></span> <span data-ttu-id="5ecf6-181">Die tatsächliche zu verwendende Frameworkversion wird durch die *runtimeconfig.json* des Testprojekts bestimmt.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-181">The actual framework version to be used is determined by the *runtimeconfig.json* of the test project.</span></span> <span data-ttu-id="5ecf6-182">Wenn nichts angegeben ist, wird das [TargetFramework-Assemblyattribut](/dotnet/api/system.runtime.versioning.targetframeworkattribute) verwendet, um den Hosttyp zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-182">When not specified, the [TargetFramework assembly attribute](/dotnet/api/system.runtime.versioning.targetframeworkattribute) is used to determine the type of host.</span></span> <span data-ttu-id="5ecf6-183">Wenn dieses Attribut von der *DLL* entfernt wird, wird der .NET Framework-Host verwendet.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-183">When that attribute is stripped from the *.dll*, the .NET Framework host is used.</span></span>

- **`--filter <EXPRESSION>`**

  <span data-ttu-id="5ecf6-184">Filtert Tests im aktuellen Projekt mithilfe des angegebenen Ausdrucks heraus.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-184">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="5ecf6-185">Weitere Informationen finden Sie im Abschnitt [Details zu Filteroptionen](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="5ecf6-185">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="5ecf6-186">Weitere Informationen und Beispiele zur Verwendung von selektiven Komponententestfiltern finden Sie unter [Ausführen von selektiven Komponententests](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="5ecf6-186">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

- **`-h|--help`**

  <span data-ttu-id="5ecf6-187">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-187">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="5ecf6-188">Ermöglicht dem Befehl, anzuhalten und auf Benutzereingaben oder Aktionen zu warten.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-188">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="5ecf6-189">Beispielsweise, um die Authentifizierung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-189">For example, to complete authentication.</span></span> <span data-ttu-id="5ecf6-190">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-190">Available since .NET Core 3.0 SDK.</span></span>

- **`-l|--logger <LOGGER>`**

  <span data-ttu-id="5ecf6-191">Gibt eine Protokollierung für die Testergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-191">Specifies a logger for test results.</span></span> <span data-ttu-id="5ecf6-192">Im Gegensatz zu MSBuild akzeptiert der Befehl „dotnet test“ keine Abkürzungen: verwenden Sie `-l "console;verbosity=detailed"` anstelle von `-l "console;v=d"`.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-192">Unlike MSBuild, dotnet test doesn't accept abbreviations: instead of `-l "console;v=d"` use `-l "console;verbosity=detailed"`.</span></span>

- **`--no-build`**

  <span data-ttu-id="5ecf6-193">Erstellt das Projekt nicht vor der Ausführung.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-193">Doesn't build the test project before running it.</span></span> <span data-ttu-id="5ecf6-194">Zudem wird das Flag `--no-restore` implizit festgelegt.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-194">It also implicitly sets the - `--no-restore` flag.</span></span>

- **`--nologo`**

  <span data-ttu-id="5ecf6-195">Führen Sie Tests aus, ohne das Microsoft TestPlatform-Banner anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-195">Run tests without displaying the Microsoft TestPlatform banner.</span></span> <span data-ttu-id="5ecf6-196">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-196">Available since .NET Core 3.0 SDK.</span></span>

- **`--no-restore`**

  <span data-ttu-id="5ecf6-197">Führt keine implizite Wiederherstellung aus, wenn der Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-197">Doesn't execute an implicit restore when running the command.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="5ecf6-198">Verzeichnis, in dem die auszuführenden Binärdateien zu finden sind.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-198">Directory in which to find the binaries to run.</span></span> <span data-ttu-id="5ecf6-199">Wenn nicht angegeben, ist der Standardpfad `./bin/<configuration>/<framework>/`.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-199">If not specified, the default path is `./bin/<configuration>/<framework>/`.</span></span>  <span data-ttu-id="5ecf6-200">Bei Projekten mit mehreren Zielframeworks (über die `TargetFrameworks`-Eigenschaft) müssen Sie auch `--framework` definieren, wenn Sie diese Option angeben.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-200">For projects with multiple target frameworks (via the `TargetFrameworks` property), you also need to define `--framework` when you specify this option.</span></span> <span data-ttu-id="5ecf6-201">`dotnet test` führt Tests immer über das Ausgabeverzeichnis aus.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-201">`dotnet test` always runs tests from the output directory.</span></span> <span data-ttu-id="5ecf6-202">Sie können <xref:System.AppDomain.BaseDirectory%2A?displayProperty=nameWithType> verwenden, um die Testobjekte im Ausgabeverzeichnis zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-202">You can use <xref:System.AppDomain.BaseDirectory%2A?displayProperty=nameWithType> to consume test assets in the output directory.</span></span>

- **`-r|--results-directory <RESULTS_DIR>`**

  <span data-ttu-id="5ecf6-203">Das Verzeichnis, in dem die Testergebnisse gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-203">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="5ecf6-204">Wenn das Verzeichnis noch nicht vorhanden ist, wird es erstellt.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-204">If the specified directory doesn't exist, it's created.</span></span> <span data-ttu-id="5ecf6-205">Der Standardwert ist `TestResults` in dem Verzeichnis, das die Projektdatei enthält.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-205">The default is `TestResults` in the directory that contains the project file.</span></span>

- **`--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="5ecf6-206">Die Zielruntime, für die Tests ausgeführt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-206">The target runtime to test for.</span></span>

- **`-s|--settings <SETTINGS_FILE>`**

  <span data-ttu-id="5ecf6-207">Die `.runsettings`-Datei, die zum Ausführen der Tests verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-207">The `.runsettings` file to use for running the tests.</span></span> <span data-ttu-id="5ecf6-208">Das `TargetPlatform`-Element (x86|x64) hat keine Auswirkung auf `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-208">The `TargetPlatform` element (x86|x64) has no effect for `dotnet test`.</span></span> <span data-ttu-id="5ecf6-209">Installieren Sie die x86-Version von .NET Core, um x86-Tests auszuführen.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-209">To run tests that target x86, install the x86 version of .NET Core.</span></span> <span data-ttu-id="5ecf6-210">Die Bitanzahl der Datei *dotnet.exe*, die sich in diesem Pfad befindet, wird zum Ausführen von Tests verwendet.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-210">The bitness of the *dotnet.exe* that is on the path is what will be used for running tests.</span></span> <span data-ttu-id="5ecf6-211">Weitere Informationen finden Sie in den folgenden Ressourcen:</span><span class="sxs-lookup"><span data-stu-id="5ecf6-211">For more information, see the following resources:</span></span>

  - [<span data-ttu-id="5ecf6-212">Konfigurieren von Komponententests mithilfe einer `.runsettings`-Datei.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-212">Configure unit tests by using a `.runsettings` file.</span></span>](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file)
  - [<span data-ttu-id="5ecf6-213">Konfigurieren eines Testlaufs</span><span class="sxs-lookup"><span data-stu-id="5ecf6-213">Configure a test run</span></span>](https://github.com/Microsoft/vstest-docs/blob/master/docs/configure.md)

- **`-t|--list-tests`**

  <span data-ttu-id="5ecf6-214">Hiermit werden die gefundenen Tests aufgelistet, anstatt sie auszuführen.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-214">List the discovered tests instead of running the tests.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="5ecf6-215">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-215">Sets the verbosity level of the command.</span></span> <span data-ttu-id="5ecf6-216">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-216">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="5ecf6-217">Der Standardwert ist `minimal`.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-217">The default is `minimal`.</span></span> <span data-ttu-id="5ecf6-218">Weitere Informationen finden Sie unter <xref:Microsoft.Build.Framework.LoggerVerbosity>.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-218">For more information, see <xref:Microsoft.Build.Framework.LoggerVerbosity>.</span></span>

- <span data-ttu-id="5ecf6-219">**`RunSettings`** -Argumente</span><span class="sxs-lookup"><span data-stu-id="5ecf6-219">**`RunSettings`** arguments</span></span>

 <span data-ttu-id="5ecf6-220">Inline-`RunSettings` werden als die letzten Argumente auf der Befehlszeile nach „-- “ (beachten Sie das Leerzeichen hinter „--“) übergeben.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-220">Inline `RunSettings` are passed as the last arguments on the command line after "-- " (note the space after --).</span></span> <span data-ttu-id="5ecf6-221">Inline-`RunSettings` werden als `[name]=[value]`-Paare angegeben.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-221">Inline `RunSettings` are specified as `[name]=[value]` pairs.</span></span> <span data-ttu-id="5ecf6-222">Ein Leerzeichen wird verwendet, um mehrere `[name]=[value]`-Paare voneinander zu trennen.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-222">A space is used to separate multiple `[name]=[value]` pairs.</span></span>

  <span data-ttu-id="5ecf6-223">Ein Beispiel: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span><span class="sxs-lookup"><span data-stu-id="5ecf6-223">Example: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span></span>

  <span data-ttu-id="5ecf6-224">Weitere Informationen finden Sie unter [Übergeben von RunSettings-Argumenten über die Befehlszeile](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).</span><span class="sxs-lookup"><span data-stu-id="5ecf6-224">For more information, see [Passing RunSettings arguments through command line](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).</span></span>

## <a name="examples"></a><span data-ttu-id="5ecf6-225">Beispiele</span><span class="sxs-lookup"><span data-stu-id="5ecf6-225">Examples</span></span>

- <span data-ttu-id="5ecf6-226">Führen Sie die Tests im Projekt im aktuellen Verzeichnis durch:</span><span class="sxs-lookup"><span data-stu-id="5ecf6-226">Run the tests in the project in the current directory:</span></span>

  ```dotnetcli
  dotnet test
  ```

- <span data-ttu-id="5ecf6-227">Führen Sie die Tests im Projekt `test1` durch:</span><span class="sxs-lookup"><span data-stu-id="5ecf6-227">Run the tests in the `test1` project:</span></span>

  ```dotnetcli
  dotnet test ~/projects/test1/test1.csproj
  ```

- <span data-ttu-id="5ecf6-228">Mit dem folgenden Befehl führen Sie die Tests im aktuellen Verzeichnis aus und generieren eine Testergebnisdatei im TRX-Format:</span><span class="sxs-lookup"><span data-stu-id="5ecf6-228">Run the tests in the project in the current directory, and generate a test results file in the trx format:</span></span>

  ```dotnetcli
  dotnet test --logger trx
  ```

- <span data-ttu-id="5ecf6-229">Führen Sie die Tests im Projekt im aktuellen Verzeichnis aus, und generieren Sie eine Code-Coverage-Datei (nach der Installation der Integration von [Coverlet](https://github.com/coverlet-coverage/coverlet/blob/master/Documentation/VSTestIntegration.md)-Collectors):</span><span class="sxs-lookup"><span data-stu-id="5ecf6-229">Run the tests in the project in the current directory, and generate a code coverage file (after installing [Coverlet](https://github.com/coverlet-coverage/coverlet/blob/master/Documentation/VSTestIntegration.md) collectors integration):</span></span>

  ```dotnetcli
  dotnet test --collect:"XPlat Code Coverage"
  ```

- <span data-ttu-id="5ecf6-230">Führen Sie die Tests im Projekt im aktuellen Verzeichnis aus, und generieren Sie eine Code Coverage-Datei (nur Windows):</span><span class="sxs-lookup"><span data-stu-id="5ecf6-230">Run the tests in the project in the current directory, and generate a code coverage file (Windows only):</span></span>

  ```dotnetcli
  dotnet test --collect "Code Coverage"
  ```

- <span data-ttu-id="5ecf6-231">Mit dem folgenden Befehl führen Sie die Tests im aktuellen Verzeichnis aus und erstellen ein ausführliches Protokoll in der Konsole:</span><span class="sxs-lookup"><span data-stu-id="5ecf6-231">Run the tests in the project in the current directory, and log with detailed verbosity to the console:</span></span>

  ```dotnetcli
  dotnet test --logger "console;verbosity=detailed"
  ```

- <span data-ttu-id="5ecf6-232">Mit dem folgenden Befehl führen Sie die Tests in dem Projekt im aktuellen Verzeichnis aus und melden Tests, die während des Absturzes des Testhosts in Arbeit waren:</span><span class="sxs-lookup"><span data-stu-id="5ecf6-232">Run the tests in the project in the current directory, and report tests that were in progress when the test host crashed:</span></span>

  ```dotnetcli
  dotnet test --blame
  ```

## <a name="filter-option-details"></a><span data-ttu-id="5ecf6-233">Details zu Filteroptionen</span><span class="sxs-lookup"><span data-stu-id="5ecf6-233">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="5ecf6-234">`<Expression>` weist das Format `<property><operator><value>[|&<Expression>]` auf.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-234">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="5ecf6-235">`<property>` ist ein Attribut von `Test Case`.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-235">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="5ecf6-236">Im Folgenden werden die Eigenschaften aufgeführt, die von gängigen Frameworks für Komponententests unterstützt werden:</span><span class="sxs-lookup"><span data-stu-id="5ecf6-236">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="5ecf6-237">Testframework</span><span class="sxs-lookup"><span data-stu-id="5ecf6-237">Test Framework</span></span> | <span data-ttu-id="5ecf6-238">Unterstützte Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="5ecf6-238">Supported properties</span></span>                                                                                      |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="5ecf6-239">MSTest</span><span class="sxs-lookup"><span data-stu-id="5ecf6-239">MSTest</span></span>         | <ul><li><span data-ttu-id="5ecf6-240">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="5ecf6-240">FullyQualifiedName</span></span></li><li><span data-ttu-id="5ecf6-241">name</span><span class="sxs-lookup"><span data-stu-id="5ecf6-241">Name</span></span></li><li><span data-ttu-id="5ecf6-242">ClassName</span><span class="sxs-lookup"><span data-stu-id="5ecf6-242">ClassName</span></span></li><li><span data-ttu-id="5ecf6-243">Priorität</span><span class="sxs-lookup"><span data-stu-id="5ecf6-243">Priority</span></span></li><li><span data-ttu-id="5ecf6-244">TestCategory</span><span class="sxs-lookup"><span data-stu-id="5ecf6-244">TestCategory</span></span></li></ul> |
| <span data-ttu-id="5ecf6-245">xUnit</span><span class="sxs-lookup"><span data-stu-id="5ecf6-245">xUnit</span></span>          | <ul><li><span data-ttu-id="5ecf6-246">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="5ecf6-246">FullyQualifiedName</span></span></li><li><span data-ttu-id="5ecf6-247">DisplayName</span><span class="sxs-lookup"><span data-stu-id="5ecf6-247">DisplayName</span></span></li><li><span data-ttu-id="5ecf6-248">Merkmale</span><span class="sxs-lookup"><span data-stu-id="5ecf6-248">Traits</span></span></li></ul>                                   |
| <span data-ttu-id="5ecf6-249">NUnit</span><span class="sxs-lookup"><span data-stu-id="5ecf6-249">NUnit</span></span>          | <ul><li><span data-ttu-id="5ecf6-250">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="5ecf6-250">FullyQualifiedName</span></span></li><li><span data-ttu-id="5ecf6-251">name</span><span class="sxs-lookup"><span data-stu-id="5ecf6-251">Name</span></span></li><li><span data-ttu-id="5ecf6-252">TestCategory</span><span class="sxs-lookup"><span data-stu-id="5ecf6-252">TestCategory</span></span></li><li><span data-ttu-id="5ecf6-253">Priorität</span><span class="sxs-lookup"><span data-stu-id="5ecf6-253">Priority</span></span></li></ul>                                   |

<span data-ttu-id="5ecf6-254">`<operator>` beschreibt die Beziehung zwischen der Eigenschaft und dem Wert:</span><span class="sxs-lookup"><span data-stu-id="5ecf6-254">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="5ecf6-255">Operator</span><span class="sxs-lookup"><span data-stu-id="5ecf6-255">Operator</span></span> | <span data-ttu-id="5ecf6-256">Funktion</span><span class="sxs-lookup"><span data-stu-id="5ecf6-256">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="5ecf6-257">Genaue Übereinstimmung</span><span class="sxs-lookup"><span data-stu-id="5ecf6-257">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="5ecf6-258">Keine genaue Übereinstimmung</span><span class="sxs-lookup"><span data-stu-id="5ecf6-258">Not exact match</span></span> |
| `~`      | <span data-ttu-id="5ecf6-259">Enthält</span><span class="sxs-lookup"><span data-stu-id="5ecf6-259">Contains</span></span>        |
| `!~`     | <span data-ttu-id="5ecf6-260">Enthält nicht</span><span class="sxs-lookup"><span data-stu-id="5ecf6-260">Not contains</span></span>    |

<span data-ttu-id="5ecf6-261">`<value>` ist eine Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-261">`<value>` is a string.</span></span> <span data-ttu-id="5ecf6-262">Bei allen Suchvorgängen ist die Groß-/Kleinschreibung nicht relevant.</span><span class="sxs-lookup"><span data-stu-id="5ecf6-262">All the lookups are case insensitive.</span></span>

<span data-ttu-id="5ecf6-263">Ein Ausdruck ohne `<operator>` gilt automatisch als `contains` für die `FullyQualifiedName`-Eigenschaft (`dotnet test --filter xyz` ist beispielsweise identisch mit `dotnet test --filter FullyQualifiedName~xyz`).</span><span class="sxs-lookup"><span data-stu-id="5ecf6-263">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="5ecf6-264">Ausdrücke können mit bedingten Operatoren verknüpft werden:</span><span class="sxs-lookup"><span data-stu-id="5ecf6-264">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="5ecf6-265">Operator</span><span class="sxs-lookup"><span data-stu-id="5ecf6-265">Operator</span></span>            | <span data-ttu-id="5ecf6-266">Funktion</span><span class="sxs-lookup"><span data-stu-id="5ecf6-266">Function</span></span> |
| ------------------- | -------- |
| <code>&#124;</code> | <span data-ttu-id="5ecf6-267">ODER</span><span class="sxs-lookup"><span data-stu-id="5ecf6-267">OR</span></span>       |
| `&`                 | <span data-ttu-id="5ecf6-268">UND</span><span class="sxs-lookup"><span data-stu-id="5ecf6-268">AND</span></span>      |

<span data-ttu-id="5ecf6-269">Sie können Ausdrücke in Klammern einschließen, wenn Sie bedingte Operatoren verwenden (z.B. `(Name~TestMethod1) | (Name~TestMethod2)`).</span><span class="sxs-lookup"><span data-stu-id="5ecf6-269">You can enclose expressions in parenthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="5ecf6-270">Weitere Informationen und Beispiele zur Verwendung von selektiven Komponententestfiltern finden Sie unter [Ausführen von selektiven Komponententests](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="5ecf6-270">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5ecf6-271">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5ecf6-271">See also</span></span>

- [<span data-ttu-id="5ecf6-272">Frameworks und Ziele</span><span class="sxs-lookup"><span data-stu-id="5ecf6-272">Frameworks and Targets</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="5ecf6-273">.NET-Runtime-ID-Katalog (RID)</span><span class="sxs-lookup"><span data-stu-id="5ecf6-273">.NET Runtime Identifier (RID) catalog</span></span>](../rid-catalog.md)
- [<span data-ttu-id="5ecf6-274">Übergeben von runsettings-Argumenten über die Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="5ecf6-274">Passing runsettings arguments through commandline</span></span>](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md)
