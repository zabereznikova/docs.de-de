---
title: Auswählen zwischen anonymen Typen und Tupeltypen
description: Informationen zur Auswahl zwischen anonymen Typen und Tupeltypen
ms.date: 07/01/2020
ms.technology: dotnet-standard
ms.openlocfilehash: 24ab770d709b9f3968f4c7fe4b01eb0729dbd751
ms.sourcegitcommit: b6a1869f97a37f11a68c90afde1a520a6887dcbc
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2020
ms.locfileid: "85853984"
---
# <a name="choosing-between-anonymous-and-tuple-types"></a><span data-ttu-id="c060d-103">Auswählen zwischen anonymen Typen und Tupeltypen</span><span class="sxs-lookup"><span data-stu-id="c060d-103">Choosing between anonymous and tuple types</span></span>

<span data-ttu-id="c060d-104">Bei der Auswahl eines Typs müssen Sie die Benutzerfreundlichkeit, Leistung und Nachteile im Vergleich zu anderen Typen berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="c060d-104">Choosing the appropriate type involves considering its usability, performance, and tradeoffs compared to other types.</span></span> <span data-ttu-id="c060d-105">Anonyme Typen sind seit C# 3.0 verfügbar. Generische <xref:System.Tuple%602?displayProperty=nameWithType>-Typen wurden bereits im Rahmen von .NET Framework 4.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="c060d-105">Anonymous types have been available since C# 3.0, while generic <xref:System.Tuple%602?displayProperty=nameWithType> types were introduced with .NET Framework 4.0.</span></span> <span data-ttu-id="c060d-106">Seitdem wurden neue Optionen mit Unterstützung auf Sprachebene hinzugefügt, z. B. <xref:System.ValueTuple%602?displayProperty=nameWithType>. Wie der Name schon sagt, stellt diese Struktur einen Werttyp bereit, der das gleiche Maß an Flexibilität bietet wie anonyme Typen.</span><span class="sxs-lookup"><span data-stu-id="c060d-106">Since then new options have been introduced with language level support, such as <xref:System.ValueTuple%602?displayProperty=nameWithType> - which as the name implies, provide a value type with the flexibility of anonymous types.</span></span> <span data-ttu-id="c060d-107">In diesem Artikel erfahren Sie, wann es sinnvoll ist, bestimmte Typen auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="c060d-107">In this article, you'll learn when it's appropriate to choose one type over the other.</span></span>

## <a name="usability-and-functionality"></a><span data-ttu-id="c060d-108">Benutzerfreundlichkeit und Funktionalität</span><span class="sxs-lookup"><span data-stu-id="c060d-108">Usability and functionality</span></span>

<span data-ttu-id="c060d-109">Anonyme Typen wurden in C# 3.0 mit LINQ-Ausdrücken (Language Integrated Query) eingeführt.</span><span class="sxs-lookup"><span data-stu-id="c060d-109">Anonymous types were introduced in C# 3.0 with Language-Integrated Query (LINQ) expressions.</span></span> <span data-ttu-id="c060d-110">Mit LINQ projizieren Entwickler häufig Ergebnisse aus Abfragen in anonyme Typen, die einige ausgewählte Eigenschaften aus den Objekten enthalten, mit denen sie arbeiten.</span><span class="sxs-lookup"><span data-stu-id="c060d-110">With LINQ, developers often project results from queries into anonymous types that hold a few select properties from the objects they're working with.</span></span> <span data-ttu-id="c060d-111">Sehen Sie sich das folgende Beispiel an, das ein Array von <xref:System.DateTime>-Objekten instanziiert und durchläuft, um diese in einen anonymen Typ mit zwei Eigenschaften zu projizieren.</span><span class="sxs-lookup"><span data-stu-id="c060d-111">Consider the following example, that instantiates an array of <xref:System.DateTime> objects, and iterates through them projecting into an anonymous type with two properties.</span></span>

```csharp-interactive
var dates = new[]
{
    DateTime.UtcNow.AddHours(-1),
    DateTime.UtcNow,
    DateTime.UtcNow.AddHours(1),
};

foreach (var anonymous in
             dates.Select(
                 date => new { Formatted = $"{date:MMM dd, yyyy hh:mm zzz}", date.Ticks }))
{
    Console.WriteLine($"Ticks: {anonymous.Ticks}, formatted: {anonymous.Formatted}");
}
```

<span data-ttu-id="c060d-112">Anonyme Typen werden mithilfe des Operators [`new`](../../csharp/language-reference/operators/new-operator.md) instanziiert, und die Eigenschaftsnamen und -typen werden aus der Deklaration abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="c060d-112">Anonymous types are instantiated by using the [`new`](../../csharp/language-reference/operators/new-operator.md) operator, and the property names and types are inferred from the declaration.</span></span> <span data-ttu-id="c060d-113">Wenn zwei oder mehr anonyme Objektinitialisierer in derselben Assembly eine Sequenz von Eigenschaften angeben, die die gleiche Reihenfolge und die gleichen Namen und Typen aufweisen, behandelt der Compiler die Objekte als Instanzen desselben Typs.</span><span class="sxs-lookup"><span data-stu-id="c060d-113">If two or more anonymous object initializers in the same assembly specify a sequence of properties that are in the same order and that have the same names and types, the compiler treats the objects as instances of the same type.</span></span> <span data-ttu-id="c060d-114">Sie erhalten die gleichen vom Compiler generierten Typinformationen.</span><span class="sxs-lookup"><span data-stu-id="c060d-114">They share the same compiler-generated type information.</span></span>

<span data-ttu-id="c060d-115">Der vorherige C#-Codeausschnitt projiziert einen anonymen Typ mit zwei Eigenschaften, ähnlich der folgenden vom Compiler generierten C#-Klasse:</span><span class="sxs-lookup"><span data-stu-id="c060d-115">The previous C# snippet projects an anonymous type with two properties, much like the following compiler-generated C# class:</span></span>

```csharp
internal sealed class f__AnonymousType0
{
    public string Formatted { get; }
    public long Ticks { get; }

    public f__AnonymousType0(string formatted, long ticks)
    {
        Formatted = formatted;
        Ticks = ticks;
    }
}
```

<span data-ttu-id="c060d-116">Weitere Informationen finden Sie unter [Anonyme Typen](../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="c060d-116">For more information, see [anonymous types](../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span></span> <span data-ttu-id="c060d-117">Dieselben Funktionen stehen auch für Tupeltypen zur Verfügung, wenn diese in LINQ-Abfragen projiziert werden. Sie können dann Eigenschaften in Tupeln auswählen.</span><span class="sxs-lookup"><span data-stu-id="c060d-117">The same functionality exists with tuples when projecting into LINQ queries, you can select properties into tuples.</span></span> <span data-ttu-id="c060d-118">Diese Tupel verlaufen genauso durch die Abfrage wie anonyme Typen.</span><span class="sxs-lookup"><span data-stu-id="c060d-118">These tuples flow through the query, just as anonymous types would.</span></span> <span data-ttu-id="c060d-119">Sehen Sie sich nun das folgende Beispiel an, in dem `System.Tuple<string, long>` verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c060d-119">Now consider the following example using the `System.Tuple<string, long>`.</span></span>

```csharp-interactive
var dates = new[]
{
    DateTime.UtcNow.AddHours(-1),
    DateTime.UtcNow,
    DateTime.UtcNow.AddHours(1),
};

foreach (var tuple in
            dates.Select(
                date => new Tuple<string, long>($"{date:MMM dd, yyyy hh:mm zzz}", date.Ticks)))
{
    Console.WriteLine($"Ticks: {tuple.Item2}, formatted: {tuple.Item1}");
}
```

<span data-ttu-id="c060d-120">Bei <xref:System.Tuple%602?displayProperty=nameWithType> macht die Instanz nummerierte Elementeigenschaften verfügbar, z. B. `Item1` und `Item2`.</span><span class="sxs-lookup"><span data-stu-id="c060d-120">With the <xref:System.Tuple%602?displayProperty=nameWithType>, the instance exposes numbered item properties, such as `Item1`, and `Item2`.</span></span> <span data-ttu-id="c060d-121">Durch diese Eigenschaftsnamen kann es schwieriger werden, die Absicht der Eigenschaftswerte nachzuvollziehen, da der Eigenschaftsname nur die Ordnungszahl bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="c060d-121">These property names can make it more difficult to understand the intent of the property values, as the property name only provides the ordinal.</span></span> <span data-ttu-id="c060d-122">Außerdem handelt es sich bei den `System.Tuple`-Typen um Verweistypen für `class`.</span><span class="sxs-lookup"><span data-stu-id="c060d-122">Furthermore, the `System.Tuple` types are reference `class` types.</span></span> <span data-ttu-id="c060d-123">Bei <xref:System.ValueTuple%602?displayProperty=nameWithType> handelt es sich jedoch um einen `struct`-Werttyp.</span><span class="sxs-lookup"><span data-stu-id="c060d-123">The <xref:System.ValueTuple%602?displayProperty=nameWithType> however, is a value `struct` type.</span></span> <span data-ttu-id="c060d-124">Im folgenden C#-Codeausschnitt wird `ValueTuple<string, long>` als Ziel für die Projektion verwendet.</span><span class="sxs-lookup"><span data-stu-id="c060d-124">The following C# snippet, uses `ValueTuple<string, long>` to project into.</span></span> <span data-ttu-id="c060d-125">Dabei wird eine Literalsyntax zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="c060d-125">In doing so, it assigns using a literal syntax.</span></span>

```csharp-interactive
var dates = new[]
{
    DateTime.UtcNow.AddHours(-1),
    DateTime.UtcNow,
    DateTime.UtcNow.AddHours(1),
};

foreach (var (formatted, ticks) in
            dates.Select(
                date => (Formatted: $"{date:MMM dd, yyyy at hh:mm zzz}", date.Ticks)))
{
    Console.WriteLine($"Ticks: {ticks}, formatted: {formatted}");
}
```

<span data-ttu-id="c060d-126">C# bietet Sprachunterstützung für Tupel vom Typ <xref:System.ValueTuple> und der Semantik für:</span><span class="sxs-lookup"><span data-stu-id="c060d-126">C# provides language support of tuples with the <xref:System.ValueTuple> type, and semantics for:</span></span>

- [<span data-ttu-id="c060d-127">Tupelzuweisung</span><span class="sxs-lookup"><span data-stu-id="c060d-127">Tuple assignment</span></span>](../../csharp/tuples.md#assignment-and-tuples)
- <span data-ttu-id="c060d-128">[Tupeldekonstruktion](../../csharp/deconstruct.md) (nicht auf Tupel beschränkt)</span><span class="sxs-lookup"><span data-stu-id="c060d-128">[Tuple deconstruction](../../csharp/deconstruct.md) (not limited to tuples)</span></span>
- [<span data-ttu-id="c060d-129">Gleichheitsüberprüfungen für Tupel</span><span class="sxs-lookup"><span data-stu-id="c060d-129">Tuple equality checks</span></span>](../../csharp/tuples.md#equality-and-tuples)
- [<span data-ttu-id="c060d-130">Tupelprojektionsinitialisierer</span><span class="sxs-lookup"><span data-stu-id="c060d-130">Tuple projection initializers</span></span>](../../csharp/tuples.md#tuple-projection-initializers)

<span data-ttu-id="c060d-131">Die vorherigen Beispiele sind jedoch alle in ihren Funktionen gleichwertig. Es gibt nur geringfügige Unterschiede bei der Benutzerfreundlichkeit und den zugrunde liegenden Implementierungen.</span><span class="sxs-lookup"><span data-stu-id="c060d-131">The previous examples are all functionally equivalent, however; there are slight differences in their usability and their underlying implementations.</span></span>

## <a name="tradeoffs"></a><span data-ttu-id="c060d-132">Kompromisse</span><span class="sxs-lookup"><span data-stu-id="c060d-132">Tradeoffs</span></span>

<span data-ttu-id="c060d-133">Möglicherweise möchten Sie immer <xref:System.ValueTuple> anstelle von <xref:System.Tuple> und anonyme Typen verwenden, aber dies kann Nachteile haben, die Sie berücksichtigen sollten.</span><span class="sxs-lookup"><span data-stu-id="c060d-133">You might want to always use <xref:System.ValueTuple> over <xref:System.Tuple>, and anonymous types, but there are tradeoffs you should consider.</span></span> <span data-ttu-id="c060d-134">Die <xref:System.ValueTuple>-Typen sind änderbar, während <xref:System.Tuple>-Typen schreibgeschützt sind.</span><span class="sxs-lookup"><span data-stu-id="c060d-134">The <xref:System.ValueTuple> types are mutable, whereas <xref:System.Tuple> are read-only.</span></span> <span data-ttu-id="c060d-135">Anonyme Typen können in Ausdrucksbaumstrukturen verwendet werden. Tupel eignen sich nicht dafür.</span><span class="sxs-lookup"><span data-stu-id="c060d-135">Anonymous types can be used in expression trees, while tuples cannot.</span></span> <span data-ttu-id="c060d-136">In der folgenden Tabelle finden Sie eine Übersicht über die wichtigsten Unterschiede.</span><span class="sxs-lookup"><span data-stu-id="c060d-136">The following table is an overview of some of the key differences.</span></span>

### <a name="key-differences"></a><span data-ttu-id="c060d-137">Wesentliche Unterschiede</span><span class="sxs-lookup"><span data-stu-id="c060d-137">Key differences</span></span>

| <span data-ttu-id="c060d-138">name</span><span class="sxs-lookup"><span data-stu-id="c060d-138">Name</span></span>                     | <span data-ttu-id="c060d-139">Zugriffsmodifizierer</span><span class="sxs-lookup"><span data-stu-id="c060d-139">Access modifier</span></span> | <span data-ttu-id="c060d-140">Typ</span><span class="sxs-lookup"><span data-stu-id="c060d-140">Type</span></span>     | <span data-ttu-id="c060d-141">Benutzerdefinierter Eigenschaftenname</span><span class="sxs-lookup"><span data-stu-id="c060d-141">Custom property name</span></span> | <span data-ttu-id="c060d-142">Unterstützung der Dekonstruktion</span><span class="sxs-lookup"><span data-stu-id="c060d-142">Deconstruction support</span></span> | <span data-ttu-id="c060d-143">Unterstützung der Ausdrucksbaumstruktur</span><span class="sxs-lookup"><span data-stu-id="c060d-143">Expression tree support</span></span> |
|--------------------------|-----------------|----------|----------------------|------------------------|-------------------------|
| <span data-ttu-id="c060d-144">Anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="c060d-144">Anonymous types</span></span>          | `internal`      | `class`  | <span data-ttu-id="c060d-145">✔️</span><span class="sxs-lookup"><span data-stu-id="c060d-145">✔️</span></span>                   | ❌                     | <span data-ttu-id="c060d-146">✔️</span><span class="sxs-lookup"><span data-stu-id="c060d-146">✔️</span></span>                     |
| <xref:System.Tuple>      | `public`        | `class`  | ❌                   | ❌                     | <span data-ttu-id="c060d-147">✔️</span><span class="sxs-lookup"><span data-stu-id="c060d-147">✔️</span></span>                     |
| <xref:System.ValueTuple> | `public`        | `struct` | <span data-ttu-id="c060d-148">✔️</span><span class="sxs-lookup"><span data-stu-id="c060d-148">✔️</span></span>                   | <span data-ttu-id="c060d-149">✔️</span><span class="sxs-lookup"><span data-stu-id="c060d-149">✔️</span></span>                     | ❌                     |

### <a name="serialization"></a><span data-ttu-id="c060d-150">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="c060d-150">Serialization</span></span>

<span data-ttu-id="c060d-151">Bei der Typauswahl muss unbedingt berücksichtigt werden, ob der Typ serialisiert werden muss.</span><span class="sxs-lookup"><span data-stu-id="c060d-151">One important consideration when choosing a type, is whether or not it will need to be serialized.</span></span> <span data-ttu-id="c060d-152">Unter Serialisierung wird das Konvertieren des Zustands eines Objekts in eine Form verstanden, die erhalten oder transportiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="c060d-152">Serialization is the process of converting the state of an object into a form that can be persisted or transported.</span></span> <span data-ttu-id="c060d-153">Weitere Informationen finden Sie unter [Serialisierung](../../csharp/programming-guide/concepts/serialization/index.md).</span><span class="sxs-lookup"><span data-stu-id="c060d-153">For more information, see [serialization](../../csharp/programming-guide/concepts/serialization/index.md).</span></span> <span data-ttu-id="c060d-154">Wenn die Serialisierung wichtig ist, sollten Sie eher einen `class`- oder `struct`-Typ erstellen anstatt anonyme Typen oder Tupeltypen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="c060d-154">When serialization is important, creating a `class` or `struct` is preferred over anonymous types or tuple types.</span></span>

## <a name="performance"></a><span data-ttu-id="c060d-155">Leistung</span><span class="sxs-lookup"><span data-stu-id="c060d-155">Performance</span></span>

<span data-ttu-id="c060d-156">Die Leistung der einzelnen Typen unterscheidet sich je nach Szenario.</span><span class="sxs-lookup"><span data-stu-id="c060d-156">Performance between these types depends on the scenario.</span></span> <span data-ttu-id="c060d-157">Insbesondere müssen bei Zuweisungs- und Kopiervorgängen Kompromisse eingegangen werden.</span><span class="sxs-lookup"><span data-stu-id="c060d-157">The major impact involves the tradeoff between allocations and copying.</span></span> <span data-ttu-id="c060d-158">In den meisten Szenarios sind die Auswirkungen aber gering.</span><span class="sxs-lookup"><span data-stu-id="c060d-158">In most scenarios, the impact is small.</span></span> <span data-ttu-id="c060d-159">Wenn schwerwiegenden Auswirkungen entstehen könnten, sollten Sie entsprechende Maßnahmen ergreifen, um eine fundierte Entscheidung zu treffen.</span><span class="sxs-lookup"><span data-stu-id="c060d-159">When major impacts could arise, measurements should be taken to inform the decision.</span></span>

## <a name="conclusion"></a><span data-ttu-id="c060d-160">Schlussbemerkung</span><span class="sxs-lookup"><span data-stu-id="c060d-160">Conclusion</span></span>

<span data-ttu-id="c060d-161">Wenn Sie als Entwickler zwischen Tupeln und anonymen Typen auswählen müssen, sollten Sie verschiedene Faktoren berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="c060d-161">As a developer choosing between tuples and anonymous types, there are several factors to consider.</span></span> <span data-ttu-id="c060d-162">Generell gilt: Wenn Sie nicht mit [Ausdrucksbaumstrukturen](../../csharp/expression-trees.md) arbeiten und sich mit der Tupelsyntax auskennen, wählen Sie <xref:System.ValueTuple>-Typen aus, da diese einen Werttyp bereitstellen und Sie flexibel Eigenschaften benennen können.</span><span class="sxs-lookup"><span data-stu-id="c060d-162">Generally speaking, if you're not working with [expression trees](../../csharp/expression-trees.md), and you're comfortable with tuple syntax then choose <xref:System.ValueTuple> as they provide a value type with the flexibility to name properties.</span></span> <span data-ttu-id="c060d-163">Wenn Sie mit Ausdrucksbaumstrukturen arbeiten und es bevorzugen, Eigenschaften zu benennen, wählen Sie anonyme Typen aus.</span><span class="sxs-lookup"><span data-stu-id="c060d-163">If you're working with expression trees, and you'd prefer to name properties, choose anonymous types.</span></span> <span data-ttu-id="c060d-164">Verwenden Sie andernfalls <xref:System.Tuple>.</span><span class="sxs-lookup"><span data-stu-id="c060d-164">Otherwise, use <xref:System.Tuple>.</span></span>

## <a name="see-also"></a><span data-ttu-id="c060d-165">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c060d-165">See also</span></span>

- [<span data-ttu-id="c060d-166">Anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="c060d-166">Anonymous types</span></span>](../../csharp/programming-guide/classes-and-structs/anonymous-types.md)
- [<span data-ttu-id="c060d-167">Ausdrucksbaumstrukturen</span><span class="sxs-lookup"><span data-stu-id="c060d-167">Expression trees</span></span>](../../csharp/expression-trees.md)
- [<span data-ttu-id="c060d-168">Tupeltypen</span><span class="sxs-lookup"><span data-stu-id="c060d-168">Tuple types</span></span>](../../csharp/tuples.md)
- [<span data-ttu-id="c060d-169">Richtlinien für den Entwurf von Typen</span><span class="sxs-lookup"><span data-stu-id="c060d-169">Type design guidelines</span></span>](../design-guidelines/type.md)
