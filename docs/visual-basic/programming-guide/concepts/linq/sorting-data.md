---
title: Sortieren von Daten
ms.date: 07/20/2015
ms.assetid: 6f81065c-0c89-4bf3-a6d8-442273f8810e
ms.openlocfilehash: f1d4d8afb9b6e176a7ac048ba3270ecafdce24c9
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350585"
---
# <a name="sorting-data-visual-basic"></a>Sortieren von Daten (Visual Basic)

Bei einem Sortiervorgang werden die Elemente einer Sequenz auf Grundlage eines oder mehrerer Attribute sortiert. Mit dem ersten Sortierkriterium wird eine primäre Sortierung der Elemente ausgeführt. Sie können die Elemente innerhalb jeder primären Sortiergruppe sortieren, indem Sie ein zweites Sortierkriterium angeben.

Die folgende Abbildung zeigt das Ergebnis eines alphabetischen Sortiervorgangs bei einer Zeichensequenz.

![Grafik, die einen alphabetischen Sortiervorgang zeigt.](./media/sorting-data/alphabetical-sort-operation.png)

Die Methoden des Standardabfrageoperators, die Daten sortieren, sind im folgenden Abschnitt aufgeführt.

## <a name="methods"></a>Methoden

|Methodenname|Beschreibung|Syntax von Visual Basic-Abfrage Ausdrücken|Weitere Informationen|
|-----------------|-----------------|------------------------------------------|----------------------|
|OrderBy|Sortiert Werte in aufsteigender Reihenfolge|`Order By`|<xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OrderBy%2A?displayProperty=nameWithType>|
|OrderByDescending|Sortiert Werte in absteigender Reihenfolge|`Order By … Descending`|<xref:System.Linq.Enumerable.OrderByDescending%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OrderByDescending%2A?displayProperty=nameWithType>|
|ThenBy|Führt eine sekundäre Sortierung in aufsteigender Reihenfolge durch|`Order By …, …`|<xref:System.Linq.Enumerable.ThenBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ThenBy%2A?displayProperty=nameWithType>|
|ThenByDescending|Führt eine sekundäre Sortierung in absteigender Reihenfolge durch|`Order By …, … Descending`|<xref:System.Linq.Enumerable.ThenByDescending%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ThenByDescending%2A?displayProperty=nameWithType>|
|Reverse|Kehrt die Reihenfolge der Elemente in einer Auflistung um|Nicht zutreffend.|<xref:System.Linq.Enumerable.Reverse%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Reverse%2A?displayProperty=nameWithType>|

## <a name="query-expression-syntax-examples"></a>Beispiele für die Abfrageausdruckssyntax

### <a name="primary-sort-examples"></a>Primäre Sortierungsbeispiele

#### <a name="primary-ascending-sort"></a>Primäre aufsteigende Sortierung

Im folgenden Beispiel wird veranschaulicht, wie man die `Order By`-Klausel in einer LINQ-Abfrage verwendet, um die Zeichenfolgen in einem Array in aufsteigender Reihenfolge nach der Länge der Zeichenfolgen zu sortieren.

```vb
Dim words = {"the", "quick", "brown", "fox", "jumps"}

Dim sortQuery = From word In words
                Order By word.Length
                Select word

Dim sb As New System.Text.StringBuilder()
For Each str As String In sortQuery
    sb.AppendLine(str)
Next

' Display the results.
MsgBox(sb.ToString())

' This code produces the following output:

' the
' fox
' quick
' brown
' jumps
```

#### <a name="primary-descending-sort"></a>Primäre absteigende Sortierung

Im nächsten Beispiel wird veranschaulicht, wie man die `Order By Descending`-Klausel in einer LINQ-Abfrage verwendet, um die Zeichenfolgen in absteigender Reihenfolge nach ihrem ersten Buchstaben zu sortieren.

```vb
Dim words = {"the", "quick", "brown", "fox", "jumps"}

Dim sortQuery = From word In words
                Order By word.Substring(0, 1) Descending
                Select word

Dim sb As New System.Text.StringBuilder()
For Each str As String In sortQuery
    sb.AppendLine(str)
Next

' Display the results.
MsgBox(sb.ToString())

' This code produces the following output:

' the
' quick
' jumps
' fox
' brown
```

### <a name="secondary-sort-examples"></a>Sekundäre Sortierungsbeispiele

#### <a name="secondary-ascending-sort"></a>Sekundäre aufsteigende Sortierung

Im folgenden Beispiel wird veranschaulicht, wie man die `Order By`-Klausel in einer LINQ-Abfrage verwendet, um eine primäre und eine sekundäre Sortierung der Zeichenfolgen in einem Array durchzuführen. Die Zeichenfolgen werden primär nach der Länge und sekundär nach dem ersten Buchstaben der Zeichenfolge sortiert, beide Male in aufsteigender Reihenfolge.

```vb
Dim words = {"the", "quick", "brown", "fox", "jumps"}

Dim sortQuery = From word In words
                Order By word.Length, word.Substring(0, 1)
                Select word

Dim sb As New System.Text.StringBuilder()
For Each str As String In sortQuery
    sb.AppendLine(str)
Next

' Display the results.
MsgBox(sb.ToString())

' This code produces the following output:

' fox
' the
' brown
' jumps
' quick
```

#### <a name="secondary-descending-sort"></a>Sekundäre absteigende Sortierung

Im nächsten Beispiel wird gezeigt, wie man die `Order By Descending`-Klausel in einer LINQ-Abfrage verwendet, um eine primäre Sortierung in aufsteigender Reihenfolge und eine sekundäre Sortierung in absteigender Reihenfolge durchzuführen. Die Zeichenfolgen werden primär nach der Länge und sekundär nach dem ersten Buchstaben der Zeichenfolge sortiert.

```vb
Dim words = {"the", "quick", "brown", "fox", "jumps"}

Dim sortQuery = From word In words
                Order By word.Length, word.Substring(0, 1) Descending
                Select word

Dim sb As New System.Text.StringBuilder()
For Each str As String In sortQuery
    sb.AppendLine(str)
Next

' Display the results.
MsgBox(sb.ToString())

' This code produces the following output:

' fox
' the
' quick
' jumps
' brown
```

## <a name="see-also"></a>Siehe auch

- <xref:System.Linq>
- [Standard Query Operators Overview (Visual Basic) (Übersicht über Standardabfrageoperatoren (Visual Basic))](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [Order By-Klausel](../../../../visual-basic/language-reference/queries/order-by-clause.md)
- [Gewusst wie: Sortieren von Abfrageergebnissen](../../../../visual-basic/programming-guide/language-features/linq/how-to-sort-query-results-by-using-linq.md)
- [Gewusst wie: Sortieren oder Filtern von Textdaten nach einem beliebigen Wort oder Feld (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
