---
title: "dotnet-test-Befehl – .NET Core-CLI"
description: "Der Befehl „dotnet-Test“ wird zum Ausführen von Komponententests in einem bestimmten Projekt verwendet."
keywords: Dotnet-Test, CLI, CLI-Befehl, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 03/25/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 4bf0aef4-148a-41c6-bb95-0a9e1af8762e
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 3308488672df2621c04de40f642c732f81284019
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---

#<a name="dotnet-test"></a><span data-ttu-id="cae7e-104">Dotnet-Test</span><span class="sxs-lookup"><span data-stu-id="cae7e-104">dotnet-test</span></span>

## <a name="name"></a><span data-ttu-id="cae7e-105">Name</span><span class="sxs-lookup"><span data-stu-id="cae7e-105">Name</span></span>

<span data-ttu-id="cae7e-106">`dotnet-test`: .NET-Testtreiber, der verwendet wird, um Komponententests auszuführen.</span><span class="sxs-lookup"><span data-stu-id="cae7e-106">`dotnet-test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="cae7e-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="cae7e-107">Synopsis</span></span>

`dotnet test [<PROJECT>] [-s|--settings] [-t|--list-tests] [--filter] [-a|--test-adapter-path] [-l|--logger] [-c|--configuration] [-f|--framework] [-o|--output] [-d|--diag] [--no-build] [-v|--verbosity] [-h|--help]`

## <a name="description"></a><span data-ttu-id="cae7e-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cae7e-108">Description</span></span>

<span data-ttu-id="cae7e-109">Der Befehl `dotnet test` wird zum Ausführen von Komponententests in einem bestimmten Projekt verwendet.</span><span class="sxs-lookup"><span data-stu-id="cae7e-109">The `dotnet test` command is used to execute unit tests in a given project.</span></span> <span data-ttu-id="cae7e-110">Komponententests sind Konsolenanwendungsprojekte, die Abhängigkeiten vom Komponententest-Framework (z.B. MSTest, NUnit oder xUnit) und dotnet-Test Runner für das Komponententest-Framework aufweisen.</span><span class="sxs-lookup"><span data-stu-id="cae7e-110">Unit tests are console application projects that have dependencies on the unit test framework (for example, MSTest, NUnit, or xUnit) and the dotnet test runner for the unit testing framework.</span></span> <span data-ttu-id="cae7e-111">Sie werden als NuGet-Pakete verpackt und als gewöhnliche Abhängigkeiten für das Projekt wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="cae7e-111">These are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="cae7e-112">Testprojekte müssen auch den Test Runner angeben.</span><span class="sxs-lookup"><span data-stu-id="cae7e-112">Test projects also must specify the test runner.</span></span> <span data-ttu-id="cae7e-113">Dieser wird mit einem normalen `<PackageReference>`-Element angegeben, wie in der folgenden Beispielprojektdatei gezeigt:</span><span class="sxs-lookup"><span data-stu-id="cae7e-113">This is specified using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

<span data-ttu-id="cae7e-114">[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]</span><span class="sxs-lookup"><span data-stu-id="cae7e-114">[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]</span></span>

## <a name="options"></a><span data-ttu-id="cae7e-115">Optionen</span><span class="sxs-lookup"><span data-stu-id="cae7e-115">Options</span></span>

`PROJECT`
    
<span data-ttu-id="cae7e-116">Gibt den Pfad des Testprojekts an.</span><span class="sxs-lookup"><span data-stu-id="cae7e-116">Specifies a path to the test project.</span></span> <span data-ttu-id="cae7e-117">Wenn nicht angegeben, wird standardmäßig das aktuelle Verzeichnis angegeben.</span><span class="sxs-lookup"><span data-stu-id="cae7e-117">If omitted, it defaults to current directory.</span></span>

`-h|--help`

<span data-ttu-id="cae7e-118">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="cae7e-118">Prints out a short help for the command.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="cae7e-119">Einstellungen, die beim Ausführen von Tests verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cae7e-119">Settings to use when running tests.</span></span> 

`-t|--list-tests`

<span data-ttu-id="cae7e-120">Listen Sie alle ermittelten Tests im aktuellen Projekt auf.</span><span class="sxs-lookup"><span data-stu-id="cae7e-120">List all of the discovered tests in the current project.</span></span> 

`--filter <EXPRESSION>`

<span data-ttu-id="cae7e-121">Filtert Tests im aktuellen Projekt mithilfe des angegebenen Ausdrucks heraus.</span><span class="sxs-lookup"><span data-stu-id="cae7e-121">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="cae7e-122">Weitere Informationen finden Sie im Abschnitt [Details zu Filteroptionen](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="cae7e-122">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="cae7e-123">Weitere Informationen und Beispiele für die Verwendung der selektiven Komponententestfilterung finden Sie unter [Ausführen von selektiven Komponententests](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="cae7e-123">For additional information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="cae7e-124">Verwenden Sie die benutzerdefinierten Testadapter aus dem angegebenen Pfad im Testlauf.</span><span class="sxs-lookup"><span data-stu-id="cae7e-124">Use the custom test adapters from the specified path in the test run.</span></span> 

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="cae7e-125">Gibt eine Protokollierung für die Testergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="cae7e-125">Specifies a logger for test results.</span></span> 

`-c|--configuration <CONFIGURATION>`

<span data-ttu-id="cae7e-126">Konfiguration für die Erstellung.</span><span class="sxs-lookup"><span data-stu-id="cae7e-126">Configuration under which to build.</span></span> <span data-ttu-id="cae7e-127">Der Standardwert ist `Debug`, aber die Konfiguration des Projekts könnte diese SDK-Standardeinstellung überschreiben.</span><span class="sxs-lookup"><span data-stu-id="cae7e-127">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="cae7e-128">Sucht nach Testbinärdateien für ein bestimmtes [Framework](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="cae7e-128">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="cae7e-129">Verzeichnis, in dem die auszuführenden Binärdateien zu finden sind.</span><span class="sxs-lookup"><span data-stu-id="cae7e-129">Directory in which to find the binaries to run.</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="cae7e-130">Aktiviert den Diagnosemodus für die Testplattform und schreibt Diagnosemeldungen in die angegebene Datei.</span><span class="sxs-lookup"><span data-stu-id="cae7e-130">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span> 

`--no-build` 

<span data-ttu-id="cae7e-131">Erstellt das Testprojekt nicht vor der Ausführung.</span><span class="sxs-lookup"><span data-stu-id="cae7e-131">Does not build the test project prior to running it.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="cae7e-132">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="cae7e-132">Sets the verbosity level of the command.</span></span> <span data-ttu-id="cae7e-133">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="cae7e-133">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

## <a name="examples"></a><span data-ttu-id="cae7e-134">Beispiele</span><span class="sxs-lookup"><span data-stu-id="cae7e-134">Examples</span></span>

<span data-ttu-id="cae7e-135">Führen Sie die Tests im Projekt im aktuellen Verzeichnis durch:</span><span class="sxs-lookup"><span data-stu-id="cae7e-135">Run the tests in the project in the current directory:</span></span>

`dotnet test` 

<span data-ttu-id="cae7e-136">Führen Sie die Tests im Projekt `test1` durch:</span><span class="sxs-lookup"><span data-stu-id="cae7e-136">Run the tests in the `test1` project:</span></span>

`dotnet test ~/projects/test1/test1.csproj`

## <a name="filter-option-details"></a><span data-ttu-id="cae7e-137">Details zu Filteroptionen</span><span class="sxs-lookup"><span data-stu-id="cae7e-137">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="cae7e-138">`<Expression>` weist das Format `<property><operator><value>[|&<Expression>]` auf.</span><span class="sxs-lookup"><span data-stu-id="cae7e-138">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="cae7e-139">`<property>` ist ein Attribut von `Test Case`.</span><span class="sxs-lookup"><span data-stu-id="cae7e-139">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="cae7e-140">Im Folgenden werden die Eigenschaften aufgeführt, die von gängigen Frameworks für Komponententests unterstützt werden:</span><span class="sxs-lookup"><span data-stu-id="cae7e-140">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="cae7e-141">Testframework</span><span class="sxs-lookup"><span data-stu-id="cae7e-141">Test Framework</span></span> | <span data-ttu-id="cae7e-142">Unterstützte Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="cae7e-142">Supported properties</span></span>                                                                                      |
| :------------: | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="cae7e-143">MSTest</span><span class="sxs-lookup"><span data-stu-id="cae7e-143">MSTest</span></span>         | <ul><li><span data-ttu-id="cae7e-144">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="cae7e-144">FullyQualifiedName</span></span></li><li><span data-ttu-id="cae7e-145">Name</span><span class="sxs-lookup"><span data-stu-id="cae7e-145">Name</span></span></li><li><span data-ttu-id="cae7e-146">ClassName</span><span class="sxs-lookup"><span data-stu-id="cae7e-146">ClassName</span></span></li><li><span data-ttu-id="cae7e-147">Priorität</span><span class="sxs-lookup"><span data-stu-id="cae7e-147">Priority</span></span></li><li><span data-ttu-id="cae7e-148">TestCategory</span><span class="sxs-lookup"><span data-stu-id="cae7e-148">TestCategory</span></span></li></ul> |
| <span data-ttu-id="cae7e-149">Xunit</span><span class="sxs-lookup"><span data-stu-id="cae7e-149">Xunit</span></span>          | <ul><li><span data-ttu-id="cae7e-150">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="cae7e-150">FullyQualifiedName</span></span></li><li><span data-ttu-id="cae7e-151">DisplayName</span><span class="sxs-lookup"><span data-stu-id="cae7e-151">DisplayName</span></span></li><li><span data-ttu-id="cae7e-152">Merkmale</span><span class="sxs-lookup"><span data-stu-id="cae7e-152">Traits</span></span></li></ul>                                   |

<span data-ttu-id="cae7e-153">`<operator>` beschreibt die Beziehung zwischen der Eigenschaft und dem Wert:</span><span class="sxs-lookup"><span data-stu-id="cae7e-153">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="cae7e-154">Operator</span><span class="sxs-lookup"><span data-stu-id="cae7e-154">Operator</span></span> | <span data-ttu-id="cae7e-155">Funktion</span><span class="sxs-lookup"><span data-stu-id="cae7e-155">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="cae7e-156">Genaue Übereinstimmung</span><span class="sxs-lookup"><span data-stu-id="cae7e-156">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="cae7e-157">Keine genaue Übereinstimmung</span><span class="sxs-lookup"><span data-stu-id="cae7e-157">Not exact match</span></span> |
| `~`      | <span data-ttu-id="cae7e-158">Enthält</span><span class="sxs-lookup"><span data-stu-id="cae7e-158">Contains</span></span>        |

<span data-ttu-id="cae7e-159">`<value>` ist eine Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="cae7e-159">`<value>` is a string.</span></span> <span data-ttu-id="cae7e-160">Bei allen Suchvorgängen ist die Groß-/Kleinschreibung nicht relevant.</span><span class="sxs-lookup"><span data-stu-id="cae7e-160">All the lookups are case insensitive.</span></span>

<span data-ttu-id="cae7e-161">Ein Ausdruck ohne `<operator>` gilt automatisch als `contains` für die `FullyQualifiedName`-Eigenschaft (`dotnet test --filter xyz` ist beispielsweise identisch mit `dotnet test --filter FullyQualifiedName~xyz`).</span><span class="sxs-lookup"><span data-stu-id="cae7e-161">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="cae7e-162">Ausdrücke können mit bedingten Operatoren verknüpft werden:</span><span class="sxs-lookup"><span data-stu-id="cae7e-162">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="cae7e-163">Operator</span><span class="sxs-lookup"><span data-stu-id="cae7e-163">Operator</span></span> | <span data-ttu-id="cae7e-164">Funktion</span><span class="sxs-lookup"><span data-stu-id="cae7e-164">Function</span></span> |
| :------: | :------: |
| <code>&#124;</code>      | <span data-ttu-id="cae7e-165">ODER</span><span class="sxs-lookup"><span data-stu-id="cae7e-165">OR</span></span>       |
| `&`      | <span data-ttu-id="cae7e-166">UND</span><span class="sxs-lookup"><span data-stu-id="cae7e-166">AND</span></span>      |

<span data-ttu-id="cae7e-167">Sie können Ausdrücke in Klammern einschließen, wenn Sie bedingte Operatoren verwenden (Beispiel: `(Name~TestMethod1) | (Name~TestMethod2)`).</span><span class="sxs-lookup"><span data-stu-id="cae7e-167">You can enclose expressions in paranthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="cae7e-168">Weitere Informationen und Beispiele für die Verwendung der selektiven Komponententestfilterung finden Sie unter [Ausführen von selektiven Komponententests](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="cae7e-168">For additional information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="cae7e-169">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cae7e-169">See also</span></span>

<span data-ttu-id="cae7e-170">[Frameworks und Ziele](../../standard/frameworks.md) </span><span class="sxs-lookup"><span data-stu-id="cae7e-170">[Frameworks and Targets](../../standard/frameworks.md) </span></span>  
[<span data-ttu-id="cae7e-171">.NET Core Runtime-ID (RID)-Katalog</span><span class="sxs-lookup"><span data-stu-id="cae7e-171">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)

