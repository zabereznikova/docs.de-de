---
title: Auswählen zwischen anonymen Typen und Tupeltypen
description: Informationen zur Auswahl zwischen anonymen Typen und Tupeltypen
author: IEvangelist
ms.author: dapine
ms.date: 07/01/2020
ms.openlocfilehash: f8465b2f22ecfafd739355ddd35635e2eee49232
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94823198"
---
# <a name="choosing-between-anonymous-and-tuple-types"></a>Auswählen zwischen anonymen Typen und Tupeltypen

Bei der Auswahl eines Typs müssen Sie die Benutzerfreundlichkeit, Leistung und Nachteile im Vergleich zu anderen Typen berücksichtigen. Anonyme Typen sind seit C# 3.0 verfügbar. Generische <xref:System.Tuple%602?displayProperty=nameWithType>-Typen wurden bereits im Rahmen von .NET Framework 4.0 eingeführt. Seitdem wurden neue Optionen mit Unterstützung auf Sprachebene hinzugefügt, z. B. <xref:System.ValueTuple%602?displayProperty=nameWithType>. Wie der Name schon sagt, stellt diese Struktur einen Werttyp bereit, der das gleiche Maß an Flexibilität bietet wie anonyme Typen. In diesem Artikel erfahren Sie, wann es sinnvoll ist, bestimmte Typen auszuwählen.

## <a name="usability-and-functionality"></a>Benutzerfreundlichkeit und Funktionalität

Anonyme Typen wurden in C# 3.0 mit LINQ-Ausdrücken (Language Integrated Query) eingeführt. Mit LINQ projizieren Entwickler häufig Ergebnisse aus Abfragen in anonyme Typen, die einige ausgewählte Eigenschaften aus den Objekten enthalten, mit denen sie arbeiten. Sehen Sie sich das folgende Beispiel an, das ein Array von <xref:System.DateTime>-Objekten instanziiert und durchläuft, um diese in einen anonymen Typ mit zwei Eigenschaften zu projizieren.

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

Anonyme Typen werden mithilfe des Operators [`new`](../../csharp/language-reference/operators/new-operator.md) instanziiert, und die Eigenschaftsnamen und -typen werden aus der Deklaration abgeleitet. Wenn zwei oder mehr anonyme Objektinitialisierer in derselben Assembly eine Sequenz von Eigenschaften angeben, die die gleiche Reihenfolge und die gleichen Namen und Typen aufweisen, behandelt der Compiler die Objekte als Instanzen desselben Typs. Sie erhalten die gleichen vom Compiler generierten Typinformationen.

Der vorherige C#-Codeausschnitt projiziert einen anonymen Typ mit zwei Eigenschaften, ähnlich der folgenden vom Compiler generierten C#-Klasse:

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

Weitere Informationen finden Sie unter [Anonyme Typen](../../csharp/programming-guide/classes-and-structs/anonymous-types.md). Dieselben Funktionen stehen auch für Tupeltypen zur Verfügung, wenn diese in LINQ-Abfragen projiziert werden. Sie können dann Eigenschaften in Tupeln auswählen. Diese Tupel verlaufen genauso durch die Abfrage wie anonyme Typen. Sehen Sie sich nun das folgende Beispiel an, in dem `System.Tuple<string, long>` verwendet wird.

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

Bei <xref:System.Tuple%602?displayProperty=nameWithType> macht die Instanz nummerierte Elementeigenschaften verfügbar, z. B. `Item1` und `Item2`. Durch diese Eigenschaftsnamen kann es schwieriger werden, die Absicht der Eigenschaftswerte nachzuvollziehen, da der Eigenschaftsname nur die Ordnungszahl bereitstellt. Außerdem handelt es sich bei den `System.Tuple`-Typen um Verweistypen für `class`. Bei <xref:System.ValueTuple%602?displayProperty=nameWithType> handelt es sich jedoch um einen `struct`-Werttyp. Im folgenden C#-Codeausschnitt wird `ValueTuple<string, long>` als Ziel für die Projektion verwendet. Dabei wird eine Literalsyntax zugewiesen.

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

Weitere Informationen zu Tupeln finden Sie unter [Tupeltypen (C#-Referenz)](../../csharp/language-reference/builtin-types/value-tuples.md) und [Tupel (Visual Basic)](../../visual-basic/programming-guide/language-features/data-types/tuples.md).

Die vorherigen Beispiele sind jedoch alle in ihren Funktionen gleichwertig. Es gibt nur geringfügige Unterschiede bei der Benutzerfreundlichkeit und den zugrunde liegenden Implementierungen.

## <a name="tradeoffs"></a>Kompromisse

Möglicherweise möchten Sie immer <xref:System.ValueTuple> anstelle von <xref:System.Tuple> und anonyme Typen verwenden, aber dies kann Nachteile haben, die Sie berücksichtigen sollten. Die <xref:System.ValueTuple>-Typen sind änderbar, während <xref:System.Tuple>-Typen schreibgeschützt sind. Anonyme Typen können in Ausdrucksbaumstrukturen verwendet werden. Tupel eignen sich nicht dafür. In der folgenden Tabelle finden Sie eine Übersicht über die wichtigsten Unterschiede.

### <a name="key-differences"></a>Wesentliche Unterschiede

| name                     | Zugriffsmodifizierer | Typ     | Benutzerdefinierter Membername | Unterstützung der Dekonstruktion | Unterstützung der Ausdrucksbaumstruktur |
|--------------------------|-----------------|----------|----------------------|------------------------|-------------------------|
| Anonyme Typen          | `internal`      | `class`  | ✔️                   | ❌                     | ✔️                     |
| <xref:System.Tuple>      | `public`        | `class`  | ❌                   | ❌                     | ✔️                     |
| <xref:System.ValueTuple> | `public`        | `struct` | ✔️                   | ✔️                     | ❌                     |

### <a name="serialization"></a>Serialisierung

Bei der Typauswahl muss unbedingt berücksichtigt werden, ob der Typ serialisiert werden muss. Unter Serialisierung wird das Konvertieren des Zustands eines Objekts in eine Form verstanden, die erhalten oder transportiert werden kann. Weitere Informationen finden Sie unter [Serialisierung](../../csharp/programming-guide/concepts/serialization/index.md). Wenn die Serialisierung wichtig ist, sollten Sie eher einen `class`- oder `struct`-Typ erstellen anstatt anonyme Typen oder Tupeltypen zu verwenden.

## <a name="performance"></a>Leistung

Die Leistung der einzelnen Typen unterscheidet sich je nach Szenario. Insbesondere müssen bei Zuweisungs- und Kopiervorgängen Kompromisse eingegangen werden. In den meisten Szenarios sind die Auswirkungen aber gering. Wenn schwerwiegenden Auswirkungen entstehen könnten, sollten Sie entsprechende Maßnahmen ergreifen, um eine fundierte Entscheidung zu treffen.

## <a name="conclusion"></a>Schlussbemerkung

Wenn Sie als Entwickler zwischen Tupeln und anonymen Typen auswählen müssen, sollten Sie verschiedene Faktoren berücksichtigen. Generell gilt: Wenn Sie nicht mit [Ausdrucksbaumstrukturen](../../csharp/expression-trees.md) arbeiten und sich mit der Tupelsyntax auskennen, wählen Sie <xref:System.ValueTuple>-Typen aus, da diese einen Werttyp bereitstellen und Sie flexibel Eigenschaften benennen können. Wenn Sie mit Ausdrucksbaumstrukturen arbeiten und es bevorzugen, Eigenschaften zu benennen, wählen Sie anonyme Typen aus. Verwenden Sie andernfalls <xref:System.Tuple>.

## <a name="see-also"></a>Siehe auch

- [Anonyme Typen](../../csharp/programming-guide/classes-and-structs/anonymous-types.md)
- [Ausdrucksbaumstrukturen](../../csharp/expression-trees.md)
- [Tupeltypen (C#-Referenz)](../../csharp/language-reference/builtin-types/value-tuples.md)
- [Tupel (Visual Basic)](../../visual-basic/programming-guide/language-features/data-types/tuples.md)
- [Richtlinien für den Entwurf von Typen](../design-guidelines/type.md)
