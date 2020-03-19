---
title: Neues in C# 8.0 – C#-Leitfaden
description: Überblick über die neuen Funktionen von C# 8.0.
ms.date: 09/20/2019
ms.openlocfilehash: 0013f621268e2a4f1b916b226d83d18c68445ed1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79398328"
---
# <a name="whats-new-in-c-80"></a><span data-ttu-id="68b76-103">Neues in C# 8.0</span><span class="sxs-lookup"><span data-stu-id="68b76-103">What's new in C# 8.0</span></span>

<span data-ttu-id="68b76-104">C# 8.0 fügt der Sprache C# die folgenden Features und Verbesserungen hinzu:</span><span class="sxs-lookup"><span data-stu-id="68b76-104">C# 8.0 adds the following features and enhancements to the C# language:</span></span>

- [<span data-ttu-id="68b76-105">Readonly-Member</span><span class="sxs-lookup"><span data-stu-id="68b76-105">Readonly members</span></span>](#readonly-members)
- [<span data-ttu-id="68b76-106">Standardschnittstellenmethoden</span><span class="sxs-lookup"><span data-stu-id="68b76-106">Default interface methods</span></span>](#default-interface-methods)
- <span data-ttu-id="68b76-107">[Verbesserungen am Musterabgleich](#more-patterns-in-more-places):</span><span class="sxs-lookup"><span data-stu-id="68b76-107">[Pattern matching enhancements](#more-patterns-in-more-places):</span></span>
  - [<span data-ttu-id="68b76-108">switch-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="68b76-108">Switch expressions</span></span>](#switch-expressions)
  - [<span data-ttu-id="68b76-109">Eigenschaftsmuster</span><span class="sxs-lookup"><span data-stu-id="68b76-109">Property patterns</span></span>](#property-patterns)
  - [<span data-ttu-id="68b76-110">Tupelmuster</span><span class="sxs-lookup"><span data-stu-id="68b76-110">Tuple patterns</span></span>](#tuple-patterns)
  - [<span data-ttu-id="68b76-111">Positionsmuster</span><span class="sxs-lookup"><span data-stu-id="68b76-111">Positional patterns</span></span>](#positional-patterns)
- [<span data-ttu-id="68b76-112">using-Deklarationen</span><span class="sxs-lookup"><span data-stu-id="68b76-112">Using declarations</span></span>](#using-declarations)
- [<span data-ttu-id="68b76-113">Statische lokale Funktionen</span><span class="sxs-lookup"><span data-stu-id="68b76-113">Static local functions</span></span>](#static-local-functions)
- [<span data-ttu-id="68b76-114">Verwerfbare Referenzstrukturen</span><span class="sxs-lookup"><span data-stu-id="68b76-114">Disposable ref structs</span></span>](#disposable-ref-structs)
- [<span data-ttu-id="68b76-115">Nullwerte zulassende Verweistypen</span><span class="sxs-lookup"><span data-stu-id="68b76-115">Nullable reference types</span></span>](#nullable-reference-types)
- [<span data-ttu-id="68b76-116">Asynchrone Streams</span><span class="sxs-lookup"><span data-stu-id="68b76-116">Asynchronous streams</span></span>](#asynchronous-streams)
- [<span data-ttu-id="68b76-117">Indizes und Bereiche</span><span class="sxs-lookup"><span data-stu-id="68b76-117">Indices and ranges</span></span>](#indices-and-ranges)
- [<span data-ttu-id="68b76-118">NULL-Coalescing-Zuweisung</span><span class="sxs-lookup"><span data-stu-id="68b76-118">Null-coalescing assignment</span></span>](#null-coalescing-assignment)
- [<span data-ttu-id="68b76-119">Nicht verwaltete konstruierte Typen</span><span class="sxs-lookup"><span data-stu-id="68b76-119">Unmanaged constructed types</span></span>](#unmanaged-constructed-types)
- [<span data-ttu-id="68b76-120">Stackalloc in geschachtelten Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="68b76-120">Stackalloc in nested expressions</span></span>](#stackalloc-in-nested-expressions)
- [<span data-ttu-id="68b76-121">Erweiterung von interpolierten ausführlichen Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="68b76-121">Enhancement of interpolated verbatim strings</span></span>](#enhancement-of-interpolated-verbatim-strings)

<span data-ttu-id="68b76-122">C# 8.0 wird unter **.NET Core 3.x** und **.NET Standard 2.1** unterstützt.</span><span class="sxs-lookup"><span data-stu-id="68b76-122">C# 8.0 is supported on **.NET Core 3.x** and **.NET Standard 2.1**.</span></span> <span data-ttu-id="68b76-123">Weitere Informationen finden Sie unter [C#-Sprachversionsverwaltung](../language-reference/configure-language-version.md).</span><span class="sxs-lookup"><span data-stu-id="68b76-123">For more information, see [C# language versioning](../language-reference/configure-language-version.md).</span></span>

<span data-ttu-id="68b76-124">Der Rest dieses Artikels beschreibt diese Funktionen kurz.</span><span class="sxs-lookup"><span data-stu-id="68b76-124">The remainder of this article briefly describes these features.</span></span> <span data-ttu-id="68b76-125">Wenn ausführliche Artikel verfügbar sind, werden Links zu diesen Tutorials und Übersichten bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="68b76-125">Where in-depth articles are available, links to those tutorials and overviews are provided.</span></span> <span data-ttu-id="68b76-126">Sie können sich diese Funktionen in unserer Umgebung mit dem globalen `dotnet try`-Tool näher ansehen:</span><span class="sxs-lookup"><span data-stu-id="68b76-126">You can explore these features in your environment using the `dotnet try` global tool:</span></span>

1. <span data-ttu-id="68b76-127">Installieren Sie das globale [dotnet-try](https://github.com/dotnet/try/blob/master/README.md#setup)-Tool.</span><span class="sxs-lookup"><span data-stu-id="68b76-127">Install the [dotnet-try](https://github.com/dotnet/try/blob/master/README.md#setup) global tool.</span></span>
1. <span data-ttu-id="68b76-128">Klonen Sie das [dotnet/try-samples](https://github.com/dotnet/try-samples)-Repository.</span><span class="sxs-lookup"><span data-stu-id="68b76-128">Clone the [dotnet/try-samples](https://github.com/dotnet/try-samples) repository.</span></span>
1. <span data-ttu-id="68b76-129">Legen Sie das aktuelle Verzeichnis auf das Unterverzeichnis *csharp8* für das *try-samples*-Repository fest.</span><span class="sxs-lookup"><span data-stu-id="68b76-129">Set the current directory to the *csharp8* subdirectory for the *try-samples* repository.</span></span>
1. <span data-ttu-id="68b76-130">Führen Sie aus `dotnet try`.</span><span class="sxs-lookup"><span data-stu-id="68b76-130">Run `dotnet try`.</span></span>

## <a name="readonly-members"></a><span data-ttu-id="68b76-131">Readonly-Member</span><span class="sxs-lookup"><span data-stu-id="68b76-131">Readonly members</span></span>

<span data-ttu-id="68b76-132">Sie können den `readonly`-Modifizierer auf jeden Member einer Struktur anwenden.</span><span class="sxs-lookup"><span data-stu-id="68b76-132">You can apply the `readonly` modifier to members of a struct.</span></span> <span data-ttu-id="68b76-133">Damit wird angezeigt, dass der Member den Zustand nicht ändert.</span><span class="sxs-lookup"><span data-stu-id="68b76-133">It indicates that the member doesn't modify state.</span></span> <span data-ttu-id="68b76-134">Dies ist granularer als das Anwenden des `readonly`-Modifikators auf eine `struct`-Deklaration.</span><span class="sxs-lookup"><span data-stu-id="68b76-134">It's more granular than applying the `readonly` modifier to a `struct` declaration.</span></span>  <span data-ttu-id="68b76-135">Betrachten Sie folgende veränderliche Struktur:</span><span class="sxs-lookup"><span data-stu-id="68b76-135">Consider the following mutable struct:</span></span>

```csharp
public struct Point
{
    public double X { get; set; }
    public double Y { get; set; }
    public double Distance => Math.Sqrt(X * X + Y * Y);

    public override string ToString() =>
        $"({X}, {Y}) is {Distance} from the origin";
}
```

<span data-ttu-id="68b76-136">Wie bei den meisten Strukturen verändert die `ToString()`-Methode den Zustand nicht.</span><span class="sxs-lookup"><span data-stu-id="68b76-136">Like most structs, the `ToString()` method doesn't modify state.</span></span> <span data-ttu-id="68b76-137">Sie könnten dies durch Hinzufügen des `readonly`-Modifikators zur Deklaration von `ToString()` angeben:</span><span class="sxs-lookup"><span data-stu-id="68b76-137">You could indicate that by adding the `readonly` modifier to the declaration of `ToString()`:</span></span>

```csharp
public readonly override string ToString() =>
    $"({X}, {Y}) is {Distance} from the origin";
```

<span data-ttu-id="68b76-138">Die vorhergehende Änderung generiert eine Compilerwarnung, weil `ToString` auf die `Distance`-Eigenschaft zugreift, die nicht als `readonly` markiert ist:</span><span class="sxs-lookup"><span data-stu-id="68b76-138">The preceding change generates a compiler warning, because `ToString` accesses the `Distance` property, which isn't marked `readonly`:</span></span>

```console
warning CS8656: Call to non-readonly member 'Point.Distance.get' from a 'readonly' member results in an implicit copy of 'this'
```

<span data-ttu-id="68b76-139">Der Compiler warnt Sie, wenn er eine Defensivkopie erstellen muss.</span><span class="sxs-lookup"><span data-stu-id="68b76-139">The compiler warns you when it needs to create a defensive copy.</span></span>  <span data-ttu-id="68b76-140">Die `Distance`-Eigenschaft verändert nicht den Zustand, sodass Sie diese Warnung aufheben können, indem Sie der Deklaration den `readonly`-Modifizierer hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="68b76-140">The `Distance` property doesn't change state, so you can fix this warning by adding the `readonly` modifier to the declaration:</span></span>

```csharp
public readonly double Distance => Math.Sqrt(X * X + Y * Y);
```

<span data-ttu-id="68b76-141">Beachten Sie, dass der `readonly`-Modifizierer bei einer schreibgeschützten Eigenschaft erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="68b76-141">Notice that the `readonly` modifier is necessary on a read-only property.</span></span> <span data-ttu-id="68b76-142">Der Compiler geht nicht davon aus, dass `get`-Zugriffsmethoden den Zustand nicht ändern. Sie müssen `readonly` explizit deklarieren.</span><span class="sxs-lookup"><span data-stu-id="68b76-142">The compiler doesn't assume `get` accessors don't modify state; you must declare `readonly` explicitly.</span></span> <span data-ttu-id="68b76-143">Automatisch implementierte Eigenschaften sind eine Ausnahme; der Compiler sieht alle automatisch implementierten Getter als schreibgeschützt an, sodass es hier nicht notwendig ist, den `readonly`-Modifizierer zu den `X`- und `Y`-Eigenschaften hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="68b76-143">Auto-implemented properties are an exception; the compiler will treat all auto-implemented getters as readonly, so here there's no need to add the `readonly` modifier to the `X` and `Y` properties.</span></span>

<span data-ttu-id="68b76-144">Der Compiler erzwingt die Regel, dass `readonly`-Member den Status nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="68b76-144">The compiler does enforce the rule that `readonly` members don't modify state.</span></span> <span data-ttu-id="68b76-145">Die folgende Methode wird nicht kompiliert, es sei denn, Sie entfernen den `readonly`-Modifizierer:</span><span class="sxs-lookup"><span data-stu-id="68b76-145">The following method won't compile unless you remove the `readonly` modifier:</span></span>

```csharp
public readonly void Translate(int xOffset, int yOffset)
{
    X += xOffset;
    Y += yOffset;
}
```

<span data-ttu-id="68b76-146">Mit diesem Feature können Sie Ihre Designabsicht angeben, damit der Compiler sie erzwingen und Optimierungen basierend auf dieser Absicht vornehmen kann.</span><span class="sxs-lookup"><span data-stu-id="68b76-146">This feature lets you specify your design intent so the compiler can enforce it, and make optimizations based on that intent.</span></span> <span data-ttu-id="68b76-147">Erfahren Sie mehr über schreibgeschützte Member in dem Artikel [`readonly`](../language-reference/keywords/readonly.md#readonly-member-examples).</span><span class="sxs-lookup"><span data-stu-id="68b76-147">You can learn more about readonly members in the language reference article on [`readonly`](../language-reference/keywords/readonly.md#readonly-member-examples).</span></span>

## <a name="default-interface-methods"></a><span data-ttu-id="68b76-148">Standardschnittstellenmethoden</span><span class="sxs-lookup"><span data-stu-id="68b76-148">Default interface methods</span></span>

<span data-ttu-id="68b76-149">Sie können nun Member zu Schnittstellen hinzufügen und eine Implementierung für diese Member bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="68b76-149">You can now add members to interfaces and provide an implementation for those members.</span></span> <span data-ttu-id="68b76-150">Dieses Sprachfeature ermöglicht es API-Autoren, in späteren Versionen Methoden zu einer Schnittstelle hinzuzufügen, ohne die Quell- oder Binärkompatibilität mit bestehenden Implementierungen dieser Schnittstelle zu beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="68b76-150">This language feature enables API authors to add methods to an interface in later versions without breaking source or binary compatibility with existing implementations of that interface.</span></span> <span data-ttu-id="68b76-151">Bestehende Implementierungen *erben* die Standardimplementierung.</span><span class="sxs-lookup"><span data-stu-id="68b76-151">Existing implementations *inherit* the default implementation.</span></span> <span data-ttu-id="68b76-152">Dieses Feature ermöglicht zudem die Interaktion zwischen C# und APIs, die auf Android oder Swift abzielen und ähnliche Funktionen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="68b76-152">This feature also enables C# to interoperate with APIs that target Android or Swift, which support similar features.</span></span> <span data-ttu-id="68b76-153">Standardschnittstellenmethoden ermöglichen auch Szenarien, die einem „Traits“-Sprachfeature ähneln.</span><span class="sxs-lookup"><span data-stu-id="68b76-153">Default interface methods also enable scenarios similar to a "traits" language feature.</span></span>

<span data-ttu-id="68b76-154">Standardschnittstellenmethoden wirken sich auf viele Szenarien und Sprachelemente aus.</span><span class="sxs-lookup"><span data-stu-id="68b76-154">Default interface methods affects many scenarios and language elements.</span></span> <span data-ttu-id="68b76-155">Unser erstes Tutorial behandelt [die Aktualisierung einer Schnittstelle mit Standardimplementierungen](../tutorials/default-interface-methods-versions.md).</span><span class="sxs-lookup"><span data-stu-id="68b76-155">Our first tutorial covers [updating an interface with default implementations](../tutorials/default-interface-methods-versions.md).</span></span> <span data-ttu-id="68b76-156">Weitere Tutorials und Referenzaktualisierungen folgen rechtzeitig zur allgemeinen Veröffentlichung.</span><span class="sxs-lookup"><span data-stu-id="68b76-156">Other tutorials and reference updates are coming in time for general release.</span></span>

## <a name="more-patterns-in-more-places"></a><span data-ttu-id="68b76-157">Weitere Muster an mehr Orten</span><span class="sxs-lookup"><span data-stu-id="68b76-157">More patterns in more places</span></span>

<span data-ttu-id="68b76-158">**Musterabgleich** bietet Tools zur Bereitstellung formabhängiger Funktionalität für verwandte, aber unterschiedliche Datentypen.</span><span class="sxs-lookup"><span data-stu-id="68b76-158">**Pattern matching** gives tools to provide shape-dependent functionality across related but different kinds of data.</span></span> <span data-ttu-id="68b76-159">C# 7.0 führte eine Syntax für Typmuster und konstante Muster ein, indem der Ausdruck [`is`](../language-reference/keywords/is.md) und die Anweisung [`switch`](../language-reference/keywords/switch.md) verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="68b76-159">C# 7.0 introduced syntax for type patterns and constant patterns by using the [`is`](../language-reference/keywords/is.md) expression and the [`switch`](../language-reference/keywords/switch.md) statement.</span></span> <span data-ttu-id="68b76-160">Diese Funktionen stellten die ersten vorläufigen Schritte zur Unterstützung von Programmierparadigmen dar, bei denen Daten und Funktionalität getrennt voneinander sind.</span><span class="sxs-lookup"><span data-stu-id="68b76-160">These features represented the first tentative steps toward supporting programming paradigms where data and functionality live apart.</span></span> <span data-ttu-id="68b76-161">Da sich die Branche immer mehr auf Mikroservices und andere Cloud-basierte Architekturen konzentriert, werden andere Sprachtools benötigt.</span><span class="sxs-lookup"><span data-stu-id="68b76-161">As the industry moves toward more microservices and other cloud-based architectures, other language tools are needed.</span></span>

<span data-ttu-id="68b76-162">C# 8.0 erweitert dieses Vokabular, sodass Sie mehr Musterausdrücke an mehreren Stellen in Ihrem Code verwenden können.</span><span class="sxs-lookup"><span data-stu-id="68b76-162">C# 8.0 expands this vocabulary so you can use more pattern expressions in more places in your code.</span></span> <span data-ttu-id="68b76-163">Berücksichtigen Sie diese Funktionen, wenn Ihre Daten und Funktionen getrennt sind.</span><span class="sxs-lookup"><span data-stu-id="68b76-163">Consider these features when your data and functionality are separate.</span></span> <span data-ttu-id="68b76-164">Berücksichtigen Sie den Musterabgleich, wenn Ihre Algorithmen von einer anderen Tatsache als dem Runtimetyp eines Objekts abhängen.</span><span class="sxs-lookup"><span data-stu-id="68b76-164">Consider pattern matching when your algorithms depend on a fact other than the runtime type of an object.</span></span> <span data-ttu-id="68b76-165">Diese Verfahren bieten eine weitere Möglichkeit, Entwürfe auszudrücken.</span><span class="sxs-lookup"><span data-stu-id="68b76-165">These techniques provide another way to express designs.</span></span>

<span data-ttu-id="68b76-166">Zusätzlich zu neuen Mustern an neuen Orten fügt C# 8.0 **rekursive Muster** hinzu.</span><span class="sxs-lookup"><span data-stu-id="68b76-166">In addition to new patterns in new places, C# 8.0 adds **recursive patterns**.</span></span> <span data-ttu-id="68b76-167">Das Ergebnis eines beliebigen Musterausdrucks ist ein Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="68b76-167">The result of any pattern expression is an expression.</span></span> <span data-ttu-id="68b76-168">Ein rekursives Muster ist einfach ein Musterausdruck, der auf die Ausgabe eines anderen Musterausdrucks angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="68b76-168">A recursive pattern is simply a pattern expression applied to the output of another pattern expression.</span></span>

### <a name="switch-expressions"></a><span data-ttu-id="68b76-169">Switch-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="68b76-169">Switch expressions</span></span>

<span data-ttu-id="68b76-170">Häufig liefert eine [`switch`](../language-reference/keywords/switch.md)-Anweisung in jedem ihrer `case`-Blöcke einen Wert.</span><span class="sxs-lookup"><span data-stu-id="68b76-170">Often, a [`switch`](../language-reference/keywords/switch.md) statement produces a value in each of its `case` blocks.</span></span> <span data-ttu-id="68b76-171">Mit **switch-Ausdrücken** können Sie eine präzisere Ausdruckssyntax verwenden.</span><span class="sxs-lookup"><span data-stu-id="68b76-171">**Switch expressions** enable you to use more concise expression syntax.</span></span> <span data-ttu-id="68b76-172">Es gibt weniger repetitive `case`- und `break`-Schlüsselwörter und weniger geschweifte Klammern.</span><span class="sxs-lookup"><span data-stu-id="68b76-172">There are fewer repetitive `case` and `break` keywords, and fewer curly braces.</span></span>  <span data-ttu-id="68b76-173">Betrachten Sie als Beispiel die folgende Enumeration, die die Farben des Regenbogens enumeriert:</span><span class="sxs-lookup"><span data-stu-id="68b76-173">As an example, consider the following enum that lists the colors of the rainbow:</span></span>

```csharp
public enum Rainbow
{
    Red,
    Orange,
    Yellow,
    Green,
    Blue,
    Indigo,
    Violet
}
```

<span data-ttu-id="68b76-174">Wenn Ihre Anwendung einen `RGBColor`-Typ definiert hat, der aus den Komponenten `R`, `G` und `B` aufgebaut ist, können Sie einen `Rainbow`-Wert in seine RGB-Werte konvertieren, indem Sie die folgende Methode verwenden, die einen Switch-Ausdruck enthält:</span><span class="sxs-lookup"><span data-stu-id="68b76-174">If your application defined an `RGBColor` type that is constructed from the `R`, `G` and `B` components, you could convert a `Rainbow` value to its RGB values using the following method containing a switch expression:</span></span>

```csharp
public static RGBColor FromRainbow(Rainbow colorBand) =>
    colorBand switch
    {
        Rainbow.Red    => new RGBColor(0xFF, 0x00, 0x00),
        Rainbow.Orange => new RGBColor(0xFF, 0x7F, 0x00),
        Rainbow.Yellow => new RGBColor(0xFF, 0xFF, 0x00),
        Rainbow.Green  => new RGBColor(0x00, 0xFF, 0x00),
        Rainbow.Blue   => new RGBColor(0x00, 0x00, 0xFF),
        Rainbow.Indigo => new RGBColor(0x4B, 0x00, 0x82),
        Rainbow.Violet => new RGBColor(0x94, 0x00, 0xD3),
        _              => throw new ArgumentException(message: "invalid enum value", paramName: nameof(colorBand)),
    };
```

<span data-ttu-id="68b76-175">Es gibt hier verschiedene Syntaxverbesserungen:</span><span class="sxs-lookup"><span data-stu-id="68b76-175">There are several syntax improvements here:</span></span>

- <span data-ttu-id="68b76-176">Die Variable steht vor dem `switch`-Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="68b76-176">The variable comes before the `switch` keyword.</span></span> <span data-ttu-id="68b76-177">Die unterschiedliche Reihenfolge macht es optisch einfach, den switch-Ausdruck von der switch-Anweisung zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="68b76-177">The different order makes it visually easy to distinguish the switch expression from the switch statement.</span></span>
- <span data-ttu-id="68b76-178">Die `case`- und `:`-Elemente werden durch `=>` ersetzt.</span><span class="sxs-lookup"><span data-stu-id="68b76-178">The `case` and `:` elements are replaced with `=>`.</span></span> <span data-ttu-id="68b76-179">Es ist präziser und intuitiver.</span><span class="sxs-lookup"><span data-stu-id="68b76-179">It's more concise and intuitive.</span></span>
- <span data-ttu-id="68b76-180">Der `default`-Fall wird durch eine `_`-Ausschlussvariable ersetzt.</span><span class="sxs-lookup"><span data-stu-id="68b76-180">The `default` case is replaced with a `_` discard.</span></span>
- <span data-ttu-id="68b76-181">Die Textkörper sind Ausdrücke, keine Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="68b76-181">The bodies are expressions, not statements.</span></span>

<span data-ttu-id="68b76-182">Stellen Sie dies mit dem entsprechenden Code unter Verwendung der klassischen `switch`-Anweisung gegenüber:</span><span class="sxs-lookup"><span data-stu-id="68b76-182">Contrast that with the equivalent code using the classic `switch` statement:</span></span>

```csharp
public static RGBColor FromRainbowClassic(Rainbow colorBand)
{
    switch (colorBand)
    {
        case Rainbow.Red:
            return new RGBColor(0xFF, 0x00, 0x00);
        case Rainbow.Orange:
            return new RGBColor(0xFF, 0x7F, 0x00);
        case Rainbow.Yellow:
            return new RGBColor(0xFF, 0xFF, 0x00);
        case Rainbow.Green:
            return new RGBColor(0x00, 0xFF, 0x00);
        case Rainbow.Blue:
            return new RGBColor(0x00, 0x00, 0xFF);
        case Rainbow.Indigo:
            return new RGBColor(0x4B, 0x00, 0x82);
        case Rainbow.Violet:
            return new RGBColor(0x94, 0x00, 0xD3);
        default:
            throw new ArgumentException(message: "invalid enum value", paramName: nameof(colorBand));
    };
}
```

### <a name="property-patterns"></a><span data-ttu-id="68b76-183">Eigenschaftsmuster</span><span class="sxs-lookup"><span data-stu-id="68b76-183">Property patterns</span></span>

<span data-ttu-id="68b76-184">Mit dem **Eigenschaftsmuster** können Sie die Eigenschaften des untersuchten Objekts anpassen.</span><span class="sxs-lookup"><span data-stu-id="68b76-184">The **property pattern** enables you to match on properties of the object examined.</span></span> <span data-ttu-id="68b76-185">Denken Sie an eine eCommerce-Website, die die Umsatzsteuer auf der Grundlage der Adresse des Käufers berechnen muss.</span><span class="sxs-lookup"><span data-stu-id="68b76-185">Consider an eCommerce site that must compute sales tax based on the buyer's address.</span></span> <span data-ttu-id="68b76-186">Diese Berechnung ist keine Kernaufgabe einer `Address`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="68b76-186">That computation isn't a core responsibility of an `Address` class.</span></span> <span data-ttu-id="68b76-187">Sie wird sich im Laufe der Zeit ändern, wahrscheinlich häufiger als Adressformatänderungen.</span><span class="sxs-lookup"><span data-stu-id="68b76-187">It will change over time, likely more often than address format changes.</span></span> <span data-ttu-id="68b76-188">Die Höhe der Umsatzsteuer hängt von der `State`-Eigenschaft der Adresse ab.</span><span class="sxs-lookup"><span data-stu-id="68b76-188">The amount of sales tax depends on the `State` property of the address.</span></span> <span data-ttu-id="68b76-189">Die folgende Methode verwendet das Eigenschaftsmuster, um die Umsatzsteuer aus der Adresse und dem Preis zu berechnen:</span><span class="sxs-lookup"><span data-stu-id="68b76-189">The following method uses the property pattern to compute the sales tax from the address and the price:</span></span>

```csharp
public static decimal ComputeSalesTax(Address location, decimal salePrice) =>
    location switch
    {
        { State: "WA" } => salePrice * 0.06M,
        { State: "MN" } => salePrice * 0.75M,
        { State: "MI" } => salePrice * 0.05M,
        // other cases removed for brevity...
        _ => 0M
    };
```

<span data-ttu-id="68b76-190">Ein Musterabgleich erstellt eine präzise Syntax,. um diesen Algorithmus auszudrücken.</span><span class="sxs-lookup"><span data-stu-id="68b76-190">Pattern matching creates a concise syntax for expressing this algorithm.</span></span>

### <a name="tuple-patterns"></a><span data-ttu-id="68b76-191">Tupelmuster</span><span class="sxs-lookup"><span data-stu-id="68b76-191">Tuple patterns</span></span>

<span data-ttu-id="68b76-192">Einige Algorithmen sind von mehreren Eingaben abhängig.</span><span class="sxs-lookup"><span data-stu-id="68b76-192">Some algorithms depend on multiple inputs.</span></span> <span data-ttu-id="68b76-193">**Tupelmuster** erlauben Ihnen, auf Grundlage mehrerer Werte, ausgedrückt als ein [Tupel](../tuples.md), zu wechseln („switch“).</span><span class="sxs-lookup"><span data-stu-id="68b76-193">**Tuple patterns** allow you to switch based on multiple values expressed as a [tuple](../tuples.md).</span></span>  <span data-ttu-id="68b76-194">Der folgende Code zeigt einen switch-Ausdruck für das Spiel *Stein, Schere, Papier* (Schnick, Schnack, Schnuck):</span><span class="sxs-lookup"><span data-stu-id="68b76-194">The following code shows a switch expression for the game *rock, paper, scissors*:</span></span>

```csharp
public static string RockPaperScissors(string first, string second)
    => (first, second) switch
    {
        ("rock", "paper") => "rock is covered by paper. Paper wins.",
        ("rock", "scissors") => "rock breaks scissors. Rock wins.",
        ("paper", "rock") => "paper covers rock. Paper wins.",
        ("paper", "scissors") => "paper is cut by scissors. Scissors wins.",
        ("scissors", "rock") => "scissors is broken by rock. Rock wins.",
        ("scissors", "paper") => "scissors cuts paper. Scissors wins.",
        (_, _) => "tie"
    };
```

<span data-ttu-id="68b76-195">Die Meldungen zeigen den Gewinner an.</span><span class="sxs-lookup"><span data-stu-id="68b76-195">The messages indicate the winner.</span></span> <span data-ttu-id="68b76-196">Der Fall „Verwerfen“ („case discard“) stellt die drei Kombinationen für Unentschieden oder andere Texteingaben dar.</span><span class="sxs-lookup"><span data-stu-id="68b76-196">The discard case represents the three combinations for ties, or other text inputs.</span></span>

### <a name="positional-patterns"></a><span data-ttu-id="68b76-197">Positionsmuster</span><span class="sxs-lookup"><span data-stu-id="68b76-197">Positional patterns</span></span>

<span data-ttu-id="68b76-198">Einige Typen umfassen eine `Deconstruct`-Methode, die ihre Eigenschaften in diskrete Variablen dekonstruiert.</span><span class="sxs-lookup"><span data-stu-id="68b76-198">Some types include a `Deconstruct` method that deconstructs its properties into discrete variables.</span></span> <span data-ttu-id="68b76-199">Wenn auf eine `Deconstruct`-Methode zugegriffen werden kann, können Sie **Positionsmuster** verwenden, um Eigenschaften des Objekts zu untersuchen, und diese Eigenschaften für ein Muster verwenden.</span><span class="sxs-lookup"><span data-stu-id="68b76-199">When a `Deconstruct` method is accessible, you can use **positional patterns** to inspect properties of the object and use those properties for a pattern.</span></span>  <span data-ttu-id="68b76-200">Beachten Sie die folgende `Point`-Klasse, die eine `Deconstruct`-Methode umfasst, um diskrete Variablen für `X` und `Y` zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="68b76-200">Consider the following `Point` class that includes a `Deconstruct` method to create discrete variables for `X` and `Y`:</span></span>

```csharp
public class Point
{
    public int X { get; }
    public int Y { get; }

    public Point(int x, int y) => (X, Y) = (x, y);

    public void Deconstruct(out int x, out int y) =>
        (x, y) = (X, Y);
}
```

<span data-ttu-id="68b76-201">Beachten Sie zudem die folgende Enumeration, die verschiedene Positionen eines Quadranten darstellt:</span><span class="sxs-lookup"><span data-stu-id="68b76-201">Additionally, consider the following enum that represents various positions of a quadrant:</span></span>

```csharp
public enum Quadrant
{
    Unknown,
    Origin,
    One,
    Two,
    Three,
    Four,
    OnBorder
}
```

<span data-ttu-id="68b76-202">Die folgende Methode verwendet das **Positionsmuster**, um die Werte von `x` und `y` zu extrahieren.</span><span class="sxs-lookup"><span data-stu-id="68b76-202">The following method uses the **positional pattern** to extract the values of `x` and `y`.</span></span> <span data-ttu-id="68b76-203">Dann wird mit einer `when`-Klausel der `Quadrant` des Punktes bestimmt:</span><span class="sxs-lookup"><span data-stu-id="68b76-203">Then, it uses a `when` clause to determine the `Quadrant` of the point:</span></span>

```csharp
static Quadrant GetQuadrant(Point point) => point switch
{
    (0, 0) => Quadrant.Origin,
    var (x, y) when x > 0 && y > 0 => Quadrant.One,
    var (x, y) when x < 0 && y > 0 => Quadrant.Two,
    var (x, y) when x < 0 && y < 0 => Quadrant.Three,
    var (x, y) when x > 0 && y < 0 => Quadrant.Four,
    var (_, _) => Quadrant.OnBorder,
    _ => Quadrant.Unknown
};
```

<span data-ttu-id="68b76-204">Das Ausschussmuster im vorherigen Switch stimmt überein, wenn entweder `x` oder `y` 0 ist, jedoch nicht beide.</span><span class="sxs-lookup"><span data-stu-id="68b76-204">The discard pattern in the preceding switch matches when either `x` or `y` is 0, but not both.</span></span> <span data-ttu-id="68b76-205">Ein switch-Ausdruck muss entweder einen Wert erzeugen oder eine Ausnahme auslösen.</span><span class="sxs-lookup"><span data-stu-id="68b76-205">A switch expression must either produce a value or throw an exception.</span></span> <span data-ttu-id="68b76-206">Wenn keiner der Fälle übereinstimmt, löst der switch-Ausdruck eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="68b76-206">If none of the cases match, the switch expression throws an exception.</span></span> <span data-ttu-id="68b76-207">Der Compiler erzeugt für Sie eine Warnung, wenn Sie nicht alle möglichen Fälle in Ihrem Switch-Ausdruck abdecken.</span><span class="sxs-lookup"><span data-stu-id="68b76-207">The compiler generates a warning for you if you don't cover all possible cases in your switch expression.</span></span>

<span data-ttu-id="68b76-208">In diesem [erweiterten Tutorial zum Musterabgleich](../tutorials/pattern-matching.md) erhalten Sie weitere Informationen zu Musterabgleichverfahren.</span><span class="sxs-lookup"><span data-stu-id="68b76-208">You can explore pattern matching techniques in this [advanced tutorial on pattern matching](../tutorials/pattern-matching.md).</span></span>

## <a name="using-declarations"></a><span data-ttu-id="68b76-209">Using-Deklarationen</span><span class="sxs-lookup"><span data-stu-id="68b76-209">Using declarations</span></span>

<span data-ttu-id="68b76-210">Eine **using-Deklaration** ist eine Variablendeklaration, der das Schlüsselwort `using` vorangestellt ist.</span><span class="sxs-lookup"><span data-stu-id="68b76-210">A **using declaration** is a variable declaration preceded by the `using` keyword.</span></span> <span data-ttu-id="68b76-211">Es teilt dem Compiler mit, dass die zu deklarierende Variable am Ende des umschließenden Bereichs angeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="68b76-211">It tells the compiler that the variable being declared should be disposed at the end of the enclosing scope.</span></span> <span data-ttu-id="68b76-212">Sehen Sie sich beispielsweise den folgenden Code an, der eine Textdatei schreibt:</span><span class="sxs-lookup"><span data-stu-id="68b76-212">For example, consider the following code that writes a text file:</span></span>

```csharp
static int WriteLinesToFile(IEnumerable<string> lines)
{
    using var file = new System.IO.StreamWriter("WriteLines2.txt");
    // Notice how we declare skippedLines after the using statement.
    int skippedLines = 0;
    foreach (string line in lines)
    {
        if (!line.Contains("Second"))
        {
            file.WriteLine(line);
        }
        else
        {
            skippedLines++;
        }
    }
    // Notice how skippedLines is in scope here.
    return skippedLines;
    // file is disposed here
}
```

<span data-ttu-id="68b76-213">Im vorhergehenden Beispiel wird die Datei angeordnet, wenn die schließende Klammer für die Methode erreicht ist.</span><span class="sxs-lookup"><span data-stu-id="68b76-213">In the preceding example, the file is disposed when the closing brace for the method is reached.</span></span> <span data-ttu-id="68b76-214">Dies ist das Ende des Bereichs, in dem `file` deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="68b76-214">That's the end of the scope in which `file` is declared.</span></span> <span data-ttu-id="68b76-215">Der obige Code entspricht dem folgenden Code mit klassischer [using-Anweisung](../language-reference/keywords/using-statement.md):</span><span class="sxs-lookup"><span data-stu-id="68b76-215">The preceding code is equivalent to the following code that uses the classic [using statement](../language-reference/keywords/using-statement.md):</span></span>

```csharp
static int WriteLinesToFile(IEnumerable<string> lines)
{
    // We must declare the variable outside of the using block
    // so that it is in scope to be returned.
    int skippedLines = 0;
    using (var file = new System.IO.StreamWriter("WriteLines2.txt"))
    {
        foreach (string line in lines)
        {
            if (!line.Contains("Second"))
            {
                file.WriteLine(line);
            }
            else
            {
                skippedLines++;
            }
        }
    } // file is disposed here
    return skippedLines;
}
```

<span data-ttu-id="68b76-216">Im vorhergehenden Beispiel wird die Datei angeordnet, wenn die der `using`-Anweisung zugeordnete schließende Klammer erreicht ist.</span><span class="sxs-lookup"><span data-stu-id="68b76-216">In the preceding example, the file is disposed when the closing brace associated with the `using` statement is reached.</span></span>

<span data-ttu-id="68b76-217">In beiden Fällen generiert der Compiler den Aufruf von `Dispose()`.</span><span class="sxs-lookup"><span data-stu-id="68b76-217">In both cases, the compiler generates the call to `Dispose()`.</span></span> <span data-ttu-id="68b76-218">Der Compiler erzeugt einen Fehler, wenn der Ausdruck in der `using`-Anweisung nicht verwerfbar ist.</span><span class="sxs-lookup"><span data-stu-id="68b76-218">The compiler generates an error if the expression in the `using` statement isn't disposable.</span></span>

## <a name="static-local-functions"></a><span data-ttu-id="68b76-219">Statische lokale Funktionen</span><span class="sxs-lookup"><span data-stu-id="68b76-219">Static local functions</span></span>

<span data-ttu-id="68b76-220">Sie können nun den `static`-Modifikator zu lokalen Funktionen hinzufügen, um sicherzustellen, dass die lokale Funktion keine Variablen aus dem umschließenden Bereich erfasst (referenziert).</span><span class="sxs-lookup"><span data-stu-id="68b76-220">You can now add the `static` modifier to local functions to ensure that local function doesn't capture (reference) any variables from the enclosing scope.</span></span> <span data-ttu-id="68b76-221">Dadurch wird `CS8421` erzeugt: „Eine statische lokale Funktion kann keine Referenz auf \<variable> enthalten.“</span><span class="sxs-lookup"><span data-stu-id="68b76-221">Doing so generates `CS8421`, "A static local function can't contain a reference to \<variable>."</span></span>

<span data-ttu-id="68b76-222">Betrachten Sie folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="68b76-222">Consider the following code.</span></span> <span data-ttu-id="68b76-223">Die lokale Funktion `LocalFunction` greift auf die Variable `y` zu, die im umschließenden Bereich (die Methode `M`) deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="68b76-223">The local function `LocalFunction` accesses the variable `y`, declared in the enclosing scope (the method `M`).</span></span> <span data-ttu-id="68b76-224">Daher kann `LocalFunction` nicht mit dem `static`-Modifikator deklariert werden:</span><span class="sxs-lookup"><span data-stu-id="68b76-224">Therefore, `LocalFunction` can't be declared with the `static` modifier:</span></span>

```csharp
int M()
{
    int y;
    LocalFunction();
    return y;

    void LocalFunction() => y = 0;
}
```

<span data-ttu-id="68b76-225">Der folgende Code enthält eine statische lokale Funktion.</span><span class="sxs-lookup"><span data-stu-id="68b76-225">The following code contains a static local function.</span></span> <span data-ttu-id="68b76-226">Er kann statisch sein, da er nicht auf Variablen im umschließenden Bereich zugreift:</span><span class="sxs-lookup"><span data-stu-id="68b76-226">It can be static because it doesn't access any variables in the enclosing scope:</span></span>

```csharp
int M()
{
    int y = 5;
    int x = 7;
    return Add(x, y);

    static int Add(int left, int right) => left + right;
}
```

## <a name="disposable-ref-structs"></a><span data-ttu-id="68b76-227">Verwerfbare Referenzstrukturen</span><span class="sxs-lookup"><span data-stu-id="68b76-227">Disposable ref structs</span></span>

<span data-ttu-id="68b76-228">Ein mit dem `ref`-Modifizierer deklarierter `struct` darf keine Schnittstellen und damit auch keine <xref:System.IDisposable> implementieren.</span><span class="sxs-lookup"><span data-stu-id="68b76-228">A `struct` declared with the `ref` modifier may not implement any interfaces and so can't implement <xref:System.IDisposable>.</span></span> <span data-ttu-id="68b76-229">Aus diesem Grund Aktivieren einer `ref struct` um verworfen werden, muss eine zugängliche `void Dispose()` Methode.</span><span class="sxs-lookup"><span data-stu-id="68b76-229">Therefore, to enable a `ref struct` to be disposed, it must have an accessible `void Dispose()` method.</span></span> <span data-ttu-id="68b76-230">Dieses Feature gilt auch für `readonly ref struct`-Deklarationen.</span><span class="sxs-lookup"><span data-stu-id="68b76-230">This feature also applies to `readonly ref struct` declarations.</span></span>

## <a name="nullable-reference-types"></a><span data-ttu-id="68b76-231">Nullwerte zulassende Verweistypen</span><span class="sxs-lookup"><span data-stu-id="68b76-231">Nullable reference types</span></span>

<span data-ttu-id="68b76-232">In einem Nullwerte zulassenden Anmerkungskontext, wird jede Variable eines Referenztyps als **keine Nullwerte zulassender Referenztyp** betrachtet.</span><span class="sxs-lookup"><span data-stu-id="68b76-232">Inside a nullable annotation context, any variable of a reference type is considered to be a **nonnullable reference type**.</span></span> <span data-ttu-id="68b76-233">Wenn Sie angeben möchten, dass eine Variable Null sein kann, müssen Sie den Typnamen mit `?` ergänzen, um die Variable als **keine Nullwerte zulassenden Verweistyp** zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="68b76-233">If you want to indicate that a variable may be null, you must append the type name with the `?` to declare the variable as a **nullable reference type**.</span></span>

<span data-ttu-id="68b76-234">Wenn der Verweistyp keine Nullwerte zulässt, verwendet der Compiler die Flussanalyse, um sicherzustellen, dass lokale Variablen bei der Deklaration auf einen Nicht-Null-Wert initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="68b76-234">For nonnullable reference types, the compiler uses flow analysis to ensure that local variables are initialized to a non-null value when declared.</span></span> <span data-ttu-id="68b76-235">Felder müssen während der Erstellung initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="68b76-235">Fields must be initialized during construction.</span></span> <span data-ttu-id="68b76-236">Der Compiler erzeugt eine Warnung, wenn die Variable nicht durch einen Aufruf eines der verfügbaren Konstruktoren oder durch einen Initialisierer festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="68b76-236">The compiler generates a warning if the variable isn't set by a call to any of the available constructors or by an initializer.</span></span> <span data-ttu-id="68b76-237">Darüber hinaus kann Verweistypen, die keine Nullwerte zulassen, kein Wert zugewiesen werden, der Null sein könnte.</span><span class="sxs-lookup"><span data-stu-id="68b76-237">Furthermore, nonnullable reference types can't be assigned a value that could be null.</span></span>

<span data-ttu-id="68b76-238">Verweistypen, die keine Nullwerte zulassen werden nicht überprüft, um sicherzustellen, dass sie nicht mit Null belegt oder initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="68b76-238">Nullable reference types aren't checked to ensure they aren't assigned or initialized to null.</span></span> <span data-ttu-id="68b76-239">Der Compiler verwendet jedoch die Flussanalyse, um sicherzustellen, dass jede Variable eines Verweistypen, der Nullwerte zulässt, gegen null geprüft wird, bevor auf sie zugegriffen oder einem nicht Verweistypen zugewiesen wird, der Nullwerte zulässt.</span><span class="sxs-lookup"><span data-stu-id="68b76-239">However, the compiler uses flow analysis to ensure that any variable of a nullable reference type is checked against null before it's accessed or assigned to a nonnullable reference type.</span></span>

<span data-ttu-id="68b76-240">Mehr über die Funktion erfahren Sie in der Übersicht der [Verweistypen, die Nullwerte zulassen](../nullable-references.md).</span><span class="sxs-lookup"><span data-stu-id="68b76-240">You can learn more about the feature in the overview of [nullable reference types](../nullable-references.md).</span></span> <span data-ttu-id="68b76-241">Probieren Sie es selbst in einer neuen Anwendung in diesem [Tutorial für Verweistypen, die Nullwerte zulassen](../tutorials/nullable-reference-types.md) aus.</span><span class="sxs-lookup"><span data-stu-id="68b76-241">Try it yourself in a new application in this [nullable reference types tutorial](../tutorials/nullable-reference-types.md).</span></span> <span data-ttu-id="68b76-242">Weitere Informationen über die Schritte zur Migration einer bestehenden Codebasis, um Verweistypen zu nutzen, die Nullwerte zulassen, finden Sie im Tutorial [Migration einer Anwendung zur Verwendung Nullwerte zulassenden Verweistypen](../tutorials/upgrade-to-nullable-references.md).</span><span class="sxs-lookup"><span data-stu-id="68b76-242">Learn about the steps to migrate an existing codebase to make use of nullable reference types in the [migrating an application to use nullable reference types tutorial](../tutorials/upgrade-to-nullable-references.md).</span></span>

## <a name="asynchronous-streams"></a><span data-ttu-id="68b76-243">Asynchrone Streams</span><span class="sxs-lookup"><span data-stu-id="68b76-243">Asynchronous streams</span></span>

<span data-ttu-id="68b76-244">Ab C# 8.0 können Sie Streams asynchron erstellen und nutzen.</span><span class="sxs-lookup"><span data-stu-id="68b76-244">Starting with C# 8.0, you can create and consume streams asynchronously.</span></span> <span data-ttu-id="68b76-245">Eine Methode, die einen asynchronen Stream zurückgibt, hat drei Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="68b76-245">A method that returns an asynchronous stream has three properties:</span></span>

1. <span data-ttu-id="68b76-246">Die Deklaration erfolgte mit dem `async`-Modifikator.</span><span class="sxs-lookup"><span data-stu-id="68b76-246">It's declared with the `async` modifier.</span></span>
1. <span data-ttu-id="68b76-247">Es wird <xref:System.Collections.Generic.IAsyncEnumerable%601> zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="68b76-247">It returns an <xref:System.Collections.Generic.IAsyncEnumerable%601>.</span></span>
1. <span data-ttu-id="68b76-248">Das Verfahren enthält `yield return`-Anweisungen, um aufeinanderfolgende Elemente im asynchronen Stream zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="68b76-248">The method contains `yield return` statements to return successive elements in the asynchronous stream.</span></span>

<span data-ttu-id="68b76-249">Die Verwendung eines asynchronen Streams erfordert, dass Sie das Schlüsselwort `await` vor dem Schlüsselwort `foreach` hinzufügen, wenn Sie die Elemente des Streams auflisten.</span><span class="sxs-lookup"><span data-stu-id="68b76-249">Consuming an asynchronous stream requires you to add the `await` keyword before the `foreach` keyword when you enumerate the elements of the stream.</span></span> <span data-ttu-id="68b76-250">Das Hinzufügen des Schlüsselwortes `await` erfordert, dass die Methode, die den asynchronen Strom enumiert, mit dem Modifikator `async` deklariert wird und einen für eine `async`-Methode zulässigen Typ zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="68b76-250">Adding the `await` keyword requires the method that enumerates the asynchronous stream to be declared with the `async` modifier and to return a type allowed for an `async` method.</span></span> <span data-ttu-id="68b76-251">In der Regel ist dies die Rückgabe von <xref:System.Threading.Tasks.Task> oder <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="68b76-251">Typically that means returning a <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="68b76-252">Es kann auch <xref:System.Threading.Tasks.ValueTask> oder <xref:System.Threading.Tasks.ValueTask%601> sein.</span><span class="sxs-lookup"><span data-stu-id="68b76-252">It can also be a <xref:System.Threading.Tasks.ValueTask> or <xref:System.Threading.Tasks.ValueTask%601>.</span></span> <span data-ttu-id="68b76-253">Eine Methode kann einen asynchronen Stream sowohl verwenden als auch erzeugen, was bedeutet, dass sie <xref:System.Collections.Generic.IAsyncEnumerable%601> zurückgeben würde.</span><span class="sxs-lookup"><span data-stu-id="68b76-253">A method can both consume and produce an asynchronous stream, which means it would return an <xref:System.Collections.Generic.IAsyncEnumerable%601>.</span></span> <span data-ttu-id="68b76-254">Der folgende Code erzeugt eine Sequenz von 0 bis 19 und wartet 100 ms zwischen der Generierung jeder Zahl:</span><span class="sxs-lookup"><span data-stu-id="68b76-254">The following code generates a sequence from 0 to 19, waiting 100 ms between generating each number:</span></span>

```csharp
public static async System.Collections.Generic.IAsyncEnumerable<int> GenerateSequence()
{
    for (int i = 0; i < 20; i++)
    {
        await Task.Delay(100);
        yield return i;
    }
}
```

<span data-ttu-id="68b76-255">Die Enumeration der Sequenz erfolgt mit der `await foreach`-Anweisung:</span><span class="sxs-lookup"><span data-stu-id="68b76-255">You would enumerate the sequence using the `await foreach` statement:</span></span>

```csharp
await foreach (var number in GenerateSequence())
{
    Console.WriteLine(number);
}
```

<span data-ttu-id="68b76-256">Sie können asynchrone Streams selbst in unserem Tutorial zum [Erstellen und Verwenden von asynchronen Streams](../tutorials/generate-consume-asynchronous-stream.md) ausprobieren.</span><span class="sxs-lookup"><span data-stu-id="68b76-256">You can try asynchronous streams yourself in our tutorial on [creating and consuming async streams](../tutorials/generate-consume-asynchronous-stream.md).</span></span> <span data-ttu-id="68b76-257">Standardmäßig werden Streamelemente im erfassten Kontext verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="68b76-257">By default, stream elements are processed in the captured context.</span></span> <span data-ttu-id="68b76-258">Wenn Sie die Erfassung des Kontexts deaktivieren möchten, verwenden Sie die Erweiterungsmethode <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="68b76-258">If you want to disable capturing of the context, use the <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait%2A?displayProperty=nameWithType> extension method.</span></span> <span data-ttu-id="68b76-259">Weitere Informationen über Synchronisierungskontexte und die Erfassung des aktuellen Kontexts finden Sie im Artikel über das [Verwenden des aufgabenbasierten asynchronen Musters](../../standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="68b76-259">For more information about synchronization contexts and capturing the current context, see the article on [consuming the Task-based asynchronous pattern](../../standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md).</span></span>

## <a name="indices-and-ranges"></a><span data-ttu-id="68b76-260">Indizes und Bereiche</span><span class="sxs-lookup"><span data-stu-id="68b76-260">Indices and ranges</span></span>

<span data-ttu-id="68b76-261">Indizes und Bereiche bieten eine prägnante Syntax für den Zugriff auf einzelne Elemente oder Bereiche in einer Sequenz.</span><span class="sxs-lookup"><span data-stu-id="68b76-261">Indices and ranges provide a succinct syntax for accessing single elements or ranges in a sequence.</span></span>

<span data-ttu-id="68b76-262">Diese Sprachunterstützung basiert auf zwei neuen Typen und zwei neuen Operatoren:</span><span class="sxs-lookup"><span data-stu-id="68b76-262">This language support relies on two new types, and two new operators:</span></span>

- <span data-ttu-id="68b76-263"><xref:System.Index?displayProperty=nameWithType>: Stellt einen Index in einer Sequenz dar.</span><span class="sxs-lookup"><span data-stu-id="68b76-263"><xref:System.Index?displayProperty=nameWithType> represents an index into a sequence.</span></span>
- <span data-ttu-id="68b76-264">Der Index vom Endeoperator `^`, der angibt, dass ein Index relativ zum Ende der Sequenz ist.</span><span class="sxs-lookup"><span data-stu-id="68b76-264">The index from end operator `^`, which specifies that an index is relative to the end of the sequence.</span></span>
- <span data-ttu-id="68b76-265"><xref:System.Range?displayProperty=nameWithType>: Stellt einen Unterbereich einer Sequenz dar.</span><span class="sxs-lookup"><span data-stu-id="68b76-265"><xref:System.Range?displayProperty=nameWithType> represents a sub range of a sequence.</span></span>
- <span data-ttu-id="68b76-266">Der Bereichsoperator `..`, der den Beginn und das Ende eines Bereichs als seine Operanden angibt.</span><span class="sxs-lookup"><span data-stu-id="68b76-266">The range operator `..`, which specifies the start and end of a range as its operands.</span></span>

<span data-ttu-id="68b76-267">Beginnen wir mit den Regeln für Indizes.</span><span class="sxs-lookup"><span data-stu-id="68b76-267">Let's start with the rules for indexes.</span></span> <span data-ttu-id="68b76-268">Betrachten Sie einen Array `sequence`.</span><span class="sxs-lookup"><span data-stu-id="68b76-268">Consider an array `sequence`.</span></span> <span data-ttu-id="68b76-269">Der `0`-Index entspricht `sequence[0]`.</span><span class="sxs-lookup"><span data-stu-id="68b76-269">The `0` index is the same as `sequence[0]`.</span></span> <span data-ttu-id="68b76-270">Der `^0`-Index entspricht `sequence[sequence.Length]`.</span><span class="sxs-lookup"><span data-stu-id="68b76-270">The `^0` index is the same as `sequence[sequence.Length]`.</span></span> <span data-ttu-id="68b76-271">Beachten Sie, dass `sequence[^0]` genau wie `sequence[sequence.Length]` eine Ausnahme auslöst.</span><span class="sxs-lookup"><span data-stu-id="68b76-271">Note that `sequence[^0]` does throw an exception, just as `sequence[sequence.Length]` does.</span></span> <span data-ttu-id="68b76-272">Für eine beliebige Zahl `n` ist der Index `^n` identisch mit `sequence.Length - n`.</span><span class="sxs-lookup"><span data-stu-id="68b76-272">For any number `n`, the index `^n` is the same as `sequence.Length - n`.</span></span>

<span data-ttu-id="68b76-273">Ein Bereich gibt den *Beginn* und das *Ende* eines Bereichs an.</span><span class="sxs-lookup"><span data-stu-id="68b76-273">A range specifies the *start* and *end* of a range.</span></span> <span data-ttu-id="68b76-274">Der Beginn des Bereichs ist inklusiv, das Ende des Bereichs ist jedoch exklusiv. Das bedeutet, dass der *Beginn* im Bereich enthalten ist, das *Ende* aber nicht.</span><span class="sxs-lookup"><span data-stu-id="68b76-274">The start of the range is inclusive, but the end of the range is exclusive, meaning the *start* is included in the range but the *end* isn't included in the range.</span></span> <span data-ttu-id="68b76-275">Der Bereich `[0..^0]` stellt ebenso wie `[0..sequence.Length]` den gesamten Bereich dar.</span><span class="sxs-lookup"><span data-stu-id="68b76-275">The range `[0..^0]` represents the entire range, just as `[0..sequence.Length]` represents the entire range.</span></span>

<span data-ttu-id="68b76-276">Schauen wir uns einige Beispiele an.</span><span class="sxs-lookup"><span data-stu-id="68b76-276">Let's look at a few examples.</span></span> <span data-ttu-id="68b76-277">Betrachten Sie das folgende Array, kommentiert mit seinem Index „from the start“ und „from the end“:</span><span class="sxs-lookup"><span data-stu-id="68b76-277">Consider the following array, annotated with its index from the start and from the end:</span></span>

```csharp
var words = new string[]
{
                // index from start    index from end
    "The",      // 0                   ^9
    "quick",    // 1                   ^8
    "brown",    // 2                   ^7
    "fox",      // 3                   ^6
    "jumped",   // 4                   ^5
    "over",     // 5                   ^4
    "the",      // 6                   ^3
    "lazy",     // 7                   ^2
    "dog"       // 8                   ^1
};              // 9 (or words.Length) ^0
```

<span data-ttu-id="68b76-278">Sie können das letzte Wort mit dem `^1`-Index abrufen:</span><span class="sxs-lookup"><span data-stu-id="68b76-278">You can retrieve the last word with the `^1` index:</span></span>

```csharp
Console.WriteLine($"The last word is {words[^1]}");
// writes "dog"
```

<span data-ttu-id="68b76-279">Der folgende Code erzeugt einen Teilbereich mit den Worten „quick“, „brown“ und „fox“.</span><span class="sxs-lookup"><span data-stu-id="68b76-279">The following code creates a subrange with the words "quick", "brown", and "fox".</span></span> <span data-ttu-id="68b76-280">Er enthält `words[1]` bis `words[3]`.</span><span class="sxs-lookup"><span data-stu-id="68b76-280">It includes `words[1]` through `words[3]`.</span></span> <span data-ttu-id="68b76-281">Das Element `words[4]` befindet sich nicht im Bereich.</span><span class="sxs-lookup"><span data-stu-id="68b76-281">The element `words[4]` isn't in the range.</span></span>

```csharp
var quickBrownFox = words[1..4];
```

<span data-ttu-id="68b76-282">Der folgende Code erzeugt einen Teilbereich mit „lazy“ und „dog“.</span><span class="sxs-lookup"><span data-stu-id="68b76-282">The following code creates a subrange with "lazy" and "dog".</span></span> <span data-ttu-id="68b76-283">Dazu gehören `words[^2]` und `words[^1]`.</span><span class="sxs-lookup"><span data-stu-id="68b76-283">It includes `words[^2]` and `words[^1]`.</span></span> <span data-ttu-id="68b76-284">Der Endindex `words[^0]` ist nicht enthalten:</span><span class="sxs-lookup"><span data-stu-id="68b76-284">The end index `words[^0]` isn't included:</span></span>

```csharp
var lazyDog = words[^2..^0];
```

<span data-ttu-id="68b76-285">Die folgenden Beispiele erstellen Bereiche, die am Anfang, am Ende und auf beiden Seiten offen sind:</span><span class="sxs-lookup"><span data-stu-id="68b76-285">The following examples create ranges that are open ended for the start, end, or both:</span></span>

```csharp
var allWords = words[..]; // contains "The" through "dog".
var firstPhrase = words[..4]; // contains "The" through "fox"
var lastPhrase = words[6..]; // contains "the", "lazy" and "dog"
```

<span data-ttu-id="68b76-286">Sie können Bereiche auch als Variablen deklarieren:</span><span class="sxs-lookup"><span data-stu-id="68b76-286">You can also declare ranges as variables:</span></span>

```csharp
Range phrase = 1..4;
```

<span data-ttu-id="68b76-287">Der Bereich kann dann innerhalb der Zeichen `[` und `]` verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="68b76-287">The range can then be used inside the `[` and `]` characters:</span></span>

```csharp
var text = words[phrase];
```

<span data-ttu-id="68b76-288">Indizes und Bereiche werden nicht nur von Arrays unterstützt.</span><span class="sxs-lookup"><span data-stu-id="68b76-288">Not only arrays support indices and ranges.</span></span> <span data-ttu-id="68b76-289">Indizes und Bereiche können auch mit [string](../language-reference/builtin-types/reference-types.md#the-string-type), <xref:System.Span%601> oder <xref:System.ReadOnlySpan%601> verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="68b76-289">You also can use indices and ranges with [string](../language-reference/builtin-types/reference-types.md#the-string-type), <xref:System.Span%601>, or <xref:System.ReadOnlySpan%601>.</span></span> <span data-ttu-id="68b76-290">Weitere Informationen finden Sie unter [Typunterstützung für Indizes und Bereiche](../tutorials/ranges-indexes.md#type-support-for-indices-and-ranges).</span><span class="sxs-lookup"><span data-stu-id="68b76-290">For more information, see [Type support for indices and ranges](../tutorials/ranges-indexes.md#type-support-for-indices-and-ranges).</span></span>

<span data-ttu-id="68b76-291">Weitere Informationen zu Indizes und Bereichen finden Sie im Tutorial zu [Indizes und Bereichen](../tutorials/ranges-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="68b76-291">You can explore more about indices and ranges in the tutorial on [indices and ranges](../tutorials/ranges-indexes.md).</span></span>

## <a name="null-coalescing-assignment"></a><span data-ttu-id="68b76-292">NULL-Coalescing-Zuweisung</span><span class="sxs-lookup"><span data-stu-id="68b76-292">Null-coalescing assignment</span></span>

<span data-ttu-id="68b76-293">In C# 8.0 wird der NULL-Coalescing-Zuweisungsoperator `??=` eingeführt.</span><span class="sxs-lookup"><span data-stu-id="68b76-293">C# 8.0 introduces the null-coalescing assignment operator `??=`.</span></span> <span data-ttu-id="68b76-294">Sie können den `??=`-Operator verwenden, um den Wert des rechten Operanden dem linken Operanden nur dann zuzuweisen, wenn die Auswertung des linken Operanden `null` ergibt.</span><span class="sxs-lookup"><span data-stu-id="68b76-294">You can use the `??=` operator to assign the value of its right-hand operand to its left-hand operand only if the left-hand operand evaluates to `null`.</span></span>

```csharp
List<int> numbers = null;
int? i = null;

numbers ??= new List<int>();
numbers.Add(i ??= 17);
numbers.Add(i ??= 20);

Console.WriteLine(string.Join(" ", numbers));  // output: 17 17
Console.WriteLine(i);  // output: 17
```

<span data-ttu-id="68b76-295">Weitere Informationen finden Sie im Artikel zu den Operatoren [?? und ??=](../language-reference/operators/null-coalescing-operator.md).</span><span class="sxs-lookup"><span data-stu-id="68b76-295">For more information, see the [?? and ??= operators](../language-reference/operators/null-coalescing-operator.md) article.</span></span>

## <a name="unmanaged-constructed-types"></a><span data-ttu-id="68b76-296">Nicht verwaltete konstruierte Typen</span><span class="sxs-lookup"><span data-stu-id="68b76-296">Unmanaged constructed types</span></span>

<span data-ttu-id="68b76-297">In C# 7.3 und früher darf ein konstruierter Typ (also ein Typ, der mindestens ein Typargument enthält) kein [nicht verwalteter Typ](../language-reference/builtin-types/unmanaged-types.md) sein.</span><span class="sxs-lookup"><span data-stu-id="68b76-297">In C# 7.3 and earlier, a constructed type (a type that includes at least one type argument) can't be an [unmanaged type](../language-reference/builtin-types/unmanaged-types.md).</span></span> <span data-ttu-id="68b76-298">Ab C# 8.0 ist ein konstruierter Werttyp nicht verwaltet, wenn er nur Felder von nicht verwalteten Typen enthält.</span><span class="sxs-lookup"><span data-stu-id="68b76-298">Starting with C# 8.0, a constructed value type is unmanaged if it contains fields of unmanaged types only.</span></span>

<span data-ttu-id="68b76-299">Ein Beispiel: Ihr Code enthält die folgende Definition des generischen `Coords<T>`-Typs:</span><span class="sxs-lookup"><span data-stu-id="68b76-299">For example, given the following definition of the generic `Coords<T>` type:</span></span>

```csharp
public struct Coords<T>
{
    public T X;
    public T Y;
}
```

<span data-ttu-id="68b76-300">Dann ist der `Coords<int>`-Typ in C# 8.0 und höher ein nicht verwalteter Typ.</span><span class="sxs-lookup"><span data-stu-id="68b76-300">the `Coords<int>` type is an unmanaged type in C# 8.0 and later.</span></span> <span data-ttu-id="68b76-301">Wie bei allen nicht verwalteten Typen können Sie einen Zeiger auf eine Variable dieses Typs erstellen oder Instanzen dieses Typs einen [Arbeitsspeicherblock im Stapel zuordnen](../language-reference/operators/stackalloc.md):</span><span class="sxs-lookup"><span data-stu-id="68b76-301">Like for any unmanaged type, you can create a pointer to a variable of this type or [allocate a block of memory on the stack](../language-reference/operators/stackalloc.md) for instances of this type:</span></span>

```csharp
Span<Coords<int>> coordinates = stackalloc[]
{
    new Coords<int> { X = 0, Y = 0 },
    new Coords<int> { X = 0, Y = 3 },
    new Coords<int> { X = 4, Y = 0 }
};
```

<span data-ttu-id="68b76-302">Weitere Informationen finden Sie unter [Nicht verwaltete Typen](../language-reference/builtin-types/unmanaged-types.md).</span><span class="sxs-lookup"><span data-stu-id="68b76-302">For more information, see [Unmanaged types](../language-reference/builtin-types/unmanaged-types.md).</span></span>

## <a name="stackalloc-in-nested-expressions"></a><span data-ttu-id="68b76-303">Stackalloc in geschachtelten Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="68b76-303">Stackalloc in nested expressions</span></span>

<span data-ttu-id="68b76-304">Ab C# 8.0 können Sie, wenn das Ergebnis eines [stackalloc](../language-reference/operators/stackalloc.md)-Ausdrucks vom Typ <xref:System.Span%601?displayProperty=nameWithType> oder <xref:System.ReadOnlySpan%601?displayProperty=nameWithType> ist, den `stackalloc`-Ausdruck in anderen Ausdrücken verwenden:</span><span class="sxs-lookup"><span data-stu-id="68b76-304">Starting with C# 8.0, if the result of a [stackalloc](../language-reference/operators/stackalloc.md) expression is of the <xref:System.Span%601?displayProperty=nameWithType> or <xref:System.ReadOnlySpan%601?displayProperty=nameWithType> type, you can use the `stackalloc` expression in other expressions:</span></span>

```csharp
Span<int> numbers = stackalloc[] { 1, 2, 3, 4, 5, 6 };
var ind = numbers.IndexOfAny(stackalloc[] { 2, 4, 6 ,8 });
Console.WriteLine(ind);  // output: 1
```

## <a name="enhancement-of-interpolated-verbatim-strings"></a><span data-ttu-id="68b76-305">Erweiterung von interpolierten ausführlichen Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="68b76-305">Enhancement of interpolated verbatim strings</span></span>

<span data-ttu-id="68b76-306">`$`- und `@`-Token in [interpolierten](../language-reference/tokens/interpolated.md) ausführlichen Zeichenfolgen können in beliebiger Reihenfolge vorliegen: sowohl `$@"..."` als auch `@$"..."` sind gültige interpolierte ausführliche Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="68b76-306">Order of the `$` and `@` tokens in [interpolated](../language-reference/tokens/interpolated.md) verbatim strings can be any: both `$@"..."` and `@$"..."` are valid interpolated verbatim strings.</span></span> <span data-ttu-id="68b76-307">In früheren C#-Versionen musste das Token `$` vor dem Token `@` vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="68b76-307">In earlier C# versions, the `$` token must appear before the `@` token.</span></span>
