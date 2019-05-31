---
title: Untersuchen der Bereiche von Daten mithilfe von Indizes und Bereichen
description: In diesem fortgeschrittenen Tutorial erfahren Sie, wie Sie Daten mithilfe von Indizes und Bereichen untersuchen, um Segmente eines sequenziellen Datasets zu untersuchen.
ms.date: 04/19/2019
ms.custom: mvc
ms.openlocfilehash: 64fae4581e265d4f70b8356d5c651b4fdaca3fe9
ms.sourcegitcommit: dd3b897feb5c4ac39732bb165848e37a344b0765
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/25/2019
ms.locfileid: "64431490"
---
# <a name="indices-and-ranges"></a>Indizes und Bereiche

Bereiche und Indizes bieten eine prägnante Syntax für den Zugriff auf einzelne Elemente oder Bereiche in <xref:System.Array>, <xref:System.Span%601> oder <xref:System.ReadOnlySpan%601>. Diese Funktionen ermöglichen eine kürzere, klarere Syntax für den Zugriff auf einzelne Elemente oder Bereiche von Elementen in einer Sequenz.

In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:

> [!div class="checklist"]
> * Verwenden Sie die Syntax für Bereiche in einer Sequenz.
> * Lernen Sie die Entwurfsentscheidungen für Start und Ende jeder Sequenz kennen.
> * Lernen Sie Szenarien für die Typen <xref:System.Index> und <xref:System.Range> kennen.

## <a name="language-support-for-indices-and-ranges"></a>Sprachunterstützung für Indizes und Bereiche

Sie können mit Verwendung des `^`-Zeichens vor dem Index einen Index **vom Ende aus** angeben. Die Indizierung vom Ende aus beginnt mit der Regel, dass `0..^0` den gesamten Bereich angibt. Starten Sie zum Auflisten eines vollständigen Arrays *beim ersten Element*, und fahren Sie fort bis *hinter das letzte Element*. Stellen Sie sich das Verhalten der `MoveNext`-Methode auf einem Enumerator vor: Sie gibt „false“ zurück, wenn die Enumeration das letzte Element passiert. Der Index `^0` bedeutet „das Ende“, `array[array.Length]`, oder der Index, der dem letzten Element folgt. Sie kennen `array[2]`. Damit wird das Element „2 from the start“ bezeichnet. Jetzt bezeichnet `array[^2]` das Element „2 from the end“. 

Sie können einen **Bereich** mit dem **Bereichsoperator** angeben: `..`. So gibt beispielsweise `0..^0` den gesamten Bereich des Arrays an: 0 vom Anfang bis zum Ende, aber nicht einschließlich 0 vom Ende. Jeder der beiden Operanden kann „from the start“ oder „from the end“ verwenden. Darüber hinaus kann jeder der beiden Operanden weggelassen werden. Die Standardeinstellungen sind `0` für den Startindex und `^0` für den Endindex.

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

Der Index jedes Elements verstärkt das Konzept von „from the start“ und „from the end“, und dass Bereiche das Ende des Bereichs ausschließen. Der „start“ des gesamten Arrays ist das erste Element. Das „end“ des gesamten Arrays liegt *hinter* dem letzten Element.

Sie können das letzte Wort mit dem `^1`-Index abrufen. Fügen Sie unter der Initialisierung folgenden Code hinzu:

[!code-csharp[LastIndex](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_LastIndex)]

Der folgende Code erzeugt einen Teilbereich mit den Worten „quick“, „brown“ und „fox“. Er enthält `words[1]` bis `words[3]`. Das Element `words[4]` befindet sich nicht im Bereich. Fügen Sie derselben Methode den folgenden Code hinzu. Kopieren Sie ihn, und fügen Sie ihn unten in das interaktive Fenster ein.

[!code-csharp[Range](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_Range)]

Der folgende Code erzeugt einen Teilbereich mit „lazy“ und „dog“. Dazu gehören `words[^2]` und `words[^1]`. Der Endindex `words[^0]` ist nicht enthalten. Fügen Sie den folgenden Code auch hinzu:

[!code-csharp[LastRange](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_LastRange)]

Die folgenden Beispiele erstellen Bereiche, die am Anfang, am Ende und auf beiden Seiten offen sind:

[!code-csharp[PartialRange](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_PartialRanges)]

Sie können Bereiche oder Indizes auch als Variablen deklarieren. Die Variable kann dann innerhalb der Zeichen `[` und `]` verwendet werden:

[!code-csharp[IndexRangeTypes](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_RangeIndexTypes)]

Die obigen Beispiele zeigen zwei Entwurfsentscheidungen, die eine ausführlichere Erläuterung erfordern:

- Bereiche sind *exklusiv*, d.h. das Element am letzten Index befindet sich nicht im Bereich.
- Der Index `^0` ist *das Ende* der Sammlung, nicht *das letzte Element* in der Sammlung.

Das folgende Beispiel zeigt viele der Gründe für diese Auswahl. Ändern Sie `x`, `y` und `z`, um verschiedene Kombinationen zu testen. Verwenden Sie beim Experimentieren Werte, wo `x` kleiner ist als `y` und `y` kleiner als `z` für gültige Kombinationen. Fügen Sie den folgenden Code in einer neuen Methode hinzu. Probieren Sie verschiedene Kombinationen aus:

[!code-csharp[SemanticsExamples](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_Semantics)]

## <a name="scenarios-for-indices-and-ranges"></a>Szenarien für Indizes und Bereiche

Sie verwenden häufig Bereiche und Indizes, wenn Sie eine Analyse eines Teilbereichs einer vollständigen Sequenz ausführen möchten. Aus der neuen Syntax lässt sich klarer herauslesen, welcher Teilbereich beteiligt ist. Die lokale Funktion `MovingAverage` nimmt einen <xref:System.Range> als Argument entgegen. Die Methode listet dann genau diesen Bereich bei der Berechnung von Minimum, Maximum und Durchschnitt auf. Probieren Sie den folgenden Code in Ihrem Projekt aus:

[!code-csharp[MovingAverages](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_MovingAverage)]

Sie können den fertig gestellten Code aus dem Repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/RangesIndexes) herunterladen.
