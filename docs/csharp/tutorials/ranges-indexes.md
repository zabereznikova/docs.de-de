---
title: Untersuchen der Bereiche von Daten mithilfe von Indizes und Bereichen
description: In diesem fortgeschrittenen Tutorial erfahren Sie, wie Sie Daten mithilfe von Indizes und Bereichen untersuchen, um Segmente eines sequenziellen Datasets zu untersuchen.
ms.date: 03/11/2020
ms.technology: csharp-fundamentals
ms.custom: mvc
ms.openlocfilehash: 82aad968e2efc437c82a7c8250bcd108b60b09e1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79156493"
---
# <a name="indices-and-ranges"></a>Indizes und Bereiche

Bereiche und Indizes bieten eine prägnante Syntax für den Zugriff auf einzelne Elemente oder Bereiche in einer Sequenz.

In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:

> [!div class="checklist"]
>
> - Verwenden Sie die Syntax für Bereiche in einer Sequenz.
> - Lernen Sie die Entwurfsentscheidungen für Start und Ende jeder Sequenz kennen.
> - Lernen Sie Szenarien für die Typen <xref:System.Index> und <xref:System.Range> kennen.

## <a name="language-support-for-indices-and-ranges"></a>Sprachunterstützung für Indizes und Bereiche

Diese Sprachunterstützung basiert auf zwei neuen Typen und zwei neuen Operatoren:

- <xref:System.Index?displayProperty=nameWithType>: Stellt einen Index in einer Sequenz dar.
- Der Index vom Endeoperator `^`, der angibt, dass ein Index relativ zum Ende einer Sequenz ist.
- <xref:System.Range?displayProperty=nameWithType>: Stellt einen Unterbereich einer Sequenz dar.
- Der Bereichsoperator `..`, der den Beginn und das Ende eines Bereichs als seine Operanden angibt.

Beginnen wir mit den Regeln für Indizes. Betrachten Sie einen Array `sequence`. Der `0`-Index entspricht `sequence[0]`. Der `^0`-Index entspricht `sequence[sequence.Length]`. Der Ausdruck `sequence[^0]` löst eine Ausnahme aus, genau wie `sequence[sequence.Length]`. Für eine beliebige Zahl `n` ist der Index `^n` identisch mit `sequence[sequence.Length - n]`.

```csharp
string[] words = new string[]
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

Sie können das letzte Wort mit dem `^1`-Index abrufen. Fügen Sie unter der Initialisierung folgenden Code hinzu:

[!code-csharp[LastIndex](~/samples/snippets/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_LastIndex)]

Ein Bereich gibt den *Beginn* und das *Ende* eines Bereichs an. Bereiche sind exklusiv, d. h. das *Ende* ist nicht im Bereich enthalten. Der Bereich `[0..^0]` stellt ebenso wie `[0..sequence.Length]` den gesamten Bereich dar.

Der folgende Code erzeugt einen Teilbereich mit den Worten „quick“, „brown“ und „fox“. Er enthält `words[1]` bis `words[3]`. Das Element `words[4]` befindet sich nicht im Bereich. Fügen Sie derselben Methode den folgenden Code hinzu. Kopieren Sie ihn, und fügen Sie ihn unten in das interaktive Fenster ein.

[!code-csharp[Range](~/samples/snippets/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_Range)]

Der folgende Code erzeugt einen Teilbereich mit „lazy“ und „dog“. Dazu gehören `words[^2]` und `words[^1]`. Der Endindex `words[^0]` ist nicht enthalten. Fügen Sie den folgenden Code auch hinzu:

[!code-csharp[LastRange](~/samples/snippets/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_LastRange)]

Die folgenden Beispiele erstellen Bereiche, die am Anfang, am Ende und auf beiden Seiten offen sind:

[!code-csharp[PartialRange](~/samples/snippets/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_PartialRanges)]

Sie können Bereiche oder Indizes auch als Variablen deklarieren. Die Variable kann dann innerhalb der Zeichen `[` und `]` verwendet werden:

[!code-csharp[IndexRangeTypes](~/samples/snippets/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_RangeIndexTypes)]

Das folgende Beispiel zeigt viele der Gründe für diese Auswahl. Ändern Sie `x`, `y` und `z`, um verschiedene Kombinationen zu testen. Verwenden Sie beim Experimentieren Werte, wo `x` kleiner ist als `y` und `y` kleiner als `z` für gültige Kombinationen. Fügen Sie den folgenden Code in einer neuen Methode hinzu. Probieren Sie verschiedene Kombinationen aus:

[!code-csharp[SemanticsExamples](~/samples/snippets/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_Semantics)]

## <a name="type-support-for-indices-and-ranges"></a>Typunterstützung für Indizes und Bereiche

Indizes und Bereiche stellen eine klare, präzise Syntax für den Zugriff auf ein einzelnes Element oder einen Teilbereich von Elementen in einer Sequenz bereit. Ein Indexausdruck gibt in der Regel den Typ der Elemente einer Sequenz zurück. Ein Bereichsausdruck gibt in der Regel den gleichen Sequenztyp wie die Quellsequenz zurück.

Jeder Typ, der einen [Indexer](../programming-guide/indexers/index.md) mit einem <xref:System.Index>- oder <xref:System.Range>-Parameter bereitstellt, unterstützt explizit Indizes bzw. Bereiche. Ein Indexer, der einen einzelnen <xref:System.Range>-Parameter annimmt, kann einen anderen Sequenztyp zurückgeben, z. B. <xref:System.Span%601?displayProperty=nameWithType>.

Ein Typ ist **zählbar**, wenn er über eine Eigenschaft mit dem Namen `Length` oder `Count` mit einem zugreifbaren Getter und einem Rückgabetyp von `int` verfügt. Ein zählbarer Typ, der Indizes oder Bereiche nicht explizit unterstützt, kann implizite Unterstützung dafür bieten. Weitere Informationen finden Sie in den Abschnitten [Implizite Indexunterstützung](~/_csharplang/proposals/csharp-8.0/ranges.md#implicit-index-support) und [Implizite Bereichsunterstützung](~/_csharplang/proposals/csharp-8.0/ranges.md#implicit-range-support) der [Featurevorschläge](~/_csharplang/proposals/csharp-8.0/ranges.md). Bereiche, die die implizite Bereichsunterstützung verwenden, geben denselben Sequenztyp wie die Quellsequenz zurück.

Beispielsweise unterstützen die folgenden .NET-Typen Indizes und Bereiche: <xref:System.String>, <xref:System.Span%601> und <xref:System.ReadOnlySpan%601>. <xref:System.Collections.Generic.List%601> unterstützt Indizes, jedoch keine Bereiche.

<xref:System.Array> zeigt ein differenzierteres Verhalten. Eindimensionale Arrays unterstützen sowohl Indizes als auch Bereiche. Bei mehrdimensionalen Arrays ist dies nicht der Fall. Der Indexer für ein mehrdimensionales Array verfügt über mehrere Parameter, nicht über einen einzelnen Parameter. Jagged Arrays, auch als Array von Arrays bezeichnet, unterstützen sowohl Bereiche als auch Indexer. Das folgende Beispiel zeigt, wie ein rechteckiger Unterabschnitt eines Jagged Arrays durchlaufen wird. Es durchläuft den Abschnitt in der Mitte, wobei die ersten und letzten drei Zeilen sowie die ersten und letzten zwei Spalten jeder ausgewählten Zeile ausgeschlossen werden:

[!code-csharp[JaggedArrays](~/samples/snippets/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_JaggedArrays)]

## <a name="scenarios-for-indices-and-ranges"></a>Szenarien für Indizes und Bereiche

Sie werden oft Bereiche und Indizes verwenden, wenn Sie einen Teilbereich einer größeren Sequenz analysieren möchten. Aus der neuen Syntax lässt sich klarer herauslesen, welcher Teilbereich beteiligt ist. Die lokale Funktion `MovingAverage` nimmt einen <xref:System.Range> als Argument entgegen. Die Methode listet dann genau diesen Bereich bei der Berechnung von Minimum, Maximum und Durchschnitt auf. Probieren Sie den folgenden Code in Ihrem Projekt aus:

[!code-csharp[MovingAverages](~/samples/snippets/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_MovingAverage)]
