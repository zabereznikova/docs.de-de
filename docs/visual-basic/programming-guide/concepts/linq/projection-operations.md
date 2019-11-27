---
title: Projektionsvorgänge
ms.date: 07/20/2015
ms.assetid: b8d38e6d-21cf-4619-8dbb-94476f4badc7
ms.openlocfilehash: d7efb46ccfe3208ae6c58043a64c236171d0c147
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346630"
---
# <a name="projection-operations-visual-basic"></a>Projektions Vorgänge (Visual Basic)

Projektion bezieht sich auf einen Vorgang, bei dem ein Objekt in eine neue Form transformiert wird, die häufig nur aus den Eigenschaften besteht, die anschließend verwendet werden. Mithilfe der Projektion können Sie einen neuen Typ erstellen, der aus den einzelnen Objekten erstellt wird. Sie können eine Eigenschaft projizieren und eine mathematische Funktion für sie ausführen. Sie können auch das ursprüngliche Objekt projizieren, ohne es zu ändern.

Die Methoden des Standardabfrageoperators, die Projektion ausführen, sind im folgenden Abschnitt aufgeführt.

## <a name="methods"></a>Methoden

|Methodenname|Beschreibung|Syntax von Visual Basic-Abfrage Ausdrücken|Weitere Informationen|
|-----------------|-----------------|------------------------------------------|----------------------|
|Auswahl|Projektwerte, die auf einer Transform-Funktion basieren.|`Select`|<xref:System.Linq.Enumerable.Select%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Select%2A?displayProperty=nameWithType>|
|SelectMany|Projiziert Sequenzen von Werten, die auf einer Transform-Funktion basieren, und fasst diese dann in eine Sequenz zusammen.|Mehrere `From`-Klauseln verwenden|<xref:System.Linq.Enumerable.SelectMany%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.SelectMany%2A?displayProperty=nameWithType>|

## <a name="query-expression-syntax-examples"></a>Beispiele für die Abfrageausdruckssyntax

### <a name="select"></a>Auswahl

Im folgenden Beispiel wird die `Select`-Klausel verwendet, um den ersten Buchstaben jeder Zeichenfolge in einer Liste von Zeichenfolgen zu projizieren.

```vb
Dim words = New List(Of String) From {"an", "apple", "a", "day"}

Dim query = From word In words
            Select word.Substring(0, 1)

Dim sb As New System.Text.StringBuilder()
For Each letter As String In query
    sb.AppendLine(letter)
Next

' Display the output.
MsgBox(sb.ToString())

' This code produces the following output:

' a
' a
' a
' d
```

### <a name="selectmany"></a>SelectMany

Im folgenden Beispiel werden mehrere `From`-Klauseln verwendet, um jedes Wort aus jeder Zeichenfolge in einer Liste von Zeichen folgen zu projizieren.

```vb
Dim phrases = New List(Of String) From {"an apple a day", "the quick brown fox"}

Dim query = From phrase In phrases
            From word In phrase.Split(" "c)
            Select word

Dim sb As New System.Text.StringBuilder()
For Each str As String In query
    sb.AppendLine(str)
Next

' Display the output.
MsgBox(sb.ToString())

' This code produces the following output:

' an
' apple
' a
' day
' the
' quick
' brown
' fox
```

## <a name="select-versus-selectmany"></a>Select im Vergleich zu SelectMany

Die Arbeit von jeweils `Select()` und `SelectMany()` besteht darin, einen Ergebniswert (oder Werte) aus den Quellwerten zu erstellen. `Select()` generiert einen Ergebniswert für jeden Quellwert. Das Ergebnis ist daher eine Auflistung, die über die gleiche Anzahl von Elementen wie die Quellauflistung verfügt. Im Gegensatz dazu erzeugt `SelectMany()` ein einziges Gesamtergebnis, das verkettete untergeordnete Auflistungen aus jedem Quellwert enthält. Die Transform-Funktion, die als Argument an `SelectMany()` übergeben wird, muss eine aufzählbare Sequenz von Werten für jeden Quellwert zurückgeben. Diese aufzählbaren Sequenzen werden anschließend von `SelectMany()` zu einer großen Sequenz verkettet.

Die folgenden zwei Abbildungen zeigen den konzeptionellen Unterschied zwischen den Aktionen der beiden Methoden. In jedem Fall wird davon ausgegangen, dass die Auswahlfunktion (Transform) das Array von Blumen aus jedem Quellwert auswählt.

Die Abbildung zeigt, wie `Select()` eine Auflistung zurückgibt, die über die gleiche Anzahl von Elementen wie die Quellauflistung verfügt.

![Grafische Darstellung der Aktion Select&#40;&#41;](./media/projection-operations/select-action-graphic.png)

Diese Abbildung zeigt, wie `SelectMany()` die Zwischenmodus-Sequenz von Arrays in einem Endergebniswert verkettet, der jeden Wert aus jedem Zwischenmodus-Array enthält.

![Grafische Darstellung der Aktion SelectMany&#40;&#41;](./media/projection-operations/select-many-action-graphic.png )

### <a name="code-example"></a>Codebeispiel

Im folgenden Beispiel wird das Verhalten von `Select()` und `SelectMany()` verglichen. Der Code erstellt eine „Bouquet“ von Blumen, indem er die ersten beiden Elemente aus jeder Liste der Blumennamen in der Quellauflistung aufführt. In diesem Beispiel ist der „einzelne Wert“, den die Transformationsfunktion <xref:System.Linq.Enumerable.Select%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29> verwendet, selbst eine Auflistung von Werten. Dies erfordert die zusätzliche `For Each`-Schleife, um jede Zeichenfolge in den einzelnen Untersequenzen aufzulisten.

```vb
Class Bouquet
    Public Flowers As List(Of String)
End Class

Sub SelectVsSelectMany()
    Dim bouquets = New List(Of Bouquet) From {
        New Bouquet With {.Flowers = New List(Of String)(New String() {"sunflower", "daisy", "daffodil", "larkspur"})},
        New Bouquet With {.Flowers = New List(Of String)(New String() {"tulip", "rose", "orchid"})},
        New Bouquet With {.Flowers = New List(Of String)(New String() {"gladiolis", "lily", "snapdragon", "aster", "protea"})},
        New Bouquet With {.Flowers = New List(Of String)(New String() {"larkspur", "lilac", "iris", "dahlia"})}}

    Dim output As New System.Text.StringBuilder

    ' Select()
    Dim query1 = bouquets.Select(Function(b) b.Flowers)

    output.AppendLine("Using Select():")
    For Each flowerList In query1
        For Each str As String In flowerList
            output.AppendLine(str)
        Next
    Next

    ' SelectMany()
    Dim query2 = bouquets.SelectMany(Function(b) b.Flowers)

    output.AppendLine(vbCrLf & "Using SelectMany():")
    For Each str As String In query2
        output.AppendLine(str)
    Next

    ' Display the output
    MsgBox(output.ToString())

    ' This code produces the following output:
    '
    ' Using Select():
    ' sunflower
    ' daisy
    ' daffodil
    ' larkspur
    ' tulip
    ' rose
    ' orchid
    ' gladiolis
    ' lily
    ' snapdragon
    ' aster
    ' protea
    ' larkspur
    ' lilac
    ' iris
    ' dahlia

    ' Using SelectMany()
    ' sunflower
    ' daisy
    ' daffodil
    ' larkspur
    ' tulip
    ' rose
    ' orchid
    ' gladiolis
    ' lily
    ' snapdragon
    ' aster
    ' protea
    ' larkspur
    ' lilac
    ' iris
    ' dahlia

End Sub
```

## <a name="see-also"></a>Siehe auch

- <xref:System.Linq>
- [Standard Query Operators Overview (Visual Basic) (Übersicht über Standardabfrageoperatoren (Visual Basic))](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [Select-Klausel](../../../../visual-basic/language-reference/queries/select-clause.md)
- [Kombinieren von Daten mithilfe von Joins](../../../../visual-basic/programming-guide/language-features/linq/how-to-combine-data-with-linq-by-using-joins.md)
- [Gewusst wie: Auffüllen von Objekt Auflistungen aus mehreren Quellen (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-populate-object-collections-from-multiple-sources-linq.md)
- [Gewusst wie: Zurückgeben eines LINQ-Abfrageergebnisses als bestimmter Typ](../../../../visual-basic/programming-guide/language-features/linq/how-to-return-a-linq-query-result-as-a-specific-type.md)
- [Vorgehensweise: Aufteilen einer Datei in viele Dateien mithilfe von Gruppen (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-split-a-file-into-many-files-by-using-groups-linq.md)
