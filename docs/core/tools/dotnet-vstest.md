---
title: Befehl „dotnet vstest“
description: Der dotnet vstest-Befehl erstellt ein Projekt und alle seine Abhängigkeiten.
ms.date: 02/27/2020
ms.openlocfilehash: 88e5b6a8966d78d0746f9ea5ccbccab142a2e0f6
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2020
ms.locfileid: "78156932"
---
# <a name="dotnet-vstest"></a><span data-ttu-id="4e5ee-103">dotnet vstest</span><span class="sxs-lookup"><span data-stu-id="4e5ee-103">dotnet vstest</span></span>

<span data-ttu-id="4e5ee-104">**Dieser Artikel gilt für:** ✔️ .NET Core 2.1 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="4e5ee-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="4e5ee-105">name</span><span class="sxs-lookup"><span data-stu-id="4e5ee-105">Name</span></span>

<span data-ttu-id="4e5ee-106">`dotnet-vstest`: Führt Tests auf Grundlage der angegebenen Dateien aus.</span><span class="sxs-lookup"><span data-stu-id="4e5ee-106">`dotnet-vstest` - Runs tests from the specified files.</span></span>

## <a name="synopsis"></a><span data-ttu-id="4e5ee-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="4e5ee-107">Synopsis</span></span>

```dotnetcli
dotnet vstest [<TEST_FILE_NAMES>] [--Settings] [--Tests]
    [--TestAdapterPath] [--Platform] [--Framework] [--Parallel]
    [--TestCaseFilter] [--logger] [-lt|--ListTests]
    [--ParentProcessId] [--Port] [--Diag] [--Blame]
    [--InIsolation] [[--] <args>...]] [-?|--Help]
```

## <a name="description"></a><span data-ttu-id="4e5ee-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4e5ee-108">Description</span></span>

<span data-ttu-id="4e5ee-109">Der `dotnet-vstest`-Befehl führt die `VSTest.Console`-Befehlszeilenanwendung aus, um automatisierte Komponententests auszuführen.</span><span class="sxs-lookup"><span data-stu-id="4e5ee-109">The `dotnet-vstest` command runs the `VSTest.Console` command-line application to run automated unit tests.</span></span>

## <a name="arguments"></a><span data-ttu-id="4e5ee-110">Argumente</span><span class="sxs-lookup"><span data-stu-id="4e5ee-110">Arguments</span></span>

- **`TEST_FILE_NAMES`**

  <span data-ttu-id="4e5ee-111">Führt Tests auf Grundlage der angegebenen Assemblys aus.</span><span class="sxs-lookup"><span data-stu-id="4e5ee-111">Run tests from the specified assemblies.</span></span> <span data-ttu-id="4e5ee-112">Trennt mehrere Test-Assemblynamen durch Leerzeichen.</span><span class="sxs-lookup"><span data-stu-id="4e5ee-112">Separate multiple test assembly names with spaces.</span></span> <span data-ttu-id="4e5ee-113">Platzhalter werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4e5ee-113">Wildcards are supported.</span></span>

## <a name="options"></a><span data-ttu-id="4e5ee-114">Optionen</span><span class="sxs-lookup"><span data-stu-id="4e5ee-114">Options</span></span>

- **`--Settings <Settings File>`**

  <span data-ttu-id="4e5ee-115">Einstellungen, die beim Ausführen von Tests verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4e5ee-115">Settings to use when running tests.</span></span>

- **`--Tests <Test Names>`**

  <span data-ttu-id="4e5ee-116">Führt Tests aus, die mit den eingegebenen Werten übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="4e5ee-116">Run tests with names that match the provided values.</span></span> <span data-ttu-id="4e5ee-117">Trennt mehrere Werte per Komma voneinander ab.</span><span class="sxs-lookup"><span data-stu-id="4e5ee-117">Separate multiple values with commas.</span></span>

- **`--TestAdapterPath`**

  <span data-ttu-id="4e5ee-118">Verwendet benutzerdefinierte Testadapter aus einem angegebenen Pfad (falls vorhanden) im Testlauf.</span><span class="sxs-lookup"><span data-stu-id="4e5ee-118">Use custom test adapters from a given path (if any) in the test run.</span></span>

- **`--Platform <Platform type>`**

  <span data-ttu-id="4e5ee-119">Verwendete Zielplattformarchitektur für die Testausführung.</span><span class="sxs-lookup"><span data-stu-id="4e5ee-119">Target platform architecture used for test execution.</span></span> <span data-ttu-id="4e5ee-120">Gültige Werte sind `x86`, `x64` und `ARM`.</span><span class="sxs-lookup"><span data-stu-id="4e5ee-120">Valid values are `x86`, `x64`, and `ARM`.</span></span>

- **`--Framework <Framework Version>`**

  <span data-ttu-id="4e5ee-121">.NET Framework-Zielversion, in der der Test ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4e5ee-121">Target .NET Framework version used for test execution.</span></span> <span data-ttu-id="4e5ee-122">`.NETFramework,Version=v4.6` und `.NETCoreApp,Version=v1.0` sind Beispiele für gültige Werte.</span><span class="sxs-lookup"><span data-stu-id="4e5ee-122">Examples of valid values are `.NETFramework,Version=v4.6` or `.NETCoreApp,Version=v1.0`.</span></span> <span data-ttu-id="4e5ee-123">Andere unterstützte Werte sind `Framework40`, `Framework45`, `FrameworkCore10` und `FrameworkUap10`.</span><span class="sxs-lookup"><span data-stu-id="4e5ee-123">Other supported values are `Framework40`, `Framework45`, `FrameworkCore10`, and `FrameworkUap10`.</span></span>

- **`--Parallel`**

  <span data-ttu-id="4e5ee-124">Mit dieser Option können Sie Tests parallel ausführen.</span><span class="sxs-lookup"><span data-stu-id="4e5ee-124">Run tests in parallel.</span></span> <span data-ttu-id="4e5ee-125">Standardmäßig stehen alle verfügbaren Kerne auf dem Computer zur Nutzung zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="4e5ee-125">By default, all available cores on the machine are available for use.</span></span> <span data-ttu-id="4e5ee-126">Geben Sie eine explizite Anzahl von Kernen an, indem Sie die `MaxCpuCount`-Eigenschaft unter dem `RunConfiguration`-Knoten in der Datei *runsettings* festlegen.</span><span class="sxs-lookup"><span data-stu-id="4e5ee-126">Specify an explicit number of cores by setting the `MaxCpuCount` property under the `RunConfiguration` node in the *runsettings* file.</span></span>

- **`--TestCaseFilter <Expression>`**

  <span data-ttu-id="4e5ee-127">Führt Tests aus, die mit dem angegebenen Ausdruck übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="4e5ee-127">Run tests that match the given expression.</span></span> <span data-ttu-id="4e5ee-128">`<Expression>` hat das Format `<property>Operator<value>[|&<Expression>]`, wobei der Operator `=`, `!=`, oder `~` ist.</span><span class="sxs-lookup"><span data-stu-id="4e5ee-128">`<Expression>` is of the format `<property>Operator<value>[|&<Expression>]`, where Operator is one of `=`, `!=`, or `~`.</span></span> <span data-ttu-id="4e5ee-129">Operator `~` verfügt über „contains“-Semantik und gilt für Zeichenfolgeneigenschaften wie `DisplayName`.</span><span class="sxs-lookup"><span data-stu-id="4e5ee-129">Operator `~` has 'contains' semantics and is applicable for string properties like `DisplayName`.</span></span> <span data-ttu-id="4e5ee-130">Klammern `()` werden zum Gruppieren untergeordneter Ausdrücke verwendet.</span><span class="sxs-lookup"><span data-stu-id="4e5ee-130">Parenthesis `()` are used to group subexpressions.</span></span>

- **`-?|--Help`**

  <span data-ttu-id="4e5ee-131">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="4e5ee-131">Prints out a short help for the command.</span></span>

- **`--logger <Logger Uri/FriendlyName>`**

  <span data-ttu-id="4e5ee-132">Geben Sie eine Protokollierung für die Testergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="4e5ee-132">Specify a logger for test results.</span></span>

  - <span data-ttu-id="4e5ee-133">Verwenden Sie den `TfsPublisher`-Protokollierungsanbieter zum Veröffentlichen von Testergebnissen in Team Foundation Server:</span><span class="sxs-lookup"><span data-stu-id="4e5ee-133">To publish test results to Team Foundation Server, use the `TfsPublisher` logger provider:</span></span>

    ```console
    /logger:TfsPublisher;
        Collection=<team project collection url>;
        BuildName=<build name>;
        TeamProject=<team project name>
        [;Platform=<Defaults to "Any CPU">]
        [;Flavor=<Defaults to "Debug">]
        [;RunTitle=<title>]
    ```

  - <span data-ttu-id="4e5ee-134">Verwenden Sie zum Protokollieren von Ergebnissen in einer Visual Studio-Testergebnisdatei (TRX) den `trx`-Protokollierungsanbieter.</span><span class="sxs-lookup"><span data-stu-id="4e5ee-134">To log results to a Visual Studio Test Results File (TRX), use the `trx` logger provider.</span></span> <span data-ttu-id="4e5ee-135">Dieser Schalter erstellt eine Datei im Verzeichnis mit den Testergebnissen mit dem angegebenen Protokolldateinamen.</span><span class="sxs-lookup"><span data-stu-id="4e5ee-135">This switch creates a file in the test results directory with given log file name.</span></span> <span data-ttu-id="4e5ee-136">Wenn `LogFileName` nicht angegeben wird, wird ein eindeutiger Dateiname erstellt, um die Testergebnisse aufzunehmen.</span><span class="sxs-lookup"><span data-stu-id="4e5ee-136">If `LogFileName` isn't provided, a unique file name is created to hold the test results.</span></span>

    ```console
    /logger:trx [;LogFileName=<Defaults to unique file name>]
    ```

- **`-lt|--ListTests <File Name>`**

  <span data-ttu-id="4e5ee-137">Listet alle gefundenen Tests aus dem angegebenen Testcontainer auf.</span><span class="sxs-lookup"><span data-stu-id="4e5ee-137">Lists all discovered tests from the given test container.</span></span>

- **`--ParentProcessId <ParentProcessId>`**

  <span data-ttu-id="4e5ee-138">Prozess-ID des übergeordneten Prozesses, der für den Start des aktuellen Prozesses verantwortlich ist.</span><span class="sxs-lookup"><span data-stu-id="4e5ee-138">Process ID of the parent process responsible for launching the current process.</span></span>

- **`--Port <Port>`**

  <span data-ttu-id="4e5ee-139">Gibt den Port für die Socketverbindung an und empfängt die Ereignismeldungen.</span><span class="sxs-lookup"><span data-stu-id="4e5ee-139">Specifies the port for the socket connection and receiving the event messages.</span></span>

- **`--Diag <Path to log file>`**

  <span data-ttu-id="4e5ee-140">Aktiviert die ausführlichen Protokolle für die Testplattform.</span><span class="sxs-lookup"><span data-stu-id="4e5ee-140">Enables verbose logs for the test platform.</span></span> <span data-ttu-id="4e5ee-141">Protokolle werden in die angegebene Datei geschrieben.</span><span class="sxs-lookup"><span data-stu-id="4e5ee-141">Logs are written to the provided file.</span></span>

- **`--Blame`**

  <span data-ttu-id="4e5ee-142">Führt die Tests im blame-Modus aus.</span><span class="sxs-lookup"><span data-stu-id="4e5ee-142">Runs the tests in blame mode.</span></span> <span data-ttu-id="4e5ee-143">Diese Option hilft beim Isolieren der fehlerhaften Tests, die den Absturz des Testhosts verursachen.</span><span class="sxs-lookup"><span data-stu-id="4e5ee-143">This option is helpful in isolating the problematic tests causing test host to crash.</span></span> <span data-ttu-id="4e5ee-144">In dem aktuellen Verzeichnis wird eine Ausgabedatei als *Sequence.xml* erstellt, die die Reihenfolge der ausgeführten Tests vor dem Absturz erfasst.</span><span class="sxs-lookup"><span data-stu-id="4e5ee-144">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

- **`--InIsolation`**

  <span data-ttu-id="4e5ee-145">Führt die Tests in einem isolierten Prozess aus.</span><span class="sxs-lookup"><span data-stu-id="4e5ee-145">Runs the tests in an isolated process.</span></span> <span data-ttu-id="4e5ee-146">Dadurch ist die Wahrscheinlichkeit, dass der *vstest.console.exe*-Prozess bei Testfehlern beendet wird, weniger hoch, die Tests werden jedoch möglicherweise langsamer ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="4e5ee-146">This makes *vstest.console.exe* process less likely to be stopped on an error in the tests, but tests may run slower.</span></span>

- **`@<file>`**

  <span data-ttu-id="4e5ee-147">Liest eine Antwortdatei für mehrere Optionen.</span><span class="sxs-lookup"><span data-stu-id="4e5ee-147">Reads response file for more options.</span></span>

- **`args`**

  <span data-ttu-id="4e5ee-148">Gibt zusätzliche Argumente an, die an den Adapter übergeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="4e5ee-148">Specifies extra arguments to pass to the adapter.</span></span> <span data-ttu-id="4e5ee-149">Argumente werden als Name-Wert-Paare des Formulars `<n>=<v>` angegeben, wobei `<n>` der Argumentname und `<v>` der Argumentwert ist.</span><span class="sxs-lookup"><span data-stu-id="4e5ee-149">Arguments are specified as name-value pairs of the form `<n>=<v>`, where `<n>` is the argument name and `<v>` is the argument value.</span></span> <span data-ttu-id="4e5ee-150">Trennt mehrere Argumente durch Leerzeichen.</span><span class="sxs-lookup"><span data-stu-id="4e5ee-150">Use a space to separate multiple arguments.</span></span>

## <a name="examples"></a><span data-ttu-id="4e5ee-151">Beispiele</span><span class="sxs-lookup"><span data-stu-id="4e5ee-151">Examples</span></span>

<span data-ttu-id="4e5ee-152">Mit dem folgenden Befehl werden Tests in *mytestproject.dll* ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="4e5ee-152">Run tests in *mytestproject.dll*:</span></span>

```dotnetcli
dotnet vstest mytestproject.dll
```

<span data-ttu-id="4e5ee-153">Mit dem folgenden Befehl werden Tests in *mytestproject.dll* ausgeführt und in einen benutzerdefinierten Ordner mit benutzerdefiniertem Namen exportiert:</span><span class="sxs-lookup"><span data-stu-id="4e5ee-153">Run tests in *mytestproject.dll*, exporting to custom folder with custom name:</span></span>

```dotnetcli
dotnet vstest mytestproject.dll --logger:"trx;LogFileName=custom_file_name.trx" --ResultsDirectory:custom/file/path
```

<span data-ttu-id="4e5ee-154">Mit dem folgenden Befehl werden Tests in *mytestproject.dll* und *myothertestproject.exe* ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="4e5ee-154">Run tests in *mytestproject.dll* and *myothertestproject.exe*:</span></span>

```dotnetcli
dotnet vstest mytestproject.dll myothertestproject.exe
```

<span data-ttu-id="4e5ee-155">Führt `TestMethod1`-Tests aus:</span><span class="sxs-lookup"><span data-stu-id="4e5ee-155">Run `TestMethod1` tests:</span></span>

```dotnetcli
dotnet vstest /Tests:TestMethod1
```

<span data-ttu-id="4e5ee-156">Führt `TestMethod1`- und `TestMethod2`-Tests aus:</span><span class="sxs-lookup"><span data-stu-id="4e5ee-156">Run `TestMethod1` and `TestMethod2` tests:</span></span>

```dotnetcli
dotnet vstest /Tests:TestMethod1,TestMethod2
```
