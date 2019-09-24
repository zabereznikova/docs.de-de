---
title: Untersuchen der Bereiche von Daten mithilfe von Indizes und Bereichen
description: In diesem fortgeschrittenen Tutorial erfahren Sie, wie Sie Daten mithilfe von Indizes und Bereichen untersuchen, um Segmente eines sequenziellen Datasets zu untersuchen.
ms.date: 04/19/2019
ms.custom: mvc
ms.openlocfilehash: d0eeadfff9732ced22e045536a88ed49cd98bbaa
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117838"
---
# <a name="indices-and-ranges"></a>Indizes und Bereiche

Bereiche und Indizes bieten eine prägnante Syntax für den Zugriff auf einzelne Elemente oder Bereiche in <xref:System.Array>, <xref:System.String>, <xref:System.Span%601> oder <xref:System.ReadOnlySpan%601>. Diese Funktionen ermöglichen eine kürzere, klarere Syntax für den Zugriff auf einzelne Elemente oder Bereiche von Elementen in einer Sequenz.

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

Beginnen wir mit den Regeln für Indizes. Betrachten Sie einen Array `sequence`. Der `0`-Index entspricht `sequence[0]`. Der `^0`-Index entspricht `sequence[sequence.Length]`. Beachten Sie, dass `sequence[^0]` genau wie `sequence[sequence.Length]` eine Ausnahme auslöst. Für eine beliebige Zahl `n` ist der Index `^n` identisch mit `sequence[sequence.Length - n]`.

```csharp-interactive
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

[!code-csharp[LastIndex](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_LastIndex)]

Ein Bereich gibt den *Beginn* und das *Ende* eines Bereichs an. Bereiche sind exklusiv, d.h. das *Ende* ist nicht im Bereich enthalten. Der Bereich `[0..^0]` stellt ebenso wie `[0..sequence.Length]` den gesamten Bereich dar. 

Der folgende Code erzeugt einen Teilbereich mit den Worten „quick“, „brown“ und „fox“. Er enthält `words[1]` bis `words[3]`. Das Element `words[4]` befindet sich nicht im Bereich. Fügen Sie derselben Methode den folgenden Code hinzu. Kopieren Sie ihn, und fügen Sie ihn unten in das interaktive Fenster ein.

[!code-csharp[Range](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_Range)]

Der folgende Code erzeugt einen Teilbereich mit „lazy“ und „dog“. Dazu gehören `words[^2]` und `words[^1]`. Der Endindex `words[^0]` ist nicht enthalten. Fügen Sie den folgenden Code auch hinzu:

[!code-csharp[LastRange](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_LastRange)]

Die folgenden Beispiele erstellen Bereiche, die am Anfang, am Ende und auf beiden Seiten offen sind:

[!code-csharp[PartialRange](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_PartialRanges)]

Sie können Bereiche oder Indizes auch als Variablen deklarieren. Die Variable kann dann innerhalb der Zeichen `[` und `]` verwendet werden:

[!code-csharp[IndexRangeTypes](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_RangeIndexTypes)]

Das folgende Beispiel zeigt viele der Gründe für diese Auswahl. Ändern Sie `x`, `y` und `z`, um verschiedene Kombinationen zu testen. Verwenden Sie beim Experimentieren Werte, wo `x` kleiner ist als `y` und `y` kleiner als `z` für gültige Kombinationen. Fügen Sie den folgenden Code in einer neuen Methode hinzu. Probieren Sie verschiedene Kombinationen aus:

[!code-csharp[SemanticsExamples](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_Semantics)]

## <a name="scenarios-for-indices-and-ranges"></a>Szenarien für Indizes und Bereiche

Sie verwenden häufig Bereiche und Indizes, wenn Sie eine Analyse eines Teilbereichs einer vollständigen Sequenz ausführen möchten. Aus der neuen Syntax lässt sich klarer herauslesen, welcher Teilbereich beteiligt ist. Die lokale Funktion `MovingAverage` nimmt einen <xref:System.Range> als Argument entgegen. Die Methode listet dann genau diesen Bereich bei der Berechnung von Minimum, Maximum und Durchschnitt auf. Probieren Sie den folgenden Code in Ihrem Projekt aus:

[!code-csharp[MovingAverages](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_MovingAverage)]

Sie können den fertig gestellten Code aus dem Repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/RangesIndexes) herunterladen.
