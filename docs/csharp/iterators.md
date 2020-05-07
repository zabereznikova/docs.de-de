---
title: Iterators
description: Erfahren Sie, wie integrierte C#-Iteratoren verwendet werden und wie Sie eigene benutzerdefinierte Iteratormethoden erstellen können.
ms.date: 06/20/2016
ms.technology: csharp-advanced-concepts
ms.assetid: 5cf36f45-f91a-4fca-a0b7-87f233e108e9
ms.openlocfilehash: efa755c2243c18fb51b653abccb2bfc702bbc055
ms.sourcegitcommit: 1cb64b53eb1f253e6a3f53ca9510ef0be1fd06fe
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/29/2020
ms.locfileid: "82507376"
---
# <a name="iterators"></a>Iterators

Bei fast jedem Programm, das Sie schreiben, muss eine Auflistung durchlaufen werden. Sie schreiben Code, der jedes Element in einer Auflistung überprüft.

Sie erstellen auch Iteratormethoden, die einen Iterator (ein Objekt, das Container und insbesondere Listen durchläuft) für die Elemente dieser Klasse erzeugen. Diese können für Folgendes verwendet werden:

+ Ausführen einer Aktion für jedes Element in einer Auflistung
+ Enumerieren einer benutzerdefinierten Auflistung
+ Erweitern von [LINQ](linq/index.md) oder anderen Bibliotheken
+ Erstellen einer Datenpipeline, in der Daten Iteratormethoden effizient durchlaufen

Die Programmiersprache C# bietet Funktionen für diese beiden Szenarien. Dieser Artikel enthält eine Übersicht über diese Funktionen.

Dieses Tutorial besteht aus vielen Schritten. Sie können die Anwendung nach jedem Schritt ausführen und sich den Fortschritt ansehen. [Hier](https://github.com/dotnet/samples/blob/master/csharp/iterators) können Sie das vollständige Beispiel für dieses Thema anzeigen oder herunterladen. Anweisungen zum Herunterladen finden Sie unter [Beispiele und Lernprogramme](../samples-and-tutorials/index.md#viewing-and-downloading-samples).

## <a name="iterating-with-foreach"></a>Durchlaufen mit foreach

Das Enumerieren einer Auflistung ist einfach: Das `foreach`-Schlüsselwort enumeriert eine Auflistung und führt die eingebettete Anweisung einmal für jedes Element in der Auflistung aus:

```csharp
foreach (var item in collection)
{
   Console.WriteLine(item.ToString());
}
```

Das ist auch schon alles. Für das Durchlaufen aller Inhalte einer Auflistung benötigen Sie nur die `foreach`-Anweisung. Die `foreach`-Anweisung ist jedoch nicht magisch. Sie beruht auf zwei generischen Schnittstellen, die in der .NET Core-Bibliothek definiert sind, um den Code für das Durchlaufen einer Auflistung zu generieren: `IEnumerable<T>` und `IEnumerator<T>`. Dieser Mechanismus wird unten ausführlich erläutert.

Für diese beiden Schnittstellen gibt es auch nicht generische Entsprechungen: `IEnumerable` und `IEnumerator`. Die [generischen](programming-guide/generics/index.md) Versionen werden für modernen Code bevorzugt.

## <a name="enumeration-sources-with-iterator-methods"></a>Enumerationsquellen mit Iteratormethoden

Mit einer weiteren großartigen Funktion der Programmiersprache C# können Sie Methoden konstruieren, die eine Quelle für eine Enumeration erstellen. Diese werden als *Iteratormethoden* bezeichnet. Eine Iteratormethode definiert, wie die Objekte in einer Sequenz bei Anforderung generiert werden. Sie verwenden die `yield return`-Kontextschlüsselwörter, um eine Iteratormethode zu definieren.

Sie könnten diese Methode schreiben, um die Sequenz von ganzen Zahlen von 0 bis 9 zu erstellen:

```csharp
public IEnumerable<int> GetSingleDigitNumbers()
{
    yield return 0;
    yield return 1;
    yield return 2;
    yield return 3;
    yield return 4;
    yield return 5;
    yield return 6;
    yield return 7;
    yield return 8;
    yield return 9;
}
```

Der obige Code zeigt verschiedene `yield return`-Anweisungen, die verdeutlichen, dass Sie mehrere diskrete `yield return`-Anweisungen in einer Iteratormethode verwenden können.
Sie können (und werden auch oft) andere Sprachkonstrukte zur Vereinfachung des Codes einer Iteratormethode verwenden. Die folgende Methodendefinition erzeugt genau dieselbe Sequenz von Zahlen:

```csharp
public IEnumerable<int> GetSingleDigitNumbers()
{
    int index = 0;
    while (index < 10)
        yield return index++;
}
```

Sie müssen sich nicht für eine davon entscheiden. Sie können so viele `yield return`-Anweisungen verwenden wie für Ihre Methode erforderlich:

```csharp
public IEnumerable<int> GetSingleDigitNumbers()
{
    int index = 0;
    while (index < 10)
        yield return index++;

    yield return 50;

    index = 100;
    while (index < 110)
        yield return index++;
}
```

Das ist die grundlegende Syntax. Betrachten wir einen realen Beispielfall, in dem Sie eine Iteratormethode schreiben würden. Angenommen, Sie arbeiten an einem IoT-Projekt und die Gerätesensoren generieren einen sehr großen Datenstrom. Um ein Gefühl für die Daten zu bekommen, können Sie eine Methode schreiben, die bei jedem n-ten Datenelement eine Stichprobe durchführt. Diese kleine Iteratormethode ist der Trick dabei:

```csharp
public static IEnumerable<T> Sample(this IEnumerable<T> sourceSequence, int interval)
{
    int index = 0;
    foreach (T item in sourceSequence)
    {
        if (index++ % interval == 0)
            yield return item;
    }
}
```

Es gibt eine wichtige Einschränkung bei Iteratormethoden: Eine `return`-Anweisung und eine `yield return`-Anweisung können nicht in derselben Methode enthalten sein. Folgendes wird nicht kompiliert:

```csharp
public IEnumerable<int> GetSingleDigitNumbers()
{
    int index = 0;
    while (index < 10)
        yield return index++;

    yield return 50;

    // generates a compile time error:
    var items = new int[] {100, 101, 102, 103, 104, 105, 106, 107, 108, 109 };
    return items;
}
```

Diese Einschränkung ist normalerweise kein Problem. Sie können in der Methode entweder durchgehend `yield return` verwenden oder die ursprüngliche Methode in mehrere Methoden aufteilen, von denen einige `return` und einige `yield return` verwenden.

Sie können die letzte Methode leicht ändern und so `yield return` überall verwenden:

```csharp
public IEnumerable<int> GetSingleDigitNumbers()
{
    int index = 0;
    while (index < 10)
        yield return index++;

    yield return 50;

    var items = new int[] {100, 101, 102, 103, 104, 105, 106, 107, 108, 109 };
    foreach (var item in items)
        yield return item;
}
```

Manchmal ist die beste Lösung, eine Iteratormethode in zwei verschiedene Methoden aufzuteilen. Die eine verwendet dann `return` und die zweite verwendet `yield return`. Betrachten Sie eine Situation, in der Sie eine leere Auflistung oder die ersten 5 ungeraden Zahlen basierend auf einem booleschen Argument zurückgeben möchten. Sie können das mit diesen zwei Methoden schreiben:

```csharp
public IEnumerable<int> GetSingleDigitOddNumbers(bool getCollection)
{
    if (getCollection == false)
        return new int[0];
    else
        return IteratorMethod();
}

private IEnumerable<int> IteratorMethod()
{
    int index = 0;
    while (index < 10)
    {
        if (index % 2 == 1)
            yield return index;
        index++;
    }
}
```

Betrachten Sie die oben genannten Methoden. Die erste Methode verwendet die `return`-Standardanweisung, um entweder eine leere Auflistung oder den Iterator, der durch die zweite Methode erstellt wurde, zurückzugeben. Die zweite Methode verwendet die `yield return`-Anweisung, um die angeforderte Reihenfolge zu erstellen.

## <a name="deeper-dive-into-foreach"></a>Tieferer Einblick in `foreach`

Die `foreach`-Anweisung wird in einen Standardausdruck erweitert, der die Schnittstellen `IEnumerable<T>` und `IEnumerator<T>` für das Durchlaufen aller Elemente einer Auflistung verwendet. Außerdem werden Fehler minimiert, die Entwickler durch falsche Ressourcenverwaltung verursachen.

Der Compiler übersetzt die im ersten Beispiel gezeigte `foreach`-Schleife in etwas wie dieses Konstrukt:

```csharp
IEnumerator<int> enumerator = collection.GetEnumerator();
while (enumerator.MoveNext())
{
    var item = enumerator.Current;
    Console.WriteLine(item.ToString());
}
```

Das obige Konstrukt stellt den Code dar, der durch den C#-Compiler ab Version 5 und höher generiert wird. Vor Version 5 hatte die `item`-Variable einen anderen Bereich:

```csharp
// C# versions 1 through 4:
IEnumerator<int> enumerator = collection.GetEnumerator();
int item = default(int);
while (enumerator.MoveNext())
{
    item = enumerator.Current;
    Console.WriteLine(item.ToString());
}
```

Dies wurde geändert, da das frühere Verhalten zu kleinen und schwierig zu diagnostizierenden Fehlern im Zusammenhang mit Lambdaausdrücken führen konnte. Weitere Informationen zu Lambdaausdrücken finden Sie unter [Lambdaausdrücke](./programming-guide/statements-expressions-operators/lambda-expressions.md).

Der genaue, vom Compiler generierte Code ist etwas komplizierter und behandelt Situationen, in denen das von `GetEnumerator()` zurückgegebene Objekt die `IDisposable`-Schnittstelle implementiert. Der durch vollständige Erweiterung generierte Code sieht eher wie folgt aus:

```csharp
{
    var enumerator = collection.GetEnumerator();
    try
    {
        while (enumerator.MoveNext())
        {
            var item = enumerator.Current;
            Console.WriteLine(item.ToString());
        }
    } finally
    {
        // dispose of enumerator.
    }
}
```

Die Art und Weise, wie der Enumerator verworfen wird, hängt von den Merkmalen des Typs von `enumerator` ab. Im Allgemeinen wird die `finally`-Klausel wie folgt erweitert:

```csharp
finally
{
   (enumerator as IDisposable)?.Dispose();
}
```

Wenn es sich bei dem Typ von `enumerator` jedoch um einen versiegelten Typ handelt und es keine implizite Konvertierung vom Typ von `enumerator` zu `IDisposable` gibt, wird die `finally`-Klausel zu einem leeren Block erweitert:

```csharp
finally
{
}
```

Wenn es eine implizite Konvertierung vom Typ von `enumerator` zu `IDisposable` gibt und `enumerator` keine NULL-Werte zulässt, wird die `finally`-Klausel wie folgt erweitert:

```csharp
finally
{
   ((IDisposable)enumerator).Dispose();
}
```

Glücklicherweise müssen Sie sich nicht alle diese Details merken. Die `foreach`-Anweisung kümmert sich für Sie um alle diese Nuancen. Der Compiler generiert den korrekten Code für jedes dieser Konstrukte.
