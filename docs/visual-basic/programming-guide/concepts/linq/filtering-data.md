---
title: Filtern von Daten
ms.date: 07/20/2015
ms.assetid: 7749519a-7edc-49fe-aef9-6a353864af6c
ms.openlocfilehash: 81e207e451055fb2952e4bf393db067f0851afb4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353490"
---
# <a name="filtering-data-visual-basic"></a>Filtern von Daten (Visual Basic)

Mit Filtern wird die Einschränkung des Resultsets auf Elemente bezeichnet, die eine bestimmte Bedingung erfüllen. Es ist auch bekannt als Auswahl.

Die folgende Abbildung zeigt die Ergebnisse des Filterns einer Zeichenfolge. Das Prädikat für den Filtervorgang gibt an, dass das Zeichen A sein muss.

![Abbildung zu einem LINQ-Filtervorgang](./media/filtering-data/linq-filter-operation.png)

Die Methoden des Standardabfrageoperators, die Auswahl ausführen, sind im folgenden Abschnitt aufgeführt.

## <a name="methods"></a>Methoden

|Methodenname|Beschreibung|Syntax von Visual Basic-Abfrage Ausdrücken|Weitere Informationen|
|-----------------|-----------------|------------------------------------------|----------------------|
|OfType|Wählt Werte aus, je nach ihrer Fähigkeit, in einen angegebenen Typ umgewandelt zu werden.|Nicht zutreffend.|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=nameWithType>|
|Where|Wählt Werte aus, die auf einer Prädikatfunktion basieren.|`Where`|<xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Where%2A?displayProperty=nameWithType>|

## <a name="query-expression-syntax-example"></a>Beispiel für die Abfrageausdruckssyntax

Im folgenden Beispiel wird die-`Where` verwendet, um die Zeichen folgen, die eine bestimmte Länge aufweisen, nach einem Array zu filtern.

```vb
Dim words() As String = {"the", "quick", "brown", "fox", "jumps"}

Dim query = From word In words
            Where word.Length = 3
            Select word

Dim sb As New System.Text.StringBuilder()
For Each str As String In query
    sb.AppendLine(str)
Next

' Display the results.
MsgBox(sb.ToString())

' This code produces the following output:

' the
' fox
```

## <a name="see-also"></a>Siehe auch

- <xref:System.Linq>
- [Standard Query Operators Overview (Visual Basic) (Übersicht über Standardabfrageoperatoren (Visual Basic))](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [Where-Klausel](../../../../visual-basic/language-reference/queries/where-clause.md)
- [Gewusst wie: Filtern von Abfrageergebnissen](../../../../visual-basic/programming-guide/language-features/linq/how-to-filter-query-results-by-using-linq.md)
- [Gewusst wie: Abfragen der Metadaten einer Assembly mit Reflektion (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-an-assembly-s-metadata-with-reflection-linq.md)
- [Gewusst wie: Abfragen von Dateien mit einem angegebenen Attribut oder Namen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-files-with-a-specified-attribute-or-name.md)
- [Gewusst wie: Sortieren oder Filtern von Textdaten nach einem beliebigen Wort oder Feld (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
