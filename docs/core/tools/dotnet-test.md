---
title: "dotnet test-Befehl – .NET Core-CLI"
description: "Der Befehl „dotnet test“ wird zum Ausführen von Unittests in einem bestimmten Projekt verwendet."
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.workload: dotnetcore
ms.openlocfilehash: fac5e3cb602f6dc5c06b1b29e9924ce4be7ae273
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="dotnet-test"></a><span data-ttu-id="9b295-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="9b295-103">dotnet test</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="9b295-104">name</span><span class="sxs-lookup"><span data-stu-id="9b295-104">Name</span></span>

<span data-ttu-id="9b295-105">`dotnet test`: .NET-Testtreiber, der verwendet wird, um Komponententests auszuführen.</span><span class="sxs-lookup"><span data-stu-id="9b295-105">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="9b295-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="9b295-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="9b295-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="9b295-107">.NET Core 2.x</span></span>](#tab/netcore2x)


```
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter] [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] [-v|--verbosity]
dotnet test [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="9b295-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="9b295-108">.NET Core 1.x</span></span>](#tab/netcore1x)

```
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [-d|--diag] [-f|--framework] [--filter] [-l|--logger] [--no-build] [-o|--output] [-s|--settings] [-t|--list-tests]  [-v|--verbosity]
dotnet test [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="9b295-109">description</span><span class="sxs-lookup"><span data-stu-id="9b295-109">Description</span></span>

<span data-ttu-id="9b295-110">Der Befehl `dotnet test` wird zum Ausführen von Komponententests in einem bestimmten Projekt verwendet.</span><span class="sxs-lookup"><span data-stu-id="9b295-110">The `dotnet test` command is used to execute unit tests in a given project.</span></span> <span data-ttu-id="9b295-111">Komponententests sind Konsolenanwendungsprojekte, die Abhängigkeiten vom Komponententest-Framework (z.B. MSTest, NUnit oder xUnit) und dotnet-Test Runner für das Komponententest-Framework aufweisen.</span><span class="sxs-lookup"><span data-stu-id="9b295-111">Unit tests are console application projects that have dependencies on the unit test framework (for example, MSTest, NUnit, or xUnit) and the dotnet test runner for the unit testing framework.</span></span> <span data-ttu-id="9b295-112">Sie werden als NuGet-Pakete verpackt und als gewöhnliche Abhängigkeiten für das Projekt wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="9b295-112">These are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="9b295-113">Testprojekte müssen auch den Test Runner angeben.</span><span class="sxs-lookup"><span data-stu-id="9b295-113">Test projects also must specify the test runner.</span></span> <span data-ttu-id="9b295-114">Dieser wird mit einem normalen `<PackageReference>`-Element angegeben, wie in der folgenden Beispielprojektdatei gezeigt:</span><span class="sxs-lookup"><span data-stu-id="9b295-114">This is specified using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

## <a name="arguments"></a><span data-ttu-id="9b295-115">Argumente</span><span class="sxs-lookup"><span data-stu-id="9b295-115">Arguments</span></span>

`PROJECT`

<span data-ttu-id="9b295-116">Gibt den Pfad des Testprojekts an.</span><span class="sxs-lookup"><span data-stu-id="9b295-116">Specifies a path to the test project.</span></span> <span data-ttu-id="9b295-117">Wenn nicht angegeben, wird standardmäßig das aktuelle Verzeichnis angegeben.</span><span class="sxs-lookup"><span data-stu-id="9b295-117">If omitted, it defaults to current directory.</span></span>

## <a name="options"></a><span data-ttu-id="9b295-118">Optionen</span><span class="sxs-lookup"><span data-stu-id="9b295-118">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="9b295-119">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="9b295-119">.NET Core 2.x</span></span>](#tab/netcore2x)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="9b295-120">Verwenden Sie die benutzerdefinierten Testadapter aus dem angegebenen Pfad im Testlauf.</span><span class="sxs-lookup"><span data-stu-id="9b295-120">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="9b295-121">Legt die Buildkonfiguration fest.</span><span class="sxs-lookup"><span data-stu-id="9b295-121">Defines the build configuration.</span></span> <span data-ttu-id="9b295-122">Der Standardwert ist `Debug`, aber die Konfiguration des Projekts könnte diese SDK-Standardeinstellung überschreiben.</span><span class="sxs-lookup"><span data-stu-id="9b295-122">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

<span data-ttu-id="9b295-123">Aktiviert den Datensammler für den Testlauf.</span><span class="sxs-lookup"><span data-stu-id="9b295-123">Enables data collector for the test run.</span></span> <span data-ttu-id="9b295-124">Weitere Informationen finden Sie unter [Monitor and analyze test run (Überwachen und Analysieren eines Testlaufs)](https://aka.ms/vstest-collect).</span><span class="sxs-lookup"><span data-stu-id="9b295-124">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="9b295-125">Aktiviert den Diagnosemodus für die Testplattform und schreibt Diagnosemeldungen in die angegebene Datei.</span><span class="sxs-lookup"><span data-stu-id="9b295-125">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="9b295-126">Sucht nach Testbinärdateien für ein bestimmtes [Framework](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="9b295-126">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="9b295-127">Filtert Tests im aktuellen Projekt mithilfe des angegebenen Ausdrucks heraus.</span><span class="sxs-lookup"><span data-stu-id="9b295-127">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="9b295-128">Weitere Informationen finden Sie im Abschnitt [Details zu Filteroptionen](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="9b295-128">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="9b295-129">Weitere Informationen und Beispiele für die Verwendung der selektiven Komponententestfilterung finden Sie unter [Ausführen von selektiven Komponententests](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="9b295-129">For additional information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="9b295-130">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="9b295-130">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="9b295-131">Gibt eine Protokollierung für die Testergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="9b295-131">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="9b295-132">Erstellt das Testprojekt nicht vor der Ausführung.</span><span class="sxs-lookup"><span data-stu-id="9b295-132">Does not build the test project prior to running it.</span></span>

`--no-restore`

<span data-ttu-id="9b295-133">Führt kein implizites Wiederherstellen durch, wenn der Befehl ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="9b295-133">Doesn't perform an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="9b295-134">Verzeichnis, in dem die auszuführenden Binärdateien zu finden sind.</span><span class="sxs-lookup"><span data-stu-id="9b295-134">Directory in which to find the binaries to run.</span></span>

`-r|--results-directory <PATH>`

<span data-ttu-id="9b295-135">Das Verzeichnis, in dem die Testergebnisse gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="9b295-135">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="9b295-136">Das angegebene Verzeichnis wird erstellt, wenn es noch nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="9b295-136">The specified directory will be created if it doesn't exist.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="9b295-137">Einstellungen, die beim Ausführen von Tests verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9b295-137">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="9b295-138">Listen Sie alle ermittelten Tests im aktuellen Projekt auf.</span><span class="sxs-lookup"><span data-stu-id="9b295-138">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="9b295-139">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="9b295-139">Sets the verbosity level of the command.</span></span> <span data-ttu-id="9b295-140">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="9b295-140">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="9b295-141">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="9b295-141">.NET Core 1.x</span></span>](#tab/netcore1x)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="9b295-142">Verwenden Sie die benutzerdefinierten Testadapter aus dem angegebenen Pfad im Testlauf.</span><span class="sxs-lookup"><span data-stu-id="9b295-142">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="9b295-143">Legt die Buildkonfiguration fest.</span><span class="sxs-lookup"><span data-stu-id="9b295-143">Defines the build configuration.</span></span> <span data-ttu-id="9b295-144">Der Standardwert ist `Debug`, aber die Konfiguration des Projekts könnte diese SDK-Standardeinstellung überschreiben.</span><span class="sxs-lookup"><span data-stu-id="9b295-144">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="9b295-145">Aktiviert den Diagnosemodus für die Testplattform und schreibt Diagnosemeldungen in die angegebene Datei.</span><span class="sxs-lookup"><span data-stu-id="9b295-145">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="9b295-146">Sucht nach Testbinärdateien für ein bestimmtes [Framework](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="9b295-146">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="9b295-147">Filtert Tests im aktuellen Projekt mithilfe des angegebenen Ausdrucks heraus.</span><span class="sxs-lookup"><span data-stu-id="9b295-147">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="9b295-148">Weitere Informationen finden Sie im Abschnitt [Details zu Filteroptionen](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="9b295-148">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="9b295-149">Weitere Informationen und Beispiele für die Verwendung der selektiven Komponententestfilterung finden Sie unter [Ausführen von selektiven Komponententests](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="9b295-149">For additional information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="9b295-150">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="9b295-150">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="9b295-151">Gibt eine Protokollierung für die Testergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="9b295-151">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="9b295-152">Erstellt das Testprojekt nicht vor der Ausführung.</span><span class="sxs-lookup"><span data-stu-id="9b295-152">Does not build the test project prior to running it.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="9b295-153">Verzeichnis, in dem die auszuführenden Binärdateien zu finden sind.</span><span class="sxs-lookup"><span data-stu-id="9b295-153">Directory in which to find the binaries to run.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="9b295-154">Einstellungen, die beim Ausführen von Tests verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9b295-154">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="9b295-155">Listen Sie alle ermittelten Tests im aktuellen Projekt auf.</span><span class="sxs-lookup"><span data-stu-id="9b295-155">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="9b295-156">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="9b295-156">Sets the verbosity level of the command.</span></span> <span data-ttu-id="9b295-157">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="9b295-157">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="9b295-158">Beispiele</span><span class="sxs-lookup"><span data-stu-id="9b295-158">Examples</span></span>

<span data-ttu-id="9b295-159">Führen Sie die Tests im Projekt im aktuellen Verzeichnis durch:</span><span class="sxs-lookup"><span data-stu-id="9b295-159">Run the tests in the project in the current directory:</span></span>

`dotnet test`

<span data-ttu-id="9b295-160">Führen Sie die Tests im Projekt `test1` durch:</span><span class="sxs-lookup"><span data-stu-id="9b295-160">Run the tests in the `test1` project:</span></span>

`dotnet test ~/projects/test1/test1.csproj`

## <a name="filter-option-details"></a><span data-ttu-id="9b295-161">Details zu Filteroptionen</span><span class="sxs-lookup"><span data-stu-id="9b295-161">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="9b295-162">`<Expression>` weist das Format `<property><operator><value>[|&<Expression>]` auf.</span><span class="sxs-lookup"><span data-stu-id="9b295-162">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="9b295-163">`<property>` ist ein Attribut von `Test Case`.</span><span class="sxs-lookup"><span data-stu-id="9b295-163">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="9b295-164">Im Folgenden werden die Eigenschaften aufgeführt, die von gängigen Frameworks für Komponententests unterstützt werden:</span><span class="sxs-lookup"><span data-stu-id="9b295-164">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="9b295-165">Testframework</span><span class="sxs-lookup"><span data-stu-id="9b295-165">Test Framework</span></span> | <span data-ttu-id="9b295-166">Unterstützte Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="9b295-166">Supported properties</span></span>                                                                                      |
| :------------: | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="9b295-167">MSTest</span><span class="sxs-lookup"><span data-stu-id="9b295-167">MSTest</span></span>         | <ul><li><span data-ttu-id="9b295-168">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="9b295-168">FullyQualifiedName</span></span></li><li><span data-ttu-id="9b295-169">name</span><span class="sxs-lookup"><span data-stu-id="9b295-169">Name</span></span></li><li><span data-ttu-id="9b295-170">ClassName</span><span class="sxs-lookup"><span data-stu-id="9b295-170">ClassName</span></span></li><li><span data-ttu-id="9b295-171">Priorität</span><span class="sxs-lookup"><span data-stu-id="9b295-171">Priority</span></span></li><li><span data-ttu-id="9b295-172">TestCategory</span><span class="sxs-lookup"><span data-stu-id="9b295-172">TestCategory</span></span></li></ul> |
| <span data-ttu-id="9b295-173">Xunit</span><span class="sxs-lookup"><span data-stu-id="9b295-173">Xunit</span></span>          | <ul><li><span data-ttu-id="9b295-174">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="9b295-174">FullyQualifiedName</span></span></li><li><span data-ttu-id="9b295-175">DisplayName</span><span class="sxs-lookup"><span data-stu-id="9b295-175">DisplayName</span></span></li><li><span data-ttu-id="9b295-176">Merkmale</span><span class="sxs-lookup"><span data-stu-id="9b295-176">Traits</span></span></li></ul>                                   |

<span data-ttu-id="9b295-177">`<operator>` beschreibt die Beziehung zwischen der Eigenschaft und dem Wert:</span><span class="sxs-lookup"><span data-stu-id="9b295-177">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="9b295-178">Operator</span><span class="sxs-lookup"><span data-stu-id="9b295-178">Operator</span></span> | <span data-ttu-id="9b295-179">Funktion</span><span class="sxs-lookup"><span data-stu-id="9b295-179">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="9b295-180">Genaue Übereinstimmung</span><span class="sxs-lookup"><span data-stu-id="9b295-180">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="9b295-181">Keine genaue Übereinstimmung</span><span class="sxs-lookup"><span data-stu-id="9b295-181">Not exact match</span></span> |
| `~`      | <span data-ttu-id="9b295-182">Enthält</span><span class="sxs-lookup"><span data-stu-id="9b295-182">Contains</span></span>        |

<span data-ttu-id="9b295-183">`<value>` ist eine Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="9b295-183">`<value>` is a string.</span></span> <span data-ttu-id="9b295-184">Bei allen Suchvorgängen ist die Groß-/Kleinschreibung nicht relevant.</span><span class="sxs-lookup"><span data-stu-id="9b295-184">All the lookups are case insensitive.</span></span>

<span data-ttu-id="9b295-185">Ein Ausdruck ohne `<operator>` gilt automatisch als `contains` für die `FullyQualifiedName`-Eigenschaft (`dotnet test --filter xyz` ist beispielsweise identisch mit `dotnet test --filter FullyQualifiedName~xyz`).</span><span class="sxs-lookup"><span data-stu-id="9b295-185">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="9b295-186">Ausdrücke können mit bedingten Operatoren verknüpft werden:</span><span class="sxs-lookup"><span data-stu-id="9b295-186">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="9b295-187">Operator</span><span class="sxs-lookup"><span data-stu-id="9b295-187">Operator</span></span> | <span data-ttu-id="9b295-188">Funktion</span><span class="sxs-lookup"><span data-stu-id="9b295-188">Function</span></span> |
| :------: | :------: |
| <code>&#124;</code>      | <span data-ttu-id="9b295-189">ODER</span><span class="sxs-lookup"><span data-stu-id="9b295-189">OR</span></span>       |
| `&`      | <span data-ttu-id="9b295-190">UND</span><span class="sxs-lookup"><span data-stu-id="9b295-190">AND</span></span>      |

<span data-ttu-id="9b295-191">Sie können Ausdrücke in Klammern einschließen, wenn Sie bedingte Operatoren verwenden (z.B. `(Name~TestMethod1) | (Name~TestMethod2)`).</span><span class="sxs-lookup"><span data-stu-id="9b295-191">You can enclose expressions in parenthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="9b295-192">Weitere Informationen und Beispiele für die Verwendung der selektiven Komponententestfilterung finden Sie unter [Ausführen von selektiven Komponententests](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="9b295-192">For additional information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9b295-193">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9b295-193">See also</span></span>

 [<span data-ttu-id="9b295-194">Frameworks und Ziele</span><span class="sxs-lookup"><span data-stu-id="9b295-194">Frameworks and Targets</span></span>](../../standard/frameworks.md)  
 [<span data-ttu-id="9b295-195">.NET Core Runtime-ID (RID)-Katalog</span><span class="sxs-lookup"><span data-stu-id="9b295-195">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
