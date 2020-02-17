---
title: Befehl „dotnet vstest“
description: Der dotnet vstest-Befehl erstellt ein Projekt und alle seine Abhängigkeiten.
ms.date: 05/30/2018
ms.openlocfilehash: c3838617ed539cf56f2840b826e9de58833820fd
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215312"
---
# <a name="dotnet-vstest"></a><span data-ttu-id="cec3d-103">dotnet vstest</span><span class="sxs-lookup"><span data-stu-id="cec3d-103">dotnet vstest</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="cec3d-104">name</span><span class="sxs-lookup"><span data-stu-id="cec3d-104">Name</span></span>

<span data-ttu-id="cec3d-105">`dotnet-vstest`: Führt Tests auf Grundlage der angegebenen Dateien aus.</span><span class="sxs-lookup"><span data-stu-id="cec3d-105">`dotnet-vstest` - Runs tests from the specified files.</span></span>

## <a name="synopsis"></a><span data-ttu-id="cec3d-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="cec3d-106">Synopsis</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="cec3d-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="cec3d-107">.NET Core 2.1</span></span>](#tab/netcore21)

```dotnetcli
dotnet vstest [<TEST_FILE_NAMES>] [--Settings|/Settings] [--Tests|/Tests] [--TestAdapterPath|/TestAdapterPath]
    [--Platform|/Platform] [--Framework|/Framework] [--Parallel|/Parallel] [--TestCaseFilter|/TestCaseFilter] [--logger|/logger]
    [-lt|--ListTests|/lt|/ListTests] [--ParentProcessId|/ParentProcessId] [--Port|/Port] [--Diag|/Diag] [--Blame|/Blame] [--InIsolation|/InIsolation]
    [[--] <args>...]] [-?|--Help|/?|/Help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="cec3d-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="cec3d-108">.NET Core 2.0</span></span>](#tab/netcore20)

```dotnetcli
dotnet vstest [<TEST_FILE_NAMES>] [--Settings|/Settings] [--Tests|/Tests] [--TestAdapterPath|/TestAdapterPath] 
    [--Platform|/Platform] [--Framework|/Framework] [--Parallel|/Parallel] [--TestCaseFilter|/TestCaseFilter] [--logger|/logger]
    [-lt|--ListTests|/lt|/ListTests] [--ParentProcessId|/ParentProcessId] [--Port|/Port] [--Diag|/Diag] [[--] <args>...]] [-?|--Help|/?|/Help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="cec3d-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="cec3d-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```dotnetcli
dotnet vstest [<TEST_FILE_NAMES>] [--Settings|/Settings] [--Tests|/Tests] [--TestAdapterPath|/TestAdapterPath]
    [--Platform|/Platform] [--Framework|/Framework] [--Parallel|/Parallel] [--TestCaseFilter|/TestCaseFilter] [--logger|/logger] 
    [-lt|--ListTests|/lt|/ListTests] [--ParentProcessId|/ParentProcessId] [--Port|/Port] [--Diag|/Diag] [[--] <args>...]] [-?|--Help|/?|/Help]
```

---

## <a name="description"></a><span data-ttu-id="cec3d-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cec3d-110">Description</span></span>

<span data-ttu-id="cec3d-111">Der `dotnet-vstest`-Befehl führt die `VSTest.Console`-Befehlszeilenanwendung aus, um automatisierte Komponententests auszuführen.</span><span class="sxs-lookup"><span data-stu-id="cec3d-111">The `dotnet-vstest` command runs the `VSTest.Console` command-line application to run automated unit tests.</span></span>

## <a name="arguments"></a><span data-ttu-id="cec3d-112">Argumente</span><span class="sxs-lookup"><span data-stu-id="cec3d-112">Arguments</span></span>

`TEST_FILE_NAMES`

<span data-ttu-id="cec3d-113">Führt Tests auf Grundlage der angegebenen Assemblys aus.</span><span class="sxs-lookup"><span data-stu-id="cec3d-113">Run tests from the specified assemblies.</span></span> <span data-ttu-id="cec3d-114">Trennt mehrere Test-Assemblynamen durch Leerzeichen.</span><span class="sxs-lookup"><span data-stu-id="cec3d-114">Separate multiple test assembly names with spaces.</span></span>

## <a name="options"></a><span data-ttu-id="cec3d-115">Optionen</span><span class="sxs-lookup"><span data-stu-id="cec3d-115">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="cec3d-116">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="cec3d-116">.NET Core 2.1</span></span>](#tab/netcore21)

`--Settings|/Settings:<Settings File>`

<span data-ttu-id="cec3d-117">Einstellungen, die beim Ausführen von Tests verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cec3d-117">Settings to use when running tests.</span></span>

`--Tests|/Tests:<Test Names>`

<span data-ttu-id="cec3d-118">Führt Tests aus, die mit den eingegebenen Werten übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="cec3d-118">Run tests with names that match the provided values.</span></span> <span data-ttu-id="cec3d-119">Trennt mehrere Werte per Komma voneinander ab.</span><span class="sxs-lookup"><span data-stu-id="cec3d-119">Separate multiple values with commas.</span></span>

`--TestAdapterPath|/TestAdapterPath`

<span data-ttu-id="cec3d-120">Verwendet benutzerdefinierte Testadapter aus einem angegebenen Pfad (falls vorhanden) im Testlauf.</span><span class="sxs-lookup"><span data-stu-id="cec3d-120">Use custom test adapters from a given path (if any) in the test run.</span></span>

`--Platform|/Platform:<Platform type>`

<span data-ttu-id="cec3d-121">Verwendete Zielplattformarchitektur für die Testausführung.</span><span class="sxs-lookup"><span data-stu-id="cec3d-121">Target platform architecture used for test execution.</span></span> <span data-ttu-id="cec3d-122">Gültige Werte sind `x86`, `x64` und `ARM`.</span><span class="sxs-lookup"><span data-stu-id="cec3d-122">Valid values are `x86`, `x64`, and `ARM`.</span></span>

`--Framework|/Framework:<Framework Version>`

<span data-ttu-id="cec3d-123">.NET Framework-Zielversion, in der der Test ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="cec3d-123">Target .NET Framework version used for test execution.</span></span> <span data-ttu-id="cec3d-124">`.NETFramework,Version=v4.6` und `.NETCoreApp,Version=v1.0` sind Beispiele für gültige Werte.</span><span class="sxs-lookup"><span data-stu-id="cec3d-124">Examples of valid values are `.NETFramework,Version=v4.6` or `.NETCoreApp,Version=v1.0`.</span></span> <span data-ttu-id="cec3d-125">Andere unterstützte Werte sind `Framework40`, `Framework45`, `FrameworkCore10` und `FrameworkUap10`.</span><span class="sxs-lookup"><span data-stu-id="cec3d-125">Other supported values are `Framework40`, `Framework45`, `FrameworkCore10`, and `FrameworkUap10`.</span></span>

`--Parallel|/Parallel`

<span data-ttu-id="cec3d-126">Führt Tests parallel aus.</span><span class="sxs-lookup"><span data-stu-id="cec3d-126">Execute tests in parallel.</span></span> <span data-ttu-id="cec3d-127">Standardmäßig stehen alle verfügbaren Kerne auf dem Computer zur Nutzung zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="cec3d-127">By default, all available cores on the machine are available for use.</span></span> <span data-ttu-id="cec3d-128">Geben Sie eine explizite Anzahl von Kernen an, indem Sie die „MaxCpuCount“-Eigenschaft unter dem Knoten „RunConfiguration“ in der Datei „runsettings“ festlegen.</span><span class="sxs-lookup"><span data-stu-id="cec3d-128">Specify an explicit number of cores by setting the MaxCpuCount property under the RunConfiguration node in the runsettings file.</span></span>

`--TestCaseFilter|/TestCaseFilter:<Expression>`

<span data-ttu-id="cec3d-129">Führt Tests aus, die mit dem angegebenen Ausdruck übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="cec3d-129">Run tests that match the given expression.</span></span> <span data-ttu-id="cec3d-130">`<Expression>` hat das Format `<property>Operator<value>[|&<Expression>]`, wobei der Operator `=`, `!=`, oder `~` ist.</span><span class="sxs-lookup"><span data-stu-id="cec3d-130">`<Expression>` is of the format `<property>Operator<value>[|&<Expression>]`, where Operator is one of `=`, `!=`, or `~`.</span></span> <span data-ttu-id="cec3d-131">Operator `~` verfügt über „contains“-Semantik und gilt für Zeichenfolgeneigenschaften wie `DisplayName`.</span><span class="sxs-lookup"><span data-stu-id="cec3d-131">Operator `~` has 'contains' semantics and is applicable for string properties like `DisplayName`.</span></span> <span data-ttu-id="cec3d-132">Klammern `()` werden verwendet, um untergeordnete Ausdrücke zu gruppieren.</span><span class="sxs-lookup"><span data-stu-id="cec3d-132">Parenthesis `()` are used to group sub-expressions.</span></span>

`-?|--Help|/?|/Help`

<span data-ttu-id="cec3d-133">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="cec3d-133">Prints out a short help for the command.</span></span>

`--logger|/logger:<Logger Uri/FriendlyName>`

<span data-ttu-id="cec3d-134">Geben Sie eine Protokollierung für die Testergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="cec3d-134">Specify a logger for test results.</span></span>

* <span data-ttu-id="cec3d-135">Verwenden Sie den `TfsPublisher`-Protokollierungsanbieter zum Veröffentlichen von Testergebnissen in Team Foundation Server:</span><span class="sxs-lookup"><span data-stu-id="cec3d-135">To publish test results to Team Foundation Server, use the `TfsPublisher` logger provider:</span></span>

  ```console
  /logger:TfsPublisher;
      Collection=<team project collection url>;
      BuildName=<build name>;
      TeamProject=<team project name>
      [;Platform=<Defaults to "Any CPU">]
      [;Flavor=<Defaults to "Debug">]
      [;RunTitle=<title>]
  ```

* <span data-ttu-id="cec3d-136">Verwenden Sie zum Protokollieren von Ergebnissen in einer Visual Studio-Testergebnisdatei (TRX) den `trx`-Protokollierungsanbieter.</span><span class="sxs-lookup"><span data-stu-id="cec3d-136">To log results to a Visual Studio Test Results File (TRX), use the `trx` logger provider.</span></span> <span data-ttu-id="cec3d-137">Dieser Schalter erstellt eine Datei im Verzeichnis mit den Testergebnissen mit dem angegebenen Protokolldateinamen.</span><span class="sxs-lookup"><span data-stu-id="cec3d-137">This switch creates a file in the test results directory with given log file name.</span></span> <span data-ttu-id="cec3d-138">Wenn `LogFileName` nicht angegeben wird, wird ein eindeutiger Dateiname erstellt, um die Testergebnisse aufzunehmen.</span><span class="sxs-lookup"><span data-stu-id="cec3d-138">If `LogFileName` isn't provided, a unique file name is created to hold the test results.</span></span>

  ```console
  /logger:trx [;LogFileName=<Defaults to unique file name>]
  ```

`-lt|--ListTests|/lt|/ListTests:<File Name>`

<span data-ttu-id="cec3d-139">Listet alle gefundenen Tests aus dem angegebenen Testcontainer auf.</span><span class="sxs-lookup"><span data-stu-id="cec3d-139">Lists all discovered tests from the given test container.</span></span>

`--ParentProcessId|/ParentProcessId:<ParentProcessId>`

<span data-ttu-id="cec3d-140">Prozess-ID des übergeordneten Prozesses, der für den Start des aktuellen Prozesses verantwortlich ist.</span><span class="sxs-lookup"><span data-stu-id="cec3d-140">Process ID of the parent process responsible for launching the current process.</span></span>

`--Port|/Port:<Port>`

<span data-ttu-id="cec3d-141">Gibt den Port für die Socketverbindung an und empfängt die Ereignismeldungen.</span><span class="sxs-lookup"><span data-stu-id="cec3d-141">Specifies the port for the socket connection and receiving the event messages.</span></span>

`--Diag|/Diag:<Path to log file>`

<span data-ttu-id="cec3d-142">Aktiviert die ausführlichen Protokolle für die Testplattform.</span><span class="sxs-lookup"><span data-stu-id="cec3d-142">Enables verbose logs for the test platform.</span></span> <span data-ttu-id="cec3d-143">Protokolle werden in die angegebene Datei geschrieben.</span><span class="sxs-lookup"><span data-stu-id="cec3d-143">Logs are written to the provided file.</span></span>

`--Blame|/Blame`

<span data-ttu-id="cec3d-144">Führt die Tests im blame-Modus aus.</span><span class="sxs-lookup"><span data-stu-id="cec3d-144">Runs the tests in blame mode.</span></span> <span data-ttu-id="cec3d-145">Diese Option hilft beim Isolieren der fehlerhaften Tests, die den Absturz des Testhosts verursachen.</span><span class="sxs-lookup"><span data-stu-id="cec3d-145">This option is helpful in isolating the problematic tests causing test host to crash.</span></span> <span data-ttu-id="cec3d-146">In dem aktuellen Verzeichnis wird eine Ausgabedatei als *Sequence.xml* erstellt, die die Reihenfolge der ausgeführten Tests vor dem Absturz erfasst.</span><span class="sxs-lookup"><span data-stu-id="cec3d-146">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

`--InIsolation|/InIsolation`

<span data-ttu-id="cec3d-147">Führt die Tests in einem isolierten Prozess aus.</span><span class="sxs-lookup"><span data-stu-id="cec3d-147">Runs the tests in an isolated process.</span></span> <span data-ttu-id="cec3d-148">Dadurch ist die Wahrscheinlichkeit, dass der *vstest.console.exe*-Prozess bei Testfehlern beendet wird, weniger hoch, die Tests werden jedoch möglicherweise langsamer ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="cec3d-148">This makes *vstest.console.exe* process less likely to be stopped on an error in the tests, but tests may run slower.</span></span>

`@<file>`

<span data-ttu-id="cec3d-149">Liest eine Antwortdatei für mehrere Optionen.</span><span class="sxs-lookup"><span data-stu-id="cec3d-149">Reads response file for more options.</span></span>

`args`

<span data-ttu-id="cec3d-150">Gibt zusätzliche Argumente an, die an den Adapter übergeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="cec3d-150">Specifies extra arguments to pass to the adapter.</span></span> <span data-ttu-id="cec3d-151">Argumente werden als Name-Wert-Paare des Formulars `<n>=<v>` angegeben, wobei `<n>` der Argumentname und `<v>` der Argumentwert ist.</span><span class="sxs-lookup"><span data-stu-id="cec3d-151">Arguments are specified as name-value pairs of the form `<n>=<v>`, where `<n>` is the argument name and `<v>` is the argument value.</span></span> <span data-ttu-id="cec3d-152">Trennt mehrere Argumente durch Leerzeichen.</span><span class="sxs-lookup"><span data-stu-id="cec3d-152">Use a space to separate multiple arguments.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="cec3d-153">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="cec3d-153">.NET Core 2.0</span></span>](#tab/netcore20)

`--Settings|/Settings:<Settings File>`

<span data-ttu-id="cec3d-154">Einstellungen, die beim Ausführen von Tests verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cec3d-154">Settings to use when running tests.</span></span>

`--Tests|/Tests:<Test Names>`

<span data-ttu-id="cec3d-155">Führt Tests aus, die mit den eingegebenen Werten übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="cec3d-155">Run tests with names that match the provided values.</span></span> <span data-ttu-id="cec3d-156">Trennt mehrere Werte per Komma voneinander ab.</span><span class="sxs-lookup"><span data-stu-id="cec3d-156">Separate multiple values with commas.</span></span>

`--TestAdapterPath|/TestAdapterPath`

<span data-ttu-id="cec3d-157">Verwendet benutzerdefinierte Testadapter aus einem angegebenen Pfad (falls vorhanden) im Testlauf.</span><span class="sxs-lookup"><span data-stu-id="cec3d-157">Use custom test adapters from a given path (if any) in the test run.</span></span>

`--Platform|/Platform:<Platform type>`

<span data-ttu-id="cec3d-158">Verwendete Zielplattformarchitektur für die Testausführung.</span><span class="sxs-lookup"><span data-stu-id="cec3d-158">Target platform architecture used for test execution.</span></span> <span data-ttu-id="cec3d-159">Gültige Werte sind `x86`, `x64` und `ARM`.</span><span class="sxs-lookup"><span data-stu-id="cec3d-159">Valid values are `x86`, `x64`, and `ARM`.</span></span>

`--Framework|/Framework:<Framework Version>`

<span data-ttu-id="cec3d-160">.NET Framework-Zielversion, in der der Test ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="cec3d-160">Target .NET Framework version used for test execution.</span></span> <span data-ttu-id="cec3d-161">`.NETFramework,Version=v4.6` und `.NETCoreApp,Version=v1.0` sind Beispiele für gültige Werte.</span><span class="sxs-lookup"><span data-stu-id="cec3d-161">Examples of valid values are `.NETFramework,Version=v4.6` or `.NETCoreApp,Version=v1.0`.</span></span> <span data-ttu-id="cec3d-162">Andere unterstützte Werte sind `Framework40`, `Framework45` und `FrameworkCore10`.</span><span class="sxs-lookup"><span data-stu-id="cec3d-162">Other supported values are `Framework40`, `Framework45`, and `FrameworkCore10`.</span></span>

`--Parallel|/Parallel`

<span data-ttu-id="cec3d-163">Führt Tests parallel aus.</span><span class="sxs-lookup"><span data-stu-id="cec3d-163">Execute tests in parallel.</span></span> <span data-ttu-id="cec3d-164">Standardmäßig stehen alle verfügbaren Kerne auf dem Computer zur Nutzung zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="cec3d-164">By default, all available cores on the machine are available for use.</span></span> <span data-ttu-id="cec3d-165">Geben Sie eine explizite Anzahl von Kernen an, indem Sie die „MaxCpuCount“-Eigenschaft unter dem Knoten „RunConfiguration“ in der Datei „runsettings“ festlegen.</span><span class="sxs-lookup"><span data-stu-id="cec3d-165">Specify an explicit number of cores by setting the MaxCpuCount property under the RunConfiguration node in the runsettings file.</span></span>

`--TestCaseFilter|/TestCaseFilter:<Expression>`

<span data-ttu-id="cec3d-166">Führt Tests aus, die mit dem angegebenen Ausdruck übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="cec3d-166">Run tests that match the given expression.</span></span> <span data-ttu-id="cec3d-167">`<Expression>` hat das Format `<property>Operator<value>[|&<Expression>]`, wobei der Operator `=`, `!=`, oder `~` ist.</span><span class="sxs-lookup"><span data-stu-id="cec3d-167">`<Expression>` is of the format `<property>Operator<value>[|&<Expression>]`, where Operator is one of `=`, `!=`, or `~`.</span></span> <span data-ttu-id="cec3d-168">Operator `~` verfügt über „contains“-Semantik und gilt für Zeichenfolgeneigenschaften wie `DisplayName`.</span><span class="sxs-lookup"><span data-stu-id="cec3d-168">Operator `~` has 'contains' semantics and is applicable for string properties like `DisplayName`.</span></span> <span data-ttu-id="cec3d-169">Klammern `()` werden verwendet, um untergeordnete Ausdrücke zu gruppieren.</span><span class="sxs-lookup"><span data-stu-id="cec3d-169">Parenthesis `()` are used to group sub-expressions.</span></span>

`-?|--Help|/?|/Help`

<span data-ttu-id="cec3d-170">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="cec3d-170">Prints out a short help for the command.</span></span>

`--logger|/logger:<Logger Uri/FriendlyName>`

<span data-ttu-id="cec3d-171">Geben Sie eine Protokollierung für die Testergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="cec3d-171">Specify a logger for test results.</span></span>

* <span data-ttu-id="cec3d-172">Verwenden Sie den `TfsPublisher`-Protokollierungsanbieter zum Veröffentlichen von Testergebnissen in Team Foundation Server:</span><span class="sxs-lookup"><span data-stu-id="cec3d-172">To publish test results to Team Foundation Server, use the `TfsPublisher` logger provider:</span></span>

  ```console
  /logger:TfsPublisher;
      Collection=<team project collection url>;
      BuildName=<build name>;
      TeamProject=<team project name>
      [;Platform=<Defaults to "Any CPU">]
      [;Flavor=<Defaults to "Debug">]
      [;RunTitle=<title>]
  ```

* <span data-ttu-id="cec3d-173">Verwenden Sie zum Protokollieren von Ergebnissen in einer Visual Studio-Testergebnisdatei (TRX) den `trx`-Protokollierungsanbieter.</span><span class="sxs-lookup"><span data-stu-id="cec3d-173">To log results to a Visual Studio Test Results File (TRX), use the `trx` logger provider.</span></span> <span data-ttu-id="cec3d-174">Dieser Schalter erstellt eine Datei im Verzeichnis mit den Testergebnissen mit dem angegebenen Protokolldateinamen.</span><span class="sxs-lookup"><span data-stu-id="cec3d-174">This switch creates a file in the test results directory with given log file name.</span></span> <span data-ttu-id="cec3d-175">Wenn `LogFileName` nicht angegeben wird, wird ein eindeutiger Dateiname erstellt, um die Testergebnisse aufzunehmen.</span><span class="sxs-lookup"><span data-stu-id="cec3d-175">If `LogFileName` isn't provided, a unique file name is created to hold the test results.</span></span>

  ```console
  /logger:trx [;LogFileName=<Defaults to unique file name>]
  ```

`-lt|--ListTests|/lt|/ListTests:<File Name>`

<span data-ttu-id="cec3d-176">Listet alle gefundenen Tests aus dem angegebenen Testcontainer auf.</span><span class="sxs-lookup"><span data-stu-id="cec3d-176">Lists all discovered tests from the given test container.</span></span>

`--ParentProcessId|/ParentProcessId:<ParentProcessId>`

<span data-ttu-id="cec3d-177">Prozess-ID des übergeordneten Prozesses, der für den Start des aktuellen Prozesses verantwortlich ist.</span><span class="sxs-lookup"><span data-stu-id="cec3d-177">Process ID of the parent process responsible for launching the current process.</span></span>

`--Port|/Port:<Port>`

<span data-ttu-id="cec3d-178">Gibt den Port für die Socketverbindung an und empfängt die Ereignismeldungen.</span><span class="sxs-lookup"><span data-stu-id="cec3d-178">Specifies the port for the socket connection and receiving the event messages.</span></span>

`--Diag|/Diag:<Path to log file>`

<span data-ttu-id="cec3d-179">Aktiviert die ausführlichen Protokolle für die Testplattform.</span><span class="sxs-lookup"><span data-stu-id="cec3d-179">Enables verbose logs for the test platform.</span></span> <span data-ttu-id="cec3d-180">Protokolle werden in die angegebene Datei geschrieben.</span><span class="sxs-lookup"><span data-stu-id="cec3d-180">Logs are written to the provided file.</span></span>

`args`

<span data-ttu-id="cec3d-181">Gibt zusätzliche Argumente an, die an den Adapter übergeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="cec3d-181">Specifies extra arguments to pass to the adapter.</span></span> <span data-ttu-id="cec3d-182">Argumente werden als Name-Wert-Paare des Formulars `<n>=<v>` angegeben, wobei `<n>` der Argumentname und `<v>` der Argumentwert ist.</span><span class="sxs-lookup"><span data-stu-id="cec3d-182">Arguments are specified as name-value pairs of the form `<n>=<v>`, where `<n>` is the argument name and `<v>` is the argument value.</span></span> <span data-ttu-id="cec3d-183">Trennt mehrere Argumente durch Leerzeichen.</span><span class="sxs-lookup"><span data-stu-id="cec3d-183">Use a space to separate multiple arguments.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="cec3d-184">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="cec3d-184">.NET Core 1.x</span></span>](#tab/netcore1x)

`--Settings|/Settings:<Settings File>`

<span data-ttu-id="cec3d-185">Einstellungen, die beim Ausführen von Tests verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cec3d-185">Settings to use when running tests.</span></span>

`--Tests|/Tests:<Test Names>`

<span data-ttu-id="cec3d-186">Führt Tests aus, die mit den eingegebenen Werten übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="cec3d-186">Run tests with names that match the provided values.</span></span> <span data-ttu-id="cec3d-187">Trennt mehrere Werte per Komma voneinander ab.</span><span class="sxs-lookup"><span data-stu-id="cec3d-187">Separate multiple values with commas.</span></span>

`--TestAdapterPath|/TestAdapterPath`

<span data-ttu-id="cec3d-188">Verwendet benutzerdefinierte Testadapter aus einem angegebenen Pfad (falls vorhanden) im Testlauf.</span><span class="sxs-lookup"><span data-stu-id="cec3d-188">Use custom test adapters from a given path (if any) in the test run.</span></span>

`--Platform|/Platform:<Platform type>`

<span data-ttu-id="cec3d-189">Verwendete Zielplattformarchitektur für die Testausführung.</span><span class="sxs-lookup"><span data-stu-id="cec3d-189">Target platform architecture used for test execution.</span></span> <span data-ttu-id="cec3d-190">Gültige Werte sind `x86`, `x64` und `ARM`.</span><span class="sxs-lookup"><span data-stu-id="cec3d-190">Valid values are `x86`, `x64`, and `ARM`.</span></span>

`--Framework|/Framework:<Framework Version>`

<span data-ttu-id="cec3d-191">.NET Framework-Zielversion, in der der Test ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="cec3d-191">Target .NET Framework version used for test execution.</span></span> <span data-ttu-id="cec3d-192">`.NETFramework,Version=v4.6` und `.NETCoreApp,Version=v1.0` sind Beispiele für gültige Werte.</span><span class="sxs-lookup"><span data-stu-id="cec3d-192">Examples of valid values are `.NETFramework,Version=v4.6` or `.NETCoreApp,Version=v1.0`.</span></span> <span data-ttu-id="cec3d-193">Andere unterstützte Werte sind `Framework40`, `Framework45` und `FrameworkCore10`.</span><span class="sxs-lookup"><span data-stu-id="cec3d-193">Other supported values are `Framework40`, `Framework45`, and `FrameworkCore10`.</span></span>

`--Parallel|/Parallel`

<span data-ttu-id="cec3d-194">Führt Tests parallel aus.</span><span class="sxs-lookup"><span data-stu-id="cec3d-194">Execute tests in parallel.</span></span> <span data-ttu-id="cec3d-195">Standardmäßig stehen alle verfügbaren Kerne auf dem Computer zur Nutzung zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="cec3d-195">By default, all available cores on the machine are available for use.</span></span> <span data-ttu-id="cec3d-196">Geben Sie eine explizite Anzahl von Kernen an, indem Sie die „MaxCpuCount“-Eigenschaft unter dem Knoten „RunConfiguration“ in der Datei „runsettings“ festlegen.</span><span class="sxs-lookup"><span data-stu-id="cec3d-196">Specify an explicit number of cores by setting the MaxCpuCount property under the RunConfiguration node in the runsettings file.</span></span>

`--TestCaseFilter|/TestCaseFilter:<Expression>`

<span data-ttu-id="cec3d-197">Führt Tests aus, die mit dem angegebenen Ausdruck übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="cec3d-197">Run tests that match the given expression.</span></span> <span data-ttu-id="cec3d-198">`<Expression>` hat das Format `<property>Operator<value>[|&<Expression>]`, wobei der Operator `=`, `!=`, oder `~` ist.</span><span class="sxs-lookup"><span data-stu-id="cec3d-198">`<Expression>` is of the format `<property>Operator<value>[|&<Expression>]`, where Operator is one of `=`, `!=`, or `~`.</span></span> <span data-ttu-id="cec3d-199">Operator `~` verfügt über „contains“-Semantik und gilt für Zeichenfolgeneigenschaften wie `DisplayName`.</span><span class="sxs-lookup"><span data-stu-id="cec3d-199">Operator `~` has 'contains' semantics and is applicable for string properties like `DisplayName`.</span></span> <span data-ttu-id="cec3d-200">Klammern `()` werden verwendet, um untergeordnete Ausdrücke zu gruppieren.</span><span class="sxs-lookup"><span data-stu-id="cec3d-200">Parenthesis `()` are used to group sub-expressions.</span></span>

`-?|--Help|/?|/Help`

<span data-ttu-id="cec3d-201">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="cec3d-201">Prints out a short help for the command.</span></span>

`--logger|/logger:<Logger Uri/FriendlyName>`

<span data-ttu-id="cec3d-202">Geben Sie eine Protokollierung für die Testergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="cec3d-202">Specify a logger for test results.</span></span>

* <span data-ttu-id="cec3d-203">Verwenden Sie den `TfsPublisher`-Protokollierungsanbieter zum Veröffentlichen von Testergebnissen in Team Foundation Server:</span><span class="sxs-lookup"><span data-stu-id="cec3d-203">To publish test results to Team Foundation Server, use the `TfsPublisher` logger provider:</span></span>

  ```console
  /logger:TfsPublisher;
      Collection=<team project collection url>;
      BuildName=<build name>;
      TeamProject=<team project name>
      [;Platform=<Defaults to "Any CPU">]
      [;Flavor=<Defaults to "Debug">]
      [;RunTitle=<title>]
  ```

* <span data-ttu-id="cec3d-204">Verwenden Sie zum Protokollieren von Ergebnissen in einer Visual Studio-Testergebnisdatei (TRX) den `trx`-Protokollierungsanbieter.</span><span class="sxs-lookup"><span data-stu-id="cec3d-204">To log results to a Visual Studio Test Results File (TRX), use the `trx` logger provider.</span></span> <span data-ttu-id="cec3d-205">Dieser Schalter erstellt eine Datei im Verzeichnis mit den Testergebnissen mit dem angegebenen Protokolldateinamen.</span><span class="sxs-lookup"><span data-stu-id="cec3d-205">This switch creates a file in the test results directory with given log file name.</span></span> <span data-ttu-id="cec3d-206">Wenn `LogFileName` nicht angegeben wird, wird ein eindeutiger Dateiname erstellt, um die Testergebnisse aufzunehmen.</span><span class="sxs-lookup"><span data-stu-id="cec3d-206">If `LogFileName` isn't provided, a unique file name is created to hold the test results.</span></span>

  ```console
  /logger:trx [;LogFileName=<Defaults to unique file name>]
  ```

`-lt|--ListTests|/lt|/ListTests:<File Name>`

<span data-ttu-id="cec3d-207">Listet alle gefundenen Tests aus dem angegebenen Testcontainer auf.</span><span class="sxs-lookup"><span data-stu-id="cec3d-207">Lists all discovered tests from the given test container.</span></span>

`--ParentProcessId|/ParentProcessId:<ParentProcessId>`

<span data-ttu-id="cec3d-208">Prozess-ID des übergeordneten Prozesses, der für den Start des aktuellen Prozesses verantwortlich ist.</span><span class="sxs-lookup"><span data-stu-id="cec3d-208">Process ID of the parent process responsible for launching the current process.</span></span>

`--Port|/Port:<Port>`

<span data-ttu-id="cec3d-209">Gibt den Port für die Socketverbindung an und empfängt die Ereignismeldungen.</span><span class="sxs-lookup"><span data-stu-id="cec3d-209">Specifies the port for the socket connection and receiving the event messages.</span></span>

`--Diag|/Diag:<Path to log file>`

<span data-ttu-id="cec3d-210">Aktiviert die ausführlichen Protokolle für die Testplattform.</span><span class="sxs-lookup"><span data-stu-id="cec3d-210">Enables verbose logs for the test platform.</span></span> <span data-ttu-id="cec3d-211">Protokolle werden in die angegebene Datei geschrieben.</span><span class="sxs-lookup"><span data-stu-id="cec3d-211">Logs are written to the provided file.</span></span>

`args`

<span data-ttu-id="cec3d-212">Gibt zusätzliche Argumente an, die an den Adapter übergeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="cec3d-212">Specifies extra arguments to pass to the adapter.</span></span> <span data-ttu-id="cec3d-213">Argumente werden als Name-Wert-Paare des Formulars `<n>=<v>` angegeben, wobei `<n>` der Argumentname und `<v>` der Argumentwert ist.</span><span class="sxs-lookup"><span data-stu-id="cec3d-213">Arguments are specified as name-value pairs of the form `<n>=<v>`, where `<n>` is the argument name and `<v>` is the argument value.</span></span> <span data-ttu-id="cec3d-214">Trennt mehrere Argumente durch Leerzeichen.</span><span class="sxs-lookup"><span data-stu-id="cec3d-214">Use a space to separate multiple arguments.</span></span>

---

## <a name="examples"></a><span data-ttu-id="cec3d-215">Beispiele</span><span class="sxs-lookup"><span data-stu-id="cec3d-215">Examples</span></span>

<span data-ttu-id="cec3d-216">Führt Tests in `mytestproject.dll` aus:</span><span class="sxs-lookup"><span data-stu-id="cec3d-216">Run tests in `mytestproject.dll`:</span></span>

`dotnet vstest mytestproject.dll`

<span data-ttu-id="cec3d-217">Führen Sie Tests in `mytestproject.dll` aus, und exportieren Sie sie in den benutzerdefinierten Ordner mit benutzerdefiniertem Namen:</span><span class="sxs-lookup"><span data-stu-id="cec3d-217">Run tests in `mytestproject.dll`, exporting to custom folder with custom name:</span></span>

`dotnet vstest mytestproject.dll --logger:"trx;LogFileName=custom_file_name.trx" --ResultsDirectory:custom/file/path`

<span data-ttu-id="cec3d-218">Führt Tests in `mytestproject.dll` und `myothertestproject.exe` aus:</span><span class="sxs-lookup"><span data-stu-id="cec3d-218">Run tests in `mytestproject.dll` and `myothertestproject.exe`:</span></span>

`dotnet vstest mytestproject.dll myothertestproject.exe`

<span data-ttu-id="cec3d-219">Führt `TestMethod1`-Tests aus:</span><span class="sxs-lookup"><span data-stu-id="cec3d-219">Run `TestMethod1` tests:</span></span>

`dotnet vstest /Tests:TestMethod1`

<span data-ttu-id="cec3d-220">Führt `TestMethod1`- und `TestMethod2`-Tests aus:</span><span class="sxs-lookup"><span data-stu-id="cec3d-220">Run `TestMethod1` and `TestMethod2` tests:</span></span>

`dotnet vstest /Tests:TestMethod1,TestMethod2`
