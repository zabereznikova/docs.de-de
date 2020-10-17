---
title: Neues in C# 7.0 – C#-Leitfaden
description: Erhalten Sie einen Überblick über die neuen Funktionen in Version 7.0 der C#-Sprache.
ms.date: 10/02/2020
ms.assetid: fd41596d-d0c2-4816-b94d-c4d00a5d0243
ms.openlocfilehash: 84f5961d573b99438320a75d7f89bc7fd94f6266
ms.sourcegitcommit: b59237ca4ec763969a0dd775a3f8f39f8c59fe24
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2020
ms.locfileid: "91955212"
---
# <a name="whats-new-in-c-70-through-c-73"></a><span data-ttu-id="c612d-103">Neuerungen von C# 7.0 bis C# 7.3</span><span class="sxs-lookup"><span data-stu-id="c612d-103">What's new in C# 7.0 through C# 7.3</span></span>

<span data-ttu-id="c612d-104">Von C# 7.0 bis C# 7.3 wurden zahlreiche Features für und inkrementelle Verbesserungen an den Entwicklungsfunktionen von C# eingeführt.</span><span class="sxs-lookup"><span data-stu-id="c612d-104">C# 7.0 through C# 7.3 brought a number of features and incremental improvements to your development experience with C#.</span></span> <span data-ttu-id="c612d-105">In diesem Artikel erhalten Sie einen Überblick über die neuen Sprachfeatures und Compileroptionen.</span><span class="sxs-lookup"><span data-stu-id="c612d-105">This article provides an overview of the new language features and compiler options.</span></span> <span data-ttu-id="c612d-106">In den Beschreibungen wird das Verhalten für C# 7.3 erläutert. Dabei handelt es sich um die aktuelle Version, die für auf dem .NET Framework basierende Anwendungen unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="c612d-106">The descriptions describe the behavior for C# 7.3, which is the most recent version supported for .NET Framework-based applications.</span></span>

<span data-ttu-id="c612d-107">Das Konfigurationselement für die [Sprachversionsauswahl](../language-reference/configure-language-version.md) wurde im Rahmen von C# 7.1 hinzugefügt. Damit können Sie die Compilersprachenversion in Ihrer Projektdatei angeben.</span><span class="sxs-lookup"><span data-stu-id="c612d-107">The [language version selection](../language-reference/configure-language-version.md) configuration element was added with C# 7.1, which enables you to specify the compiler language version in your project file.</span></span>

<span data-ttu-id="c612d-108">Von C# 7.0 bis C# 7.3 wurden der C#-Sprache die folgenden Features und Designs hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="c612d-108">C# 7.0-7.3 adds these features and themes to the C# language:</span></span>

- [<span data-ttu-id="c612d-109">Tupel und Verwerfen</span><span class="sxs-lookup"><span data-stu-id="c612d-109">Tuples and discards</span></span>](#tuples-and-discards)
  - <span data-ttu-id="c612d-110">Sie können einfache, unbenannte Typen erstellen, die mehrere öffentliche Felder enthalten.</span><span class="sxs-lookup"><span data-stu-id="c612d-110">You can create lightweight, unnamed types that contain multiple public fields.</span></span> <span data-ttu-id="c612d-111">Compiler und IDE-Tools kennen die Semantik dieser Typen.</span><span class="sxs-lookup"><span data-stu-id="c612d-111">Compilers and IDE tools understand the semantics of these types.</span></span>
  - <span data-ttu-id="c612d-112">Ausschussvariablen (discards) sind temporäre, lesegeschützte Variablen, die in Zuweisungen verwendet werden, wenn der zugewiesene Wert nicht weiter interessiert.</span><span class="sxs-lookup"><span data-stu-id="c612d-112">Discards are temporary, write-only variables used in assignments when you don't care about the value assigned.</span></span> <span data-ttu-id="c612d-113">Sie eignen sich besonders zum Dekonstruieren von Tupeln und benutzerdefinierten Typen sowie beim Aufrufen von Methoden mit `out`-Parametern.</span><span class="sxs-lookup"><span data-stu-id="c612d-113">They're most useful when deconstructing tuples and user-defined types, as well as when calling methods with `out` parameters.</span></span>
- [<span data-ttu-id="c612d-114">Mustervergleich</span><span class="sxs-lookup"><span data-stu-id="c612d-114">Pattern Matching</span></span>](#pattern-matching)
  - <span data-ttu-id="c612d-115">Sie können Verzweigungslogik basierend auf beliebigen Typen und Werten der Member dieser Typen erstellen.</span><span class="sxs-lookup"><span data-stu-id="c612d-115">You can create branching logic based on arbitrary types and values of the members of those types.</span></span>
- [<span data-ttu-id="c612d-116">`async` `Main`-Methode</span><span class="sxs-lookup"><span data-stu-id="c612d-116">`async` `Main` method</span></span>](#async-main)
  - <span data-ttu-id="c612d-117">Der Einstiegspunkt für eine Anwendung kann über den Modifizierer `async` verfügen.</span><span class="sxs-lookup"><span data-stu-id="c612d-117">The entry point for an application can have the `async` modifier.</span></span>
- [<span data-ttu-id="c612d-118">Lokale Funktionen</span><span class="sxs-lookup"><span data-stu-id="c612d-118">Local Functions</span></span>](#local-functions)
  - <span data-ttu-id="c612d-119">Sie können Funktionen innerhalb von anderen Funktionen verschachteln, um deren Bereich und Sichtbarkeit zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="c612d-119">You can nest functions inside other functions to limit their scope and visibility.</span></span>
- [<span data-ttu-id="c612d-120">Mehr Ausdruckskörpermember</span><span class="sxs-lookup"><span data-stu-id="c612d-120">More expression-bodied members</span></span>](#more-expression-bodied-members)
  - <span data-ttu-id="c612d-121">Die Liste der Member, die mithilfe von Ausdrücken erstellt werden können, ist länger geworden.</span><span class="sxs-lookup"><span data-stu-id="c612d-121">The list of members that can be authored using expressions has grown.</span></span>
- [<span data-ttu-id="c612d-122">`throw`-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="c612d-122">`throw` Expressions</span></span>](#throw-expressions)
  - <span data-ttu-id="c612d-123">Sie können Ausnahmen in Codekonstrukten auslösen, die vorher nicht zulässig waren, da `throw` eine Anweisung war.</span><span class="sxs-lookup"><span data-stu-id="c612d-123">You can throw exceptions in code constructs that previously weren't allowed because `throw` was a statement.</span></span>
- [<span data-ttu-id="c612d-124">`default`Literale Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="c612d-124">`default` literal expressions</span></span>](#default-literal-expressions)
  - <span data-ttu-id="c612d-125">Sie können literale Standardausdrücke in Standardwertausdrücken verwenden, wenn der Zieltyp abgeleitet werden kann.</span><span class="sxs-lookup"><span data-stu-id="c612d-125">You can use default literal expressions in default value expressions when the target type can be inferred.</span></span>
- [<span data-ttu-id="c612d-126">Verbesserung der numerischen literalen Syntax</span><span class="sxs-lookup"><span data-stu-id="c612d-126">Numeric literal syntax improvements</span></span>](#numeric-literal-syntax-improvements)
  - <span data-ttu-id="c612d-127">Neue Token verbessern die Lesbarkeit für numerische Konstanten.</span><span class="sxs-lookup"><span data-stu-id="c612d-127">New tokens improve readability for numeric constants.</span></span>
- [<span data-ttu-id="c612d-128">`out`Variablen</span><span class="sxs-lookup"><span data-stu-id="c612d-128">`out` variables</span></span>](#out-variables)
  - <span data-ttu-id="c612d-129">Sie können `out`-Werte als Inlineargumente für die Methode deklarieren, wenn sie verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c612d-129">You can declare `out` values inline as arguments to the method where they're used.</span></span>
- [<span data-ttu-id="c612d-130">Nicht schließende benannte Argumente</span><span class="sxs-lookup"><span data-stu-id="c612d-130">Non-trailing named arguments</span></span>](#non-trailing-named-arguments)
  - <span data-ttu-id="c612d-131">Positionelle Argumente können auf benannte Argumente folgen.</span><span class="sxs-lookup"><span data-stu-id="c612d-131">Named arguments can be followed by positional arguments.</span></span>
- [<span data-ttu-id="c612d-132">`private protected`-Zugriffsmodifizierer</span><span class="sxs-lookup"><span data-stu-id="c612d-132">`private protected` access modifier</span></span>](#private-protected-access-modifier)
  - <span data-ttu-id="c612d-133">Der `private protected`-Zugriffsmodifizierer ermöglicht den Zugriff für abgeleitete Klassen innerhalb der gleichen Assembly.</span><span class="sxs-lookup"><span data-stu-id="c612d-133">The `private protected` access modifier enables access for derived classes in the same assembly.</span></span>
- [<span data-ttu-id="c612d-134">Verbesserte Überladungsauflösung</span><span class="sxs-lookup"><span data-stu-id="c612d-134">Improved overload resolution</span></span>](#improved-overload-candidates)
  - <span data-ttu-id="c612d-135">Neue Regeln sorgen nun für die Auflösung von Ambiguitäten bei Überladungsauflösungen.</span><span class="sxs-lookup"><span data-stu-id="c612d-135">New rules to resolve overload resolution ambiguity.</span></span>
- [<span data-ttu-id="c612d-136">Techniken zum Schreiben von sicherem, effizientem Code</span><span class="sxs-lookup"><span data-stu-id="c612d-136">Techniques for writing safe efficient code</span></span>](#enabling-more-efficient-safe-code)
  - <span data-ttu-id="c612d-137">Eine Kombination aus Verbesserungen der Syntax, die das Arbeiten mit Werttypen mithilfe von Verweissemantik ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="c612d-137">A combination of syntax improvements that enable working with value types using reference semantics.</span></span>

<span data-ttu-id="c612d-138">Schließlich verfügt der Compiler über neue Optionen:</span><span class="sxs-lookup"><span data-stu-id="c612d-138">Finally, the compiler has new options:</span></span>

- <span data-ttu-id="c612d-139">`-refout` und `-refonly`, wodurch die [Erstellung von Referenzassemblys](#reference-assembly-generation) gesteuert wird.</span><span class="sxs-lookup"><span data-stu-id="c612d-139">`-refout` and `-refonly` that control [reference assembly generation](#reference-assembly-generation).</span></span>
- <span data-ttu-id="c612d-140">`-publicsign`, um das Signieren von Assemblys durch Open Source Software (OSS) zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="c612d-140">`-publicsign` to enable Open Source Software (OSS) signing of assemblies.</span></span>
- <span data-ttu-id="c612d-141">`-pathmap`, um eine Zuordnung für Quellverzeichnisse bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="c612d-141">`-pathmap` to provide a mapping for source directories.</span></span>

<span data-ttu-id="c612d-142">Dieser Artikel enthält im Folgenden eine Übersicht über die einzelnen Funktionen.</span><span class="sxs-lookup"><span data-stu-id="c612d-142">The remainder of this article provides an overview of each feature.</span></span> <span data-ttu-id="c612d-143">Sie werden die Hintergründe sowie die Syntax jedes einzelnen Features kennenlernen.</span><span class="sxs-lookup"><span data-stu-id="c612d-143">For each feature, you'll learn the reasoning behind it and the syntax.</span></span> <span data-ttu-id="c612d-144">Sie können sich diese Funktionen in unserer Umgebung mit dem globalen `dotnet try`-Tool näher ansehen:</span><span class="sxs-lookup"><span data-stu-id="c612d-144">You can explore these features in your environment using the `dotnet try` global tool:</span></span>

1. <span data-ttu-id="c612d-145">Installieren Sie das globale [dotnet-try](https://github.com/dotnet/try/blob/master/README.md#setup)-Tool.</span><span class="sxs-lookup"><span data-stu-id="c612d-145">Install the [dotnet-try](https://github.com/dotnet/try/blob/master/README.md#setup) global tool.</span></span>
1. <span data-ttu-id="c612d-146">Klonen Sie das [dotnet/try-samples](https://github.com/dotnet/try-samples)-Repository.</span><span class="sxs-lookup"><span data-stu-id="c612d-146">Clone the [dotnet/try-samples](https://github.com/dotnet/try-samples) repository.</span></span>
1. <span data-ttu-id="c612d-147">Legen Sie das aktuelle Verzeichnis auf das Unterverzeichnis *csharp7* für das *try-samples*-Repository fest.</span><span class="sxs-lookup"><span data-stu-id="c612d-147">Set the current directory to the *csharp7* subdirectory for the *try-samples* repository.</span></span>
1. <span data-ttu-id="c612d-148">Führen Sie aus `dotnet try`.</span><span class="sxs-lookup"><span data-stu-id="c612d-148">Run `dotnet try`.</span></span>

## <a name="tuples-and-discards"></a><span data-ttu-id="c612d-149">Tupel und Verwerfen</span><span class="sxs-lookup"><span data-stu-id="c612d-149">Tuples and discards</span></span>

<span data-ttu-id="c612d-150">C# bietet eine umfangreiche Syntax für Klassen und Strukturen, die verwendet wird, um Ihre Entwurfsabsicht zu erläutern.</span><span class="sxs-lookup"><span data-stu-id="c612d-150">C# provides a rich syntax for classes and structs that is used to explain your design intent.</span></span> <span data-ttu-id="c612d-151">Aber manchmal erfordert diese umfangreiche Syntax zusätzliche Arbeit mit minimalem Nutzen.</span><span class="sxs-lookup"><span data-stu-id="c612d-151">But sometimes that rich syntax requires extra work with minimal benefit.</span></span> <span data-ttu-id="c612d-152">Möglicherweise schreiben Sie häufig Methoden, die eine einfache Struktur erfordern, die mehr als ein Datenelement enthält.</span><span class="sxs-lookup"><span data-stu-id="c612d-152">You may often write methods that need a simple structure containing more than one data element.</span></span> <span data-ttu-id="c612d-153">Zur Unterstützung dieser Szenarios wurden C# *Tupel* hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="c612d-153">To support these scenarios *tuples* were added to C#.</span></span> <span data-ttu-id="c612d-154">Tupel sind einfache Datenstrukturen, die mehrere Felder zur Darstellung der Datenmember enthalten.</span><span class="sxs-lookup"><span data-stu-id="c612d-154">Tuples are lightweight data structures that contain multiple fields to represent the data members.</span></span> <span data-ttu-id="c612d-155">Die Felder werden nicht überprüft, und Sie können keine eigenen Methoden definieren.</span><span class="sxs-lookup"><span data-stu-id="c612d-155">The fields aren't validated, and you can't define your own methods.</span></span> <span data-ttu-id="c612d-156">C#-Tupeltypen unterstützen `==` und `!=`.</span><span class="sxs-lookup"><span data-stu-id="c612d-156">C# tuple types support `==` and `!=`.</span></span> <span data-ttu-id="c612d-157">Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="c612d-157">For more information.</span></span>

> [!NOTE]
> <span data-ttu-id="c612d-158">Tupel waren schon vor C# 7.0 verfügbar, sie waren jedoch ineffizient und hatten keine Sprachunterstützung.</span><span class="sxs-lookup"><span data-stu-id="c612d-158">Tuples were available before C# 7.0, but they were inefficient and had no language support.</span></span> <span data-ttu-id="c612d-159">Das brachte mit sich, dass auf Tupelelemente nur als `Item1`, `Item2` usw. verwiesen werden konnte.</span><span class="sxs-lookup"><span data-stu-id="c612d-159">This meant that tuple elements could only be referenced as `Item1`, `Item2` and so on.</span></span> <span data-ttu-id="c612d-160">Mit C# 7.0 wird Sprachunterstützung für Tupel eingeführt, wodurch semantische Namen für die Felder eines Tupels mit Einsatz neuer, effizienterer Tupeltypen möglich werden.</span><span class="sxs-lookup"><span data-stu-id="c612d-160">C# 7.0 introduces language support for tuples, which enables semantic names for the fields of a tuple using new, more efficient tuple types.</span></span>

<span data-ttu-id="c612d-161">Sie können ein Tupel erstellen, indem Sie jedem Member einen Wert zuweisen und ihnen optional auch semantische Namen bereitstellen:</span><span class="sxs-lookup"><span data-stu-id="c612d-161">You can create a tuple by assigning a value to each member, and optionally providing semantic names to each of the members of the tuple:</span></span>

[!code-csharp[NamedTuple](~/samples/snippets/csharp/new-in-7/program.cs#NamedTuple "Named tuple")]

<span data-ttu-id="c612d-162">Das `namedLetters`-Tupel enthält Felder, die als `Alpha` und `Beta` bezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="c612d-162">The `namedLetters` tuple contains fields referred to as `Alpha` and `Beta`.</span></span> <span data-ttu-id="c612d-163">Diese Namen bestehen nur zur Kompilierzeit und werden nicht beibehalten, wenn das Tupel beispielsweise zur Laufzeit mithilfe von Reflektion untersucht wird.</span><span class="sxs-lookup"><span data-stu-id="c612d-163">Those names exist only at compile time and aren't preserved, for example when inspecting the tuple using reflection at run time.</span></span>

<span data-ttu-id="c612d-164">In einer Tupelzuweisung können Sie auch die Namen der Felder auf der rechten Seite der Zuweisung angeben:</span><span class="sxs-lookup"><span data-stu-id="c612d-164">In a tuple assignment, you can also specify the names of the fields on the right-hand side of the assignment:</span></span>

[!code-csharp[ImplicitNamedTuple](~/samples/snippets/csharp/new-in-7/program.cs#ImplicitNamedTuple "Implicitly named tuple")]

<span data-ttu-id="c612d-165">Manchmal möchten Sie vielleicht die Member eines Tupels entpacken, die von einer Methode zurückgegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="c612d-165">There may be times when you want to unpackage the members of a tuple that were returned from a method.</span></span>  <span data-ttu-id="c612d-166">Sie können dazu für jeden Wert im Tupel separate Variablen deklarieren.</span><span class="sxs-lookup"><span data-stu-id="c612d-166">You can do that by declaring separate variables for each of the values in the tuple.</span></span> <span data-ttu-id="c612d-167">Das Auspacken wird als *Dekonstruieren* des Tupels bezeichnet:</span><span class="sxs-lookup"><span data-stu-id="c612d-167">This unpackaging is called *deconstructing* the tuple:</span></span>

[!code-csharp[CallingWithDeconstructor](~/samples/snippets/csharp/new-in-7/program.cs#CallingWithDeconstructor "Deconstructing a tuple")]

<span data-ttu-id="c612d-168">Sie können auch eine ähnliche Dekonstruktion für alle Typen in .NET bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="c612d-168">You can also provide a similar deconstruction for any type in .NET.</span></span> <span data-ttu-id="c612d-169">Schreiben Sie eine `Deconstruct`-Methode als Member der Klasse.</span><span class="sxs-lookup"><span data-stu-id="c612d-169">You write a `Deconstruct` method as a member of the class.</span></span> <span data-ttu-id="c612d-170">Diese `Deconstruct`-Methode bietet eine Reihe von `out`-Argumenten für jede der Eigenschaften, die Sie extrahieren möchten.</span><span class="sxs-lookup"><span data-stu-id="c612d-170">That `Deconstruct` method provides a set of `out` arguments for each of the properties you want to extract.</span></span> <span data-ttu-id="c612d-171">Berücksichtigen Sie diese `Point`-Klasse, die eine Dekonstruktionsmethode bereitstellt, die die `X`- und `Y`-Koordinaten extrahiert:</span><span class="sxs-lookup"><span data-stu-id="c612d-171">Consider this `Point` class that provides a deconstructor method that extracts the `X` and `Y` coordinates:</span></span>

[!code-csharp[PointWithDeconstruction](~/samples/snippets/csharp/new-in-7/point.cs#PointWithDeconstruction "Point with deconstruction method")]

<span data-ttu-id="c612d-172">Sie können die einzelnen Felder extrahieren, indem Sie einem `Point` ein Tupel zuweisen:</span><span class="sxs-lookup"><span data-stu-id="c612d-172">You can extract the individual fields by assigning a `Point` to a tuple:</span></span>

[!code-csharp[DeconstructPoint](~/samples/snippets/csharp/new-in-7/program.cs#DeconstructPoint "Deconstruct a point")]

<span data-ttu-id="c612d-173">Wenn Sie einen Tupel initialisieren, sind die Variablen, die für die rechte Seite der Zuweisung verwendet werden, oft dieselben, wie die Namen, die Sie den Tupelelementen geben möchten. Die Namen von Tupelelementen können von den Variablen abgeleitet werden, die zum Initialisieren der Tupel verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="c612d-173">Many times when you initialize a tuple, the variables used for the right side of the assignment are the same as the names you'd like for the tuple elements: The names of tuple elements can be inferred from the variables used to initialize the tuple:</span></span>

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count, label); // element names are "count" and "label"
```

<span data-ttu-id="c612d-174">Weitere Informationen zu diesem Feature finden Sie im Artikel [Tupeltypen](../language-reference/builtin-types/value-tuples.md).</span><span class="sxs-lookup"><span data-stu-id="c612d-174">You can learn more about this feature in the [Tuple types](../language-reference/builtin-types/value-tuples.md) article.</span></span>

<span data-ttu-id="c612d-175">Beim Dekonstruieren eines Tupels oder dem Aufrufen einer Methode mit `out`-Parametern sind Sie gezwungen, eine Variable zu definieren, deren Wert Sie nicht interessiert und die Sie nicht zu verwenden beabsichtigen.</span><span class="sxs-lookup"><span data-stu-id="c612d-175">Often when deconstructing a tuple or calling a method with `out` parameters, you're forced to define a variable whose value you don't care about and don't intend to use.</span></span> <span data-ttu-id="c612d-176">C# verfügt jetzt über Unterstützung für *Ausschussvariablen* (discards), um diesem Szenario Rechnung zu tragen.</span><span class="sxs-lookup"><span data-stu-id="c612d-176">C# adds support for *discards* to handle this scenario.</span></span> <span data-ttu-id="c612d-177">Eine Ausschussvariable ist eine lesegeschützte Variable mit dem Namen `_` (dem Unterstrichzeichen); Sie können der einzelnen Variablen alle Werte zuweisen, die Sie verwerfen möchten.</span><span class="sxs-lookup"><span data-stu-id="c612d-177">A discard is a write-only variable whose name is `_` (the underscore character); you can assign all of the values that you intend to discard to the single variable.</span></span> <span data-ttu-id="c612d-178">Eine Ausschussvariable ist wie eine nicht zugewiesene Variable; abgesehen von der Zuweisungsanweisung kann die Ausschussvariable nicht in Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c612d-178">A discard is like an unassigned variable; apart from the assignment statement, the discard can't be used in code.</span></span>

<span data-ttu-id="c612d-179">Ausschussvariablen werden in den folgenden Szenarien unterstützt:</span><span class="sxs-lookup"><span data-stu-id="c612d-179">Discards are supported in the following scenarios:</span></span>

- <span data-ttu-id="c612d-180">Beim Dekonstruieren von Tupeln oder benutzerdefinierten Typen.</span><span class="sxs-lookup"><span data-stu-id="c612d-180">When deconstructing tuples or user-defined types.</span></span>
- <span data-ttu-id="c612d-181">Beim Aufrufen von Methoden mit [out](../language-reference/keywords/out-parameter-modifier.md)-Parametern.</span><span class="sxs-lookup"><span data-stu-id="c612d-181">When calling methods with [out](../language-reference/keywords/out-parameter-modifier.md) parameters.</span></span>
- <span data-ttu-id="c612d-182">In einem Musterabgleichsvorgang mit den Anweisungen [is](../language-reference/keywords/is.md) und [switch](../language-reference/keywords/switch.md).</span><span class="sxs-lookup"><span data-stu-id="c612d-182">In a pattern matching operation with the [is](../language-reference/keywords/is.md) and [switch](../language-reference/keywords/switch.md) statements.</span></span>
- <span data-ttu-id="c612d-183">Als eigenständiger Bezeichner, wenn Sie den Wert einer Zuweisung explizit als Ausschuss kennzeichnen möchten.</span><span class="sxs-lookup"><span data-stu-id="c612d-183">As a standalone identifier when you want to explicitly identify the value of an assignment as a discard.</span></span>

<span data-ttu-id="c612d-184">Das folgende Beispiel definiert eine `QueryCityDataForYears`-Methode, die ein 6-Tupel zurückgibt, das ein Datum für eine Stadt für zwei verschiedene Jahre enthält.</span><span class="sxs-lookup"><span data-stu-id="c612d-184">The following example defines a `QueryCityDataForYears` method that returns a 6-tuple that contains data for a city for two different years.</span></span> <span data-ttu-id="c612d-185">Der Methodenaufruf im Beispiel befasst sich nur mit den zwei Bevölkerungswerten, die von der Methode zurückgegeben werden und behandelt so die verbleibenden Werte im Tupel beim Dekonstruieren des Tupels als Ausschuss.</span><span class="sxs-lookup"><span data-stu-id="c612d-185">The method call in the example is concerned only with the two population values returned by the method and so treats the remaining values in the tuple as discards when it deconstructs the tuple.</span></span>

[!code-csharp[Tuple-discard](~/samples/snippets/csharp/programming-guide/deconstructing-tuples/discard-tuple1.cs)]

<span data-ttu-id="c612d-186">Weitere Informationen finden Sie unter [Ausschuss](../discards.md).</span><span class="sxs-lookup"><span data-stu-id="c612d-186">For more information, see [Discards](../discards.md).</span></span>

## <a name="pattern-matching"></a><span data-ttu-id="c612d-187">Musterabgleich</span><span class="sxs-lookup"><span data-stu-id="c612d-187">Pattern matching</span></span>

<span data-ttu-id="c612d-188">Beim *Musterabgleich* handelt es sich um mehrere Features, die neue Möglichkeiten eröffnen, Ablaufsteuerung in Ihrem Code auszudrücken.</span><span class="sxs-lookup"><span data-stu-id="c612d-188">*Pattern matching* is a set of features that enable new ways to express control flow in your code.</span></span> <span data-ttu-id="c612d-189">Sie können Variablen nach Typ, Werten oder den Werten ihrer Eigenschaften testen.</span><span class="sxs-lookup"><span data-stu-id="c612d-189">You can test variables for their type, values or the values of their properties.</span></span> <span data-ttu-id="c612d-190">Dieses Vorgehen sorgt für einen besser lesbaren Codeflow.</span><span class="sxs-lookup"><span data-stu-id="c612d-190">These techniques create more readable code flow.</span></span>

<span data-ttu-id="c612d-191">Mustervergleich unterstützt `is`-Ausdrücke und `switch`-Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="c612d-191">Pattern matching supports `is` expressions and `switch` expressions.</span></span> <span data-ttu-id="c612d-192">Jeder davon ermöglicht das Überprüfen eines Objekts und dessen Eigenschaften, um zu bestimmen, ob das Objekt dem gesuchten Muster entspricht.</span><span class="sxs-lookup"><span data-stu-id="c612d-192">Each enables inspecting an object and its properties to determine if that object satisfies the sought pattern.</span></span> <span data-ttu-id="c612d-193">Sie verwenden das `when`-Schlüsselwort, um zusätzliche Regeln für das Muster anzugeben.</span><span class="sxs-lookup"><span data-stu-id="c612d-193">You use the `when` keyword to specify additional rules to the pattern.</span></span>

<span data-ttu-id="c612d-194">Der Musterausdruck `is` erweitert den vertrauten [`is`-Operator](../language-reference/keywords/is.md#pattern-matching-with-is), um eine Abfrage zum Typ eines Objekts auszuführen und das Ergebnis in einer Anweisung zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="c612d-194">The `is` pattern expression extends the familiar [`is` operator](../language-reference/keywords/is.md#pattern-matching-with-is) to query an object about its type and assign the result in one instruction.</span></span> <span data-ttu-id="c612d-195">Der folgende Code überprüft, ob es sich bei einer Variablen um einen `int`-Wert handelt und fügt sie, wenn dies der Fall ist, der aktuellen Summe hinzu:</span><span class="sxs-lookup"><span data-stu-id="c612d-195">The following code checks if a variable is an `int`, and if so, adds it to the current sum:</span></span>

```csharp
if (input is int count)
    sum += count;
```

<span data-ttu-id="c612d-196">Das vorausgegangene kleine Beispiel verdeutlicht die Verbesserungen des `is`-Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="c612d-196">The preceding small example demonstrates the enhancements to the `is` expression.</span></span> <span data-ttu-id="c612d-197">Sie können für Wert- und Verweistypen testen und das erfolgreiche Ergebnis einer neuen Variable des richtigen Typs zuweisen.</span><span class="sxs-lookup"><span data-stu-id="c612d-197">You can test against value types as well as reference types, and you can assign the successful result to a new variable of the correct type.</span></span>

<span data-ttu-id="c612d-198">Der Switch-Vergleichsausdruck verfügt über eine vertraute Syntax basierend auf der `switch`-Anweisung, die bereits Teil der C#-Sprache ist.</span><span class="sxs-lookup"><span data-stu-id="c612d-198">The switch match expression has a familiar syntax, based on the `switch` statement already part of the C# language.</span></span> <span data-ttu-id="c612d-199">Die aktualisierte Switch-Anweisung verfügt über mehrere neue Konstrukte:</span><span class="sxs-lookup"><span data-stu-id="c612d-199">The updated switch statement has several new constructs:</span></span>

- <span data-ttu-id="c612d-200">Der maßgebliche Typ eines `switch`-Ausdrucks ist nicht mehr beschränkt auf ganzzahlige Typen, `Enum`-Typen, `string` oder einen Nullable-Typ, der einem dieser Typen entspricht.</span><span class="sxs-lookup"><span data-stu-id="c612d-200">The governing type of a `switch` expression is no longer restricted to integral types, `Enum` types, `string`, or a nullable type corresponding to one of those types.</span></span> <span data-ttu-id="c612d-201">Es kann jeder Typ verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c612d-201">Any type may be used.</span></span>
- <span data-ttu-id="c612d-202">Sie können den Typ des `switch`-Ausdrucks in jeder `case`-Bezeichnung testen.</span><span class="sxs-lookup"><span data-stu-id="c612d-202">You can test the type of the `switch` expression in each `case` label.</span></span> <span data-ttu-id="c612d-203">Sie können diesem Typ wie schon beim `is`-Ausdruck eine neue Variable zuweisen.</span><span class="sxs-lookup"><span data-stu-id="c612d-203">As with the `is` expression, you may assign a new variable to that type.</span></span>
- <span data-ttu-id="c612d-204">Wenn Sie die Bedingungen für diese Variable weiter testen möchten, können Sie eine `when`-Klausel hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="c612d-204">You may add a `when` clause to further test conditions on that variable.</span></span>
- <span data-ttu-id="c612d-205">Die Reihenfolge der `case`-Bezeichnungen ist hierbei entscheidend.</span><span class="sxs-lookup"><span data-stu-id="c612d-205">The order of `case` labels is now important.</span></span> <span data-ttu-id="c612d-206">Die erste Verzweigung, für die eine Übereinstimmung gefunden wird, wird ausgeführt. Alle weiteren werden übersprungen.</span><span class="sxs-lookup"><span data-stu-id="c612d-206">The first branch to match is executed; others are skipped.</span></span>

<span data-ttu-id="c612d-207">Im folgenden Code werden diese Funktionen veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="c612d-207">The following code demonstrates these new features:</span></span>

```csharp
public static int SumPositiveNumbers(IEnumerable<object> sequence)
{
    int sum = 0;
    foreach (var i in sequence)
    {
        switch (i)
        {
            case 0:
                break;
            case IEnumerable<int> childSequence:
            {
                foreach(var item in childSequence)
                    sum += (item > 0) ? item : 0;
                break;
            }
            case int n when n > 0:
                sum += n;
                break;
            case null:
                throw new NullReferenceException("Null found in sequence");
            default:
                throw new InvalidOperationException("Unrecognized type");
        }
    }
    return sum;
}
```

- <span data-ttu-id="c612d-208">`case 0:` ist das vertraute Konstantenmuster.</span><span class="sxs-lookup"><span data-stu-id="c612d-208">`case 0:` is the familiar constant pattern.</span></span>
- <span data-ttu-id="c612d-209">`case IEnumerable<int> childSequence:` ist ein Typmuster.</span><span class="sxs-lookup"><span data-stu-id="c612d-209">`case IEnumerable<int> childSequence:` is a type pattern.</span></span>
- <span data-ttu-id="c612d-210">`case int n when n > 0:` ist ein Typmuster mit einer zusätzlichen `when`-Bedingung.</span><span class="sxs-lookup"><span data-stu-id="c612d-210">`case int n when n > 0:` is a type pattern with an additional `when` condition.</span></span>
- <span data-ttu-id="c612d-211">`case null:` ist das NULL-Muster.</span><span class="sxs-lookup"><span data-stu-id="c612d-211">`case null:` is the null pattern.</span></span>
- <span data-ttu-id="c612d-212">`default:` ist die vertraute Standardanfrage.</span><span class="sxs-lookup"><span data-stu-id="c612d-212">`default:` is the familiar default case.</span></span>

<span data-ttu-id="c612d-213">Ab C# 7.1 kann der Musterausdruck für `is` und das `switch`-Typmuster den Typ eines generischen Typparameters haben.</span><span class="sxs-lookup"><span data-stu-id="c612d-213">Beginning with C# 7.1, the pattern expression for `is` and the `switch` type pattern may have the type of a generic type parameter.</span></span> <span data-ttu-id="c612d-214">Dies kann sehr nützlich sein, wenn Sie Typen überprüfen, die entweder `struct`- oder `class`-Typen sein können, und Sie Boxing vermeiden möchten.</span><span class="sxs-lookup"><span data-stu-id="c612d-214">This can be most useful when checking types that may be either `struct` or `class` types, and you want to avoid boxing.</span></span>

<span data-ttu-id="c612d-215">Weitere Informationen zum Mustervergleich finden Sie unter [Pattern Matching in C# (Mustervergleich in C#)](../pattern-matching.md).</span><span class="sxs-lookup"><span data-stu-id="c612d-215">You can learn more about pattern matching in [Pattern Matching in C#](../pattern-matching.md).</span></span>

## <a name="async-main"></a><span data-ttu-id="c612d-216">Async Main</span><span class="sxs-lookup"><span data-stu-id="c612d-216">Async main</span></span>

<span data-ttu-id="c612d-217">Mithilfe einer *async main*-Methode können Sie `await` in Ihrer `Main`-Methode verwenden.</span><span class="sxs-lookup"><span data-stu-id="c612d-217">An *async main* method enables you to use `await` in your `Main` method.</span></span> <span data-ttu-id="c612d-218">Vorher hätten Sie das Folgende schreiben müssen:</span><span class="sxs-lookup"><span data-stu-id="c612d-218">Previously you would need to write:</span></span>

```csharp
static int Main()
{
    return DoAsyncWork().GetAwaiter().GetResult();
}
```

<span data-ttu-id="c612d-219">Nun können Sie das Folgende schreiben:</span><span class="sxs-lookup"><span data-stu-id="c612d-219">You can now write:</span></span>

```csharp
static async Task<int> Main()
{
    // This could also be replaced with the body
    // DoAsyncWork, including its await expressions:
    return await DoAsyncWork();
}
```

<span data-ttu-id="c612d-220">Wenn Ihr Programm keinen Exitcode zurückgibt, können Sie eine `Main`-Methode deklarieren, die einen <xref:System.Threading.Tasks.Task> zurückgibt:</span><span class="sxs-lookup"><span data-stu-id="c612d-220">If your program doesn't return an exit code, you can declare a `Main` method that returns a <xref:System.Threading.Tasks.Task>:</span></span>

```csharp
static async Task Main()
{
    await SomeAsyncMethod();
}
```

<span data-ttu-id="c612d-221">Ausführliche Informationen finden Sie unter [Async Main](../programming-guide/main-and-command-args/index.md) im Programmierhandbuch.</span><span class="sxs-lookup"><span data-stu-id="c612d-221">You can read more about the details in the [async main](../programming-guide/main-and-command-args/index.md) article in the programming guide.</span></span>

## <a name="local-functions"></a><span data-ttu-id="c612d-222">Lokale Funktionen</span><span class="sxs-lookup"><span data-stu-id="c612d-222">Local functions</span></span>

<span data-ttu-id="c612d-223">Viele Entwürfe für Klassen enthalten Methoden, die nur von einer Stelle aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="c612d-223">Many designs for classes include methods that are called from only one location.</span></span> <span data-ttu-id="c612d-224">Durch diese zusätzlichen privaten Methoden bleibt jede Methode klein und konzentriert.</span><span class="sxs-lookup"><span data-stu-id="c612d-224">These additional private methods keep each method small and focused.</span></span> <span data-ttu-id="c612d-225">Mit *lokalen Funktionen* können Sie Methoden innerhalb des Kontexts einer anderen Methode deklarieren.</span><span class="sxs-lookup"><span data-stu-id="c612d-225">*Local functions* enable you to declare methods inside the context of another method.</span></span> <span data-ttu-id="c612d-226">So können Leser der Klasse leichter erkennen, dass die lokale Methode nur aus dem Kontext aufgerufen wird, in dem sie deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="c612d-226">Local functions make it easier for readers of the class to see that the local method is only called from the context in which it is declared.</span></span>

<span data-ttu-id="c612d-227">Es gibt zwei häufige Anwendungsfälle für lokale Funktionen: öffentliche Iteratormethoden und öffentliche asynchrone Methoden.</span><span class="sxs-lookup"><span data-stu-id="c612d-227">There are two common use cases for local functions: public iterator methods and public async methods.</span></span> <span data-ttu-id="c612d-228">Beide Arten von Methoden generieren Code, der Fehler später meldet, als Programmierer erwarten würden.</span><span class="sxs-lookup"><span data-stu-id="c612d-228">Both types of methods generate code that reports errors later than programmers might expect.</span></span> <span data-ttu-id="c612d-229">Bei Iteratormethoden werden Ausnahmen nur festgestellt, wenn Code aufgerufen wird, der die zurückgegebene Sequenz auflistet.</span><span class="sxs-lookup"><span data-stu-id="c612d-229">In iterator methods, any exceptions are observed only when calling code that enumerates the returned sequence.</span></span> <span data-ttu-id="c612d-230">Bei asynchronen Methoden werden Ausnahmen nur festgestellt, wenn der zurückgegebene `Task`-Wert erwartet wird.</span><span class="sxs-lookup"><span data-stu-id="c612d-230">In async methods, any exceptions are only observed when the returned `Task` is awaited.</span></span> <span data-ttu-id="c612d-231">Im folgenden Beispiel wird veranschaulicht, wie mithilfe einer lokalen Funktion die Überprüfung der Parameter von der Iteratorimplementierung getrennt wird:</span><span class="sxs-lookup"><span data-stu-id="c612d-231">The following example demonstrates separating parameter validation from the iterator implementation using a local function:</span></span>

[!code-csharp[22_IteratorMethodLocal](~/samples/snippets/csharp/new-in-7/Iterator.cs#IteratorMethodLocal "Iterator method with local function")]

<span data-ttu-id="c612d-232">Das gleiche Verfahren kann mit `async`-Methoden eingesetzt werden, um sicherzustellen, dass Ausnahmen aufgrund der Argumentüberprüfung ausgelöst werden, bevor die asynchrone Arbeit beginnt:</span><span class="sxs-lookup"><span data-stu-id="c612d-232">The same technique can be employed with `async` methods to ensure that exceptions arising from argument validation are thrown before the asynchronous work begins:</span></span>

[!code-csharp[TaskExample](~/samples/snippets/csharp/new-in-7/AsyncWork.cs#TaskExample "Task returning method with local function")]

<span data-ttu-id="c612d-233">Diese Syntax wird jetzt unterstützt:</span><span class="sxs-lookup"><span data-stu-id="c612d-233">This syntax is now supported:</span></span>

```csharp
[field: SomeThingAboutFieldAttribute]
public int SomeProperty { get; set; }
```

<span data-ttu-id="c612d-234">Das Attribut `SomeThingAboutFieldAttribute` wird auf das vom Compiler generierte Unterstützungsfeld für `SomeProperty` angewendet.</span><span class="sxs-lookup"><span data-stu-id="c612d-234">The attribute `SomeThingAboutFieldAttribute` is applied to the compiler generated backing field for `SomeProperty`.</span></span> <span data-ttu-id="c612d-235">Weitere Informationen finden Sie unter [attributes](../programming-guide/concepts/attributes/index.md) im C#-Programmierhandbuch.</span><span class="sxs-lookup"><span data-stu-id="c612d-235">For more information, see [attributes](../programming-guide/concepts/attributes/index.md) in the C# programming guide.</span></span>

> [!NOTE]
> <span data-ttu-id="c612d-236">Einige der Entwürfe, die von lokalen Funktionen unterstützt werden, können auch mithilfe von *Lambdaausdrücken* erreicht werden.</span><span class="sxs-lookup"><span data-stu-id="c612d-236">Some of the designs that are supported by local functions can also be accomplished using *lambda expressions*.</span></span> <span data-ttu-id="c612d-237">Weitere Informationen finden Sie unter [Lokale Funktionen im Vergleich zu Lambdaausdrücken](../programming-guide/classes-and-structs/local-functions.md#local-functions-vs-lambda-expressions).</span><span class="sxs-lookup"><span data-stu-id="c612d-237">For more information, see [Local functions vs. lambda expressions](../programming-guide/classes-and-structs/local-functions.md#local-functions-vs-lambda-expressions).</span></span>

## <a name="more-expression-bodied-members"></a><span data-ttu-id="c612d-238">Mehr Ausdruckskörpermember</span><span class="sxs-lookup"><span data-stu-id="c612d-238">More expression-bodied members</span></span>

<span data-ttu-id="c612d-239">In C# 6 wurden [Ausdruckskörpermember](csharp-6.md#expression-bodied-function-members) für Memberfunktionen und schreibgeschützte Eigenschaften eingeführt.</span><span class="sxs-lookup"><span data-stu-id="c612d-239">C# 6 introduced [expression-bodied members](csharp-6.md#expression-bodied-function-members) for member functions, and read-only properties.</span></span> <span data-ttu-id="c612d-240">Mit C# 7.0 werden die zulässigen Member erweitert, die als Ausdrücke implementiert werden können.</span><span class="sxs-lookup"><span data-stu-id="c612d-240">C# 7.0 expands the allowed members that can be implemented as expressions.</span></span> <span data-ttu-id="c612d-241">In C# 7.0 können Sie *Konstruktoren*, *Finalizer* sowie `get`- und `set`-Zugriffsmethoden für *Eigenschaften* und *Indexer* implementieren.</span><span class="sxs-lookup"><span data-stu-id="c612d-241">In C# 7.0, you can implement *constructors*, *finalizers*, and `get` and `set` accessors on *properties* and *indexers*.</span></span> <span data-ttu-id="c612d-242">Der folgende Code zeigt entsprechende Beispiele:</span><span class="sxs-lookup"><span data-stu-id="c612d-242">The following code shows examples of each:</span></span>

[!code-csharp[ExpressionBodiedMembers](~/samples/snippets/csharp/new-in-7/expressionmembers.cs#ExpressionBodiedEverything "new expression-bodied members")]

> [!NOTE]
> <span data-ttu-id="c612d-243">In diesem Beispiel ist kein Finalizer erforderlich, aber damit soll die Syntax dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="c612d-243">This example does not need a finalizer, but it is shown to demonstrate the syntax.</span></span> <span data-ttu-id="c612d-244">Sie sollten in Ihrer Klasse nur einen Finalizer implementieren, wenn es notwendig ist, nicht verwaltete Ressourcen freizugeben.</span><span class="sxs-lookup"><span data-stu-id="c612d-244">You should not implement a finalizer in your class unless it is necessary to  release unmanaged resources.</span></span> <span data-ttu-id="c612d-245">Sie sollten auch die Verwendung der <xref:System.Runtime.InteropServices.SafeHandle>-Klasse in Betracht ziehen, anstatt nicht verwaltete Ressourcen direkt zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="c612d-245">You should also consider using the <xref:System.Runtime.InteropServices.SafeHandle> class instead of managing unmanaged resources directly.</span></span>

<span data-ttu-id="c612d-246">Diese neuen Speicherorte für Member mit Ausdruckskörper sind ein wichtiger Meilenstein für die Sprache C#: Diese Features wurden von Community-Mitgliedern implementiert, die am Open Source-Projekt [Roslyn](https://github.com/dotnet/Roslyn) arbeiten.</span><span class="sxs-lookup"><span data-stu-id="c612d-246">These new locations for expression-bodied members represent an important milestone for the C# language: These features were implemented by community members working on the open-source [Roslyn](https://github.com/dotnet/Roslyn) project.</span></span>

<span data-ttu-id="c612d-247">Das Ändern einer Methode in ein Ausdruckskörpermember ist eine [binärkompatible](version-update-considerations.md#binary-compatible-changes) Änderung.</span><span class="sxs-lookup"><span data-stu-id="c612d-247">Changing a method to an expression bodied member is a [binary compatible change](version-update-considerations.md#binary-compatible-changes).</span></span>

## <a name="throw-expressions"></a><span data-ttu-id="c612d-248">Throw-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="c612d-248">Throw expressions</span></span>

<span data-ttu-id="c612d-249">In C# ist `throw` schon immer eine Anweisung.</span><span class="sxs-lookup"><span data-stu-id="c612d-249">In C#, `throw` has always been a statement.</span></span> <span data-ttu-id="c612d-250">Da `throw` eine Anweisung und kein Ausdruck ist, gab es C#-Konstrukte, in denen diese Anweisung nicht verwendet werden konnte.</span><span class="sxs-lookup"><span data-stu-id="c612d-250">Because `throw` is a statement, not an expression, there were C# constructs where you couldn't use it.</span></span> <span data-ttu-id="c612d-251">Darunter waren bedingte Ausdrücke, NULL-Sammelausdrücke und einige Lambdaausdrücke.</span><span class="sxs-lookup"><span data-stu-id="c612d-251">These included conditional expressions, null coalescing expressions, and some lambda expressions.</span></span> <span data-ttu-id="c612d-252">Das Hinzufügen von Ausdruckskörpermembern fügt mehr Speicherorte hinzu, bei denen `throw`-Ausdrücke nützlich wären.</span><span class="sxs-lookup"><span data-stu-id="c612d-252">The addition of expression-bodied members adds more locations where `throw` expressions would be useful.</span></span> <span data-ttu-id="c612d-253">Damit Sie diese Konstrukte schreiben können, wurden in C# 7.0 [*Throw-Ausdrücke*](../language-reference/keywords/throw.md#the-throw-expression) eingeführt.</span><span class="sxs-lookup"><span data-stu-id="c612d-253">So that you can write any of these constructs, C# 7.0 introduces [*throw expressions*](../language-reference/keywords/throw.md#the-throw-expression).</span></span>

<span data-ttu-id="c612d-254">Diese Ergänzung erleichtert das Schreiben ausdrucksbasierteren Codes.</span><span class="sxs-lookup"><span data-stu-id="c612d-254">This addition makes it easier to write more expression-based code.</span></span> <span data-ttu-id="c612d-255">Sie benötigen zur Fehlerüberprüfung keine weiteren Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="c612d-255">You don't need additional statements for error checking.</span></span>

## <a name="default-literal-expressions"></a><span data-ttu-id="c612d-256">Literale Standardausdrücke</span><span class="sxs-lookup"><span data-stu-id="c612d-256">Default literal expressions</span></span>

<span data-ttu-id="c612d-257">Literale Standardausdrücke sind eine Erweiterung von Ausdrücken mit Standardwert.</span><span class="sxs-lookup"><span data-stu-id="c612d-257">Default literal expressions are an enhancement to default value expressions.</span></span> <span data-ttu-id="c612d-258">Diese Ausdrücke initialisieren eine Variable auf dem Standardwert.</span><span class="sxs-lookup"><span data-stu-id="c612d-258">These expressions initialize a variable to the default value.</span></span> <span data-ttu-id="c612d-259">Dort, wo Sie vorher das Folgende geschrieben haben:</span><span class="sxs-lookup"><span data-stu-id="c612d-259">Where you previously would write:</span></span>

```csharp
Func<string, bool> whereClause = default(Func<string, bool>);
```

<span data-ttu-id="c612d-260">Können Sie nun den Typ weglassen, der auf der rechten Seite der Initialisierung steht.</span><span class="sxs-lookup"><span data-stu-id="c612d-260">You can now omit the type on the right-hand side of the initialization:</span></span>

```csharp
Func<string, bool> whereClause = default;
```

<span data-ttu-id="c612d-261">Weitere Informationen finden Sie im Abschnitt [Standardliteral](../language-reference/operators/default.md#default-literal) des Artikels zum [default-Operator](../language-reference/operators/default.md).</span><span class="sxs-lookup"><span data-stu-id="c612d-261">For more information, see the [default literal](../language-reference/operators/default.md#default-literal) section of the [default operator](../language-reference/operators/default.md) article.</span></span>

## <a name="numeric-literal-syntax-improvements"></a><span data-ttu-id="c612d-262">Verbesserung der numerischen literalen Syntax</span><span class="sxs-lookup"><span data-stu-id="c612d-262">Numeric literal syntax improvements</span></span>

<span data-ttu-id="c612d-263">Falsches Lesen numerischer Konstanten kann Code beim ersten Lesen schwerer verständlich machen.</span><span class="sxs-lookup"><span data-stu-id="c612d-263">Misreading numeric constants can make it harder to understand code when reading it for the first time.</span></span> <span data-ttu-id="c612d-264">Bitmasken oder andere symbolische Werte können Missverständnisse hervorrufen.</span><span class="sxs-lookup"><span data-stu-id="c612d-264">Bit masks or other symbolic values are prone to misunderstanding.</span></span> <span data-ttu-id="c612d-265">C# 7.0 enthält zwei neue Funktionen, mit denen Zahlen für den beabsichtigten Zweck so lesbar wie möglich geschrieben werden können: *binäre Literale* und *Zifferntrennzeichen*.</span><span class="sxs-lookup"><span data-stu-id="c612d-265">C# 7.0 includes two new features to write numbers in the most readable fashion for the intended use: *binary literals*, and *digit separators*.</span></span>

<span data-ttu-id="c612d-266">Beim Erstellen von Bitmasken oder wenn die binäre Darstellung einer Zahl den Code besonders gut lesbar macht, sollten Sie diese Zahl im Binärformat schreiben:</span><span class="sxs-lookup"><span data-stu-id="c612d-266">For those times when you're creating bit masks, or whenever a binary representation of a number makes the most readable code, write that number in binary:</span></span>

[!code-csharp[ThousandSeparators](~/samples/snippets/csharp/new-in-7/Program.cs#ThousandSeparators "Thousands separators")]

<span data-ttu-id="c612d-267">Das `0b` am Anfang der Konstante gibt an, dass die Zahl als binäre Zahl geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="c612d-267">The `0b` at the beginning of the constant indicates that the number is written as a binary number.</span></span> <span data-ttu-id="c612d-268">Binäre Zahlen können lang werden. Daher kann die Einführung von `_` als Ziffertrennzeichen wie in der binären Konstante im vorherigen Beispiel gezeigt die Bitmuster übersichtlicher machen.</span><span class="sxs-lookup"><span data-stu-id="c612d-268">Binary numbers can get long, so it's often easier to see the bit patterns by introducing the `_` as a digit separator, as shown in the binary constant in the preceding example.</span></span> <span data-ttu-id="c612d-269">Das Zifferntrennzeichen kann überall in der Konstante angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c612d-269">The digit separator can appear anywhere in the constant.</span></span> <span data-ttu-id="c612d-270">Für Zahlen der Basis 10 wird es üblicherweise als Tausendertrennzeichen verwendet.</span><span class="sxs-lookup"><span data-stu-id="c612d-270">For base 10 numbers, it is common to use it as a thousands separator.</span></span> <span data-ttu-id="c612d-271">Hexadezimale und binäre numerische Literale dürfen jetzt mit `_` beginnen:</span><span class="sxs-lookup"><span data-stu-id="c612d-271">Hex and binary numeric literals may begin with an `_`:</span></span>

[!code-csharp[LargeIntegers](~/samples/snippets/csharp/new-in-7/Program.cs#LargeIntegers "Large integer")]

<span data-ttu-id="c612d-272">Das Zifferntrennzeichen kann auch mit `decimal`-, `float`- und `double`-Typen verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="c612d-272">The digit separator can be used with `decimal`, `float`, and `double` types as well:</span></span>

[!code-csharp[OtherConstants](~/samples/snippets/csharp/new-in-7/Program.cs#OtherConstants "non-integral constants")]

<span data-ttu-id="c612d-273">Insgesamt können Sie numerische Konstanten viel leserlicher deklarieren.</span><span class="sxs-lookup"><span data-stu-id="c612d-273">Taken together, you can declare numeric constants with much more readability.</span></span>

## <a name="out-variables"></a><span data-ttu-id="c612d-274">`out`-Variablen</span><span class="sxs-lookup"><span data-stu-id="c612d-274">`out` variables</span></span>

<span data-ttu-id="c612d-275">Die vorhandene Syntax zur Unterstützung von `out`-Parametern wurde in C# 7 verbessert.</span><span class="sxs-lookup"><span data-stu-id="c612d-275">The existing syntax that supports `out` parameters has been improved in C# 7.</span></span> <span data-ttu-id="c612d-276">Nun können Sie `out`-Variablen in der Argumentliste eines Methodenaufrufs deklarieren, anstatt eine separate Deklarationsanweisung zu schreiben:</span><span class="sxs-lookup"><span data-stu-id="c612d-276">You can now declare `out` variables in the argument list of a method call, rather than writing a separate declaration statement:</span></span>

[!code-csharp[OutVariableDeclarations](~/samples/snippets/csharp/new-in-7/program.cs#OutVariableDeclarations "Out variable declarations")]

<span data-ttu-id="c612d-277">Sie sollten den Typ der `out`-Variablen aus Gründen der Übersichtlichkeit angeben. Dies wird im vorherigen Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="c612d-277">You may want to specify the type of the `out` variable for clarity, as shown in the preceding example.</span></span> <span data-ttu-id="c612d-278">Die Sprache unterstützt jedoch die Verwendung einer implizit typisierten lokalen Variable:</span><span class="sxs-lookup"><span data-stu-id="c612d-278">However, the language does support using an implicitly typed local variable:</span></span>

[!code-csharp[OutVarVariableDeclarations](~/samples/snippets/csharp/new-in-7/program.cs#OutVarVariableDeclarations "Implicitly typed Out variable")]

- <span data-ttu-id="c612d-279">Der Code ist einfacher zu lesen.</span><span class="sxs-lookup"><span data-stu-id="c612d-279">The code is easier to read.</span></span>
  - <span data-ttu-id="c612d-280">Sie deklarieren die out-Variable, wenn Sie sie verwenden, nicht in einer anderen Codezeile weiter oben.</span><span class="sxs-lookup"><span data-stu-id="c612d-280">You declare the out variable where you use it, not on a preceding line of code.</span></span>
- <span data-ttu-id="c612d-281">Sie müssen keinen Anfangswert zuweisen.</span><span class="sxs-lookup"><span data-stu-id="c612d-281">No need to assign an initial value.</span></span>
  - <span data-ttu-id="c612d-282">Durch das Deklarieren der `out`-Variable, wenn sie in einem Methodenaufruf verwendet wird, können Sie diese nicht versehentlich verwenden, bevor sie zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="c612d-282">By declaring the `out` variable where it's used in a method call, you can't accidentally use it before it is assigned.</span></span>

<span data-ttu-id="c612d-283">Die in C# 7.0 zum Zulassen von `out`-Variablendeklarationen hinzugefügte Syntax wurde erweitert, sodass sie Feldinitialisierer, Eigenschafteninitialisierer, Konstruktorinitialisierer und Abfrageklauseln umfasst.</span><span class="sxs-lookup"><span data-stu-id="c612d-283">The syntax added in C# 7.0 to allow `out` variable declarations has been extended to include field initializers, property initializers, constructor initializers, and query clauses.</span></span> <span data-ttu-id="c612d-284">Sie ermöglicht Code wie im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c612d-284">It enables code such as the following example:</span></span>

```csharp
public class B
{
   public B(int i, out int j)
   {
      j = i;
   }
}

public class D : B
{
   public D(int i) : base(i, out var j)
   {
      Console.WriteLine($"The value of 'j' is {j}");
   }
}
```

## <a name="non-trailing-named-arguments"></a><span data-ttu-id="c612d-285">Nicht schließende benannte Argumente</span><span class="sxs-lookup"><span data-stu-id="c612d-285">Non-trailing named arguments</span></span>

<span data-ttu-id="c612d-286">Methodenaufrufe dürfen jetzt benannte Argumente verwenden, die positionellen Argumenten vorstehen, wenn diese benannten Argumente in der richtigen Position verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c612d-286">Method calls may now use named arguments that precede positional arguments when those named arguments are in the correct positions.</span></span> <span data-ttu-id="c612d-287">Weitere Informationen finden Sie unter [Benannte und optionale Argumente (C#-Programmierhandbuch)](../programming-guide/classes-and-structs/named-and-optional-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="c612d-287">For more information, see [Named and optional arguments](../programming-guide/classes-and-structs/named-and-optional-arguments.md).</span></span>

## <a name="private-protected-access-modifier"></a><span data-ttu-id="c612d-288">Zugriffsmodifizierer *private protected*</span><span class="sxs-lookup"><span data-stu-id="c612d-288">*private protected* access modifier</span></span>

<span data-ttu-id="c612d-289">Ein neuer zusammengesetzter Zugriffsmodifizierer: `private protected` zeigt an, dass auf ein Element durch eine es enthaltende Klasse oder durch innerhalb der gleichen Assembly deklarierte abgeleitete Klassen zugegriffen werden darf.</span><span class="sxs-lookup"><span data-stu-id="c612d-289">A new compound access modifier: `private protected` indicates that a member may be accessed by containing class or derived classes that are declared in the same assembly.</span></span> <span data-ttu-id="c612d-290">Während `protected internal` den Zugriff durch abgeleitete Klassen oder Klassen, die sich in der gleichen Assembly befinden, erlaubt, schränkt `private protected` den Zugriff auf innerhalb der gleichen Assembly deklarierte abgeleitete Typen ein.</span><span class="sxs-lookup"><span data-stu-id="c612d-290">While `protected internal` allows access by derived classes or classes that are in the same assembly, `private protected` limits access to derived types declared in the same assembly.</span></span>

<span data-ttu-id="c612d-291">Weitere Informationen finden Sie unter [Zugriffsmodifizierer (C#-Referenz)](../language-reference/keywords/access-modifiers.md) in der Sprachreferenz.</span><span class="sxs-lookup"><span data-stu-id="c612d-291">For more information, see [access modifiers](../language-reference/keywords/access-modifiers.md) in the language reference.</span></span>

## <a name="improved-overload-candidates"></a><span data-ttu-id="c612d-292">Verbesserte Überladungskandidaten</span><span class="sxs-lookup"><span data-stu-id="c612d-292">Improved overload candidates</span></span>

<span data-ttu-id="c612d-293">In jedem Release werden die Überladungsauflösungsregeln für Situationen aktualisiert, in denen mehrdeutige Methodenaufrufe eine „naheliegende“ Auswahlmöglichkeit haben.</span><span class="sxs-lookup"><span data-stu-id="c612d-293">In every release, the overload resolution rules get updated to address situations where ambiguous method invocations have an "obvious" choice.</span></span> <span data-ttu-id="c612d-294">In diesem Release werden drei neue Regeln hinzufügt, damit der Compiler die naheliegende Auswahlmöglichkeit nutzt:</span><span class="sxs-lookup"><span data-stu-id="c612d-294">This release adds three new rules to help the compiler pick the obvious choice:</span></span>

1. <span data-ttu-id="c612d-295">Wenn eine Methodengruppe sowohl Instanz- als auch statische Member enthält, verwirft der Compiler die Instanzmember, wenn die Methode ohne Instanzempfänger oder -kontext aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="c612d-295">When a method group contains both instance and static members, the compiler discards the instance members if the method was invoked without an instance receiver or context.</span></span> <span data-ttu-id="c612d-296">Der Compiler verwirft die statischen Member, wenn die Methode mit einem Instanzempfänger aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="c612d-296">The compiler discards the static members if the method was invoked with an instance receiver.</span></span> <span data-ttu-id="c612d-297">Wenn kein Empfänger vorhanden ist, bezieht der Compiler nur statische Member in einen statischen Kontext ein – andernfalls sowohl statische als auch Instanzmember.</span><span class="sxs-lookup"><span data-stu-id="c612d-297">When there is no receiver, the compiler includes only static members in a static context, otherwise both static and instance members.</span></span> <span data-ttu-id="c612d-298">Wenn unklar ist, ob der Empfänger eine Instanz oder ein Typ ist, bezieht der Compiler beides ein.</span><span class="sxs-lookup"><span data-stu-id="c612d-298">When the receiver is ambiguously an instance or type, the compiler includes both.</span></span> <span data-ttu-id="c612d-299">Ein statischer Kontext, wo ein impliziter `this`-Instanzempfänger nicht verwendet werden kann, enthält den Text von Membern, wo kein `this` definiert ist, z.B. statische Member, sowie Orte, an denen `this` nicht verwendet werden kann, z.B. Feld- und Konstruktorinitialisierer.</span><span class="sxs-lookup"><span data-stu-id="c612d-299">A static context, where an implicit `this` instance receiver cannot be used, includes the body of members where no `this` is defined, such as static members, as well as places where `this` cannot be used, such as field initializers and constructor-initializers.</span></span>
1. <span data-ttu-id="c612d-300">Wenn eine Methodengruppe einige generische Methoden enthält, deren Typargumente ihre Einschränkungen nicht erfüllen, werden diese Member aus dem Satz von Kandidaten entfernt.</span><span class="sxs-lookup"><span data-stu-id="c612d-300">When a method group contains some generic methods whose type arguments do not satisfy their constraints, these members are removed from the candidate set.</span></span>
1. <span data-ttu-id="c612d-301">Für eine Methodengruppenkonvertierung werden Kandidatenmethoden, deren Rückgabetyp nicht mit dem des Delegaten übereinstimmt, aus dem Satz entfernt.</span><span class="sxs-lookup"><span data-stu-id="c612d-301">For a method group conversion, candidate methods whose return type doesn't match up with the delegate's return type are removed from the set.</span></span>

<span data-ttu-id="c612d-302">Sie werden diese Änderung bemerken, da Sie weniger Compilerfehler für mehrdeutige Methodenüberladungen finden werden, wenn Sie sicher sind, welche Methode besser ist.</span><span class="sxs-lookup"><span data-stu-id="c612d-302">You'll only notice this change because you'll find fewer compiler errors for ambiguous method overloads when you are sure which method is better.</span></span>

## <a name="enabling-more-efficient-safe-code"></a><span data-ttu-id="c612d-303">Ermöglichen von effizienterem sicherem Code</span><span class="sxs-lookup"><span data-stu-id="c612d-303">Enabling more efficient safe code</span></span>

<span data-ttu-id="c612d-304">Sie sollten C#-Code sicher schreiben können, der so leistungsstark ist wie unsicherer Code.</span><span class="sxs-lookup"><span data-stu-id="c612d-304">You should be able to write C# code safely that performs as well as unsafe code.</span></span> <span data-ttu-id="c612d-305">Sicherer Code vermeidet Fehlerklassen, z.B. Pufferüberläufe, verirrte Zeiger und andere Fehler beim Arbeitsspeicherzugriff.</span><span class="sxs-lookup"><span data-stu-id="c612d-305">Safe code avoids classes of errors, such as buffer overruns, stray pointers, and other memory access errors.</span></span> <span data-ttu-id="c612d-306">Diese neuen Features erweitern die Funktionen des überprüfbaren sicheren Codes.</span><span class="sxs-lookup"><span data-stu-id="c612d-306">These new features expand the capabilities of verifiable safe code.</span></span> <span data-ttu-id="c612d-307">Schreiben Sie mithilfe sicherer Konstrukte mehr Code.</span><span class="sxs-lookup"><span data-stu-id="c612d-307">Strive to write more of your code using safe constructs.</span></span> <span data-ttu-id="c612d-308">Diese Features erleichtern dies.</span><span class="sxs-lookup"><span data-stu-id="c612d-308">These features make that easier.</span></span>

<span data-ttu-id="c612d-309">Die folgenden neuen Features unterstützen das Design der besseren Leistung für sicheren Code:</span><span class="sxs-lookup"><span data-stu-id="c612d-309">The following new features support the theme of better performance for safe code:</span></span>

- <span data-ttu-id="c612d-310">Sie können ohne Anheften auf feste Felder zugreifen.</span><span class="sxs-lookup"><span data-stu-id="c612d-310">You can access fixed fields without pinning.</span></span>
- <span data-ttu-id="c612d-311">Sie können `ref` erneut lokale Variablen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="c612d-311">You can reassign `ref` local variables.</span></span>
- <span data-ttu-id="c612d-312">Sie können Initialisierer auf `stackalloc`-Arrays verwenden.</span><span class="sxs-lookup"><span data-stu-id="c612d-312">You can use initializers on `stackalloc` arrays.</span></span>
- <span data-ttu-id="c612d-313">Sie können `fixed`-Anweisungen mit jedem Typ verwenden, der ein Muster unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c612d-313">You can use `fixed` statements with any type that supports a pattern.</span></span>
- <span data-ttu-id="c612d-314">Sie können zusätzliche generische Einschränkungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="c612d-314">You can use additional generic constraints.</span></span>
- <span data-ttu-id="c612d-315">Den `in`-Modifizierer für Parameter zur Angabe, dass ein Argument durch Verweis übergeben, von der aufgerufenen Methode aber nicht verändert wird.</span><span class="sxs-lookup"><span data-stu-id="c612d-315">The `in` modifier on parameters, to specify that an argument is passed by reference but not modified by the called method.</span></span> <span data-ttu-id="c612d-316">Das Hinzufügen des Modifizierers `in` zu einem Argument ist eine [quellkompatible Änderung](version-update-considerations.md#source-compatible-changes).</span><span class="sxs-lookup"><span data-stu-id="c612d-316">Adding the `in` modifier to an argument is a [source compatible change](version-update-considerations.md#source-compatible-changes).</span></span>
- <span data-ttu-id="c612d-317">Der `ref readonly`-Modifizierer für die Methodenrückgabe, um anzugeben, dass eine Methode ihren Wert als Verweis zurückgibt und keinen Schreibzugriff auf dieses Objekt zulässt.</span><span class="sxs-lookup"><span data-stu-id="c612d-317">The `ref readonly` modifier on method returns, to indicate that a method returns its value by reference but doesn't allow writes to that object.</span></span> <span data-ttu-id="c612d-318">Das Hinzufügen des Modifizierers `ref readonly` ist eine [quellkompatible Änderung](version-update-considerations.md#source-compatible-changes), wenn die Rückgabe einem Wert zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="c612d-318">Adding the `ref readonly` modifier is a [source compatible change](version-update-considerations.md#source-compatible-changes), if the return is assigned to a value.</span></span> <span data-ttu-id="c612d-319">Das Hinzufügen des Modifizierers `readonly` zu einer vorhandenen `ref`-Rückgabeanweisung ist eine [inkompatible Änderung](version-update-considerations.md#incompatible-changes).</span><span class="sxs-lookup"><span data-stu-id="c612d-319">Adding the `readonly` modifier to an existing `ref` return statement is an [incompatible change](version-update-considerations.md#incompatible-changes).</span></span> <span data-ttu-id="c612d-320">Es verlangt von Aufrufern das Aktualisieren der lokalen `ref`-Variablen, um den `readonly`-Modifizierer einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="c612d-320">It requires callers to update the declaration of `ref` local variables to include the `readonly` modifier.</span></span>
- <span data-ttu-id="c612d-321">Die `readonly struct`-Deklaration, um anzugeben, dass eine Struktur unveränderlich ist und ihren Membermethoden als `in`-Parameter übergeben werden sollte.</span><span class="sxs-lookup"><span data-stu-id="c612d-321">The `readonly struct` declaration, to indicate that a struct is immutable and should be passed as an `in` parameter to its member methods.</span></span> <span data-ttu-id="c612d-322">Das Hinzufügen des Modifizierers `readonly` zu einer vorhandenen Strukturdeklaration ist eine [binärkompatible Änderung](version-update-considerations.md#binary-compatible-changes).</span><span class="sxs-lookup"><span data-stu-id="c612d-322">Adding the `readonly` modifier to an existing struct declaration is a [binary compatible change](version-update-considerations.md#binary-compatible-changes).</span></span>
- <span data-ttu-id="c612d-323">Die `ref struct`-Deklaration, um anzugeben, dass ein Strukturtyp direkt auf verwalteten Arbeitsspeicher zugreift und immer per Stapel zugeordnet werden muss.</span><span class="sxs-lookup"><span data-stu-id="c612d-323">The `ref struct` declaration, to indicate that a struct type accesses managed memory directly and must always be stack allocated.</span></span> <span data-ttu-id="c612d-324">Das Hinzufügen des Modifizierers `ref` zu einer vorhandenen `struct`-Deklaration ist eine [inkompatible Änderung](version-update-considerations.md#incompatible-changes).</span><span class="sxs-lookup"><span data-stu-id="c612d-324">Adding the `ref` modifier to an existing `struct` declaration is an [incompatible change](version-update-considerations.md#incompatible-changes).</span></span> <span data-ttu-id="c612d-325">Ein `ref struct` kann kein Mitglied einer Klasse sein oder an anderen Stellen verwendet werden, wo es auf dem Heap zugewiesen werden könnte.</span><span class="sxs-lookup"><span data-stu-id="c612d-325">A `ref struct` cannot be a member of a class or used in other locations where it may be allocated on the heap.</span></span>

<span data-ttu-id="c612d-326">Weitere Informationen zu all diesen Änderungen finden Sie unter [Schreiben von sicherem und effizientem Code](../write-safe-efficient-code.md).</span><span class="sxs-lookup"><span data-stu-id="c612d-326">You can read more about all these changes in [Write safe efficient code](../write-safe-efficient-code.md).</span></span>

### <a name="ref-locals-and-returns"></a><span data-ttu-id="c612d-327">Lokale ref-Variablen und Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="c612d-327">Ref locals and returns</span></span>

<span data-ttu-id="c612d-328">Diese Funktion ermöglicht Algorithmen, die Verweise auf Variablen verwenden und zurückgeben, die an anderer Stelle definiert sind.</span><span class="sxs-lookup"><span data-stu-id="c612d-328">This feature enables algorithms that use and return references to variables defined elsewhere.</span></span> <span data-ttu-id="c612d-329">Ein Beispiel ist das Arbeiten mit großen Matrizen und die Suche nach einem einzigen Ort mit bestimmten Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="c612d-329">One example is working with large matrices, and finding a single location with certain characteristics.</span></span> <span data-ttu-id="c612d-330">Die folgende Methode gibt einen **Verweis** auf diesen Speicher in der Matrix zurück:</span><span class="sxs-lookup"><span data-stu-id="c612d-330">The following method returns a **reference** to that storage in the matrix:</span></span>

[!code-csharp[FindReturningRef](~/samples/snippets/csharp/new-in-7/MatrixSearch.cs#FindReturningRef "Find returning by reference")]

<span data-ttu-id="c612d-331">Sie können den Rückgabewert als `ref` deklarieren und diesen Wert wie im folgenden Code gezeigt in der Matrix ändern:</span><span class="sxs-lookup"><span data-stu-id="c612d-331">You can declare the return value as a `ref` and modify that value in the matrix, as shown in the following code:</span></span>

[!code-csharp[AssignRefReturn](~/samples/snippets/csharp/new-in-7/Program.cs#AssignRefReturn "Assign ref return")]

<span data-ttu-id="c612d-332">Die C#-Sprache verfügt über mehrere Regeln, die Sie vor einer falschen Verwendung der lokalen `ref`-Variablen und Rückgabetypen schützen:</span><span class="sxs-lookup"><span data-stu-id="c612d-332">The C# language has several rules that protect you from misusing the `ref` locals and returns:</span></span>

- <span data-ttu-id="c612d-333">Sie müssen der Methodensignatur und allen `return`-Anweisungen einer Methode das `ref`-Schlüsselwort hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="c612d-333">You must add the `ref` keyword to the method signature and to all `return` statements in a method.</span></span>
  - <span data-ttu-id="c612d-334">Dadurch wird deutlich, dass Rückgaben in der gesamten Methode als Verweis erfolgen.</span><span class="sxs-lookup"><span data-stu-id="c612d-334">That makes it clear the method returns by reference throughout the method.</span></span>
- <span data-ttu-id="c612d-335">Eine `ref return`-Rückgabe kann einer Wert- oder einer `ref`-Variablen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="c612d-335">A `ref return` may be assigned to a value variable, or a `ref` variable.</span></span>
  - <span data-ttu-id="c612d-336">Der Aufrufer steuert, ob der Rückgabewert kopiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="c612d-336">The caller controls whether the return value is copied or not.</span></span> <span data-ttu-id="c612d-337">Durch Auslassen des `ref`-Modifizierers beim Zuweisen des Rückgabewerts gibt der Aufrufer an, dass der Wert kopiert werden und nicht etwa ein Verweis auf den Speicher erfolgen soll.</span><span class="sxs-lookup"><span data-stu-id="c612d-337">Omitting the `ref` modifier when assigning the return value indicates that the caller wants a copy of the value, not a reference to the storage.</span></span>
- <span data-ttu-id="c612d-338">Sie können einer lokalen `ref`-Variablen keinen Rückgabewert einer Standardmethode zuweisen.</span><span class="sxs-lookup"><span data-stu-id="c612d-338">You can't assign a standard method return value to a `ref` local variable.</span></span>
  - <span data-ttu-id="c612d-339">Dadurch werden Aussagen wie `ref int i = sequence.Count();` nicht zugelassen.</span><span class="sxs-lookup"><span data-stu-id="c612d-339">That disallows statements like `ref int i = sequence.Count();`</span></span>
- <span data-ttu-id="c612d-340">Sie können `ref` nicht an eine Variable zurückgeben, deren Lebensdauer nicht über die Ausführung der Methode hinausgeht.</span><span class="sxs-lookup"><span data-stu-id="c612d-340">You can't return a `ref` to a variable whose lifetime doesn't extend beyond the execution of the method.</span></span>
  - <span data-ttu-id="c612d-341">Das bedeutet, dass Sie keinen Verweis auf eine lokale Variable oder eine Variable mit einem ähnlichen Bereich zurückgeben können.</span><span class="sxs-lookup"><span data-stu-id="c612d-341">That means you can't return a reference to a local variable or a variable with a similar scope.</span></span>
- <span data-ttu-id="c612d-342">Lokale `ref`-Variablen und Rückgabewerte können nicht in Verbindung mit asynchronen Methoden verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c612d-342">`ref` locals and returns can't be used with async methods.</span></span>
  - <span data-ttu-id="c612d-343">Der Compiler kann nicht feststellen, ob die Variable, auf die verwiesen wird, bei der Rückgabe der asynchronen Methode auf ihren endgültigen Wert festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="c612d-343">The compiler can't know if the referenced variable has been set to its final value when the async method returns.</span></span>

<span data-ttu-id="c612d-344">Das Hinzufügen von lokalen ref-Variablen und ref-Rückgaben ermöglicht effizientere Algorithmen, da Werte nicht kopiert oder dereferenzierende Vorgänge nicht mehrmals ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c612d-344">The addition of ref locals and ref returns enables algorithms that are more efficient by avoiding copying values, or performing dereferencing operations multiple times.</span></span>

<span data-ttu-id="c612d-345">Das Hinzufügen von `ref` zum Rückgabewert stellt eine [quellkompatible Änderung](version-update-considerations.md#source-compatible-changes) dar.</span><span class="sxs-lookup"><span data-stu-id="c612d-345">Adding `ref` to the return value is a [source compatible change](version-update-considerations.md#source-compatible-changes).</span></span> <span data-ttu-id="c612d-346">Vorhandener Code lässt sich kompilieren, der ref-Rückgabewert wird aber bei der Zuweisung kopiert.</span><span class="sxs-lookup"><span data-stu-id="c612d-346">Existing code compiles, but the ref return value is copied when assigned.</span></span> <span data-ttu-id="c612d-347">Aufrufer müssen den Speicher für den Rückgabewert in eine lokale `ref`-Variable aktualisieren, um die Rückgabe als Verweis zu speichern.</span><span class="sxs-lookup"><span data-stu-id="c612d-347">Callers must update the storage for the return value to a `ref` local variable to store the return as a reference.</span></span>

<span data-ttu-id="c612d-348">Lokale `ref`-Variablen werden jetzt möglicherweise neu zugewiesen, um nach der Initialisierung auf verschiedene Instanzen zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="c612d-348">Now, `ref` locals may be reassigned to refer to different instances after being initialized.</span></span> <span data-ttu-id="c612d-349">Der folgende Code wird jetzt kompiliert:</span><span class="sxs-lookup"><span data-stu-id="c612d-349">The following code now compiles:</span></span>

```csharp
ref VeryLargeStruct refLocal = ref veryLargeStruct; // initialization
refLocal = ref anotherVeryLargeStruct; // reassigned, refLocal refers to different storage.
```

<span data-ttu-id="c612d-350">Weitere Informationen finden Sie im Artikel zu [`ref`-Rückgaben und lokalen `ref`-Variablen](../programming-guide/classes-and-structs/ref-returns.md) und im Artikel zu [`foreach`](../language-reference/keywords/foreach-in.md).</span><span class="sxs-lookup"><span data-stu-id="c612d-350">For more information, see the article on [`ref` returns and `ref` locals](../programming-guide/classes-and-structs/ref-returns.md), and the article on [`foreach`](../language-reference/keywords/foreach-in.md).</span></span>

<span data-ttu-id="c612d-351">Weitere Informationen finden Sie im Artikel [Schlüsselwort „ref“](../language-reference/keywords/ref.md).</span><span class="sxs-lookup"><span data-stu-id="c612d-351">For more information, see the [ref keyword](../language-reference/keywords/ref.md) article.</span></span>

### <a name="conditional-ref-expressions"></a><span data-ttu-id="c612d-352">Bedingte `ref` Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="c612d-352">Conditional `ref` expressions</span></span>

<span data-ttu-id="c612d-353">Schließlich kann ein bedingter Ausdruck als Ergebnis einen Verweis anstatt eines Werts erzeugen.</span><span class="sxs-lookup"><span data-stu-id="c612d-353">Finally, the conditional expression may produce a ref result instead of a value result.</span></span> <span data-ttu-id="c612d-354">Beispielsweise würden Sie folgendes schreiben, um einen Verweis auf das erste Element in einem von zwei Arrays abzurufen:</span><span class="sxs-lookup"><span data-stu-id="c612d-354">For example, you would write the following to retrieve a reference to the first element in one of two arrays:</span></span>

```csharp
ref var r = ref (arr != null ? ref arr[0] : ref otherArr[0]);
```

<span data-ttu-id="c612d-355">Die Variable `r` ist ein Verweis auf den ersten Wert in `arr` oder `otherArr`.</span><span class="sxs-lookup"><span data-stu-id="c612d-355">The variable `r` is a reference to the first value in either `arr` or `otherArr`.</span></span>

<span data-ttu-id="c612d-356">Weitere Informationen finden Sie unter [conditional-Operator (?:)](../language-reference/operators/conditional-operator.md) in der Sprachreferenz.</span><span class="sxs-lookup"><span data-stu-id="c612d-356">For more information, see [conditional operator (?:)](../language-reference/operators/conditional-operator.md) in the language reference.</span></span>

### <a name="in-parameter-modifier"></a><span data-ttu-id="c612d-357">Modifizierer für `in`-Parameter</span><span class="sxs-lookup"><span data-stu-id="c612d-357">`in` parameter modifier</span></span>

<span data-ttu-id="c612d-358">Das `in`-Schlüsselwort ergänzt die vorhandenen Schlüsselwörter ref und out zum Übergeben von Argumenten als Verweis.</span><span class="sxs-lookup"><span data-stu-id="c612d-358">The `in` keyword complements the existing ref and out keywords to pass arguments by reference.</span></span> <span data-ttu-id="c612d-359">Durch das `in`-Schlüsselwort wird festgelegt, dass das Argument als Verweis übergeben wird, die aufgerufene Methode aber nicht den Wert ändert.</span><span class="sxs-lookup"><span data-stu-id="c612d-359">The `in` keyword specifies passing the argument by reference, but the called method doesn't modify the value.</span></span>

<span data-ttu-id="c612d-360">Sie können Überladungen, die nach Wert oder nach schreibgeschütztem Verweis übergeben werden, wie im folgenden Code gezeigt deklarieren:</span><span class="sxs-lookup"><span data-stu-id="c612d-360">You may declare overloads that pass by value or by readonly reference, as shown in the following code:</span></span>

```csharp
static void M(S arg);
static void M(in S arg);
```

<span data-ttu-id="c612d-361">Die Überladung, die nach Wert übergeben wird (die erste im obigen Beispiel) ist besser als die Version, die nach schreibgeschütztem Verweis übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="c612d-361">The by value (first in the preceding example) overload is better than the by readonly reference version.</span></span> <span data-ttu-id="c612d-362">Um die Version mit dem readonly-Verweisargument aufzurufen, müssen Sie auch den `in`-Modifizierer beim Aufrufen der Methode einbeziehen.</span><span class="sxs-lookup"><span data-stu-id="c612d-362">To call the version with the readonly reference argument, you must include the `in` modifier when calling the method.</span></span>

<span data-ttu-id="c612d-363">Weitere Informationen finden Sie im Artikel zum [`in`-Parametermodifizierer](../language-reference/keywords/in-parameter-modifier.md).</span><span class="sxs-lookup"><span data-stu-id="c612d-363">For more information, see the article on the [`in` parameter modifier](../language-reference/keywords/in-parameter-modifier.md).</span></span>

### <a name="more-types-support-the-fixed-statement"></a><span data-ttu-id="c612d-364">Weitere Typen unterstützen die `fixed`-Anweisung</span><span class="sxs-lookup"><span data-stu-id="c612d-364">More types support the `fixed` statement</span></span>

<span data-ttu-id="c612d-365">Die `fixed`-Anweisung unterstützte eine begrenzte Anzahl von Typen.</span><span class="sxs-lookup"><span data-stu-id="c612d-365">The `fixed` statement supported a limited set of types.</span></span> <span data-ttu-id="c612d-366">Ab C# 7.3 kann jeder Typ, der eine `GetPinnableReference()`-Methode enthält, die eine `ref T` oder `ref readonly T` zurückgibt, `fixed` sein.</span><span class="sxs-lookup"><span data-stu-id="c612d-366">Starting with C# 7.3, any type that contains a `GetPinnableReference()` method that returns a `ref T` or `ref readonly T` may be `fixed`.</span></span> <span data-ttu-id="c612d-367">Dieses Feature hinzuzufügen, bedeutet, dass `fixed` mit <xref:System.Span%601?displayProperty=nameWithType> und verwandten Typen genutzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="c612d-367">Adding this feature means that `fixed` can be used with <xref:System.Span%601?displayProperty=nameWithType> and related types.</span></span>

<span data-ttu-id="c612d-368">Weitere Informationen finden Sie im Artikel zur [`fixed`-Anweisung](../language-reference/keywords/fixed-statement.md) in der Sprachreferenz.</span><span class="sxs-lookup"><span data-stu-id="c612d-368">For more information, see the [`fixed` statement](../language-reference/keywords/fixed-statement.md) article in the language reference.</span></span>

### <a name="indexing-fixed-fields-does-not-require-pinning"></a><span data-ttu-id="c612d-369">Indizieren von `fixed`-Feldern erfordert kein Anheften</span><span class="sxs-lookup"><span data-stu-id="c612d-369">Indexing `fixed` fields does not require pinning</span></span>

<span data-ttu-id="c612d-370">Betrachten Sie diese Struktur:</span><span class="sxs-lookup"><span data-stu-id="c612d-370">Consider this struct:</span></span>

```csharp
unsafe struct S
{
    public fixed int myFixedField[10];
}
```

<span data-ttu-id="c612d-371">In früheren Versionen von C# mussten Sie eine Variable für den Zugriff auf eine der ganzen Zahlen anheften, die Teil von `myFixedField` sind.</span><span class="sxs-lookup"><span data-stu-id="c612d-371">In earlier versions of C#, you needed to pin a variable to access one of the integers that are part of `myFixedField`.</span></span> <span data-ttu-id="c612d-372">Der folgende Code wird kompiliert, ohne die Variable `p` in einer separaten `fixed`-Anweisung anzuheften:</span><span class="sxs-lookup"><span data-stu-id="c612d-372">Now, the following code compiles without pinning the variable `p` inside a separate `fixed` statement:</span></span>

```csharp
class C
{
    static S s = new S();

    unsafe public void M()
    {
        int p = s.myFixedField[5];
    }
}
```

<span data-ttu-id="c612d-373">Die Variable `p` greift auf ein Element in `myFixedField` zu.</span><span class="sxs-lookup"><span data-stu-id="c612d-373">The variable `p` accesses one element in `myFixedField`.</span></span> <span data-ttu-id="c612d-374">Sie müssen keine separate `int*`-Variable deklarieren.</span><span class="sxs-lookup"><span data-stu-id="c612d-374">You don't need to declare a separate `int*` variable.</span></span> <span data-ttu-id="c612d-375">Sie benötigen weiterhin einen `unsafe`-Kontext.</span><span class="sxs-lookup"><span data-stu-id="c612d-375">You still need an `unsafe` context.</span></span> <span data-ttu-id="c612d-376">In früheren Versionen von C# müssen Sie einen zweiten festen Zeiger deklarieren:</span><span class="sxs-lookup"><span data-stu-id="c612d-376">In earlier versions of C#, you need to declare a second fixed pointer:</span></span>

```csharp
class C
{
    static S s = new S();

    unsafe public void M()
    {
        fixed (int* ptr = s.myFixedField)
        {
            int p = ptr[5];
        }
    }
}
```

<span data-ttu-id="c612d-377">Weitere Informationen finden Sie im Artikel zur [`fixed`-Anweisung](../language-reference/keywords/fixed-statement.md).</span><span class="sxs-lookup"><span data-stu-id="c612d-377">For more information, see the article on the [`fixed` statement](../language-reference/keywords/fixed-statement.md).</span></span>

### <a name="stackalloc-arrays-support-initializers"></a><span data-ttu-id="c612d-378">`stackalloc`-Arrays unterstützen Initialisierer</span><span class="sxs-lookup"><span data-stu-id="c612d-378">`stackalloc` arrays support initializers</span></span>

<span data-ttu-id="c612d-379">Sie konnten schon die Werte für Elemente in einem Array angeben, wenn Sie es initialisierten:</span><span class="sxs-lookup"><span data-stu-id="c612d-379">You've been able to specify the values for elements in an array when you initialize it:</span></span>

```csharp
var arr = new int[3] {1, 2, 3};
var arr2 = new int[] {1, 2, 3};
```

<span data-ttu-id="c612d-380">Nun kann die gleiche Syntax auf Arrays angewendet werden, die mit `stackalloc` deklariert werden:</span><span class="sxs-lookup"><span data-stu-id="c612d-380">Now, that same syntax can be applied to arrays that are declared with `stackalloc`:</span></span>

```csharp
int* pArr = stackalloc int[3] {1, 2, 3};
int* pArr2 = stackalloc int[] {1, 2, 3};
Span<int> arr = stackalloc [] {1, 2, 3};
```

<span data-ttu-id="c612d-381">Weitere Informationen finden Sie im Artikel zum [`stackalloc`-Operator](../language-reference/operators/stackalloc.md).</span><span class="sxs-lookup"><span data-stu-id="c612d-381">For more information, see the [`stackalloc` operator](../language-reference/operators/stackalloc.md) article.</span></span>

### <a name="enhanced-generic-constraints"></a><span data-ttu-id="c612d-382">Verbesserte generische Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="c612d-382">Enhanced generic constraints</span></span>

<span data-ttu-id="c612d-383">Sie können jetzt Typ <xref:System.Enum?displayProperty=nameWithType> oder <xref:System.Delegate?displayProperty=nameWithType> als Basisklasseneinschränkungen für einen Typparameter angeben.</span><span class="sxs-lookup"><span data-stu-id="c612d-383">You can now specify the type <xref:System.Enum?displayProperty=nameWithType> or <xref:System.Delegate?displayProperty=nameWithType> as base class constraints for a type parameter.</span></span>

<span data-ttu-id="c612d-384">Sie können auch die neue `unmanaged`-Einschränkung nutzen, um anzugeben, dass der Typparameter ein [nicht verwalteter Non-Nullable-Typ](../language-reference/builtin-types/unmanaged-types.md) sein muss.</span><span class="sxs-lookup"><span data-stu-id="c612d-384">You can also use the new `unmanaged` constraint, to specify that a type parameter must be a non-nullable [unmanaged type](../language-reference/builtin-types/unmanaged-types.md).</span></span>

<span data-ttu-id="c612d-385">Weitere Informationen finden Sie in den Artikeln zu generischen [`where`-Einschränkungen](../language-reference/keywords/where-generic-type-constraint.md) und [Einschränkungen für Typparameter](../programming-guide/generics/constraints-on-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="c612d-385">For more information, see the articles on [`where` generic constraints](../language-reference/keywords/where-generic-type-constraint.md) and [constraints on type parameters](../programming-guide/generics/constraints-on-type-parameters.md).</span></span>

<span data-ttu-id="c612d-386">Das Hinzufügen dieser Einschränkungen zu vorhandenen Typen ist eine [inkompatible Änderung](version-update-considerations.md#incompatible-changes).</span><span class="sxs-lookup"><span data-stu-id="c612d-386">Adding these constraints to existing types is an [incompatible change](version-update-considerations.md#incompatible-changes).</span></span> <span data-ttu-id="c612d-387">Geschlossene generische Typen erfüllen diese neuen Einschränkungen möglicherweise nicht mehr.</span><span class="sxs-lookup"><span data-stu-id="c612d-387">Closed generic types may no longer meet these new constraints.</span></span>

### <a name="generalized-async-return-types"></a><span data-ttu-id="c612d-388">Generalisierte asynchrone Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="c612d-388">Generalized async return types</span></span>

<span data-ttu-id="c612d-389">Das Zurückgeben eines `Task`-Objekts von asynchronen Methoden kann Leistungsengpässe in bestimmten Pfaden verursachen.</span><span class="sxs-lookup"><span data-stu-id="c612d-389">Returning a `Task` object from async methods can introduce performance bottlenecks in certain paths.</span></span> <span data-ttu-id="c612d-390">`Task` ist ein Verweistyp, seine Verwendung bedeutet also das Zuordnen eines Objekts.</span><span class="sxs-lookup"><span data-stu-id="c612d-390">`Task` is a reference type, so using it means allocating an object.</span></span> <span data-ttu-id="c612d-391">In Fällen, in denen eine mit dem `async`-Modifizierer deklarierte Methode ein zwischengespeichertes Ergebnis zurückgibt oder synchron abschließt, können die zusätzlichen Zuordnungen viel Zeit bei der Ausführung kritischer Codeabschnitte kosten.</span><span class="sxs-lookup"><span data-stu-id="c612d-391">In cases where a method declared with the `async` modifier returns a cached result, or completes synchronously, the extra allocations can become a significant time cost in performance critical sections of code.</span></span> <span data-ttu-id="c612d-392">Es kann kostspielig werden, wenn diese Zuordnungen in engen Schleifen auftreten.</span><span class="sxs-lookup"><span data-stu-id="c612d-392">It can become costly if those allocations occur in tight loops.</span></span>

<span data-ttu-id="c612d-393">Durch die neue Sprachfunktion sind die Rückgabetypen asynchroner Methoden nicht auf `Task`, `Task<T>` und `void` beschränkt.</span><span class="sxs-lookup"><span data-stu-id="c612d-393">The new language feature means that async method return types aren't limited to `Task`, `Task<T>`, and `void`.</span></span> <span data-ttu-id="c612d-394">Der zurückgegebene Typ muss noch immer das asynchrone Muster erfüllen, d.h. dass eine `GetAwaiter`-Methode verfügbar sein muss.</span><span class="sxs-lookup"><span data-stu-id="c612d-394">The returned type must still satisfy the async pattern, meaning a `GetAwaiter` method must be accessible.</span></span> <span data-ttu-id="c612d-395">Als konkretes Beispiel wurde der `ValueTask`-Typ zu .NET hinzugefügt, um diese neue Sprachfunktion zu nutzen:</span><span class="sxs-lookup"><span data-stu-id="c612d-395">As one concrete example, the `ValueTask` type has been added to .NET to make use of this new language feature:</span></span>

[!code-csharp[UsingValueTask](~/samples/snippets/csharp/new-in-7/AsyncWork.cs#UsingValueTask "Using ValueTask")]

> [!NOTE]
> <span data-ttu-id="c612d-396">Sie müssen das NuGet-Paket [`System.Threading.Tasks.Extensions`](https://www.nuget.org/packages/System.Threading.Tasks.Extensions/) hinzufügen, um den Typ <xref:System.Threading.Tasks.ValueTask%601> verwenden zu können.</span><span class="sxs-lookup"><span data-stu-id="c612d-396">You need to add the NuGet package [`System.Threading.Tasks.Extensions`](https://www.nuget.org/packages/System.Threading.Tasks.Extensions/) > in order to use the <xref:System.Threading.Tasks.ValueTask%601> type.</span></span>

<span data-ttu-id="c612d-397">Diese Verbesserung ist besonders für Bibliotheksautoren hilfreich, um die Zuordnung von `Task` in leistungskritischem Code zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="c612d-397">This enhancement is most useful for library authors to avoid allocating a `Task` in performance critical code.</span></span>

## <a name="new-compiler-options"></a><span data-ttu-id="c612d-398">Neue Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="c612d-398">New compiler options</span></span>

<span data-ttu-id="c612d-399">Neue Compileroptionen unterstützen neue Build- und DevOpsszenarien für C#-Programme.</span><span class="sxs-lookup"><span data-stu-id="c612d-399">New compiler options support new build and DevOps scenarios for C# programs.</span></span>

### <a name="reference-assembly-generation"></a><span data-ttu-id="c612d-400">Generierung der Referenzassembly</span><span class="sxs-lookup"><span data-stu-id="c612d-400">Reference assembly generation</span></span>

<span data-ttu-id="c612d-401">Es gibt zwei neue Compileroptionen, die *Assemblys nur für Referenzen* generieren: [-refout](../language-reference/compiler-options/refout-compiler-option.md) und [-refonly](../language-reference/compiler-options/refonly-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="c612d-401">There are two new compiler options that generate *reference-only assemblies*: [-refout](../language-reference/compiler-options/refout-compiler-option.md) and [-refonly](../language-reference/compiler-options/refonly-compiler-option.md).</span></span>
<span data-ttu-id="c612d-402">In den verlinkten Artikeln werden diese Optionen und Referenzassemblys ausführlich beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c612d-402">The linked articles explain these options and reference assemblies in more detail.</span></span>

### <a name="public-or-open-source-signing"></a><span data-ttu-id="c612d-403">Öffentliche oder Open Source-Signierung</span><span class="sxs-lookup"><span data-stu-id="c612d-403">Public or Open Source signing</span></span>

<span data-ttu-id="c612d-404">Die `-publicsign`-Compileroption weist den Compiler an, die Assembly mit einem öffentlichen Schlüssel zu signieren.</span><span class="sxs-lookup"><span data-stu-id="c612d-404">The `-publicsign` compiler option instructs the compiler to sign the assembly using a public key.</span></span> <span data-ttu-id="c612d-405">Die Assembly wird als signiert markiert, aber die Signatur wird dem öffentlichen Schlüssel entnommen.</span><span class="sxs-lookup"><span data-stu-id="c612d-405">The assembly is marked as signed, but the signature is taken from the public key.</span></span> <span data-ttu-id="c612d-406">Mit dieser Option können Sie signierte Assemblys aus Open Source-Projekten mit einem öffentlichen Schlüssel erstellen.</span><span class="sxs-lookup"><span data-stu-id="c612d-406">This option enables you to build signed assemblies from open-source projects using a public key.</span></span>

<span data-ttu-id="c612d-407">Weitere Informationen finden Sie im Artikel zur [Compileroption „-publicsign“](../language-reference/compiler-options/publicsign-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="c612d-407">For more information, see the [-publicsign compiler option](../language-reference/compiler-options/publicsign-compiler-option.md) article.</span></span>

### <a name="pathmap"></a><span data-ttu-id="c612d-408">pathmap</span><span class="sxs-lookup"><span data-stu-id="c612d-408">pathmap</span></span>

<span data-ttu-id="c612d-409">Die `-pathmap`-Compileroption weist den Compiler an, Quellpfade aus der Buildumgebung mit zugeordneten Quellpfaden zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="c612d-409">The `-pathmap` compiler option instructs the compiler to replace source paths from the build environment with mapped source paths.</span></span> <span data-ttu-id="c612d-410">Die `-pathmap`-Option bestimmt den Quellpfad, der vom Compiler in PDB-Dateien oder für <xref:System.Runtime.CompilerServices.CallerFilePathAttribute> geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="c612d-410">The `-pathmap` option controls the source path written by the compiler to PDB files or for the <xref:System.Runtime.CompilerServices.CallerFilePathAttribute>.</span></span>

<span data-ttu-id="c612d-411">Weitere Informationen finden Sie im Artikel zur [Compileroption „-pathmap“](../language-reference/compiler-options/pathmap-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="c612d-411">For more information, see the [-pathmap compiler option](../language-reference/compiler-options/pathmap-compiler-option.md) article.</span></span>
