---
title: Filtern von Daten
ms.date: 07/20/2015
ms.assetid: 7749519a-7edc-49fe-aef9-6a353864af6c
ms.openlocfilehash: f7a1aa76dc93cc03952e55f5f8fc3f75176a3f9f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84383416"
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
|Hierbei gilt:|Wählt Werte aus, die auf einer Prädikatfunktion basieren.|`Where`|<xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Where%2A?displayProperty=nameWithType>|

## <a name="query-expression-syntax-example"></a>Beispiel für die Abfrageausdruckssyntax

Im folgenden Beispiel wird der verwendet, um die Zeichen folgen `Where` , die eine bestimmte Länge aufweisen, aus einem Array zu filtern.

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

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Linq>
- [Standard Query Operators Overview (Visual Basic) (Übersicht über Standardabfrageoperatoren (Visual Basic))](standard-query-operators-overview.md)
- [WHERE-Klausel](../../../language-reference/queries/where-clause.md)
- [Gewusst wie: Filtern von Abfrageergebnissen](../../language-features/linq/how-to-filter-query-results-by-using-linq.md)
- [Gewusst wie: Abfragen der Metadaten einer Assembly mit Reflektion (LINQ) (Visual Basic)](how-to-query-an-assembly-s-metadata-with-reflection-linq.md)
- [Gewusst wie: Abfragen von Dateien mit einem angegebenen Attribut oder Namen (Visual Basic)](how-to-query-for-files-with-a-specified-attribute-or-name.md)
- [Gewusst wie: Sortieren oder Filtern von Textdaten nach einem beliebigen Wort oder Feld (LINQ) (Visual Basic)](how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
