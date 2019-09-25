---
title: Neues in C# 8.0 – C#-Leitfaden
description: Überblick über die neuen Funktionen von C# 8.0. Dieser Artikel ist auf dem neuesten Stand mit Vorschauversion 5.
ms.date: 09/20/2019
ms.openlocfilehash: a434d1f7598bc3f6787f7466e48fb161db192761
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2019
ms.locfileid: "71182414"
---
# <a name="whats-new-in-c-80"></a><span data-ttu-id="9bc4f-104">Neues in C# 8.0</span><span class="sxs-lookup"><span data-stu-id="9bc4f-104">What's new in C# 8.0</span></span>

<span data-ttu-id="9bc4f-105">Wir haben viele Verbesserungen an der C#-Sprache vorgenommen, die Sie bereits ausprobieren können.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-105">There are many enhancements to the C# language that you can try out already.</span></span>

- [<span data-ttu-id="9bc4f-106">Readonly-Member</span><span class="sxs-lookup"><span data-stu-id="9bc4f-106">Readonly members</span></span>](#readonly-members)
- [<span data-ttu-id="9bc4f-107">Standardschnittstellenmember</span><span class="sxs-lookup"><span data-stu-id="9bc4f-107">Default interface members</span></span>](#default-interface-members)
- <span data-ttu-id="9bc4f-108">[Verbesserungen am Musterabgleich](#more-patterns-in-more-places):</span><span class="sxs-lookup"><span data-stu-id="9bc4f-108">[Pattern matching enhancements](#more-patterns-in-more-places):</span></span>
  - [<span data-ttu-id="9bc4f-109">switch-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="9bc4f-109">Switch expressions</span></span>](#switch-expressions)
  - [<span data-ttu-id="9bc4f-110">Eigenschaftsmuster</span><span class="sxs-lookup"><span data-stu-id="9bc4f-110">Property patterns</span></span>](#property-patterns)
  - [<span data-ttu-id="9bc4f-111">Tupelmuster</span><span class="sxs-lookup"><span data-stu-id="9bc4f-111">Tuple patterns</span></span>](#tuple-patterns)
  - [<span data-ttu-id="9bc4f-112">Positionsmuster</span><span class="sxs-lookup"><span data-stu-id="9bc4f-112">Positional patterns</span></span>](#positional-patterns)
- [<span data-ttu-id="9bc4f-113">using-Deklarationen</span><span class="sxs-lookup"><span data-stu-id="9bc4f-113">Using declarations</span></span>](#using-declarations)
- [<span data-ttu-id="9bc4f-114">Statische lokale Funktionen</span><span class="sxs-lookup"><span data-stu-id="9bc4f-114">Static local functions</span></span>](#static-local-functions)
- [<span data-ttu-id="9bc4f-115">Verwerfbare Referenzstrukturen</span><span class="sxs-lookup"><span data-stu-id="9bc4f-115">Disposable ref structs</span></span>](#disposable-ref-structs)
- [<span data-ttu-id="9bc4f-116">Nullwerte zulassende Verweistypen</span><span class="sxs-lookup"><span data-stu-id="9bc4f-116">Nullable reference types</span></span>](#nullable-reference-types)
- [<span data-ttu-id="9bc4f-117">Asynchrone Streams</span><span class="sxs-lookup"><span data-stu-id="9bc4f-117">Asynchronous streams</span></span>](#asynchronous-streams)
- [<span data-ttu-id="9bc4f-118">Indizes und Bereiche</span><span class="sxs-lookup"><span data-stu-id="9bc4f-118">Indices and ranges</span></span>](#indices-and-ranges)
- [<span data-ttu-id="9bc4f-119">NULL-Coalescing-Zuweisung</span><span class="sxs-lookup"><span data-stu-id="9bc4f-119">Null-coalescing assignment</span></span>](#null-coalescing-assignment)
- [<span data-ttu-id="9bc4f-120">Nicht verwaltete konstruierte Typen</span><span class="sxs-lookup"><span data-stu-id="9bc4f-120">Unmanaged constructed types</span></span>](#unmanaged-constructed-types)
- [<span data-ttu-id="9bc4f-121">„stackalloc“ in geschachtelten Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="9bc4f-121">stackalloc in nested expressions</span></span>](#stackalloc-in-nested-expressions)
- [<span data-ttu-id="9bc4f-122">Erweiterung von interpolierten ausführlichen Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="9bc4f-122">Enhancement of interpolated verbatim strings</span></span>](#enhancement-of-interpolated-verbatim-strings)

> [!NOTE]
> <span data-ttu-id="9bc4f-123">Dieser Artikel wurde zuletzt für Vorschauversion 5 von C# 8.0 aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-123">This article was last updated for C# 8.0 preview 5.</span></span>

<span data-ttu-id="9bc4f-124">Der Rest dieses Artikels beschreibt diese Funktionen kurz.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-124">The remainder of this article briefly describes these features.</span></span> <span data-ttu-id="9bc4f-125">Wenn ausführliche Artikel verfügbar sind, werden Links zu diesen Tutorials und Übersichten bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-125">Where in-depth articles are available, links to those tutorials and overviews are provided.</span></span> <span data-ttu-id="9bc4f-126">Sie können sich diese Funktionen in unserer Umgebung mit dem globalen `dotnet try`-Tool näher ansehen:</span><span class="sxs-lookup"><span data-stu-id="9bc4f-126">You can explore these features in your environment using the `dotnet try` global tool:</span></span>

1. <span data-ttu-id="9bc4f-127">Installieren Sie das globale [dotnet-try](https://github.com/dotnet/try/blob/master/README.md#setup)-Tool.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-127">Install the [dotnet-try](https://github.com/dotnet/try/blob/master/README.md#setup) global tool.</span></span>
1. <span data-ttu-id="9bc4f-128">Klonen Sie das [dotnet/try-samples](https://github.com/dotnet/try-samples)-Repository.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-128">Clone the [dotnet/try-samples](https://github.com/dotnet/try-samples) repository.</span></span>
1. <span data-ttu-id="9bc4f-129">Legen Sie das aktuelle Verzeichnis auf das Unterverzeichnis *csharp8* für das *try-samples*-Repository fest.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-129">Set the current directory to the *csharp8* subdirectory for the *try-samples* repository.</span></span>
1. <span data-ttu-id="9bc4f-130">Führen Sie aus `dotnet try`.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-130">Run `dotnet try`.</span></span>

## <a name="readonly-members"></a><span data-ttu-id="9bc4f-131">Readonly-Member</span><span class="sxs-lookup"><span data-stu-id="9bc4f-131">Readonly members</span></span>

<span data-ttu-id="9bc4f-132">Sie können den `readonly`-Modifikator auf jedes Member einer Struktur anwenden.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-132">You can apply the `readonly` modifier to any member of a struct.</span></span> <span data-ttu-id="9bc4f-133">Damit wird angezeigt, dass das Element den Zustand nicht ändert.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-133">It indicates that the member does not modify state.</span></span> <span data-ttu-id="9bc4f-134">Dies ist granularer als das Anwenden des `readonly`-Modifikators auf eine `struct`-Deklaration.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-134">It's more granular than applying the `readonly` modifier to a `struct` declaration.</span></span>  <span data-ttu-id="9bc4f-135">Betrachten Sie folgende veränderliche Struktur:</span><span class="sxs-lookup"><span data-stu-id="9bc4f-135">Consider the following mutable struct:</span></span>

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

<span data-ttu-id="9bc4f-136">Wie die meisten Strukturen ändert die `ToString()`-Methode den Zustand nicht.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-136">Like most structs, the `ToString()` method does not modify state.</span></span> <span data-ttu-id="9bc4f-137">Sie könnten dies durch Hinzufügen des `readonly`-Modifikators zur Deklaration von `ToString()` angeben:</span><span class="sxs-lookup"><span data-stu-id="9bc4f-137">You could indicate that by adding the `readonly` modifier to the declaration of `ToString()`:</span></span>

```csharp
public readonly override string ToString() =>
    $"({X}, {Y}) is {Distance} from the origin";
```

<span data-ttu-id="9bc4f-138">Die vorhergehende Änderung generiert eine Compilerwarnung, weil `ToString` auf die `Distance`-Eigenschaft zugreift, die nicht als `readonly` markiert ist:</span><span class="sxs-lookup"><span data-stu-id="9bc4f-138">The preceding change generates a compiler warning, because `ToString` accesses the `Distance` property, which is not marked `readonly`:</span></span>

```console
warning CS8656: Call to non-readonly member 'Point.Distance.get' from a 'readonly' member results in an implicit copy of 'this'
```

<span data-ttu-id="9bc4f-139">Der Compiler warnt Sie, wenn er eine Defensivkopie erstellen muss.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-139">The compiler warns you when it needs to create a defensive copy.</span></span>  <span data-ttu-id="9bc4f-140">Die `Distance`-Eigenschaft ändert den Zustand nicht, sodass Sie diese Warnung beheben können, indem Sie den `readonly`-Modifikator zur Deklaration hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="9bc4f-140">The `Distance` property does not change state, so you can fix this warning by adding the `readonly` modifier to the declaration:</span></span>

```csharp
public readonly double Distance => Math.Sqrt(X * X + Y * Y);
```

<span data-ttu-id="9bc4f-141">Beachten Sie, dass der `readonly`-Modifikator bei einer schreibgeschützten Eigenschaft notwendig ist.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-141">Notice that the `readonly` modifier is necessary on a read only property.</span></span> <span data-ttu-id="9bc4f-142">Der Compiler geht nicht davon aus, dass `get`-Zugriffsmethoden den Zustand nicht ändern; Sie müssen `readonly` explizit deklarieren.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-142">The compiler doesn't assume `get` accessors do not modify state; you must declare `readonly` explicitly.</span></span> <span data-ttu-id="9bc4f-143">Der Compiler erzwingt die Regel, dass `readonly`-Member den Zustand nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-143">The compiler does enforce the rule that `readonly` members do not modify state.</span></span> <span data-ttu-id="9bc4f-144">Die folgende Methode wird nicht kompiliert, es sei denn, Sie entfernen den `readonly`-Modifikator:</span><span class="sxs-lookup"><span data-stu-id="9bc4f-144">The following method will not compile unless you remove the `readonly` modifier:</span></span>

```csharp
public readonly void Translate(int xOffset, int yOffset)
{
    X += xOffset;
    Y += yOffset;
}
```

<span data-ttu-id="9bc4f-145">Mit diesem Feature können Sie Ihre Designabsicht angeben, damit der Compiler sie erzwingen und Optimierungen basierend auf dieser Absicht vornehmen kann.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-145">This feature lets you specify your design intent so the compiler can enforce it, and make optimizations based on that intent.</span></span>

## <a name="default-interface-members"></a><span data-ttu-id="9bc4f-146">Standardschnittstellenmember</span><span class="sxs-lookup"><span data-stu-id="9bc4f-146">Default interface members</span></span>

<span data-ttu-id="9bc4f-147">Sie können nun Member zu Schnittstellen hinzufügen und eine Implementierung für diese Member bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-147">You can now add members to interfaces and provide an implementation for those members.</span></span> <span data-ttu-id="9bc4f-148">Dieses Sprachfeature ermöglicht es API-Autoren, in späteren Versionen Methoden zu einer Schnittstelle hinzuzufügen, ohne die Quell- oder Binärkompatibilität mit bestehenden Implementierungen dieser Schnittstelle zu beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-148">This language feature enables API authors to add methods to an interface in later versions without breaking source or binary compatibility with existing implementations of that interface.</span></span> <span data-ttu-id="9bc4f-149">Bestehende Implementierungen *erben* die Standardimplementierung.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-149">Existing implementations *inherit* the default implementation.</span></span> <span data-ttu-id="9bc4f-150">Dieses Feature ermöglicht zudem die Interaktion zwischen C# und APIs, die auf Android oder Swift abzielen und ähnliche Funktionen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-150">This feature also enables C# to interoperate with APIs that target Android or Swift, which support similar features.</span></span> <span data-ttu-id="9bc4f-151">Standardschnittstellenmember ermöglichen auch Szenarien, die einem „Traits“-Sprachfeature ähneln.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-151">Default interface members also enable scenarios similar to a "traits" language feature.</span></span>

<span data-ttu-id="9bc4f-152">Standardschnittstellenmember wirken sich auf viele Szenarien und Sprachelemente aus.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-152">Default interface members affects many scenarios and language elements.</span></span> <span data-ttu-id="9bc4f-153">Unser erstes Tutorial behandelt [die Aktualisierung einer Schnittstelle mit Standardimplementierungen](../tutorials/default-interface-members-versions.md).</span><span class="sxs-lookup"><span data-stu-id="9bc4f-153">Our first tutorial covers [updating an interface with default implementations](../tutorials/default-interface-members-versions.md).</span></span> <span data-ttu-id="9bc4f-154">Weitere Tutorials und Referenzaktualisierungen folgen rechtzeitig zur allgemeinen Veröffentlichung.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-154">Other tutorials and reference updates are coming in time for general release.</span></span>

## <a name="more-patterns-in-more-places"></a><span data-ttu-id="9bc4f-155">Weitere Muster an mehr Orten</span><span class="sxs-lookup"><span data-stu-id="9bc4f-155">More patterns in more places</span></span>

<span data-ttu-id="9bc4f-156">**Musterabgleich** bietet Tools zur Bereitstellung formabhängiger Funktionalität für verwandte, aber unterschiedliche Datentypen.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-156">**Pattern matching** gives tools to provide shape-dependent functionality across related but different kinds of data.</span></span> <span data-ttu-id="9bc4f-157">C# 7.0 führte eine Syntax für Typmuster und konstante Muster ein, indem der Ausdruck [`is`](../language-reference/keywords/is.md) und die Anweisung [`switch`](../language-reference/keywords/switch.md) verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-157">C# 7.0 introduced syntax for type patterns and constant patterns by using the [`is`](../language-reference/keywords/is.md) expression and the [`switch`](../language-reference/keywords/switch.md) statement.</span></span> <span data-ttu-id="9bc4f-158">Diese Funktionen stellten die ersten vorläufigen Schritte zur Unterstützung von Programmierparadigmen dar, bei denen Daten und Funktionalität getrennt voneinander sind.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-158">These features represented the first tentative steps toward supporting programming paradigms where data and functionality live apart.</span></span> <span data-ttu-id="9bc4f-159">Da sich die Branche immer mehr auf Mikroservices und andere Cloud-basierte Architekturen konzentriert, werden andere Sprachtools benötigt.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-159">As the industry moves toward more microservices and other cloud-based architectures, other language tools are needed.</span></span>

<span data-ttu-id="9bc4f-160">C# 8.0 erweitert dieses Vokabular, sodass Sie mehr Musterausdrücke an mehreren Stellen in Ihrem Code verwenden können.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-160">C# 8.0 expands this vocabulary so you can use more pattern expressions in more places in your code.</span></span> <span data-ttu-id="9bc4f-161">Berücksichtigen Sie diese Funktionen, wenn Ihre Daten und Funktionen getrennt sind.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-161">Consider these features when your data and functionality are separate.</span></span> <span data-ttu-id="9bc4f-162">Berücksichtigen Sie den Musterabgleich, wenn Ihre Algorithmen von einer anderen Tatsache als dem Runtimetyp eines Objekts abhängen.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-162">Consider pattern matching when your algorithms depend on a fact other than the runtime type of an object.</span></span> <span data-ttu-id="9bc4f-163">Diese Verfahren bieten eine weitere Möglichkeit, Entwürfe auszudrücken.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-163">These techniques provide another way to express designs.</span></span>

<span data-ttu-id="9bc4f-164">Zusätzlich zu neuen Mustern an neuen Orten fügt C# 8.0 **rekursive Muster** hinzu.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-164">In addition to new patterns in new places, C# 8.0 adds **recursive patterns**.</span></span> <span data-ttu-id="9bc4f-165">Das Ergebnis eines beliebigen Musterausdrucks ist ein Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-165">The result of any pattern expression is an expression.</span></span> <span data-ttu-id="9bc4f-166">Ein rekursives Muster ist einfach ein Musterausdruck, der auf die Ausgabe eines anderen Musterausdrucks angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-166">A recursive pattern is simply a pattern expression applied to the output of another pattern expression.</span></span>

### <a name="switch-expressions"></a><span data-ttu-id="9bc4f-167">switch-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="9bc4f-167">switch expressions</span></span>

<span data-ttu-id="9bc4f-168">Häufig liefert eine [`switch`](../language-reference/keywords/switch.md)-Anweisung in jedem ihrer `case`-Blöcke einen Wert.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-168">Often, a [`switch`](../language-reference/keywords/switch.md) statement produces a value in each of its `case` blocks.</span></span> <span data-ttu-id="9bc4f-169">Mit **switch-Ausdrücken** können Sie eine präzisere Ausdruckssyntax verwenden.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-169">**Switch expressions** enable you to use more concise expression syntax.</span></span> <span data-ttu-id="9bc4f-170">Es gibt weniger repetitive `case`- und `break`-Schlüsselwörter und weniger geschweifte Klammern.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-170">There are fewer repetitive `case` and `break` keywords, and fewer curly braces.</span></span>  <span data-ttu-id="9bc4f-171">Betrachten Sie als Beispiel die folgende Enumeration, die die Farben des Regenbogens enumeriert:</span><span class="sxs-lookup"><span data-stu-id="9bc4f-171">As an example, consider the following enum that lists the colors of the rainbow:</span></span>

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

<span data-ttu-id="9bc4f-172">Wenn Ihre Anwendung einen `RGBColor`-Typ definiert hat, der aus den Komponenten `R`, `G` und `B` aufgebaut ist, können Sie einen `Rainbow`-Wert in seine RGB-Werte konvertieren, indem Sie die folgende Methode verwenden, die einen Switch-Ausdruck enthält:</span><span class="sxs-lookup"><span data-stu-id="9bc4f-172">If your application defined an `RGBColor` type that is constructed from the `R`, `G` and `B` components, you could convert a `Rainbow` value to its RGB values using the following method containing a switch expression:</span></span>

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

<span data-ttu-id="9bc4f-173">Es gibt hier verschiedene Syntaxverbesserungen:</span><span class="sxs-lookup"><span data-stu-id="9bc4f-173">There are several syntax improvements here:</span></span>

- <span data-ttu-id="9bc4f-174">Die Variable steht vor dem `switch`-Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-174">The variable comes before the `switch` keyword.</span></span> <span data-ttu-id="9bc4f-175">Die unterschiedliche Reihenfolge macht es optisch einfach, den switch-Ausdruck von der switch-Anweisung zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-175">The different order makes it visually easy to distinguish the switch expression from the switch statement.</span></span>
- <span data-ttu-id="9bc4f-176">Die `case`- und `:`-Elemente werden durch `=>` ersetzt.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-176">The `case` and `:` elements are replaced with `=>`.</span></span> <span data-ttu-id="9bc4f-177">Es ist präziser und intuitiver.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-177">It's more concise and intuitive.</span></span>
- <span data-ttu-id="9bc4f-178">Der `default`-Fall wird durch eine `_`-Ausschlussvariable ersetzt.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-178">The `default` case is replaced with a `_` discard.</span></span>
- <span data-ttu-id="9bc4f-179">Die Textkörper sind Ausdrücke, keine Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-179">The bodies are expressions, not statements.</span></span>

<span data-ttu-id="9bc4f-180">Stellen Sie dies mit dem entsprechenden Code unter Verwendung der klassischen `switch`-Anweisung gegenüber:</span><span class="sxs-lookup"><span data-stu-id="9bc4f-180">Contrast that with the equivalent code using the classic `switch` statement:</span></span>

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

### <a name="property-patterns"></a><span data-ttu-id="9bc4f-181">Eigenschaftsmuster</span><span class="sxs-lookup"><span data-stu-id="9bc4f-181">Property patterns</span></span>

<span data-ttu-id="9bc4f-182">Mit dem **Eigenschaftsmuster** können Sie die Eigenschaften des untersuchten Objekts anpassen.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-182">The **property pattern** enables you to match on properties of the object examined.</span></span> <span data-ttu-id="9bc4f-183">Denken Sie an eine eCommerce-Website, die die Umsatzsteuer auf der Grundlage der Adresse des Käufers berechnen muss.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-183">Consider an eCommerce site that must compute sales tax based on the buyer's address.</span></span> <span data-ttu-id="9bc4f-184">Diese Berechnung ist keine Kernaufgabe einer `Address`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-184">That computation is not a core responsibility of an `Address` class.</span></span> <span data-ttu-id="9bc4f-185">Sie wird sich im Laufe der Zeit ändern, wahrscheinlich häufiger als Adressformatänderungen.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-185">It will change over time, likely more often than address format changes.</span></span> <span data-ttu-id="9bc4f-186">Die Höhe der Umsatzsteuer hängt von der `State`-Eigenschaft der Adresse ab.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-186">The amount of sales tax depends on the `State` property of the address.</span></span> <span data-ttu-id="9bc4f-187">Die folgende Methode verwendet das Eigenschaftsmuster, um die Umsatzsteuer aus der Adresse und dem Preis zu berechnen:</span><span class="sxs-lookup"><span data-stu-id="9bc4f-187">The following method uses the property pattern to compute the sales tax from the address and the price:</span></span>

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

<span data-ttu-id="9bc4f-188">Ein Musterabgleich erstellt eine präzise Syntax,. um diesen Algorithmus auszudrücken.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-188">Pattern matching creates a concise syntax for expressing this algorithm.</span></span>

### <a name="tuple-patterns"></a><span data-ttu-id="9bc4f-189">Tupelmuster</span><span class="sxs-lookup"><span data-stu-id="9bc4f-189">Tuple patterns</span></span>

<span data-ttu-id="9bc4f-190">Einige Algorithmen sind von mehreren Eingaben abhängig.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-190">Some algorithms depend on multiple inputs.</span></span> <span data-ttu-id="9bc4f-191">**Tupelmuster** erlauben Ihnen, auf Grundlage mehrerer Werte, ausgedrückt als ein [Tupel](../tuples.md), zu wechseln („switch“).</span><span class="sxs-lookup"><span data-stu-id="9bc4f-191">**Tuple patterns** allow you to switch based on multiple values expressed as a [tuple](../tuples.md).</span></span>  <span data-ttu-id="9bc4f-192">Der folgende Code zeigt einen switch-Ausdruck für das Spiel *Stein, Schere, Papier* (Schnick, Schnack, Schnuck):</span><span class="sxs-lookup"><span data-stu-id="9bc4f-192">The following code shows a switch expression for the game *rock, paper, scissors*:</span></span>

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

<span data-ttu-id="9bc4f-193">Die Meldungen zeigen den Gewinner an.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-193">The messages indicate the winner.</span></span> <span data-ttu-id="9bc4f-194">Der Fall „Verwerfen“ („case discard“) stellt die drei Kombinationen für Unentschieden oder andere Texteingaben dar.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-194">The discard case represents the three combinations for ties, or other text inputs.</span></span>

### <a name="positional-patterns"></a><span data-ttu-id="9bc4f-195">Positionsmuster</span><span class="sxs-lookup"><span data-stu-id="9bc4f-195">Positional patterns</span></span>

<span data-ttu-id="9bc4f-196">Einige Typen umfassen eine `Deconstruct`-Methode, die ihre Eigenschaften in diskrete Variablen dekonstruiert.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-196">Some types include a `Deconstruct` method that deconstructs its properties into discrete variables.</span></span> <span data-ttu-id="9bc4f-197">Wenn auf eine `Deconstruct`-Methode zugegriffen werden kann, können Sie **Positionsmuster** verwenden, um Eigenschaften des Objekts zu untersuchen, und diese Eigenschaften für ein Muster verwenden.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-197">When a `Deconstruct` method is accessible, you can use **positional patterns** to inspect properties of the object and use those properties for a pattern.</span></span>  <span data-ttu-id="9bc4f-198">Beachten Sie die folgende `Point`-Klasse, die eine `Deconstruct`-Methode umfasst, um diskrete Variablen für `X` und `Y` zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="9bc4f-198">Consider the following `Point` class that includes a `Deconstruct` method to create discrete variables for `X` and `Y`:</span></span>

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

<span data-ttu-id="9bc4f-199">Beachten Sie zudem die folgende Enumeration, die verschiedene Positionen eines Quadranten darstellt:</span><span class="sxs-lookup"><span data-stu-id="9bc4f-199">Additionally, consider the following enum that represents various positions of a quadrant:</span></span>

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

<span data-ttu-id="9bc4f-200">Die folgende Methode verwendet das **Positionsmuster**, um die Werte von `x` und `y` zu extrahieren.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-200">The following method uses the **positional pattern** to extract the values of `x` and `y`.</span></span> <span data-ttu-id="9bc4f-201">Dann wird mit einer `when`-Klausel der `Quadrant` des Punktes bestimmt:</span><span class="sxs-lookup"><span data-stu-id="9bc4f-201">Then, it uses a `when` clause to determine the `Quadrant` of the point:</span></span>

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

<span data-ttu-id="9bc4f-202">Das Ausschussmuster im vorherigen Switch stimmt überein, wenn entweder `x` oder `y` 0 ist, jedoch nicht beide.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-202">The discard pattern in the preceding switch matches when either `x` or `y` is 0, but not both.</span></span> <span data-ttu-id="9bc4f-203">Ein switch-Ausdruck muss entweder einen Wert erzeugen oder eine Ausnahme auslösen.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-203">A switch expression must either produce a value or throw an exception.</span></span> <span data-ttu-id="9bc4f-204">Wenn keiner der Fälle übereinstimmt, löst der switch-Ausdruck eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-204">If none of the cases match, the switch expression throws an exception.</span></span> <span data-ttu-id="9bc4f-205">Der Compiler erzeugt für Sie eine Warnung, wenn Sie nicht alle möglichen Fälle in Ihrem switch-Ausdruck abdecken.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-205">The compiler generates a warning for you if you do not cover all possible cases in your switch expression.</span></span>

<span data-ttu-id="9bc4f-206">In diesem [erweiterten Tutorial zum Musterabgleich](../tutorials/pattern-matching.md) erhalten Sie weitere Informationen zu Musterabgleichverfahren.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-206">You can explore pattern matching techniques in this [advanced tutorial on pattern matching](../tutorials/pattern-matching.md).</span></span>

## <a name="using-declarations"></a><span data-ttu-id="9bc4f-207">using-Deklarationen</span><span class="sxs-lookup"><span data-stu-id="9bc4f-207">using declarations</span></span>

<span data-ttu-id="9bc4f-208">Eine **using-Deklaration** ist eine Variablendeklaration, der das Schlüsselwort `using` vorangestellt ist.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-208">A **using declaration** is a variable declaration preceded by the `using` keyword.</span></span> <span data-ttu-id="9bc4f-209">Es teilt dem Compiler mit, dass die zu deklarierende Variable am Ende des umschließenden Bereichs angeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-209">It tells the compiler that the variable being declared should be disposed at the end of the enclosing scope.</span></span> <span data-ttu-id="9bc4f-210">Sehen Sie sich beispielsweise den folgenden Code an, der eine Textdatei schreibt:</span><span class="sxs-lookup"><span data-stu-id="9bc4f-210">For example, consider the following code that writes a text file:</span></span>

```csharp
static void WriteLinesToFile(IEnumerable<string> lines)
{
    using var file = new System.IO.StreamWriter("WriteLines2.txt");
    foreach (string line in lines)
    {
        if (!line.Contains("Second"))
        {
            file.WriteLine(line);
        }
    }
// file is disposed here
}
```

<span data-ttu-id="9bc4f-211">Im vorhergehenden Beispiel wird die Datei angeordnet, wenn die schließende Klammer für die Methode erreicht ist.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-211">In the preceding example, the file is disposed when the closing brace for the method is reached.</span></span> <span data-ttu-id="9bc4f-212">Dies ist das Ende des Bereichs, in dem `file` deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-212">That's the end of the scope in which `file` is declared.</span></span> <span data-ttu-id="9bc4f-213">Der obige Code entspricht dem folgenden Code mit klassischer [using-Anweisung](../language-reference/keywords/using-statement.md):</span><span class="sxs-lookup"><span data-stu-id="9bc4f-213">The preceding code is equivalent to the following code that uses the classic [using statement](../language-reference/keywords/using-statement.md):</span></span>

```csharp
static void WriteLinesToFile(IEnumerable<string> lines)
{
    using (var file = new System.IO.StreamWriter("WriteLines2.txt"))
    {
        foreach (string line in lines)
        {
            if (!line.Contains("Second"))
            {
                file.WriteLine(line);
            }
        }
    } // file is disposed here
}
```

<span data-ttu-id="9bc4f-214">Im vorhergehenden Beispiel wird die Datei angeordnet, wenn die der `using`-Anweisung zugeordnete schließende Klammer erreicht ist.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-214">In the preceding example, the file is disposed when the closing brace associated with the `using` statement is reached.</span></span>

<span data-ttu-id="9bc4f-215">In beiden Fällen generiert der Compiler den Aufruf von `Dispose()`.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-215">In both cases, the compiler generates the call to `Dispose()`.</span></span> <span data-ttu-id="9bc4f-216">Der Compiler erzeugt einen Fehler, wenn der Ausdruck in der `using`-Anweisung nicht verwerfbar ist.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-216">The compiler generates an error if the expression in the `using` statement is not disposable.</span></span>

## <a name="static-local-functions"></a><span data-ttu-id="9bc4f-217">Statische lokale Funktionen</span><span class="sxs-lookup"><span data-stu-id="9bc4f-217">Static local functions</span></span>

<span data-ttu-id="9bc4f-218">Sie können nun den `static`-Modifikator zu lokalen Funktionen hinzufügen, um sicherzustellen, dass die lokale Funktion keine Variablen aus dem umschließenden Bereich erfasst (referenziert).</span><span class="sxs-lookup"><span data-stu-id="9bc4f-218">You can now add the `static` modifier to local functions to ensure that local function doesn't capture (reference) any variables from the enclosing scope.</span></span> <span data-ttu-id="9bc4f-219">Dadurch wird `CS8421` erzeugt: „Eine statische lokale Funktion kann keine Referenz auf \<variable> enthalten.“</span><span class="sxs-lookup"><span data-stu-id="9bc4f-219">Doing so generates `CS8421`, "A static local function can't contain a reference to \<variable>."</span></span> 

<span data-ttu-id="9bc4f-220">Betrachten Sie folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-220">Consider the following code.</span></span> <span data-ttu-id="9bc4f-221">Die lokale Funktion `LocalFunction` greift auf die Variable `y` zu, die im umschließenden Bereich (die Methode `M`) deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-221">The local function `LocalFunction` accesses the variable `y`, declared in the enclosing scope (the method `M`).</span></span> <span data-ttu-id="9bc4f-222">Daher kann `LocalFunction` nicht mit dem `static`-Modifikator deklariert werden:</span><span class="sxs-lookup"><span data-stu-id="9bc4f-222">Therefore, `LocalFunction` can't be declared with the `static` modifier:</span></span>

```csharp
int M()
{
    int y;
    LocalFunction();
    return y;

    void LocalFunction() => y = 0;
}
```

<span data-ttu-id="9bc4f-223">Der folgende Code enthält eine statische lokale Funktion.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-223">The following code contains a static local function.</span></span> <span data-ttu-id="9bc4f-224">Er kann statisch sein, da er nicht auf Variablen im umschließenden Bereich zugreift:</span><span class="sxs-lookup"><span data-stu-id="9bc4f-224">It can be static because it doesn't access any variables in the enclosing scope:</span></span>

```csharp
int M()
{
    int y = 5;
    int x = 7;
    return Add(x, y);

    static int Add(int left, int right) => left + right;
}
```

## <a name="disposable-ref-structs"></a><span data-ttu-id="9bc4f-225">Verwerfbare Referenzstrukturen</span><span class="sxs-lookup"><span data-stu-id="9bc4f-225">Disposable ref structs</span></span>

<span data-ttu-id="9bc4f-226">Ein mit dem `ref`-Modifikator deklarierter `struct` darf keine Schnittstellen und damit auch keine <xref:System.IDisposable> implementieren.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-226">A `struct` declared with the `ref` modifier may not implement any interfaces and so cannot implement <xref:System.IDisposable>.</span></span> <span data-ttu-id="9bc4f-227">Aus diesem Grund Aktivieren einer `ref struct` um verworfen werden, muss eine zugängliche `void Dispose()` Methode.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-227">Therefore, to enable a `ref struct` to be disposed, it must have an accessible `void Dispose()` method.</span></span> <span data-ttu-id="9bc4f-228">Dies gilt auch für `readonly ref struct`-Deklarationen.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-228">This also applies to `readonly ref struct` declarations.</span></span>

## <a name="nullable-reference-types"></a><span data-ttu-id="9bc4f-229">Nullwerte zulassende Verweistypen</span><span class="sxs-lookup"><span data-stu-id="9bc4f-229">Nullable reference types</span></span>

<span data-ttu-id="9bc4f-230">In einem Nullwerte zulassenden Anmerkungskontext, wird jede Variable eines Referenztyps als **keine Nullwerte zulassender Referenztyp** betrachtet.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-230">Inside a nullable annotation context, any variable of a reference type is considered to be a **nonnullable reference type**.</span></span> <span data-ttu-id="9bc4f-231">Wenn Sie angeben möchten, dass eine Variable Null sein kann, müssen Sie den Typnamen mit `?` ergänzen, um die Variable als **keine Nullwerte zulassenden Verweistyp** zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-231">If you want to indicate that a variable may be null, you must append the type name with the `?` to declare the variable as a **nullable reference type**.</span></span>

<span data-ttu-id="9bc4f-232">Wenn der Verweistyp keine Nullwerte zulässt, verwendet der Compiler die Flussanalyse, um sicherzustellen, dass lokale Variablen bei der Deklaration auf einen Nicht-Null-Wert initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-232">For nonnullable reference types, the compiler uses flow analysis to ensure that local variables are initialized to a non-null value when declared.</span></span> <span data-ttu-id="9bc4f-233">Felder müssen während der Erstellung initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-233">Fields must be initialized during construction.</span></span> <span data-ttu-id="9bc4f-234">Der Compiler erzeugt eine Warnung, wenn die Variable nicht durch einen Aufruf eines der verfügbaren Konstruktoren oder durch einen Initialisierer festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-234">The compiler generates a warning if the variable is not set by a call to any of the available constructors or by an initializer.</span></span> <span data-ttu-id="9bc4f-235">Darüber hinaus kann Verweistypen, die keine Nullwerte zulassen, kein Wert zugewiesen werden, der Null sein könnte.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-235">Furthermore, nonnullable reference types can't be assigned a value that could be null.</span></span>

<span data-ttu-id="9bc4f-236">Verweistypen, die keine Nullwerte zulassen werden nicht überprüft, um sicherzustellen, dass sie nicht mit Null belegt oder initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-236">Nullable reference types aren't checked to ensure they aren't assigned or initialized to null.</span></span> <span data-ttu-id="9bc4f-237">Der Compiler verwendet jedoch die Flussanalyse, um sicherzustellen, dass jede Variable eines Verweistypen, der Nullwerte zulässt, gegen null geprüft wird, bevor auf sie zugegriffen oder einem nicht Verweistypen zugewiesen wird, der Nullwerte zulässt.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-237">However, the compiler uses flow analysis to ensure that any variable of a nullable reference type is checked against null before it's accessed or assigned to a nonnullable reference type.</span></span>

<span data-ttu-id="9bc4f-238">Mehr über die Funktion erfahren Sie in der Übersicht der [Verweistypen, die Nullwerte zulassen](../nullable-references.md).</span><span class="sxs-lookup"><span data-stu-id="9bc4f-238">You can learn more about the feature in the overview of [nullable reference types](../nullable-references.md).</span></span> <span data-ttu-id="9bc4f-239">Probieren Sie es selbst in einer neuen Anwendung in diesem [Tutorial für Verweistypen, die Nullwerte zulassen](../tutorials/nullable-reference-types.md) aus.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-239">Try it yourself in a new application in this [nullable reference types tutorial](../tutorials/nullable-reference-types.md).</span></span> <span data-ttu-id="9bc4f-240">Weitere Informationen über die Schritte zur Migration einer bestehenden Codebasis, um Verweistypen zu nutzen, die Nullwerte zulassen, finden Sie im Tutorial [Migration einer Anwendung zur Verwendung Nullwerte zulassenden Verweistypen](../tutorials/upgrade-to-nullable-references.md).</span><span class="sxs-lookup"><span data-stu-id="9bc4f-240">Learn about the steps to migrate an existing codebase to make use of nullable reference types in the [migrating an application to use nullable reference types tutorial](../tutorials/upgrade-to-nullable-references.md).</span></span>

## <a name="asynchronous-streams"></a><span data-ttu-id="9bc4f-241">Asynchrone Streams</span><span class="sxs-lookup"><span data-stu-id="9bc4f-241">Asynchronous streams</span></span>

<span data-ttu-id="9bc4f-242">Ab C# 8.0 können Sie Streams asynchron erstellen und nutzen.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-242">Starting with C# 8.0, you can create and consume streams asynchronously.</span></span> <span data-ttu-id="9bc4f-243">Eine Methode, die einen asynchronen Stream zurückgibt, hat drei Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="9bc4f-243">A method that returns an asynchronous stream has three properties:</span></span>

1. <span data-ttu-id="9bc4f-244">Die Deklaration erfolgte mit dem `async`-Modifikator.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-244">It's declared with the `async` modifier.</span></span>
1. <span data-ttu-id="9bc4f-245">Es wird <xref:System.Collections.Generic.IAsyncEnumerable%601> zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-245">It returns an <xref:System.Collections.Generic.IAsyncEnumerable%601>.</span></span>
1. <span data-ttu-id="9bc4f-246">Das Verfahren enthält `yield return`-Anweisungen, um aufeinanderfolgende Elemente im asynchronen Stream zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-246">The method contains `yield return` statements to return successive elements in the asynchronous stream.</span></span>

<span data-ttu-id="9bc4f-247">Die Verwendung eines asynchronen Streams erfordert, dass Sie das Schlüsselwort `await` vor dem Schlüsselwort `foreach` hinzufügen, wenn Sie die Elemente des Streams auflisten.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-247">Consuming an asynchronous stream requires you to add the `await` keyword before the `foreach` keyword when you enumerate the elements of the stream.</span></span> <span data-ttu-id="9bc4f-248">Das Hinzufügen des Schlüsselwortes `await` erfordert, dass die Methode, die den asynchronen Strom enumiert, mit dem Modifikator `async` deklariert wird und einen für eine `async`-Methode zulässigen Typ zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-248">Adding the `await` keyword requires the method that enumerates the asynchronous stream to be declared with the `async` modifier and to return a type allowed for an `async` method.</span></span> <span data-ttu-id="9bc4f-249">In der Regel ist dies die Rückgabe von <xref:System.Threading.Tasks.Task> oder <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-249">Typically that means returning a <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="9bc4f-250">Es kann auch <xref:System.Threading.Tasks.ValueTask> oder <xref:System.Threading.Tasks.ValueTask%601> sein.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-250">It can also be a <xref:System.Threading.Tasks.ValueTask> or <xref:System.Threading.Tasks.ValueTask%601>.</span></span> <span data-ttu-id="9bc4f-251">Eine Methode kann einen asynchronen Stream sowohl verwenden als auch erzeugen, was bedeutet, dass sie <xref:System.Collections.Generic.IAsyncEnumerable%601> zurückgeben würde.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-251">A method can both consume and produce an asynchronous stream, which means it would return an <xref:System.Collections.Generic.IAsyncEnumerable%601>.</span></span> <span data-ttu-id="9bc4f-252">Der folgende Code erzeugt eine Sequenz von 0 bis 19 und wartet 100 ms zwischen der Generierung jeder Zahl:</span><span class="sxs-lookup"><span data-stu-id="9bc4f-252">The following code generates a sequence from 0 to 19, waiting 100 ms between generating each number:</span></span>

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

<span data-ttu-id="9bc4f-253">Die Enumeration der Sequenz erfolgt mit der `await foreach`-Anweisung:</span><span class="sxs-lookup"><span data-stu-id="9bc4f-253">You would enumerate the sequence using the `await foreach` statement:</span></span>

```csharp
await foreach (var number in GenerateSequence())
{
    Console.WriteLine(number);
}
```

<span data-ttu-id="9bc4f-254">Sie können asynchrone Streams selbst in unserem Tutorial zum [Erstellen und Verwenden von asynchronen Streams](../tutorials/generate-consume-asynchronous-stream.md) ausprobieren.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-254">You can try asynchronous streams yourself in our tutorial on [creating and consuming async streams](../tutorials/generate-consume-asynchronous-stream.md).</span></span>

## <a name="indices-and-ranges"></a><span data-ttu-id="9bc4f-255">Indizes und Bereiche</span><span class="sxs-lookup"><span data-stu-id="9bc4f-255">Indices and ranges</span></span>

<span data-ttu-id="9bc4f-256">Bereiche und Indizes bieten eine prägnante Syntax zur Angabe von Teilbereichen in einem Array, einer [Zeichenfolge](../language-reference/builtin-types/reference-types.md#the-string-type), <xref:System.Span%601> oder <xref:System.ReadOnlySpan%601>.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-256">Ranges and indices provide a succinct syntax for specifying subranges in an array, [string](../language-reference/builtin-types/reference-types.md#the-string-type), <xref:System.Span%601>, or <xref:System.ReadOnlySpan%601>.</span></span>

<span data-ttu-id="9bc4f-257">Diese Sprachunterstützung basiert auf zwei neuen Typen und zwei neuen Operatoren:</span><span class="sxs-lookup"><span data-stu-id="9bc4f-257">This language support relies on two new types, and two new operators:</span></span>

- <span data-ttu-id="9bc4f-258"><xref:System.Index?displayProperty=nameWithType>: Stellt einen Index in einer Sequenz dar.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-258"><xref:System.Index?displayProperty=nameWithType> represents an index into a sequence.</span></span>
- <span data-ttu-id="9bc4f-259">Der `^`-Operator, der angibt, dass ein Index relativ zum Ende der Sequenz ist.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-259">The `^` operator, which specifies that an index is relative to the end of the sequence.</span></span>
- <span data-ttu-id="9bc4f-260"><xref:System.Range?displayProperty=nameWithType>: Stellt einen Unterbereich einer Sequenz dar.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-260"><xref:System.Range?displayProperty=nameWithType> represents a sub range of a sequence.</span></span>
- <span data-ttu-id="9bc4f-261">Der Bereichsoperator (`..`), die den Beginn und das Ende eines Bereichs als Operanden angibt.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-261">The Range operator (`..`), which specifies the start and end of a range as its operands.</span></span>

<span data-ttu-id="9bc4f-262">Beginnen wir mit den Regeln für Indizes.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-262">Let's start with the rules for indexes.</span></span> <span data-ttu-id="9bc4f-263">Betrachten Sie einen Array `sequence`.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-263">Consider an array `sequence`.</span></span> <span data-ttu-id="9bc4f-264">Der `0`-Index entspricht `sequence[0]`.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-264">The `0` index is the same as `sequence[0]`.</span></span> <span data-ttu-id="9bc4f-265">Der `^0`-Index entspricht `sequence[sequence.Length]`.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-265">The `^0` index is the same as `sequence[sequence.Length]`.</span></span> <span data-ttu-id="9bc4f-266">Beachten Sie, dass `sequence[^0]` genau wie `sequence[sequence.Length]` eine Ausnahme auslöst.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-266">Note that `sequence[^0]` does throw an exception, just as `sequence[sequence.Length]` does.</span></span> <span data-ttu-id="9bc4f-267">Für eine beliebige Zahl `n` ist der Index `^n` identisch mit `sequence.Length - n`.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-267">For any number `n`, the index `^n` is the same as `sequence.Length - n`.</span></span>

<span data-ttu-id="9bc4f-268">Ein Bereich gibt den *Beginn* und das *Ende* eines Bereichs an.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-268">A range specifies the *start* and *end* of a range.</span></span> <span data-ttu-id="9bc4f-269">Der Beginn des Bereichs ist inklusiv, das Ende des Bereichs ist jedoch exklusiv. Das bedeutet dass der *Beginn* im Bereich enthalten ist, das *Ende* aber nicht.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-269">The start of the range is inclusive, but the end of the range is exclusive, meaning the *start* is included in the range but the *end* is not included in the range.</span></span> <span data-ttu-id="9bc4f-270">Der Bereich `[0..^0]` stellt ebenso wie `[0..sequence.Length]` den gesamten Bereich dar.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-270">The range `[0..^0]` represents the entire range, just as `[0..sequence.Length]` represents the entire range.</span></span> 

<span data-ttu-id="9bc4f-271">Schauen wir uns einige Beispiele an.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-271">Let's look at a few examples.</span></span> <span data-ttu-id="9bc4f-272">Betrachten Sie das folgende Array, kommentiert mit seinem Index „from the start“ und „from the end“:</span><span class="sxs-lookup"><span data-stu-id="9bc4f-272">Consider the following array, annotated with its index from the start and from the end:</span></span>

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

<span data-ttu-id="9bc4f-273">Sie können das letzte Wort mit dem `^1`-Index abrufen:</span><span class="sxs-lookup"><span data-stu-id="9bc4f-273">You can retrieve the last word with the `^1` index:</span></span>

```csharp
Console.WriteLine($"The last word is {words[^1]}");
// writes "dog"
```

<span data-ttu-id="9bc4f-274">Der folgende Code erzeugt einen Teilbereich mit den Worten „quick“, „brown“ und „fox“.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-274">The following code creates a subrange with the words "quick", "brown", and "fox".</span></span> <span data-ttu-id="9bc4f-275">Er enthält `words[1]` bis `words[3]`.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-275">It includes `words[1]` through `words[3]`.</span></span> <span data-ttu-id="9bc4f-276">Das Element `words[4]` gehört nicht zum Bereich.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-276">The element `words[4]` is not in the range.</span></span>

```csharp
var quickBrownFox = words[1..4];
```

<span data-ttu-id="9bc4f-277">Der folgende Code erzeugt einen Teilbereich mit „lazy“ und „dog“.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-277">The following code creates a subrange with "lazy" and "dog".</span></span> <span data-ttu-id="9bc4f-278">Dazu gehören `words[^2]` und `words[^1]`.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-278">It includes `words[^2]` and `words[^1]`.</span></span> <span data-ttu-id="9bc4f-279">Der Endindex `words[^0]` ist nicht enthalten:</span><span class="sxs-lookup"><span data-stu-id="9bc4f-279">The end index `words[^0]` is not included:</span></span>

```csharp
var lazyDog = words[^2..^0];
```

<span data-ttu-id="9bc4f-280">Die folgenden Beispiele erstellen Bereiche, die am Anfang, am Ende und auf beiden Seiten offen sind:</span><span class="sxs-lookup"><span data-stu-id="9bc4f-280">The following examples create ranges that are open ended for the start, end, or both:</span></span>

```csharp
var allWords = words[..]; // contains "The" through "dog".
var firstPhrase = words[..4]; // contains "The" through "fox"
var lastPhrase = words[6..]; // contains "the", "lazy" and "dog"
```

<span data-ttu-id="9bc4f-281">Sie können Bereiche auch als Variablen deklarieren:</span><span class="sxs-lookup"><span data-stu-id="9bc4f-281">You can also declare ranges as variables:</span></span>

```csharp
Range phrase = 1..4;
```

<span data-ttu-id="9bc4f-282">Der Bereich kann dann innerhalb der Zeichen `[` und `]` verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="9bc4f-282">The range can then be used inside the `[` and `]` characters:</span></span>

```csharp
var text = words[phrase];
```

<span data-ttu-id="9bc4f-283">Weitere Informationen zu Indizes und Bereichen finden Sie im Tutorial zu [Indizes und Bereichen](../tutorials/ranges-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="9bc4f-283">You can explore more about indices and ranges in the tutorial on [indices and ranges](../tutorials/ranges-indexes.md).</span></span>

## <a name="null-coalescing-assignment"></a><span data-ttu-id="9bc4f-284">NULL-Coalescing-Zuweisung</span><span class="sxs-lookup"><span data-stu-id="9bc4f-284">Null-coalescing assignment</span></span>

<span data-ttu-id="9bc4f-285">In C# 8.0 wird der NULL-Coalescing-Zuweisungsoperator `??=` eingeführt.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-285">C# 8.0 introduces the null-coalescing assignment operator `??=`.</span></span> <span data-ttu-id="9bc4f-286">Sie können den `??=`-Operator verwenden, um den Wert des rechten Operanden dem linken Operanden nur dann zuzuweisen, wenn die Auswertung des linken Operanden `null` ergibt.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-286">You can use the `??=` operator to assign the value of its right-hand operand to its left-hand operand only if the left-hand operand evaluates to `null`.</span></span>

```csharp
List<int> numbers = null;
int? i = null;

numbers ??= new List<int>();
numbers.Add(i ??= 17);
numbers.Add(i ??= 20);

Console.WriteLine(string.Join(' ', numbers));  // output: 17 17
Console.WriteLine(i);  // output: 17
```

<span data-ttu-id="9bc4f-287">Weitere Informationen finden Sie im Artikel zu den Operatoren [?? und ??=](../language-reference/operators/null-coalescing-operator.md).</span><span class="sxs-lookup"><span data-stu-id="9bc4f-287">For more information, see the [?? and ??= operators](../language-reference/operators/null-coalescing-operator.md) article.</span></span>

## <a name="unmanaged-constructed-types"></a><span data-ttu-id="9bc4f-288">Nicht verwaltete konstruierte Typen</span><span class="sxs-lookup"><span data-stu-id="9bc4f-288">Unmanaged constructed types</span></span>

<span data-ttu-id="9bc4f-289">In C# 7.3 und früher darf ein konstruierter Typ (also ein Typ, der mindestens ein Typargument enthält) kein [nicht verwalteter Typ](../language-reference/builtin-types/unmanaged-types.md) sein.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-289">In C# 7.3 and earlier, a constructed type (a type that includes at least one type argument) cannot be an [unmanaged type](../language-reference/builtin-types/unmanaged-types.md).</span></span> <span data-ttu-id="9bc4f-290">Ab C# 8.0 ist ein konstruierter Werttyp nicht verwaltet, wenn er nur Felder von nicht verwalteten Typen enthält.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-290">Starting with C# 8.0, a constructed value type is unmanaged if it contains fields of unmanaged types only.</span></span>

<span data-ttu-id="9bc4f-291">Ein Beispiel: Ihr Code enthält die folgende Definition des generischen `Coords<T>`-Typs:</span><span class="sxs-lookup"><span data-stu-id="9bc4f-291">For example, given the following definition of the generic `Coords<T>` type:</span></span>

```csharp
public struct Coords<T>
{
    public T X;
    public T Y;
}
```

<span data-ttu-id="9bc4f-292">Dann ist der `Coords<int>`-Typ in C# 8.0 und höher ein nicht verwalteter Typ.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-292">the `Coords<int>` type is an unmanaged type in C# 8.0 and later.</span></span> <span data-ttu-id="9bc4f-293">Wie bei allen nicht verwalteten Typen können Sie einen Zeiger auf eine Variable dieses Typs erstellen oder Instanzen dieses Typs einen [Arbeitsspeicherblock im Stapel zuordnen](../language-reference/operators/stackalloc.md):</span><span class="sxs-lookup"><span data-stu-id="9bc4f-293">Like for any unmanaged type, you can create a pointer to a variable of this type or [allocate a block of memory on the stack](../language-reference/operators/stackalloc.md) for instances of this type:</span></span>

```csharp
Span<Coords<int>> coordinates = stackalloc[]
{
    new Coords<int> { X = 0, Y = 0 },
    new Coords<int> { X = 0, Y = 3 },
    new Coords<int> { X = 4, Y = 0 }
};
```

<span data-ttu-id="9bc4f-294">Weitere Informationen finden Sie unter [Nicht verwaltete Typen](../language-reference/builtin-types/unmanaged-types.md).</span><span class="sxs-lookup"><span data-stu-id="9bc4f-294">For more information, see [Unmanaged types](../language-reference/builtin-types/unmanaged-types.md).</span></span>

## <a name="stackalloc-in-nested-expressions"></a><span data-ttu-id="9bc4f-295">„stackalloc“ in geschachtelten Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="9bc4f-295">stackalloc in nested expressions</span></span>

<span data-ttu-id="9bc4f-296">Ab C# 8.0 können Sie, wenn das Ergebnis eines [stackalloc](../language-reference/operators/stackalloc.md)-Ausdrucks vom Typ <xref:System.Span%601?displayProperty=nameWithType> oder <xref:System.ReadOnlySpan%601?displayProperty=nameWithType> ist, den `stackalloc`-Ausdruck in anderen Ausdrücken verwenden:</span><span class="sxs-lookup"><span data-stu-id="9bc4f-296">Starting with C# 8.0, if the result of a [stackalloc](../language-reference/operators/stackalloc.md) expression is of the <xref:System.Span%601?displayProperty=nameWithType> or <xref:System.ReadOnlySpan%601?displayProperty=nameWithType> type, you can use the `stackalloc` expression in other expressions:</span></span>

```csharp
Span<int> numbers = stackalloc[] { 1, 2, 3, 4, 5, 6 };
var ind = numbers.IndexOfAny(stackalloc[] { 2, 4, 6 ,8 });
Console.WriteLine(ind);  // output: 1
```

## <a name="enhancement-of-interpolated-verbatim-strings"></a><span data-ttu-id="9bc4f-297">Erweiterung von interpolierten ausführlichen Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="9bc4f-297">Enhancement of interpolated verbatim strings</span></span>

<span data-ttu-id="9bc4f-298">`$`- und `@`-Token in [interpolierten](../language-reference/tokens/interpolated.md) ausführlichen Zeichenfolgen können in beliebiger Reihenfolge vorliegen: sowohl `$@"..."` als auch `@$"..."` sind gültige interpolierte ausführliche Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-298">Order of the `$` and `@` tokens in [interpolated](../language-reference/tokens/interpolated.md) verbatim strings can be any: both `$@"..."` and `@$"..."` are valid interpolated verbatim strings.</span></span> <span data-ttu-id="9bc4f-299">In früheren C#-Versionen musste das Token `$` vor dem Token `@` vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="9bc4f-299">In earlier C# versions, the `$` token must appear before the `@` token.</span></span>
