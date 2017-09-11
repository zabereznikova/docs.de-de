---
title: dotnet-vstest-Befehl
description: "Der dotnet-vstest-Befehl erstellt ein Projekt und alle seine Abhängigkeiten."
keywords: dotnet-vstest, CLI, CLI-Befehl, .NET Core
author: guardrex
ms.author: mairaw
ms.date: 03/09/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 0e36c070-2242-41d3-96f1-aea0aca48d4d
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 740e0e002b8fde1c5bfd1eb8e53be54b4113c74d
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---

# <a name="dotnet-vstest"></a><span data-ttu-id="23790-104">dotnet-vstest</span><span class="sxs-lookup"><span data-stu-id="23790-104">dotnet-vstest</span></span>

## <a name="name"></a><span data-ttu-id="23790-105">Name</span><span class="sxs-lookup"><span data-stu-id="23790-105">Name</span></span>

<span data-ttu-id="23790-106">`dotnet-vstest`: Führt Tests auf Grundlage der angegebenen Dateien aus.</span><span class="sxs-lookup"><span data-stu-id="23790-106">`dotnet-vstest` - Runs tests from the specified files.</span></span>

## <a name="synopsis"></a><span data-ttu-id="23790-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="23790-107">Synopsis</span></span>

`dotnet vstest [<TEST_FILE_NAMES>] [--Settings|/Settings] [--Tests|/Tests] [--TestAdapterPath|/TestAdapterPath] [--Platform|/Platform] [--Framework|/Framework] [--Parallel|/Parallel] [--TestCaseFilter|/TestCaseFilter] [--logger|/logger] [-lt|--ListTests|/lt|/ListTests] [--ParentProcessId|/ParentProcessId] [--Port|/Port] [--Diag|/Diag] [[--] <args>...]] [-?|--Help|/?|/Help]`

## <a name="description"></a><span data-ttu-id="23790-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="23790-108">Description</span></span>

<span data-ttu-id="23790-109">Der `dotnet-vstest`-Befehl führt die `VSTest.Console`-Befehlszeilenanwendung aus, um automatisierte Komponententests und Tests der codierten UI-Anwendung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="23790-109">The `dotnet-vstest` command runs the `VSTest.Console` command-line application to run automated unit and coded UI application tests.</span></span>

## <a name="arguments"></a><span data-ttu-id="23790-110">Argumente</span><span class="sxs-lookup"><span data-stu-id="23790-110">Arguments</span></span>

`TEST_FILE_NAMES`

<span data-ttu-id="23790-111">Führt Tests auf Grundlage der angegebenen Assemblys aus.</span><span class="sxs-lookup"><span data-stu-id="23790-111">Run tests from the specified assemblies.</span></span> <span data-ttu-id="23790-112">Trennt mehrere Test-Assemblynamen durch Leerzeichen.</span><span class="sxs-lookup"><span data-stu-id="23790-112">Separate multiple test assembly names with spaces.</span></span>

## <a name="options"></a><span data-ttu-id="23790-113">Optionen</span><span class="sxs-lookup"><span data-stu-id="23790-113">Options</span></span>

`--Settings|/Settings:<Settings File>`

<span data-ttu-id="23790-114">Einstellungen, die beim Ausführen von Tests verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="23790-114">Settings to use when running tests.</span></span>

`--Tests|/Tests:<Test Names>`

<span data-ttu-id="23790-115">Führt Tests aus, die mit den eingegebenen Werten übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="23790-115">Run tests with names that match the provided values.</span></span> <span data-ttu-id="23790-116">Trennt mehrere Werte per Komma voneinander ab.</span><span class="sxs-lookup"><span data-stu-id="23790-116">Separate multiple values with commas.</span></span>

`--TestAdapterPath|/TestAdapterPath`

<span data-ttu-id="23790-117">Verwendet benutzerdefinierte Testadapter aus einem angegebenen Pfad (falls vorhanden) im Testlauf.</span><span class="sxs-lookup"><span data-stu-id="23790-117">Use custom test adapters from a given path (if any) in the test run.</span></span>

`--Platform|/Platform:<Platform type>`

<span data-ttu-id="23790-118">Verwendete Zielplattformarchitektur für die Testausführung.</span><span class="sxs-lookup"><span data-stu-id="23790-118">Target platform architecture used for test execution.</span></span> <span data-ttu-id="23790-119">Gültige Werte sind `x86`, `x64` und `ARM`.</span><span class="sxs-lookup"><span data-stu-id="23790-119">Valid values are `x86`, `x64`, and `ARM`.</span></span>

`--Framework|/Framework:<Framework Version>`

<span data-ttu-id="23790-120">.NET Framework-Zielversion, in der der Test ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="23790-120">Target .NET Framework version used for test execution.</span></span> <span data-ttu-id="23790-121">Beispiele für gültige Werte sind `.NETFramework,Version=v4.6`, `.NETCoreApp,Version=v1.0` usw. Andere unterstützte Werte sind `Framework35`, `Framework40`, `Framework45` und `FrameworkCore10`.</span><span class="sxs-lookup"><span data-stu-id="23790-121">Examples of valid values are `.NETFramework,Version=v4.6`, `.NETCoreApp,Version=v1.0`, etc. Other supported values are `Framework35`, `Framework40`, `Framework45`, and `FrameworkCore10`.</span></span>

`--Parallel|/Parallel`

<span data-ttu-id="23790-122">Führt Tests parallel aus.</span><span class="sxs-lookup"><span data-stu-id="23790-122">Execute tests in parallel.</span></span> <span data-ttu-id="23790-123">Standardmäßig stehen alle verfügbaren Kerne auf dem Computer zur Nutzung zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="23790-123">By default, all available cores on the machine are available for use.</span></span> <span data-ttu-id="23790-124">Legt eine explizite Zahl an Kernen mit einer Einstellungsdatei fest.</span><span class="sxs-lookup"><span data-stu-id="23790-124">Set an explicit number of cores with a settings file.</span></span>

`--TestCaseFilter|/TestCaseFilter:<Expression>`

<span data-ttu-id="23790-125">Führt Tests aus, die mit dem angegebenen Ausdruck übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="23790-125">Run tests that match the given expression.</span></span> <span data-ttu-id="23790-126">`<Expression>` hat das Format `<property>Operator<value>[|&<Expression>]`, wobei der Operator `=`, `!=`, oder `~` ist.</span><span class="sxs-lookup"><span data-stu-id="23790-126">`<Expression>` is of the format `<property>Operator<value>[|&<Expression>]`, where Operator is one of `=`, `!=`, or `~`.</span></span>  <span data-ttu-id="23790-127">Operator `~` verfügt über „contains“-Semantik und gilt für Zeichenfolgeneigenschaften wie `DisplayName`.</span><span class="sxs-lookup"><span data-stu-id="23790-127">Operator `~` has 'contains' semantics and is applicable for string properties like `DisplayName`.</span></span> <span data-ttu-id="23790-128">Klammern `()` werden verwendet, um untergeordnete Ausdrücke zu gruppieren.</span><span class="sxs-lookup"><span data-stu-id="23790-128">Parenthesis `()` are used to group sub-expressions.</span></span>

`-?|--Help|/?|/Help`

<span data-ttu-id="23790-129">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="23790-129">Prints out a short help for the command.</span></span>

`--logger|/logger:<Logger Uri/FriendlyName>`

<span data-ttu-id="23790-130">Geben Sie eine Protokollierung für die Testergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="23790-130">Specify a logger for test results.</span></span>  

* <span data-ttu-id="23790-131">Verwenden Sie den `TfsPublisher`-Protokollierungsanbieter zum Veröffentlichen von Testergebnissen in Team Foundation Server:</span><span class="sxs-lookup"><span data-stu-id="23790-131">To publish test results to Team Foundation Server, use the `TfsPublisher` logger provider:</span></span>

  ```
  /logger:TfsPublisher;
      Collection=<team project collection url>;
      BuildName=<build name>;
      TeamProject=<team project name>
      [;Platform=<Defaults to "Any CPU">]
      [;Flavor=<Defaults to "Debug">]
      [;RunTitle=<title>]
  ```

* <span data-ttu-id="23790-132">Verwenden Sie zum Protokollieren von Ergebnissen in einer Visual Studio-Testergebnisdatei (TRX) den `trx`-Protokollierungsanbieter.</span><span class="sxs-lookup"><span data-stu-id="23790-132">To log results to a Visual Studio Test Results File (TRX), use the `trx` logger provider.</span></span> <span data-ttu-id="23790-133">Dieser Schalter erstellt eine Datei im Verzeichnis mit den Testergebnissen mit dem angegebenen Protokolldateinamen.</span><span class="sxs-lookup"><span data-stu-id="23790-133">This switch creates a file in the test results directory with given log file name.</span></span> <span data-ttu-id="23790-134">Wenn `LogFileName` nicht angegeben wird, wird ein eindeutiger Dateiname erstellt, um die Testergebnisse aufzunehmen.</span><span class="sxs-lookup"><span data-stu-id="23790-134">If `LogFileName` isn't provided, a unique file name is created to hold the test results.</span></span>

  ```
  /logger:trx [;LogFileName=<Defaults to unique file name>]
  ```

`-lt|--ListTests|/lt|/ListTests:<File Name>`

<span data-ttu-id="23790-135">Listet gefundene Tests aus dem angegebenen Testcontainer auf.</span><span class="sxs-lookup"><span data-stu-id="23790-135">Lists discovered tests from the given test container.</span></span>

`--ParentProcessId|/ParentProcessId:<ParentProcessId>`

<span data-ttu-id="23790-136">Prozess-ID des übergeordneten Prozesses, der für den Start des aktuellen Prozesses verantwortlich ist.</span><span class="sxs-lookup"><span data-stu-id="23790-136">Process Id of the parent process responsible for launching the current process.</span></span>

`--Port|/Port:<Port>`

<span data-ttu-id="23790-137">Gibt den Port für die Socketverbindung an und empfängt die Ereignismeldungen.</span><span class="sxs-lookup"><span data-stu-id="23790-137">Specifies the port for the socket connection and receiving the event messages.</span></span>

`--Diag|/Diag:<Path to log file>`

<span data-ttu-id="23790-138">Aktiviert die ausführlichen Protokolle für die Testplattform.</span><span class="sxs-lookup"><span data-stu-id="23790-138">Enables verbose logs for the test platform.</span></span> <span data-ttu-id="23790-139">Protokolle werden in die angegebene Datei geschrieben.</span><span class="sxs-lookup"><span data-stu-id="23790-139">Logs are written to the provided file.</span></span>

`args`

<span data-ttu-id="23790-140">Gibt zusätzliche Argumente an, die an den Adapter übergeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="23790-140">Specifies extra arguments to pass to the adapter.</span></span> <span data-ttu-id="23790-141">Argumente werden als Name-Wert-Paare des Formulars `<n>=<v>` angegeben, wobei `<n>` der Argumentname und `<v>` der Argumentwert ist.</span><span class="sxs-lookup"><span data-stu-id="23790-141">Arguments are specified as name-value pairs of the form `<n>=<v>`, where `<n>` is the argument name and `<v>` is the argument value.</span></span> <span data-ttu-id="23790-142">Trennt mehrere Argumente durch Leerzeichen.</span><span class="sxs-lookup"><span data-stu-id="23790-142">Use a space to separate multiple arguments.</span></span>

## <a name="examples"></a><span data-ttu-id="23790-143">Beispiele</span><span class="sxs-lookup"><span data-stu-id="23790-143">Examples</span></span>

<span data-ttu-id="23790-144">Führt Tests in `mytestproject.dll` aus:</span><span class="sxs-lookup"><span data-stu-id="23790-144">Run tests in `mytestproject.dll`:</span></span>

`dotnet vstest mytestproject.dll`

<span data-ttu-id="23790-145">Führt Tests in `mytestproject.dll` und `myothertestproject.exe` aus:</span><span class="sxs-lookup"><span data-stu-id="23790-145">Run tests in `mytestproject.dll` and `myothertestproject.exe`:</span></span>

`dotnet vstest mytestproject.dll myothertestproject.exe`

<span data-ttu-id="23790-146">Führt `TestMethod1`-Tests aus:</span><span class="sxs-lookup"><span data-stu-id="23790-146">Run `TestMethod1` tests:</span></span>

`dotnet vstest /Tests:TestMethod1`

<span data-ttu-id="23790-147">Führt `TestMethod1`- und `TestMethod2`-Tests aus:</span><span class="sxs-lookup"><span data-stu-id="23790-147">Run `TestMethod1` and `TestMethod2` tests:</span></span>

`dotnet vstest /Tests:TestMethod1,TestMethod2`

