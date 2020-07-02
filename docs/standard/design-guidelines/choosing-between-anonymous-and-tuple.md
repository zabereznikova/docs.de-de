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
# <a name="choosing-between-anonymous-and-tuple-types"></a>Auswählen zwischen anonymen und Tupeltypen

Wenn Sie den geeigneten Typ auswählen, sollten Sie die Benutzerfreundlichkeit, Leistung und Kompromisse im Vergleich zu anderen Typen berücksichtigen. Anonyme Typen sind seit c# 3,0 verfügbar, während generische <xref:System.Tuple%602?displayProperty=nameWithType> Typen mit .NET Framework 4,0 eingeführt wurden. Seit wurden neue Optionen mit Unterstützung auf Sprachebene eingeführt, wie z <xref:System.ValueTuple%602?displayProperty=nameWithType> . b., wie der Name schon sagt, einen Werttyp mit der Flexibilität anonymer Typen bereitzustellen. In diesem Artikel erfahren Sie, wann es sinnvoll ist, einen Typ über den anderen auszuwählen.

## <a name="usability-and-functionality"></a>Benutzerfreundlichkeit und Funktionalität

Anonyme Typen wurden in c# 3,0 mit LINQ-Ausdrücken (Language-Integrated Query) eingeführt. Mit LINQ projizieren Entwickler häufig Ergebnisse aus Abfragen in anonyme Typen, die einige ausgewählte Eigenschaften aus den Objekten enthalten, mit denen Sie arbeiten. Sehen Sie sich das folgende Beispiel an, das ein Array von-Objekten instanziiert <xref:System.DateTime> und durchläuft, um Sie in einen anonymen Typ mit zwei Eigenschaften zu projizieren.

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

Anonyme Typen werden mit dem-Operator instanziiert [`new`](../../csharp/language-reference/operators/new-operator.md) , und die Eigenschaftsnamen und-Typen werden aus der Deklaration abgeleitet. Wenn zwei oder mehr anonyme Objektinitialisierer in derselben Assembly eine Sequenz von Eigenschaften angeben, die in derselben Reihenfolge vorliegen und dieselben Namen und Typen aufweisen, behandelt der Compiler die Objekte als Instanzen desselben Typs. Sie erhalten die gleichen vom Compiler generierten Typinformationen.

Der vorherige c#-Code Ausschnitt projiziert einen anonymen Typ mit zwei Eigenschaften, ähnlich wie die folgende vom Compiler generierte c#-Klasse:

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

Weitere Informationen finden Sie unter [Anonyme Typen](../../csharp/programming-guide/classes-and-structs/anonymous-types.md). Die gleiche Funktionalität ist mit Tupeln vorhanden, wenn Sie in LINQ-Abfragen projiziert werden, können Sie Eigenschaften in Tupel auswählen. Diese Tupel werden durch die Abfrage durchlaufen, ebenso wie anonyme Typen. Sehen Sie sich nun das folgende Beispiel mit dem an `System.Tuple<string, long>` .

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

Mit macht <xref:System.Tuple%602?displayProperty=nameWithType> die-Instanz nummerierte Element Eigenschaften verfügbar, z `Item1` . b `Item2` . und. Diese Eigenschaftsnamen können das Verständnis der Eigenschaftswerte erschweren, da der Eigenschaftsname nur die Ordinalzahl bereitstellt. Außerdem handelt es sich bei den `System.Tuple` Typen um Verweis `class` Typen. <xref:System.ValueTuple%602?displayProperty=nameWithType>Ist jedoch ein `struct` Werttyp. Der folgende c#-Code Ausschnitt verwendet, `ValueTuple<string, long>` um in zu projizieren. Dabei wird eine Literalsyntax zugewiesen.

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

C# bietet Sprachunterstützung von Tupeln mit dem <xref:System.ValueTuple> Typ und der Semantik für:

- [Tupelzuweisung](../../csharp/tuples.md#assignment-and-tuples)
- [Tupelerstellung](../../csharp/deconstruct.md) (nicht beschränkt auf Tupel)
- [Tupel-Gleichheits Überprüfungen](../../csharp/tuples.md#equality-and-tuples)
- [Tupel-Projektionsinitialisierer](../../csharp/tuples.md#tuple-projection-initializers)

Die vorherigen Beispiele sind jedoch alle funktionell gleichwertig. Es gibt geringfügige Unterschiede bei der Benutzerfreundlichkeit und den zugrunde liegenden Implementierungen.

## <a name="tradeoffs"></a>Kompromisse

Möglicherweise möchten Sie immer <xref:System.ValueTuple> over <xref:System.Tuple> und anonyme Typen verwenden, aber es gibt Kompromisse, die Sie berücksichtigen sollten. Die <xref:System.ValueTuple> Typen sind änderbar, wohingegen jedoch schreibgeschützt <xref:System.Tuple> sind. Anonyme Typen können in Ausdrucks Baumstrukturen verwendet werden, während Tupel nicht möglich sind. In der folgenden Tabelle finden Sie eine Übersicht über die wichtigsten Unterschiede.

### <a name="key-differences"></a>Wichtige Unterschiede

| name                     | Access-Modifizierer | Typ     | Name der benutzerdefinierten Eigenschaft | Unterstützung der Dekonstruktion | Ausdrucks Baumstruktur Unterstützung |
|--------------------------|-----------------|----------|----------------------|------------------------|-------------------------|
| Anonyme Typen          | `internal`      | `class`  | ✔️                   | ❌                     | ✔️                     |
| <xref:System.Tuple>      | `public`        | `class`  | ❌                   | ❌                     | ✔️                     |
| <xref:System.ValueTuple> | `public`        | `struct` | ✔️                   | ✔️                     | ❌                     |

### <a name="serialization"></a>Serialisierung

Ein wichtiger Aspekt bei der Auswahl eines Typs ist, ob er serialisiert werden muss. Unter Serialisierung wird das Konvertieren des Zustands eines Objekts in eine Form verstanden, die erhalten oder transportiert werden kann. Weitere Informationen finden Sie unter [Serialisierung](../../csharp/programming-guide/concepts/serialization/index.md). Wenn die Serialisierung wichtig ist, wird das Erstellen von `class` oder `struct` für anonyme Typen oder Tupeltypen bevorzugt.

## <a name="performance"></a>Leistung

Die Leistung zwischen diesen Typen hängt vom Szenario ab. Die Haupt Auswirkung umfasst den Kompromiss zwischen Zuordnungen und Kopiervorgang. In den meisten Szenarien ist die Auswirkung gering. Wenn schwerwiegenden Auswirkungen entstehen könnten, sollten Sie Messungen durchgeführt werden, um die Entscheidung zu informieren.

## <a name="conclusion"></a>Zusammenfassung

Als Entwickler, der zwischen Tupeln und anonymen Typen wählt, müssen mehrere Faktoren berücksichtigt werden. Wenn Sie in der Regel nicht mit [Ausdrucks Baum](../../csharp/expression-trees.md)Strukturen arbeiten und mit der tupelsyntax vertraut sind, wählen Sie aus, wenn Sie <xref:System.ValueTuple> einen Werttyp mit der Flexibilität zum Benennen von Eigenschaften bereitstellen. Wenn Sie mit Ausdrucks Baumstrukturen arbeiten und Eigenschaften bevorzugen, wählen Sie anonyme Typen aus. Verwenden Sie andernfalls <xref:System.Tuple>.

## <a name="see-also"></a>Weitere Informationen

- [Anonyme Typen](../../csharp/programming-guide/classes-and-structs/anonymous-types.md)
- [Ausdrucksbaumstrukturen](../../csharp/expression-trees.md)
- [Framework-Entwurfsrichtlinien](index.md)
- [Tupeltypen](../../csharp/tuples.md)
- [Richtlinien für den Entwurf von Typen](type.md)
