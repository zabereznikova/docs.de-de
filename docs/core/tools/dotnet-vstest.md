---
title: Befehl „dotnet vstest“
description: Der dotnet vstest-Befehl erstellt ein Projekt und alle seine Abhängigkeiten.
ms.date: 02/27/2020
ms.openlocfilehash: f7db58f4aab59354b8c69ce0371324c23482dafe
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2020
ms.locfileid: "82975393"
---
# <a name="dotnet-vstest"></a><span data-ttu-id="cb55b-103">dotnet vstest</span><span class="sxs-lookup"><span data-stu-id="cb55b-103">dotnet vstest</span></span>

<span data-ttu-id="cb55b-104">**Dieser Artikel gilt für:** ✔️ .NET Core 2.1 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="cb55b-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cb55b-105">Der Befehl `dotnet vstest` wird von `dotnet test` abgelöst, der nun zum Ausführen von Assemblys verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="cb55b-105">The `dotnet vstest` command is superseded by `dotnet test`, which can now be used to run assemblies.</span></span> <span data-ttu-id="cb55b-106">Weitere Informationen finden Sie unter [`dotnet test`](dotnet-test.md).</span><span class="sxs-lookup"><span data-stu-id="cb55b-106">See [`dotnet test`](dotnet-test.md).</span></span>

## <a name="name"></a><span data-ttu-id="cb55b-107">name</span><span class="sxs-lookup"><span data-stu-id="cb55b-107">Name</span></span>

<span data-ttu-id="cb55b-108">`dotnet-vstest`: Führt Tests auf Grundlage der angegebenen Assemblys aus.</span><span class="sxs-lookup"><span data-stu-id="cb55b-108">`dotnet-vstest` - Runs tests from the specified assemblies.</span></span>

## <a name="synopsis"></a><span data-ttu-id="cb55b-109">Übersicht</span><span class="sxs-lookup"><span data-stu-id="cb55b-109">Synopsis</span></span>

```dotnetcli
dotnet vstest [<TEST_FILE_NAMES>] [--Blame] [--Diag <PATH_TO_LOG_FILE>]
    [--Framework <FRAMEWORK>] [--InIsolation] [-lt|--ListTests <FILE_NAME>]
    [--logger <LOGGER_URI/FRIENDLY_NAME>] [--Parallel]
    [--ParentProcessId <PROCESS_ID>] [--Platform] <PLATFORM_TYPE>
    [--Port <PORT>] [--ResultsDirectory<PATH>] [--Settings <SETTINGS_FILE>]
    [--TestAdapterPath <PATH>] [--TestCaseFilter <EXPRESSION>]
    [--Tests <TEST_NAMES>] [[--] <args>...]]

dotnet vstest -?|--Help
```

## <a name="description"></a><span data-ttu-id="cb55b-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cb55b-110">Description</span></span>

<span data-ttu-id="cb55b-111">Der `dotnet-vstest`-Befehl führt die `VSTest.Console`-Befehlszeilenanwendung aus, um automatisierte Komponententests auszuführen.</span><span class="sxs-lookup"><span data-stu-id="cb55b-111">The `dotnet-vstest` command runs the `VSTest.Console` command-line application to run automated unit tests.</span></span>

## <a name="arguments"></a><span data-ttu-id="cb55b-112">Argumente</span><span class="sxs-lookup"><span data-stu-id="cb55b-112">Arguments</span></span>

- **`TEST_FILE_NAMES`**

  <span data-ttu-id="cb55b-113">Führt Tests auf Grundlage der angegebenen Assemblys aus.</span><span class="sxs-lookup"><span data-stu-id="cb55b-113">Run tests from the specified assemblies.</span></span> <span data-ttu-id="cb55b-114">Trennt mehrere Test-Assemblynamen durch Leerzeichen.</span><span class="sxs-lookup"><span data-stu-id="cb55b-114">Separate multiple test assembly names with spaces.</span></span> <span data-ttu-id="cb55b-115">Platzhalter werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="cb55b-115">Wildcards are supported.</span></span>

## <a name="options"></a><span data-ttu-id="cb55b-116">Optionen</span><span class="sxs-lookup"><span data-stu-id="cb55b-116">Options</span></span>

- **`--Blame`**

  <span data-ttu-id="cb55b-117">Führt die Tests im blame-Modus aus.</span><span class="sxs-lookup"><span data-stu-id="cb55b-117">Runs the tests in blame mode.</span></span> <span data-ttu-id="cb55b-118">Diese Option hilft beim Isolieren der fehlerhaften Tests, die den Absturz des Testhosts verursachen.</span><span class="sxs-lookup"><span data-stu-id="cb55b-118">This option is helpful in isolating the problematic tests causing test host to crash.</span></span> <span data-ttu-id="cb55b-119">In dem aktuellen Verzeichnis wird eine Ausgabedatei als *Sequence.xml* erstellt, die die Reihenfolge der ausgeführten Tests vor dem Absturz erfasst.</span><span class="sxs-lookup"><span data-stu-id="cb55b-119">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

- **`--Diag <PATH_TO_LOG_FILE>`**

  <span data-ttu-id="cb55b-120">Aktiviert die ausführlichen Protokolle für die Testplattform.</span><span class="sxs-lookup"><span data-stu-id="cb55b-120">Enables verbose logs for the test platform.</span></span> <span data-ttu-id="cb55b-121">Protokolle werden in die angegebene Datei geschrieben.</span><span class="sxs-lookup"><span data-stu-id="cb55b-121">Logs are written to the provided file.</span></span>

- **`--Framework <FRAMEWORK>`**

  <span data-ttu-id="cb55b-122">.NET Framework-Zielversion, in der der Test ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="cb55b-122">Target .NET Framework version used for test execution.</span></span> <span data-ttu-id="cb55b-123">`.NETFramework,Version=v4.6` und `.NETCoreApp,Version=v1.0` sind Beispiele für gültige Werte.</span><span class="sxs-lookup"><span data-stu-id="cb55b-123">Examples of valid values are `.NETFramework,Version=v4.6` or `.NETCoreApp,Version=v1.0`.</span></span> <span data-ttu-id="cb55b-124">Andere unterstützte Werte sind `Framework40`, `Framework45`, `FrameworkCore10` und `FrameworkUap10`.</span><span class="sxs-lookup"><span data-stu-id="cb55b-124">Other supported values are `Framework40`, `Framework45`, `FrameworkCore10`, and `FrameworkUap10`.</span></span>

- **`--InIsolation`**

  <span data-ttu-id="cb55b-125">Führt die Tests in einem isolierten Prozess aus.</span><span class="sxs-lookup"><span data-stu-id="cb55b-125">Runs the tests in an isolated process.</span></span> <span data-ttu-id="cb55b-126">Dadurch ist die Wahrscheinlichkeit, dass der *vstest.console.exe*-Prozess bei Testfehlern beendet wird, weniger hoch, die Tests werden jedoch möglicherweise langsamer ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="cb55b-126">This makes *vstest.console.exe* process less likely to be stopped on an error in the tests, but tests may run slower.</span></span>

- **`-lt|--ListTests <FILE_NAME>`**

  <span data-ttu-id="cb55b-127">Listet alle gefundenen Tests aus dem angegebenen Testcontainer auf.</span><span class="sxs-lookup"><span data-stu-id="cb55b-127">Lists all discovered tests from the given test container.</span></span>

- **`--logger <LOGGER_URI/FRIENDLY_NAME>`**

  <span data-ttu-id="cb55b-128">Geben Sie eine Protokollierung für die Testergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="cb55b-128">Specify a logger for test results.</span></span>

  - <span data-ttu-id="cb55b-129">Verwenden Sie den `TfsPublisher`-Protokollierungsanbieter zum Veröffentlichen von Testergebnissen in Team Foundation Server:</span><span class="sxs-lookup"><span data-stu-id="cb55b-129">To publish test results to Team Foundation Server, use the `TfsPublisher` logger provider:</span></span>

    ```console
    /logger:TfsPublisher;
        Collection=<team project collection url>;
        BuildName=<build name>;
        TeamProject=<team project name>
        [;Platform=<Defaults to "Any CPU">]
        [;Flavor=<Defaults to "Debug">]
        [;RunTitle=<title>]
    ```

  - <span data-ttu-id="cb55b-130">Verwenden Sie zum Protokollieren von Ergebnissen in einer Visual Studio-Testergebnisdatei (TRX) den `trx`-Protokollierungsanbieter.</span><span class="sxs-lookup"><span data-stu-id="cb55b-130">To log results to a Visual Studio Test Results File (TRX), use the `trx` logger provider.</span></span> <span data-ttu-id="cb55b-131">Dieser Schalter erstellt eine Datei im Verzeichnis mit den Testergebnissen mit dem angegebenen Protokolldateinamen.</span><span class="sxs-lookup"><span data-stu-id="cb55b-131">This switch creates a file in the test results directory with given log file name.</span></span> <span data-ttu-id="cb55b-132">Wenn `LogFileName` nicht angegeben wird, wird ein eindeutiger Dateiname erstellt, um die Testergebnisse aufzunehmen.</span><span class="sxs-lookup"><span data-stu-id="cb55b-132">If `LogFileName` isn't provided, a unique file name is created to hold the test results.</span></span>

    ```console
    /logger:trx [;LogFileName=<Defaults to unique file name>]
    ```

- **`--Parallel`**

  <span data-ttu-id="cb55b-133">Mit dieser Option können Sie Tests parallel ausführen.</span><span class="sxs-lookup"><span data-stu-id="cb55b-133">Run tests in parallel.</span></span> <span data-ttu-id="cb55b-134">Standardmäßig stehen alle verfügbaren Kerne auf dem Computer zur Nutzung zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="cb55b-134">By default, all available cores on the machine are available for use.</span></span> <span data-ttu-id="cb55b-135">Geben Sie eine explizite Anzahl von Kernen an, indem Sie die `MaxCpuCount`-Eigenschaft unter dem `RunConfiguration`-Knoten in der Datei *runsettings* festlegen.</span><span class="sxs-lookup"><span data-stu-id="cb55b-135">Specify an explicit number of cores by setting the `MaxCpuCount` property under the `RunConfiguration` node in the *runsettings* file.</span></span>

- **`--ParentProcessId <PROCESS_ID>`**

  <span data-ttu-id="cb55b-136">Prozess-ID des übergeordneten Prozesses, der für den Start des aktuellen Prozesses verantwortlich ist.</span><span class="sxs-lookup"><span data-stu-id="cb55b-136">Process ID of the parent process responsible for launching the current process.</span></span>

- **`--Platform <PLATFORM_TYPE>`**

  <span data-ttu-id="cb55b-137">Verwendete Zielplattformarchitektur für die Testausführung.</span><span class="sxs-lookup"><span data-stu-id="cb55b-137">Target platform architecture used for test execution.</span></span> <span data-ttu-id="cb55b-138">Gültige Werte sind `x86`, `x64` und `ARM`.</span><span class="sxs-lookup"><span data-stu-id="cb55b-138">Valid values are `x86`, `x64`, and `ARM`.</span></span>

- **`--Port <PORT>`**

  <span data-ttu-id="cb55b-139">Gibt den Port für die Socketverbindung an und empfängt die Ereignismeldungen.</span><span class="sxs-lookup"><span data-stu-id="cb55b-139">Specifies the port for the socket connection and receiving the event messages.</span></span>

- **`--ResultsDirectory:<PATH>`**

  <span data-ttu-id="cb55b-140">Das Verzeichnis mit den Testergebnissen wird am angegebenen Pfad erstellt, falls es noch nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="cb55b-140">Test results directory will be created in specified path if not exists.</span></span>

- **`--Settings <SETTINGS_FILE>`**

  <span data-ttu-id="cb55b-141">Einstellungen, die beim Ausführen von Tests verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cb55b-141">Settings to use when running tests.</span></span>

- **`--TestAdapterPath <PATH>`**

  <span data-ttu-id="cb55b-142">Verwendet benutzerdefinierte Testadapter aus einem angegebenen Pfad (falls vorhanden) im Testlauf.</span><span class="sxs-lookup"><span data-stu-id="cb55b-142">Use custom test adapters from a given path (if any) in the test run.</span></span>

- **`--TestCaseFilter <EXPRESSION>`**

  <span data-ttu-id="cb55b-143">Führt Tests aus, die mit dem angegebenen Ausdruck übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="cb55b-143">Run tests that match the given expression.</span></span> <span data-ttu-id="cb55b-144">`<EXPRESSION>` hat das Format `<property>Operator<value>[|&<EXPRESSION>]`, wobei der Operator `=`, `!=`, oder `~` ist.</span><span class="sxs-lookup"><span data-stu-id="cb55b-144">`<EXPRESSION>` is of the format `<property>Operator<value>[|&<EXPRESSION>]`, where Operator is one of `=`, `!=`, or `~`.</span></span> <span data-ttu-id="cb55b-145">Operator `~` verfügt über „contains“-Semantik und gilt für Zeichenfolgeneigenschaften wie `DisplayName`.</span><span class="sxs-lookup"><span data-stu-id="cb55b-145">Operator `~` has 'contains' semantics and is applicable for string properties like `DisplayName`.</span></span> <span data-ttu-id="cb55b-146">Klammern `()` werden zum Gruppieren untergeordneter Ausdrücke verwendet.</span><span class="sxs-lookup"><span data-stu-id="cb55b-146">Parentheses `()` are used to group subexpressions.</span></span> <span data-ttu-id="cb55b-147">Weitere Informationen finden Sie unter [TestCase-Filter](https://github.com/Microsoft/vstest-docs/blob/master/docs/filter.md).</span><span class="sxs-lookup"><span data-stu-id="cb55b-147">For more information, see [TestCase filter](https://github.com/Microsoft/vstest-docs/blob/master/docs/filter.md).</span></span>

- **`--Tests <TEST_NAMES>`**

  <span data-ttu-id="cb55b-148">Führt Tests aus, die mit den eingegebenen Werten übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="cb55b-148">Run tests with names that match the provided values.</span></span> <span data-ttu-id="cb55b-149">Trennt mehrere Werte per Komma voneinander ab.</span><span class="sxs-lookup"><span data-stu-id="cb55b-149">Separate multiple values with commas.</span></span>

- **`-?|--Help`**

  <span data-ttu-id="cb55b-150">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="cb55b-150">Prints out a short help for the command.</span></span>

- **`@<file>`**

  <span data-ttu-id="cb55b-151">Liest eine Antwortdatei für mehrere Optionen.</span><span class="sxs-lookup"><span data-stu-id="cb55b-151">Reads response file for more options.</span></span>

- **`args`**

  <span data-ttu-id="cb55b-152">Gibt zusätzliche Argumente an, die an den Adapter übergeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="cb55b-152">Specifies extra arguments to pass to the adapter.</span></span> <span data-ttu-id="cb55b-153">Argumente werden als Name-Wert-Paare des Formulars `<n>=<v>` angegeben, wobei `<n>` der Argumentname und `<v>` der Argumentwert ist.</span><span class="sxs-lookup"><span data-stu-id="cb55b-153">Arguments are specified as name-value pairs of the form `<n>=<v>`, where `<n>` is the argument name and `<v>` is the argument value.</span></span> <span data-ttu-id="cb55b-154">Trennt mehrere Argumente durch Leerzeichen.</span><span class="sxs-lookup"><span data-stu-id="cb55b-154">Use a space to separate multiple arguments.</span></span>

## <a name="examples"></a><span data-ttu-id="cb55b-155">Beispiele</span><span class="sxs-lookup"><span data-stu-id="cb55b-155">Examples</span></span>

<span data-ttu-id="cb55b-156">Mit dem folgenden Befehl werden Tests in *mytestproject.dll* ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="cb55b-156">Run tests in *mytestproject.dll*:</span></span>

```dotnetcli
dotnet vstest mytestproject.dll
```

<span data-ttu-id="cb55b-157">Mit dem folgenden Befehl werden Tests in *mytestproject.dll* ausgeführt und in einen benutzerdefinierten Ordner mit benutzerdefiniertem Namen exportiert:</span><span class="sxs-lookup"><span data-stu-id="cb55b-157">Run tests in *mytestproject.dll*, exporting to custom folder with custom name:</span></span>

```dotnetcli
dotnet vstest mytestproject.dll --logger:"trx;LogFileName=custom_file_name.trx" --ResultsDirectory:custom/file/path
```

<span data-ttu-id="cb55b-158">Mit dem folgenden Befehl werden Tests in *mytestproject.dll* und *myothertestproject.exe* ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="cb55b-158">Run tests in *mytestproject.dll* and *myothertestproject.exe*:</span></span>

```dotnetcli
dotnet vstest mytestproject.dll myothertestproject.exe
```

<span data-ttu-id="cb55b-159">Führt `TestMethod1`-Tests aus:</span><span class="sxs-lookup"><span data-stu-id="cb55b-159">Run `TestMethod1` tests:</span></span>

```dotnetcli
dotnet vstest /Tests:TestMethod1
```

<span data-ttu-id="cb55b-160">Führt `TestMethod1`- und `TestMethod2`-Tests aus:</span><span class="sxs-lookup"><span data-stu-id="cb55b-160">Run `TestMethod1` and `TestMethod2` tests:</span></span>

```dotnetcli
dotnet vstest /Tests:TestMethod1,TestMethod2
```

## <a name="see-also"></a><span data-ttu-id="cb55b-161">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cb55b-161">See also</span></span>

- [<span data-ttu-id="cb55b-162">Befehlszeilenoptionen für VSTest.Console.exe</span><span class="sxs-lookup"><span data-stu-id="cb55b-162">VSTest.Console.exe command-line options</span></span>](/visualstudio/test/vstest-console-options)
