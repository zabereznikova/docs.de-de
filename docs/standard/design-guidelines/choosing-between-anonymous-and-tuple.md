---
title: Auswählen zwischen anonymen und Tupeltypen
description: Informieren Sie sich über die Wahl zwischen anonymen Typen und Tupeltypen.
ms.date: 06/29/2020
ms.technology: dotnet-standard
ms.openlocfilehash: bc17695830a42a6eed9d60c0e097ee9d02a7957e
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85803767"
---
# <a name="choosing-between-anonymous-and-tuple-types"></a><span data-ttu-id="0dc8f-103">Auswählen zwischen anonymen und Tupeltypen</span><span class="sxs-lookup"><span data-stu-id="0dc8f-103">Choosing between anonymous and tuple types</span></span>

<span data-ttu-id="0dc8f-104">Wenn Sie den geeigneten Typ auswählen, sollten Sie die Benutzerfreundlichkeit, Leistung und Kompromisse im Vergleich zu anderen Typen berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="0dc8f-104">Choosing the appropriate type involves considering its usability, performance, and tradeoffs compared to other types.</span></span> <span data-ttu-id="0dc8f-105">Anonyme Typen sind seit c# 3,0 verfügbar, während generische <xref:System.Tuple%602?displayProperty=nameWithType> Typen mit .NET Framework 4,0 eingeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="0dc8f-105">Anonymous types have been available since C# 3.0, while generic <xref:System.Tuple%602?displayProperty=nameWithType> types were introduced with .NET Framework 4.0.</span></span> <span data-ttu-id="0dc8f-106">Seit wurden neue Optionen mit Unterstützung auf Sprachebene eingeführt, wie z <xref:System.ValueTuple%602?displayProperty=nameWithType> . b., wie der Name schon sagt, einen Werttyp mit der Flexibilität anonymer Typen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="0dc8f-106">Since then new options have been introduced with language level support, such as <xref:System.ValueTuple%602?displayProperty=nameWithType> - which as the name implies, provide a value type with the flexibility of anonymous types.</span></span> <span data-ttu-id="0dc8f-107">In diesem Artikel erfahren Sie, wann es sinnvoll ist, einen Typ über den anderen auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="0dc8f-107">In this article, you'll learn when it's appropriate to choose one type over the other.</span></span>

## <a name="usability-and-functionality"></a><span data-ttu-id="0dc8f-108">Benutzerfreundlichkeit und Funktionalität</span><span class="sxs-lookup"><span data-stu-id="0dc8f-108">Usability and functionality</span></span>

<span data-ttu-id="0dc8f-109">Anonyme Typen wurden in c# 3,0 mit LINQ-Ausdrücken (Language-Integrated Query) eingeführt.</span><span class="sxs-lookup"><span data-stu-id="0dc8f-109">Anonymous types were introduced in C# 3.0 with Language-Integrated Query (LINQ) expressions.</span></span> <span data-ttu-id="0dc8f-110">Mit LINQ projizieren Entwickler häufig Ergebnisse aus Abfragen in anonyme Typen, die einige ausgewählte Eigenschaften aus den Objekten enthalten, mit denen Sie arbeiten.</span><span class="sxs-lookup"><span data-stu-id="0dc8f-110">With LINQ, developers often project results from queries into anonymous types that hold a few select properties from the objects they're working with.</span></span> <span data-ttu-id="0dc8f-111">Sehen Sie sich das folgende Beispiel an, das ein Array von-Objekten instanziiert <xref:System.DateTime> und durchläuft, um Sie in einen anonymen Typ mit zwei Eigenschaften zu projizieren.</span><span class="sxs-lookup"><span data-stu-id="0dc8f-111">Consider the following example, that instantiates an array of <xref:System.DateTime> objects, and iterates through them projecting into an anonymous type with two properties.</span></span>

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

<span data-ttu-id="0dc8f-112">Anonyme Typen werden mit dem-Operator instanziiert [`new`](../../csharp/language-reference/operators/new-operator.md) , und die Eigenschaftsnamen und-Typen werden aus der Deklaration abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="0dc8f-112">Anonymous types are instantiated by using the [`new`](../../csharp/language-reference/operators/new-operator.md) operator, and the property names and types are inferred from the declaration.</span></span> <span data-ttu-id="0dc8f-113">Wenn zwei oder mehr anonyme Objektinitialisierer in derselben Assembly eine Sequenz von Eigenschaften angeben, die in derselben Reihenfolge vorliegen und dieselben Namen und Typen aufweisen, behandelt der Compiler die Objekte als Instanzen desselben Typs.</span><span class="sxs-lookup"><span data-stu-id="0dc8f-113">If two or more anonymous object initializers in the same assembly specify a sequence of properties that are in the same order and that have the same names and types, the compiler treats the objects as instances of the same type.</span></span> <span data-ttu-id="0dc8f-114">Sie erhalten die gleichen vom Compiler generierten Typinformationen.</span><span class="sxs-lookup"><span data-stu-id="0dc8f-114">They share the same compiler-generated type information.</span></span>

<span data-ttu-id="0dc8f-115">Der vorherige c#-Code Ausschnitt projiziert einen anonymen Typ mit zwei Eigenschaften, ähnlich wie die folgende vom Compiler generierte c#-Klasse:</span><span class="sxs-lookup"><span data-stu-id="0dc8f-115">The previous C# snippet projects an anonymous type with two properties, much like the following compiler-generated C# class:</span></span>

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

<span data-ttu-id="0dc8f-116">Weitere Informationen finden Sie unter [Anonyme Typen](../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="0dc8f-116">For more information, see [anonymous types](../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span></span> <span data-ttu-id="0dc8f-117">Die gleiche Funktionalität ist mit Tupeln vorhanden, wenn Sie in LINQ-Abfragen projiziert werden, können Sie Eigenschaften in Tupel auswählen.</span><span class="sxs-lookup"><span data-stu-id="0dc8f-117">The same functionality exists with tuples when projecting into LINQ queries, you can select properties into tuples.</span></span> <span data-ttu-id="0dc8f-118">Diese Tupel werden durch die Abfrage durchlaufen, ebenso wie anonyme Typen.</span><span class="sxs-lookup"><span data-stu-id="0dc8f-118">These tuples flow through the query, just as anonymous types would.</span></span> <span data-ttu-id="0dc8f-119">Sehen Sie sich nun das folgende Beispiel mit dem an `System.Tuple<string, long>` .</span><span class="sxs-lookup"><span data-stu-id="0dc8f-119">Now consider the following example using the `System.Tuple<string, long>`.</span></span>

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

<span data-ttu-id="0dc8f-120">Mit macht <xref:System.Tuple%602?displayProperty=nameWithType> die-Instanz nummerierte Element Eigenschaften verfügbar, z `Item1` . b `Item2` . und.</span><span class="sxs-lookup"><span data-stu-id="0dc8f-120">With the <xref:System.Tuple%602?displayProperty=nameWithType>, the instance exposes numbered item properties, such as `Item1`, and `Item2`.</span></span> <span data-ttu-id="0dc8f-121">Diese Eigenschaftsnamen können das Verständnis der Eigenschaftswerte erschweren, da der Eigenschaftsname nur die Ordinalzahl bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="0dc8f-121">These property names can make it more difficult to understand the intent of the property values, as the property name only provides the ordinal.</span></span> <span data-ttu-id="0dc8f-122">Außerdem handelt es sich bei den `System.Tuple` Typen um Verweis `class` Typen.</span><span class="sxs-lookup"><span data-stu-id="0dc8f-122">Furthermore, the `System.Tuple` types are reference `class` types.</span></span> <span data-ttu-id="0dc8f-123"><xref:System.ValueTuple%602?displayProperty=nameWithType>Ist jedoch ein `struct` Werttyp.</span><span class="sxs-lookup"><span data-stu-id="0dc8f-123">The <xref:System.ValueTuple%602?displayProperty=nameWithType> however, is a value `struct` type.</span></span> <span data-ttu-id="0dc8f-124">Der folgende c#-Code Ausschnitt verwendet, `ValueTuple<string, long>` um in zu projizieren.</span><span class="sxs-lookup"><span data-stu-id="0dc8f-124">The following C# snippet, uses `ValueTuple<string, long>` to project into.</span></span> <span data-ttu-id="0dc8f-125">Dabei wird eine Literalsyntax zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="0dc8f-125">In doing so, it assigns using a literal syntax.</span></span>

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

<span data-ttu-id="0dc8f-126">C# bietet Sprachunterstützung von Tupeln mit dem <xref:System.ValueTuple> Typ und der Semantik für:</span><span class="sxs-lookup"><span data-stu-id="0dc8f-126">C# provides language support of tuples with the <xref:System.ValueTuple> type, and semantics for:</span></span>

- [<span data-ttu-id="0dc8f-127">Tupelzuweisung</span><span class="sxs-lookup"><span data-stu-id="0dc8f-127">Tuple assignment</span></span>](../../csharp/tuples.md#assignment-and-tuples)
- <span data-ttu-id="0dc8f-128">[Tupelerstellung](../../csharp/deconstruct.md) (nicht beschränkt auf Tupel)</span><span class="sxs-lookup"><span data-stu-id="0dc8f-128">[Tuple deconstruction](../../csharp/deconstruct.md) (not limited to tuples)</span></span>
- [<span data-ttu-id="0dc8f-129">Tupel-Gleichheits Überprüfungen</span><span class="sxs-lookup"><span data-stu-id="0dc8f-129">Tuple equality checks</span></span>](../../csharp/tuples.md#equality-and-tuples)
- [<span data-ttu-id="0dc8f-130">Tupel-Projektionsinitialisierer</span><span class="sxs-lookup"><span data-stu-id="0dc8f-130">Tuple projection initializers</span></span>](../../csharp/tuples.md#tuple-projection-initializers)

<span data-ttu-id="0dc8f-131">Die vorherigen Beispiele sind jedoch alle funktionell gleichwertig. Es gibt geringfügige Unterschiede bei der Benutzerfreundlichkeit und den zugrunde liegenden Implementierungen.</span><span class="sxs-lookup"><span data-stu-id="0dc8f-131">The previous examples are all functionally equivalent, however; there are slight differences in their usability and their underlying implementations.</span></span>

## <a name="tradeoffs"></a><span data-ttu-id="0dc8f-132">Kompromisse</span><span class="sxs-lookup"><span data-stu-id="0dc8f-132">Tradeoffs</span></span>

<span data-ttu-id="0dc8f-133">Möglicherweise möchten Sie immer <xref:System.ValueTuple> over <xref:System.Tuple> und anonyme Typen verwenden, aber es gibt Kompromisse, die Sie berücksichtigen sollten.</span><span class="sxs-lookup"><span data-stu-id="0dc8f-133">You might want to always use <xref:System.ValueTuple> over <xref:System.Tuple>, and anonymous types, but there are tradeoffs you should consider.</span></span> <span data-ttu-id="0dc8f-134">Die <xref:System.ValueTuple> Typen sind änderbar, wohingegen jedoch schreibgeschützt <xref:System.Tuple> sind.</span><span class="sxs-lookup"><span data-stu-id="0dc8f-134">The <xref:System.ValueTuple> types are mutable, whereas <xref:System.Tuple> are read-only.</span></span> <span data-ttu-id="0dc8f-135">Anonyme Typen können in Ausdrucks Baumstrukturen verwendet werden, während Tupel nicht möglich sind.</span><span class="sxs-lookup"><span data-stu-id="0dc8f-135">Anonymous types can be used in expression trees, while tuples cannot.</span></span> <span data-ttu-id="0dc8f-136">In der folgenden Tabelle finden Sie eine Übersicht über die wichtigsten Unterschiede.</span><span class="sxs-lookup"><span data-stu-id="0dc8f-136">The following table is an overview of some of the key differences.</span></span>

### <a name="key-differences"></a><span data-ttu-id="0dc8f-137">Wichtige Unterschiede</span><span class="sxs-lookup"><span data-stu-id="0dc8f-137">Key differences</span></span>

| <span data-ttu-id="0dc8f-138">name</span><span class="sxs-lookup"><span data-stu-id="0dc8f-138">Name</span></span>                     | <span data-ttu-id="0dc8f-139">Access-Modifizierer</span><span class="sxs-lookup"><span data-stu-id="0dc8f-139">Access modifier</span></span> | <span data-ttu-id="0dc8f-140">Typ</span><span class="sxs-lookup"><span data-stu-id="0dc8f-140">Type</span></span>     | <span data-ttu-id="0dc8f-141">Name der benutzerdefinierten Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="0dc8f-141">Custom property name</span></span> | <span data-ttu-id="0dc8f-142">Unterstützung der Dekonstruktion</span><span class="sxs-lookup"><span data-stu-id="0dc8f-142">Deconstruction support</span></span> | <span data-ttu-id="0dc8f-143">Ausdrucks Baumstruktur Unterstützung</span><span class="sxs-lookup"><span data-stu-id="0dc8f-143">Expression tree support</span></span> |
|--------------------------|-----------------|----------|----------------------|------------------------|-------------------------|
| <span data-ttu-id="0dc8f-144">Anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="0dc8f-144">Anonymous types</span></span>          | `internal`      | `class`  | <span data-ttu-id="0dc8f-145">✔️</span><span class="sxs-lookup"><span data-stu-id="0dc8f-145">✔️</span></span>                   | ❌                     | <span data-ttu-id="0dc8f-146">✔️</span><span class="sxs-lookup"><span data-stu-id="0dc8f-146">✔️</span></span>                     |
| <xref:System.Tuple>      | `public`        | `class`  | ❌                   | ❌                     | <span data-ttu-id="0dc8f-147">✔️</span><span class="sxs-lookup"><span data-stu-id="0dc8f-147">✔️</span></span>                     |
| <xref:System.ValueTuple> | `public`        | `struct` | <span data-ttu-id="0dc8f-148">✔️</span><span class="sxs-lookup"><span data-stu-id="0dc8f-148">✔️</span></span>                   | <span data-ttu-id="0dc8f-149">✔️</span><span class="sxs-lookup"><span data-stu-id="0dc8f-149">✔️</span></span>                     | ❌                     |

### <a name="serialization"></a><span data-ttu-id="0dc8f-150">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="0dc8f-150">Serialization</span></span>

<span data-ttu-id="0dc8f-151">Ein wichtiger Aspekt bei der Auswahl eines Typs ist, ob er serialisiert werden muss.</span><span class="sxs-lookup"><span data-stu-id="0dc8f-151">One important consideration when choosing a type, is whether or not it will need to be serialized.</span></span> <span data-ttu-id="0dc8f-152">Unter Serialisierung wird das Konvertieren des Zustands eines Objekts in eine Form verstanden, die erhalten oder transportiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="0dc8f-152">Serialization is the process of converting the state of an object into a form that can be persisted or transported.</span></span> <span data-ttu-id="0dc8f-153">Weitere Informationen finden Sie unter [Serialisierung](../../csharp/programming-guide/concepts/serialization/index.md).</span><span class="sxs-lookup"><span data-stu-id="0dc8f-153">For more information, see [serialization](../../csharp/programming-guide/concepts/serialization/index.md).</span></span> <span data-ttu-id="0dc8f-154">Wenn die Serialisierung wichtig ist, wird das Erstellen von `class` oder `struct` für anonyme Typen oder Tupeltypen bevorzugt.</span><span class="sxs-lookup"><span data-stu-id="0dc8f-154">When serialization is important, creating a `class` or `struct` is preferred over anonymous types or tuple types.</span></span>

## <a name="performance"></a><span data-ttu-id="0dc8f-155">Leistung</span><span class="sxs-lookup"><span data-stu-id="0dc8f-155">Performance</span></span>

<span data-ttu-id="0dc8f-156">Die Leistung zwischen diesen Typen hängt vom Szenario ab.</span><span class="sxs-lookup"><span data-stu-id="0dc8f-156">Performance between these types depends on the scenario.</span></span> <span data-ttu-id="0dc8f-157">Die Haupt Auswirkung umfasst den Kompromiss zwischen Zuordnungen und Kopiervorgang.</span><span class="sxs-lookup"><span data-stu-id="0dc8f-157">The major impact involves the tradeoff between allocations and copying.</span></span> <span data-ttu-id="0dc8f-158">In den meisten Szenarien ist die Auswirkung gering.</span><span class="sxs-lookup"><span data-stu-id="0dc8f-158">In most scenarios, the impact is small.</span></span> <span data-ttu-id="0dc8f-159">Wenn schwerwiegenden Auswirkungen entstehen könnten, sollten Sie Messungen durchgeführt werden, um die Entscheidung zu informieren.</span><span class="sxs-lookup"><span data-stu-id="0dc8f-159">When major impacts could arise, measurements should be taken to inform the decision.</span></span>

## <a name="conclusion"></a><span data-ttu-id="0dc8f-160">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="0dc8f-160">Conclusion</span></span>

<span data-ttu-id="0dc8f-161">Als Entwickler, der zwischen Tupeln und anonymen Typen wählt, müssen mehrere Faktoren berücksichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="0dc8f-161">As a developer choosing between tuples and anonymous types, there are several factors to consider.</span></span> <span data-ttu-id="0dc8f-162">Wenn Sie in der Regel nicht mit [Ausdrucks Baum](../../csharp/expression-trees.md)Strukturen arbeiten und mit der tupelsyntax vertraut sind, wählen Sie aus, wenn Sie <xref:System.ValueTuple> einen Werttyp mit der Flexibilität zum Benennen von Eigenschaften bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="0dc8f-162">Generally speaking, if you're not working with [expression trees](../../csharp/expression-trees.md), and you're comfortable with tuple syntax then choose <xref:System.ValueTuple> as they provide a value type with the flexibility to name properties.</span></span> <span data-ttu-id="0dc8f-163">Wenn Sie mit Ausdrucks Baumstrukturen arbeiten und Eigenschaften bevorzugen, wählen Sie anonyme Typen aus.</span><span class="sxs-lookup"><span data-stu-id="0dc8f-163">If you're working with expression trees, and you'd prefer to name properties, choose anonymous types.</span></span> <span data-ttu-id="0dc8f-164">Verwenden Sie andernfalls <xref:System.Tuple>.</span><span class="sxs-lookup"><span data-stu-id="0dc8f-164">Otherwise, use <xref:System.Tuple>.</span></span>

## <a name="see-also"></a><span data-ttu-id="0dc8f-165">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0dc8f-165">See also</span></span>

- [<span data-ttu-id="0dc8f-166">Anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="0dc8f-166">Anonymous types</span></span>](../../csharp/programming-guide/classes-and-structs/anonymous-types.md)
- [<span data-ttu-id="0dc8f-167">Ausdrucksbaumstrukturen</span><span class="sxs-lookup"><span data-stu-id="0dc8f-167">Expression trees</span></span>](../../csharp/expression-trees.md)
- [<span data-ttu-id="0dc8f-168">Framework-Entwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="0dc8f-168">Framework design guidelines</span></span>](index.md)
- [<span data-ttu-id="0dc8f-169">Tupeltypen</span><span class="sxs-lookup"><span data-stu-id="0dc8f-169">Tuple types</span></span>](../../csharp/tuples.md)
- [<span data-ttu-id="0dc8f-170">Richtlinien für den Entwurf von Typen</span><span class="sxs-lookup"><span data-stu-id="0dc8f-170">Type design guidelines</span></span>](type.md)
