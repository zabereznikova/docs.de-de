---
title: Befehl „dotnet vstest“
description: Der dotnet vstest-Befehl erstellt ein Projekt und alle seine Abhängigkeiten.
ms.date: 02/27/2020
ms.openlocfilehash: e8fa94cf12ca2fe5fb99c6e3c1dcdb52185798c0
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463285"
---
# <a name="dotnet-vstest"></a><span data-ttu-id="284f6-103">dotnet vstest</span><span class="sxs-lookup"><span data-stu-id="284f6-103">dotnet vstest</span></span>

<span data-ttu-id="284f6-104">**Dieser Artikel gilt für:** ✔️ .NET Core 2.1 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="284f6-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="284f6-105">name</span><span class="sxs-lookup"><span data-stu-id="284f6-105">Name</span></span>

<span data-ttu-id="284f6-106">`dotnet-vstest`: Führt Tests auf Grundlage der angegebenen Dateien aus.</span><span class="sxs-lookup"><span data-stu-id="284f6-106">`dotnet-vstest` - Runs tests from the specified files.</span></span>

## <a name="synopsis"></a><span data-ttu-id="284f6-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="284f6-107">Synopsis</span></span>

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

## <a name="description"></a><span data-ttu-id="284f6-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="284f6-108">Description</span></span>

<span data-ttu-id="284f6-109">Der `dotnet-vstest`-Befehl führt die `VSTest.Console`-Befehlszeilenanwendung aus, um automatisierte Komponententests auszuführen.</span><span class="sxs-lookup"><span data-stu-id="284f6-109">The `dotnet-vstest` command runs the `VSTest.Console` command-line application to run automated unit tests.</span></span>

## <a name="arguments"></a><span data-ttu-id="284f6-110">Argumente</span><span class="sxs-lookup"><span data-stu-id="284f6-110">Arguments</span></span>

- **`TEST_FILE_NAMES`**

  <span data-ttu-id="284f6-111">Führt Tests auf Grundlage der angegebenen Assemblys aus.</span><span class="sxs-lookup"><span data-stu-id="284f6-111">Run tests from the specified assemblies.</span></span> <span data-ttu-id="284f6-112">Trennt mehrere Test-Assemblynamen durch Leerzeichen.</span><span class="sxs-lookup"><span data-stu-id="284f6-112">Separate multiple test assembly names with spaces.</span></span> <span data-ttu-id="284f6-113">Platzhalter werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="284f6-113">Wildcards are supported.</span></span>

## <a name="options"></a><span data-ttu-id="284f6-114">Optionen</span><span class="sxs-lookup"><span data-stu-id="284f6-114">Options</span></span>

- **`--Blame`**

  <span data-ttu-id="284f6-115">Führt die Tests im blame-Modus aus.</span><span class="sxs-lookup"><span data-stu-id="284f6-115">Runs the tests in blame mode.</span></span> <span data-ttu-id="284f6-116">Diese Option hilft beim Isolieren der fehlerhaften Tests, die den Absturz des Testhosts verursachen.</span><span class="sxs-lookup"><span data-stu-id="284f6-116">This option is helpful in isolating the problematic tests causing test host to crash.</span></span> <span data-ttu-id="284f6-117">In dem aktuellen Verzeichnis wird eine Ausgabedatei als *Sequence.xml* erstellt, die die Reihenfolge der ausgeführten Tests vor dem Absturz erfasst.</span><span class="sxs-lookup"><span data-stu-id="284f6-117">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

- **`--Diag <PATH_TO_LOG_FILE>`**

  <span data-ttu-id="284f6-118">Aktiviert die ausführlichen Protokolle für die Testplattform.</span><span class="sxs-lookup"><span data-stu-id="284f6-118">Enables verbose logs for the test platform.</span></span> <span data-ttu-id="284f6-119">Protokolle werden in die angegebene Datei geschrieben.</span><span class="sxs-lookup"><span data-stu-id="284f6-119">Logs are written to the provided file.</span></span>

- **`--Framework <FRAMEWORK>`**

  <span data-ttu-id="284f6-120">.NET Framework-Zielversion, in der der Test ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="284f6-120">Target .NET Framework version used for test execution.</span></span> <span data-ttu-id="284f6-121">`.NETFramework,Version=v4.6` und `.NETCoreApp,Version=v1.0` sind Beispiele für gültige Werte.</span><span class="sxs-lookup"><span data-stu-id="284f6-121">Examples of valid values are `.NETFramework,Version=v4.6` or `.NETCoreApp,Version=v1.0`.</span></span> <span data-ttu-id="284f6-122">Andere unterstützte Werte sind `Framework40`, `Framework45`, `FrameworkCore10` und `FrameworkUap10`.</span><span class="sxs-lookup"><span data-stu-id="284f6-122">Other supported values are `Framework40`, `Framework45`, `FrameworkCore10`, and `FrameworkUap10`.</span></span>

- **`--InIsolation`**

  <span data-ttu-id="284f6-123">Führt die Tests in einem isolierten Prozess aus.</span><span class="sxs-lookup"><span data-stu-id="284f6-123">Runs the tests in an isolated process.</span></span> <span data-ttu-id="284f6-124">Dadurch ist die Wahrscheinlichkeit, dass der *vstest.console.exe*-Prozess bei Testfehlern beendet wird, weniger hoch, die Tests werden jedoch möglicherweise langsamer ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="284f6-124">This makes *vstest.console.exe* process less likely to be stopped on an error in the tests, but tests may run slower.</span></span>

- **`-lt|--ListTests <FILE_NAME>`**

  <span data-ttu-id="284f6-125">Listet alle gefundenen Tests aus dem angegebenen Testcontainer auf.</span><span class="sxs-lookup"><span data-stu-id="284f6-125">Lists all discovered tests from the given test container.</span></span>

- **`--logger <LOGGER_URI/FRIENDLY_NAME>`**

  <span data-ttu-id="284f6-126">Geben Sie eine Protokollierung für die Testergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="284f6-126">Specify a logger for test results.</span></span>

  - <span data-ttu-id="284f6-127">Verwenden Sie den `TfsPublisher`-Protokollierungsanbieter zum Veröffentlichen von Testergebnissen in Team Foundation Server:</span><span class="sxs-lookup"><span data-stu-id="284f6-127">To publish test results to Team Foundation Server, use the `TfsPublisher` logger provider:</span></span>

    ```console
    /logger:TfsPublisher;
        Collection=<team project collection url>;
        BuildName=<build name>;
        TeamProject=<team project name>
        [;Platform=<Defaults to "Any CPU">]
        [;Flavor=<Defaults to "Debug">]
        [;RunTitle=<title>]
    ```

  - <span data-ttu-id="284f6-128">Verwenden Sie zum Protokollieren von Ergebnissen in einer Visual Studio-Testergebnisdatei (TRX) den `trx`-Protokollierungsanbieter.</span><span class="sxs-lookup"><span data-stu-id="284f6-128">To log results to a Visual Studio Test Results File (TRX), use the `trx` logger provider.</span></span> <span data-ttu-id="284f6-129">Dieser Schalter erstellt eine Datei im Verzeichnis mit den Testergebnissen mit dem angegebenen Protokolldateinamen.</span><span class="sxs-lookup"><span data-stu-id="284f6-129">This switch creates a file in the test results directory with given log file name.</span></span> <span data-ttu-id="284f6-130">Wenn `LogFileName` nicht angegeben wird, wird ein eindeutiger Dateiname erstellt, um die Testergebnisse aufzunehmen.</span><span class="sxs-lookup"><span data-stu-id="284f6-130">If `LogFileName` isn't provided, a unique file name is created to hold the test results.</span></span>

    ```console
    /logger:trx [;LogFileName=<Defaults to unique file name>]
    ```

- **`--Parallel`**

  <span data-ttu-id="284f6-131">Mit dieser Option können Sie Tests parallel ausführen.</span><span class="sxs-lookup"><span data-stu-id="284f6-131">Run tests in parallel.</span></span> <span data-ttu-id="284f6-132">Standardmäßig stehen alle verfügbaren Kerne auf dem Computer zur Nutzung zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="284f6-132">By default, all available cores on the machine are available for use.</span></span> <span data-ttu-id="284f6-133">Geben Sie eine explizite Anzahl von Kernen an, indem Sie die `MaxCpuCount`-Eigenschaft unter dem `RunConfiguration`-Knoten in der Datei *runsettings* festlegen.</span><span class="sxs-lookup"><span data-stu-id="284f6-133">Specify an explicit number of cores by setting the `MaxCpuCount` property under the `RunConfiguration` node in the *runsettings* file.</span></span>

- **`--ParentProcessId <PROCESS_ID>`**

  <span data-ttu-id="284f6-134">Prozess-ID des übergeordneten Prozesses, der für den Start des aktuellen Prozesses verantwortlich ist.</span><span class="sxs-lookup"><span data-stu-id="284f6-134">Process ID of the parent process responsible for launching the current process.</span></span>

- **`--Platform <PLATFORM_TYPE>`**

  <span data-ttu-id="284f6-135">Verwendete Zielplattformarchitektur für die Testausführung.</span><span class="sxs-lookup"><span data-stu-id="284f6-135">Target platform architecture used for test execution.</span></span> <span data-ttu-id="284f6-136">Gültige Werte sind `x86`, `x64` und `ARM`.</span><span class="sxs-lookup"><span data-stu-id="284f6-136">Valid values are `x86`, `x64`, and `ARM`.</span></span>

- **`--Port <PORT>`**

  <span data-ttu-id="284f6-137">Gibt den Port für die Socketverbindung an und empfängt die Ereignismeldungen.</span><span class="sxs-lookup"><span data-stu-id="284f6-137">Specifies the port for the socket connection and receiving the event messages.</span></span>

- **`--ResultsDirectory:<PATH>`**

  <span data-ttu-id="284f6-138">Das Verzeichnis mit den Testergebnissen wird am angegebenen Pfad erstellt, falls es noch nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="284f6-138">Test results directory will be created in specified path if not exists.</span></span>

- **`--Settings <SETTINGS_FILE>`**

  <span data-ttu-id="284f6-139">Einstellungen, die beim Ausführen von Tests verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="284f6-139">Settings to use when running tests.</span></span>

- **`--TestAdapterPath <PATH>`**

  <span data-ttu-id="284f6-140">Verwendet benutzerdefinierte Testadapter aus einem angegebenen Pfad (falls vorhanden) im Testlauf.</span><span class="sxs-lookup"><span data-stu-id="284f6-140">Use custom test adapters from a given path (if any) in the test run.</span></span>

- **`--TestCaseFilter <EXPRESSION>`**

  <span data-ttu-id="284f6-141">Führt Tests aus, die mit dem angegebenen Ausdruck übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="284f6-141">Run tests that match the given expression.</span></span> <span data-ttu-id="284f6-142">`<EXPRESSION>` hat das Format `<property>Operator<value>[|&<EXPRESSION>]`, wobei der Operator `=`, `!=`, oder `~` ist.</span><span class="sxs-lookup"><span data-stu-id="284f6-142">`<EXPRESSION>` is of the format `<property>Operator<value>[|&<EXPRESSION>]`, where Operator is one of `=`, `!=`, or `~`.</span></span> <span data-ttu-id="284f6-143">Operator `~` verfügt über „contains“-Semantik und gilt für Zeichenfolgeneigenschaften wie `DisplayName`.</span><span class="sxs-lookup"><span data-stu-id="284f6-143">Operator `~` has 'contains' semantics and is applicable for string properties like `DisplayName`.</span></span> <span data-ttu-id="284f6-144">Klammern `()` werden zum Gruppieren untergeordneter Ausdrücke verwendet.</span><span class="sxs-lookup"><span data-stu-id="284f6-144">Parentheses `()` are used to group subexpressions.</span></span> <span data-ttu-id="284f6-145">Weitere Informationen finden Sie unter [TestCase-Filter](https://github.com/Microsoft/vstest-docs/blob/master/docs/filter.md).</span><span class="sxs-lookup"><span data-stu-id="284f6-145">For more information, see [TestCase filter](https://github.com/Microsoft/vstest-docs/blob/master/docs/filter.md).</span></span>

- **`--Tests <TEST_NAMES>`**

  <span data-ttu-id="284f6-146">Führt Tests aus, die mit den eingegebenen Werten übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="284f6-146">Run tests with names that match the provided values.</span></span> <span data-ttu-id="284f6-147">Trennt mehrere Werte per Komma voneinander ab.</span><span class="sxs-lookup"><span data-stu-id="284f6-147">Separate multiple values with commas.</span></span>

- **`-?|--Help`**

  <span data-ttu-id="284f6-148">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="284f6-148">Prints out a short help for the command.</span></span>

- **`@<file>`**

  <span data-ttu-id="284f6-149">Liest eine Antwortdatei für mehrere Optionen.</span><span class="sxs-lookup"><span data-stu-id="284f6-149">Reads response file for more options.</span></span>

- **`args`**

  <span data-ttu-id="284f6-150">Gibt zusätzliche Argumente an, die an den Adapter übergeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="284f6-150">Specifies extra arguments to pass to the adapter.</span></span> <span data-ttu-id="284f6-151">Argumente werden als Name-Wert-Paare des Formulars `<n>=<v>` angegeben, wobei `<n>` der Argumentname und `<v>` der Argumentwert ist.</span><span class="sxs-lookup"><span data-stu-id="284f6-151">Arguments are specified as name-value pairs of the form `<n>=<v>`, where `<n>` is the argument name and `<v>` is the argument value.</span></span> <span data-ttu-id="284f6-152">Trennt mehrere Argumente durch Leerzeichen.</span><span class="sxs-lookup"><span data-stu-id="284f6-152">Use a space to separate multiple arguments.</span></span>

## <a name="examples"></a><span data-ttu-id="284f6-153">Beispiele</span><span class="sxs-lookup"><span data-stu-id="284f6-153">Examples</span></span>

<span data-ttu-id="284f6-154">Mit dem folgenden Befehl werden Tests in *mytestproject.dll* ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="284f6-154">Run tests in *mytestproject.dll*:</span></span>

```dotnetcli
dotnet vstest mytestproject.dll
```

<span data-ttu-id="284f6-155">Mit dem folgenden Befehl werden Tests in *mytestproject.dll* ausgeführt und in einen benutzerdefinierten Ordner mit benutzerdefiniertem Namen exportiert:</span><span class="sxs-lookup"><span data-stu-id="284f6-155">Run tests in *mytestproject.dll*, exporting to custom folder with custom name:</span></span>

```dotnetcli
dotnet vstest mytestproject.dll --logger:"trx;LogFileName=custom_file_name.trx" --ResultsDirectory:custom/file/path
```

<span data-ttu-id="284f6-156">Mit dem folgenden Befehl werden Tests in *mytestproject.dll* und *myothertestproject.exe* ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="284f6-156">Run tests in *mytestproject.dll* and *myothertestproject.exe*:</span></span>

```dotnetcli
dotnet vstest mytestproject.dll myothertestproject.exe
```

<span data-ttu-id="284f6-157">Führt `TestMethod1`-Tests aus:</span><span class="sxs-lookup"><span data-stu-id="284f6-157">Run `TestMethod1` tests:</span></span>

```dotnetcli
dotnet vstest /Tests:TestMethod1
```

<span data-ttu-id="284f6-158">Führt `TestMethod1`- und `TestMethod2`-Tests aus:</span><span class="sxs-lookup"><span data-stu-id="284f6-158">Run `TestMethod1` and `TestMethod2` tests:</span></span>

```dotnetcli
dotnet vstest /Tests:TestMethod1,TestMethod2
```

## <a name="see-also"></a><span data-ttu-id="284f6-159">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="284f6-159">See also</span></span>

- [<span data-ttu-id="284f6-160">Befehlszeilenoptionen für VSTest.Console.exe</span><span class="sxs-lookup"><span data-stu-id="284f6-160">VSTest.Console.exe command-line options</span></span>](/visualstudio/test/vstest-console-options)
