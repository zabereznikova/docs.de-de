---
title: dotnet test-Befehl – .NET Core-CLI
description: Der Befehl „dotnet test“ wird zum Ausführen von Unittests in einem bestimmten Projekt verwendet.
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.openlocfilehash: d85ca0bf75baa94e63358bd66d11bc29e8b9284b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="dotnet-test"></a><span data-ttu-id="70472-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="70472-103">dotnet test</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="70472-104">name</span><span class="sxs-lookup"><span data-stu-id="70472-104">Name</span></span>

<span data-ttu-id="70472-105">`dotnet test`: .NET-Testtreiber, der verwendet wird, um Komponententests auszuführen.</span><span class="sxs-lookup"><span data-stu-id="70472-105">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="70472-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="70472-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="70472-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="70472-107">.NET Core 2.x</span></span>](#tab/netcore2x)


```
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter] [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] [-v|--verbosity]
dotnet test [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="70472-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="70472-108">.NET Core 1.x</span></span>](#tab/netcore1x)

```
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [-d|--diag] [-f|--framework] [--filter] [-l|--logger] [--no-build] [-o|--output] [-s|--settings] [-t|--list-tests]  [-v|--verbosity]
dotnet test [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="70472-109">description</span><span class="sxs-lookup"><span data-stu-id="70472-109">Description</span></span>

<span data-ttu-id="70472-110">Der Befehl `dotnet test` wird zum Ausführen von Komponententests in einem bestimmten Projekt verwendet.</span><span class="sxs-lookup"><span data-stu-id="70472-110">The `dotnet test` command is used to execute unit tests in a given project.</span></span> <span data-ttu-id="70472-111">Mit dem `dotnet test`-Befehl wird die Testlauf-Konsolenanwendung gestartet, die für ein Projekt angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="70472-111">The `dotnet test` command launches the test runner console application specified for a project.</span></span> <span data-ttu-id="70472-112">Durch den Testlauf werden Tests ausgeführt, die für ein Komponententestframework (z.B. MSTest, NUnit oder xUnit) definiert wurden, und der Erfolg oder Misserfolg der einzelnen Testausführungen wird gemeldet.</span><span class="sxs-lookup"><span data-stu-id="70472-112">The test runner executes the tests defined for a unit test framework (for example, MSTest, NUnit, or xUnit) and reports the success or failure of each test.</span></span> <span data-ttu-id="70472-113">Der Testlauf und die Komponententestbibliothek werden als NuGet-Pakete gepackt und als gewöhnliche Abhängigkeiten für das Projekt wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="70472-113">The test runner and the unit test library are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="70472-114">In Testprojekten wird der Testlauf mittels eines normalen `<PackageReference>`-Elements angegeben, wie in der folgenden Beispielprojektdatei gezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="70472-114">Test projects specify the test runner using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

## <a name="arguments"></a><span data-ttu-id="70472-115">Argumente</span><span class="sxs-lookup"><span data-stu-id="70472-115">Arguments</span></span>

`PROJECT`

<span data-ttu-id="70472-116">Gibt den Pfad des Testprojekts an.</span><span class="sxs-lookup"><span data-stu-id="70472-116">Specifies a path to the test project.</span></span> <span data-ttu-id="70472-117">Wenn nicht angegeben, wird standardmäßig das aktuelle Verzeichnis angegeben.</span><span class="sxs-lookup"><span data-stu-id="70472-117">If omitted, it defaults to current directory.</span></span>

## <a name="options"></a><span data-ttu-id="70472-118">Optionen</span><span class="sxs-lookup"><span data-stu-id="70472-118">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="70472-119">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="70472-119">.NET Core 2.x</span></span>](#tab/netcore2x)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="70472-120">Verwenden Sie die benutzerdefinierten Testadapter aus dem angegebenen Pfad im Testlauf.</span><span class="sxs-lookup"><span data-stu-id="70472-120">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="70472-121">Legt die Buildkonfiguration fest.</span><span class="sxs-lookup"><span data-stu-id="70472-121">Defines the build configuration.</span></span> <span data-ttu-id="70472-122">Der Standardwert ist `Debug`, aber die Konfiguration des Projekts könnte diese SDK-Standardeinstellung überschreiben.</span><span class="sxs-lookup"><span data-stu-id="70472-122">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

<span data-ttu-id="70472-123">Aktiviert den Datensammler für den Testlauf.</span><span class="sxs-lookup"><span data-stu-id="70472-123">Enables data collector for the test run.</span></span> <span data-ttu-id="70472-124">Weitere Informationen finden Sie unter [Monitor and analyze test run (Überwachen und Analysieren eines Testlaufs)](https://aka.ms/vstest-collect).</span><span class="sxs-lookup"><span data-stu-id="70472-124">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="70472-125">Aktiviert den Diagnosemodus für die Testplattform und schreibt Diagnosemeldungen in die angegebene Datei.</span><span class="sxs-lookup"><span data-stu-id="70472-125">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="70472-126">Sucht nach Testbinärdateien für ein bestimmtes [Framework](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="70472-126">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="70472-127">Filtert Tests im aktuellen Projekt mithilfe des angegebenen Ausdrucks heraus.</span><span class="sxs-lookup"><span data-stu-id="70472-127">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="70472-128">Weitere Informationen finden Sie im Abschnitt [Details zu Filteroptionen](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="70472-128">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="70472-129">Weitere Informationen und Beispiele für die Verwendung der selektiven Komponententestfilterung finden Sie unter [Ausführen von selektiven Komponententests](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="70472-129">For additional information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="70472-130">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="70472-130">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="70472-131">Gibt eine Protokollierung für die Testergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="70472-131">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="70472-132">Erstellt das Testprojekt nicht vor der Ausführung.</span><span class="sxs-lookup"><span data-stu-id="70472-132">Does not build the test project prior to running it.</span></span>

`--no-restore`

<span data-ttu-id="70472-133">Führt kein implizites Wiederherstellen durch, wenn der Befehl ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="70472-133">Doesn't perform an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="70472-134">Verzeichnis, in dem die auszuführenden Binärdateien zu finden sind.</span><span class="sxs-lookup"><span data-stu-id="70472-134">Directory in which to find the binaries to run.</span></span>

`-r|--results-directory <PATH>`

<span data-ttu-id="70472-135">Das Verzeichnis, in dem die Testergebnisse gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="70472-135">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="70472-136">Das angegebene Verzeichnis wird erstellt, wenn es noch nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="70472-136">The specified directory will be created if it doesn't exist.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="70472-137">Einstellungen, die beim Ausführen von Tests verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="70472-137">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="70472-138">Listen Sie alle ermittelten Tests im aktuellen Projekt auf.</span><span class="sxs-lookup"><span data-stu-id="70472-138">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="70472-139">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="70472-139">Sets the verbosity level of the command.</span></span> <span data-ttu-id="70472-140">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="70472-140">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="70472-141">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="70472-141">.NET Core 1.x</span></span>](#tab/netcore1x)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="70472-142">Verwenden Sie die benutzerdefinierten Testadapter aus dem angegebenen Pfad im Testlauf.</span><span class="sxs-lookup"><span data-stu-id="70472-142">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="70472-143">Legt die Buildkonfiguration fest.</span><span class="sxs-lookup"><span data-stu-id="70472-143">Defines the build configuration.</span></span> <span data-ttu-id="70472-144">Der Standardwert ist `Debug`, aber die Konfiguration des Projekts könnte diese SDK-Standardeinstellung überschreiben.</span><span class="sxs-lookup"><span data-stu-id="70472-144">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="70472-145">Aktiviert den Diagnosemodus für die Testplattform und schreibt Diagnosemeldungen in die angegebene Datei.</span><span class="sxs-lookup"><span data-stu-id="70472-145">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="70472-146">Sucht nach Testbinärdateien für ein bestimmtes [Framework](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="70472-146">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="70472-147">Filtert Tests im aktuellen Projekt mithilfe des angegebenen Ausdrucks heraus.</span><span class="sxs-lookup"><span data-stu-id="70472-147">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="70472-148">Weitere Informationen finden Sie im Abschnitt [Details zu Filteroptionen](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="70472-148">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="70472-149">Weitere Informationen und Beispiele für die Verwendung der selektiven Komponententestfilterung finden Sie unter [Ausführen von selektiven Komponententests](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="70472-149">For additional information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="70472-150">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="70472-150">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="70472-151">Gibt eine Protokollierung für die Testergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="70472-151">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="70472-152">Erstellt das Testprojekt nicht vor der Ausführung.</span><span class="sxs-lookup"><span data-stu-id="70472-152">Does not build the test project prior to running it.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="70472-153">Verzeichnis, in dem die auszuführenden Binärdateien zu finden sind.</span><span class="sxs-lookup"><span data-stu-id="70472-153">Directory in which to find the binaries to run.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="70472-154">Einstellungen, die beim Ausführen von Tests verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="70472-154">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="70472-155">Listen Sie alle ermittelten Tests im aktuellen Projekt auf.</span><span class="sxs-lookup"><span data-stu-id="70472-155">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="70472-156">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="70472-156">Sets the verbosity level of the command.</span></span> <span data-ttu-id="70472-157">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="70472-157">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="70472-158">Beispiele</span><span class="sxs-lookup"><span data-stu-id="70472-158">Examples</span></span>

<span data-ttu-id="70472-159">Führen Sie die Tests im Projekt im aktuellen Verzeichnis durch:</span><span class="sxs-lookup"><span data-stu-id="70472-159">Run the tests in the project in the current directory:</span></span>

`dotnet test`

<span data-ttu-id="70472-160">Führen Sie die Tests im Projekt `test1` durch:</span><span class="sxs-lookup"><span data-stu-id="70472-160">Run the tests in the `test1` project:</span></span>

`dotnet test ~/projects/test1/test1.csproj`

## <a name="filter-option-details"></a><span data-ttu-id="70472-161">Details zu Filteroptionen</span><span class="sxs-lookup"><span data-stu-id="70472-161">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="70472-162">`<Expression>` weist das Format `<property><operator><value>[|&<Expression>]` auf.</span><span class="sxs-lookup"><span data-stu-id="70472-162">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="70472-163">`<property>` ist ein Attribut von `Test Case`.</span><span class="sxs-lookup"><span data-stu-id="70472-163">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="70472-164">Im Folgenden werden die Eigenschaften aufgeführt, die von gängigen Frameworks für Komponententests unterstützt werden:</span><span class="sxs-lookup"><span data-stu-id="70472-164">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="70472-165">Testframework</span><span class="sxs-lookup"><span data-stu-id="70472-165">Test Framework</span></span> | <span data-ttu-id="70472-166">Unterstützte Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="70472-166">Supported properties</span></span>                                                                                      |
| :------------: | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="70472-167">MSTest</span><span class="sxs-lookup"><span data-stu-id="70472-167">MSTest</span></span>         | <ul><li><span data-ttu-id="70472-168">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="70472-168">FullyQualifiedName</span></span></li><li><span data-ttu-id="70472-169">name</span><span class="sxs-lookup"><span data-stu-id="70472-169">Name</span></span></li><li><span data-ttu-id="70472-170">ClassName</span><span class="sxs-lookup"><span data-stu-id="70472-170">ClassName</span></span></li><li><span data-ttu-id="70472-171">Priorität</span><span class="sxs-lookup"><span data-stu-id="70472-171">Priority</span></span></li><li><span data-ttu-id="70472-172">TestCategory</span><span class="sxs-lookup"><span data-stu-id="70472-172">TestCategory</span></span></li></ul> |
| <span data-ttu-id="70472-173">Xunit</span><span class="sxs-lookup"><span data-stu-id="70472-173">Xunit</span></span>          | <ul><li><span data-ttu-id="70472-174">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="70472-174">FullyQualifiedName</span></span></li><li><span data-ttu-id="70472-175">DisplayName</span><span class="sxs-lookup"><span data-stu-id="70472-175">DisplayName</span></span></li><li><span data-ttu-id="70472-176">Merkmale</span><span class="sxs-lookup"><span data-stu-id="70472-176">Traits</span></span></li></ul>                                   |

<span data-ttu-id="70472-177">`<operator>` beschreibt die Beziehung zwischen der Eigenschaft und dem Wert:</span><span class="sxs-lookup"><span data-stu-id="70472-177">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="70472-178">Operator</span><span class="sxs-lookup"><span data-stu-id="70472-178">Operator</span></span> | <span data-ttu-id="70472-179">Funktion</span><span class="sxs-lookup"><span data-stu-id="70472-179">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="70472-180">Genaue Übereinstimmung</span><span class="sxs-lookup"><span data-stu-id="70472-180">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="70472-181">Keine genaue Übereinstimmung</span><span class="sxs-lookup"><span data-stu-id="70472-181">Not exact match</span></span> |
| `~`      | <span data-ttu-id="70472-182">Enthält</span><span class="sxs-lookup"><span data-stu-id="70472-182">Contains</span></span>        |

<span data-ttu-id="70472-183">`<value>` ist eine Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="70472-183">`<value>` is a string.</span></span> <span data-ttu-id="70472-184">Bei allen Suchvorgängen ist die Groß-/Kleinschreibung nicht relevant.</span><span class="sxs-lookup"><span data-stu-id="70472-184">All the lookups are case insensitive.</span></span>

<span data-ttu-id="70472-185">Ein Ausdruck ohne `<operator>` gilt automatisch als `contains` für die `FullyQualifiedName`-Eigenschaft (`dotnet test --filter xyz` ist beispielsweise identisch mit `dotnet test --filter FullyQualifiedName~xyz`).</span><span class="sxs-lookup"><span data-stu-id="70472-185">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="70472-186">Ausdrücke können mit bedingten Operatoren verknüpft werden:</span><span class="sxs-lookup"><span data-stu-id="70472-186">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="70472-187">Operator</span><span class="sxs-lookup"><span data-stu-id="70472-187">Operator</span></span> | <span data-ttu-id="70472-188">Funktion</span><span class="sxs-lookup"><span data-stu-id="70472-188">Function</span></span> |
| :------: | :------: |
| <code>&#124;</code>      | <span data-ttu-id="70472-189">ODER</span><span class="sxs-lookup"><span data-stu-id="70472-189">OR</span></span>       |
| `&`      | <span data-ttu-id="70472-190">UND</span><span class="sxs-lookup"><span data-stu-id="70472-190">AND</span></span>      |

<span data-ttu-id="70472-191">Sie können Ausdrücke in Klammern einschließen, wenn Sie bedingte Operatoren verwenden (z.B. `(Name~TestMethod1) | (Name~TestMethod2)`).</span><span class="sxs-lookup"><span data-stu-id="70472-191">You can enclose expressions in parenthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="70472-192">Weitere Informationen und Beispiele für die Verwendung der selektiven Komponententestfilterung finden Sie unter [Ausführen von selektiven Komponententests](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="70472-192">For additional information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="70472-193">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="70472-193">See also</span></span>

 [<span data-ttu-id="70472-194">Frameworks und Ziele</span><span class="sxs-lookup"><span data-stu-id="70472-194">Frameworks and Targets</span></span>](../../standard/frameworks.md)  
 [<span data-ttu-id="70472-195">.NET Core Runtime-ID (RID)-Katalog</span><span class="sxs-lookup"><span data-stu-id="70472-195">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
