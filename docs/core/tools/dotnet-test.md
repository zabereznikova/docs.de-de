---
title: dotnet test-Befehl – .NET Core-CLI
description: Der Befehl „dotnet test“ wird zum Ausführen von Unittests in einem bestimmten Projekt verwendet.
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.workload:
- dotnetcore
ms.openlocfilehash: 6102281c4daf149f31e65ef8360831fe9e0ef4f6
ms.sourcegitcommit: 935d5267c44f9bce801468ef95f44572f1417e8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="dotnet-test"></a><span data-ttu-id="c44cf-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="c44cf-103">dotnet test</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="c44cf-104">name</span><span class="sxs-lookup"><span data-stu-id="c44cf-104">Name</span></span>

<span data-ttu-id="c44cf-105">`dotnet test`: .NET-Testtreiber, der verwendet wird, um Komponententests auszuführen.</span><span class="sxs-lookup"><span data-stu-id="c44cf-105">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="c44cf-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="c44cf-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="c44cf-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="c44cf-107">.NET Core 2.x</span></span>](#tab/netcore2x)


```
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter] [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] [-v|--verbosity]
dotnet test [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="c44cf-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="c44cf-108">.NET Core 1.x</span></span>](#tab/netcore1x)

```
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [-d|--diag] [-f|--framework] [--filter] [-l|--logger] [--no-build] [-o|--output] [-s|--settings] [-t|--list-tests]  [-v|--verbosity]
dotnet test [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="c44cf-109">description</span><span class="sxs-lookup"><span data-stu-id="c44cf-109">Description</span></span>

<span data-ttu-id="c44cf-110">Der Befehl `dotnet test` wird zum Ausführen von Komponententests in einem bestimmten Projekt verwendet.</span><span class="sxs-lookup"><span data-stu-id="c44cf-110">The `dotnet test` command is used to execute unit tests in a given project.</span></span> <span data-ttu-id="c44cf-111">Mit dem `dotnet test`-Befehl wird die Testlauf-Konsolenanwendung gestartet, die für ein Projekt angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="c44cf-111">The `dotnet test` command launches the test runner console application specified for a project.</span></span> <span data-ttu-id="c44cf-112">Durch den Testlauf werden Tests ausgeführt, die für ein Komponententestframework (z.B. MSTest, NUnit oder xUnit) definiert wurden, und der Erfolg oder Misserfolg der einzelnen Testausführungen wird gemeldet.</span><span class="sxs-lookup"><span data-stu-id="c44cf-112">The test runner executes the tests defined for a unit test framework (for example, MSTest, NUnit, or xUnit) and reports the success or failure of each test.</span></span> <span data-ttu-id="c44cf-113">Der Testlauf und die Komponententestbibliothek werden als NuGet-Pakete gepackt und als gewöhnliche Abhängigkeiten für das Projekt wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="c44cf-113">The test runner and the unit test library are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="c44cf-114">In Testprojekten wird der Testlauf mittels eines normalen `<PackageReference>`-Elements angegeben, wie in der folgenden Beispielprojektdatei gezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="c44cf-114">Test projects specify the test runner using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

## <a name="arguments"></a><span data-ttu-id="c44cf-115">Argumente</span><span class="sxs-lookup"><span data-stu-id="c44cf-115">Arguments</span></span>

`PROJECT`

<span data-ttu-id="c44cf-116">Gibt den Pfad des Testprojekts an.</span><span class="sxs-lookup"><span data-stu-id="c44cf-116">Specifies a path to the test project.</span></span> <span data-ttu-id="c44cf-117">Wenn nicht angegeben, wird standardmäßig das aktuelle Verzeichnis angegeben.</span><span class="sxs-lookup"><span data-stu-id="c44cf-117">If omitted, it defaults to current directory.</span></span>

## <a name="options"></a><span data-ttu-id="c44cf-118">Optionen</span><span class="sxs-lookup"><span data-stu-id="c44cf-118">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="c44cf-119">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="c44cf-119">.NET Core 2.x</span></span>](#tab/netcore2x)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="c44cf-120">Verwenden Sie die benutzerdefinierten Testadapter aus dem angegebenen Pfad im Testlauf.</span><span class="sxs-lookup"><span data-stu-id="c44cf-120">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="c44cf-121">Legt die Buildkonfiguration fest.</span><span class="sxs-lookup"><span data-stu-id="c44cf-121">Defines the build configuration.</span></span> <span data-ttu-id="c44cf-122">Der Standardwert ist `Debug`, aber die Konfiguration des Projekts könnte diese SDK-Standardeinstellung überschreiben.</span><span class="sxs-lookup"><span data-stu-id="c44cf-122">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

<span data-ttu-id="c44cf-123">Aktiviert den Datensammler für den Testlauf.</span><span class="sxs-lookup"><span data-stu-id="c44cf-123">Enables data collector for the test run.</span></span> <span data-ttu-id="c44cf-124">Weitere Informationen finden Sie unter [Monitor and analyze test run (Überwachen und Analysieren eines Testlaufs)](https://aka.ms/vstest-collect).</span><span class="sxs-lookup"><span data-stu-id="c44cf-124">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="c44cf-125">Aktiviert den Diagnosemodus für die Testplattform und schreibt Diagnosemeldungen in die angegebene Datei.</span><span class="sxs-lookup"><span data-stu-id="c44cf-125">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="c44cf-126">Sucht nach Testbinärdateien für ein bestimmtes [Framework](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="c44cf-126">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="c44cf-127">Filtert Tests im aktuellen Projekt mithilfe des angegebenen Ausdrucks heraus.</span><span class="sxs-lookup"><span data-stu-id="c44cf-127">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="c44cf-128">Weitere Informationen finden Sie im Abschnitt [Details zu Filteroptionen](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="c44cf-128">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="c44cf-129">Weitere Informationen und Beispiele für die Verwendung der selektiven Komponententestfilterung finden Sie unter [Ausführen von selektiven Komponententests](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="c44cf-129">For additional information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="c44cf-130">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="c44cf-130">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="c44cf-131">Gibt eine Protokollierung für die Testergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="c44cf-131">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="c44cf-132">Erstellt das Testprojekt nicht vor der Ausführung.</span><span class="sxs-lookup"><span data-stu-id="c44cf-132">Does not build the test project prior to running it.</span></span>

`--no-restore`

<span data-ttu-id="c44cf-133">Führt kein implizites Wiederherstellen durch, wenn der Befehl ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="c44cf-133">Doesn't perform an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="c44cf-134">Verzeichnis, in dem die auszuführenden Binärdateien zu finden sind.</span><span class="sxs-lookup"><span data-stu-id="c44cf-134">Directory in which to find the binaries to run.</span></span>

`-r|--results-directory <PATH>`

<span data-ttu-id="c44cf-135">Das Verzeichnis, in dem die Testergebnisse gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="c44cf-135">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="c44cf-136">Das angegebene Verzeichnis wird erstellt, wenn es noch nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="c44cf-136">The specified directory will be created if it doesn't exist.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="c44cf-137">Einstellungen, die beim Ausführen von Tests verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c44cf-137">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="c44cf-138">Listen Sie alle ermittelten Tests im aktuellen Projekt auf.</span><span class="sxs-lookup"><span data-stu-id="c44cf-138">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="c44cf-139">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="c44cf-139">Sets the verbosity level of the command.</span></span> <span data-ttu-id="c44cf-140">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="c44cf-140">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="c44cf-141">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="c44cf-141">.NET Core 1.x</span></span>](#tab/netcore1x)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="c44cf-142">Verwenden Sie die benutzerdefinierten Testadapter aus dem angegebenen Pfad im Testlauf.</span><span class="sxs-lookup"><span data-stu-id="c44cf-142">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="c44cf-143">Legt die Buildkonfiguration fest.</span><span class="sxs-lookup"><span data-stu-id="c44cf-143">Defines the build configuration.</span></span> <span data-ttu-id="c44cf-144">Der Standardwert ist `Debug`, aber die Konfiguration des Projekts könnte diese SDK-Standardeinstellung überschreiben.</span><span class="sxs-lookup"><span data-stu-id="c44cf-144">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="c44cf-145">Aktiviert den Diagnosemodus für die Testplattform und schreibt Diagnosemeldungen in die angegebene Datei.</span><span class="sxs-lookup"><span data-stu-id="c44cf-145">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="c44cf-146">Sucht nach Testbinärdateien für ein bestimmtes [Framework](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="c44cf-146">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="c44cf-147">Filtert Tests im aktuellen Projekt mithilfe des angegebenen Ausdrucks heraus.</span><span class="sxs-lookup"><span data-stu-id="c44cf-147">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="c44cf-148">Weitere Informationen finden Sie im Abschnitt [Details zu Filteroptionen](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="c44cf-148">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="c44cf-149">Weitere Informationen und Beispiele für die Verwendung der selektiven Komponententestfilterung finden Sie unter [Ausführen von selektiven Komponententests](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="c44cf-149">For additional information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="c44cf-150">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="c44cf-150">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="c44cf-151">Gibt eine Protokollierung für die Testergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="c44cf-151">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="c44cf-152">Erstellt das Testprojekt nicht vor der Ausführung.</span><span class="sxs-lookup"><span data-stu-id="c44cf-152">Does not build the test project prior to running it.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="c44cf-153">Verzeichnis, in dem die auszuführenden Binärdateien zu finden sind.</span><span class="sxs-lookup"><span data-stu-id="c44cf-153">Directory in which to find the binaries to run.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="c44cf-154">Einstellungen, die beim Ausführen von Tests verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c44cf-154">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="c44cf-155">Listen Sie alle ermittelten Tests im aktuellen Projekt auf.</span><span class="sxs-lookup"><span data-stu-id="c44cf-155">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="c44cf-156">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="c44cf-156">Sets the verbosity level of the command.</span></span> <span data-ttu-id="c44cf-157">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="c44cf-157">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="c44cf-158">Beispiele</span><span class="sxs-lookup"><span data-stu-id="c44cf-158">Examples</span></span>

<span data-ttu-id="c44cf-159">Führen Sie die Tests im Projekt im aktuellen Verzeichnis durch:</span><span class="sxs-lookup"><span data-stu-id="c44cf-159">Run the tests in the project in the current directory:</span></span>

`dotnet test`

<span data-ttu-id="c44cf-160">Führen Sie die Tests im Projekt `test1` durch:</span><span class="sxs-lookup"><span data-stu-id="c44cf-160">Run the tests in the `test1` project:</span></span>

`dotnet test ~/projects/test1/test1.csproj`

## <a name="filter-option-details"></a><span data-ttu-id="c44cf-161">Details zu Filteroptionen</span><span class="sxs-lookup"><span data-stu-id="c44cf-161">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="c44cf-162">`<Expression>` weist das Format `<property><operator><value>[|&<Expression>]` auf.</span><span class="sxs-lookup"><span data-stu-id="c44cf-162">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="c44cf-163">`<property>` ist ein Attribut von `Test Case`.</span><span class="sxs-lookup"><span data-stu-id="c44cf-163">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="c44cf-164">Im Folgenden werden die Eigenschaften aufgeführt, die von gängigen Frameworks für Komponententests unterstützt werden:</span><span class="sxs-lookup"><span data-stu-id="c44cf-164">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="c44cf-165">Testframework</span><span class="sxs-lookup"><span data-stu-id="c44cf-165">Test Framework</span></span> | <span data-ttu-id="c44cf-166">Unterstützte Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="c44cf-166">Supported properties</span></span>                                                                                      |
| :------------: | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="c44cf-167">MSTest</span><span class="sxs-lookup"><span data-stu-id="c44cf-167">MSTest</span></span>         | <ul><li><span data-ttu-id="c44cf-168">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="c44cf-168">FullyQualifiedName</span></span></li><li><span data-ttu-id="c44cf-169">name</span><span class="sxs-lookup"><span data-stu-id="c44cf-169">Name</span></span></li><li><span data-ttu-id="c44cf-170">ClassName</span><span class="sxs-lookup"><span data-stu-id="c44cf-170">ClassName</span></span></li><li><span data-ttu-id="c44cf-171">Priorität</span><span class="sxs-lookup"><span data-stu-id="c44cf-171">Priority</span></span></li><li><span data-ttu-id="c44cf-172">TestCategory</span><span class="sxs-lookup"><span data-stu-id="c44cf-172">TestCategory</span></span></li></ul> |
| <span data-ttu-id="c44cf-173">Xunit</span><span class="sxs-lookup"><span data-stu-id="c44cf-173">Xunit</span></span>          | <ul><li><span data-ttu-id="c44cf-174">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="c44cf-174">FullyQualifiedName</span></span></li><li><span data-ttu-id="c44cf-175">DisplayName</span><span class="sxs-lookup"><span data-stu-id="c44cf-175">DisplayName</span></span></li><li><span data-ttu-id="c44cf-176">Merkmale</span><span class="sxs-lookup"><span data-stu-id="c44cf-176">Traits</span></span></li></ul>                                   |

<span data-ttu-id="c44cf-177">`<operator>` beschreibt die Beziehung zwischen der Eigenschaft und dem Wert:</span><span class="sxs-lookup"><span data-stu-id="c44cf-177">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="c44cf-178">Operator</span><span class="sxs-lookup"><span data-stu-id="c44cf-178">Operator</span></span> | <span data-ttu-id="c44cf-179">Funktion</span><span class="sxs-lookup"><span data-stu-id="c44cf-179">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="c44cf-180">Genaue Übereinstimmung</span><span class="sxs-lookup"><span data-stu-id="c44cf-180">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="c44cf-181">Keine genaue Übereinstimmung</span><span class="sxs-lookup"><span data-stu-id="c44cf-181">Not exact match</span></span> |
| `~`      | <span data-ttu-id="c44cf-182">Enthält</span><span class="sxs-lookup"><span data-stu-id="c44cf-182">Contains</span></span>        |

<span data-ttu-id="c44cf-183">`<value>` ist eine Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="c44cf-183">`<value>` is a string.</span></span> <span data-ttu-id="c44cf-184">Bei allen Suchvorgängen ist die Groß-/Kleinschreibung nicht relevant.</span><span class="sxs-lookup"><span data-stu-id="c44cf-184">All the lookups are case insensitive.</span></span>

<span data-ttu-id="c44cf-185">Ein Ausdruck ohne `<operator>` gilt automatisch als `contains` für die `FullyQualifiedName`-Eigenschaft (`dotnet test --filter xyz` ist beispielsweise identisch mit `dotnet test --filter FullyQualifiedName~xyz`).</span><span class="sxs-lookup"><span data-stu-id="c44cf-185">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="c44cf-186">Ausdrücke können mit bedingten Operatoren verknüpft werden:</span><span class="sxs-lookup"><span data-stu-id="c44cf-186">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="c44cf-187">Operator</span><span class="sxs-lookup"><span data-stu-id="c44cf-187">Operator</span></span> | <span data-ttu-id="c44cf-188">Funktion</span><span class="sxs-lookup"><span data-stu-id="c44cf-188">Function</span></span> |
| :------: | :------: |
| <code>&#124;</code>      | <span data-ttu-id="c44cf-189">ODER</span><span class="sxs-lookup"><span data-stu-id="c44cf-189">OR</span></span>       |
| `&`      | <span data-ttu-id="c44cf-190">UND</span><span class="sxs-lookup"><span data-stu-id="c44cf-190">AND</span></span>      |

<span data-ttu-id="c44cf-191">Sie können Ausdrücke in Klammern einschließen, wenn Sie bedingte Operatoren verwenden (z.B. `(Name~TestMethod1) | (Name~TestMethod2)`).</span><span class="sxs-lookup"><span data-stu-id="c44cf-191">You can enclose expressions in parenthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="c44cf-192">Weitere Informationen und Beispiele für die Verwendung der selektiven Komponententestfilterung finden Sie unter [Ausführen von selektiven Komponententests](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="c44cf-192">For additional information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c44cf-193">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c44cf-193">See also</span></span>

 [<span data-ttu-id="c44cf-194">Frameworks und Ziele</span><span class="sxs-lookup"><span data-stu-id="c44cf-194">Frameworks and Targets</span></span>](../../standard/frameworks.md)  
 [<span data-ttu-id="c44cf-195">.NET Core Runtime-ID (RID)-Katalog</span><span class="sxs-lookup"><span data-stu-id="c44cf-195">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
