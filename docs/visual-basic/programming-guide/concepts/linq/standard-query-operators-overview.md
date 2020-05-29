---
title: Übersicht über Standardabfrageoperatoren
ms.date: 07/20/2015
ms.assetid: 302bd39e-2ec1-495b-94bf-37d370d6f05f
ms.openlocfilehash: 0f68d175b526a9da86853272c47b5e7d7b4a5992
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2020
ms.locfileid: "84201085"
---
# <a name="standard-query-operators-overview-visual-basic"></a>Standard Query Operators Overview (Visual Basic) (Übersicht über Standardabfrageoperatoren (Visual Basic))

Die *Standardabfrageoperatoren* sind die Methoden, die das LINQ-Muster bilden. Die meisten dieser Methoden bearbeiten Sequenzen. Eine Sequenz ist hier ein Objekt, dessen Typ die <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle oder die <xref:System.Linq.IQueryable%601>-Schnittstelle implementiert. Die Standardabfrageoperatoren stellen Abfragefunktionen wie Filterung, Projektion, Aggregation, Sortierung und weitere bereit.

Es gibt zwei Gruppen von LINQ-Standardabfrageoperatoren: Eine Gruppe funktioniert auf Grundlage von Objekten vom Typ <xref:System.Collections.Generic.IEnumerable%601>, die andere auf Grundlage von Objekten vom Typ <xref:System.Linq.IQueryable%601>. Die Methoden, die eine Gruppe bilden, sind statische Member der Klassen <xref:System.Linq.Enumerable> und <xref:System.Linq.Queryable>. Sie werden als *Erweiterungsmethoden* des Typs, auf dessen Grundlage sie funktionieren, definiert. Das bedeutet, dass Sie entweder mit der Syntax für statische Methoden oder für Instanzmethoden aufgerufen werden.

Darüber hinaus funktionieren mehrere Standardabfrageoperator-Methoden auf Grundlage anderer Typen als die, die auf <xref:System.Collections.Generic.IEnumerable%601> oder <xref:System.Linq.IQueryable%601> basieren. Der Typ <xref:System.Linq.Enumerable> definiert zwei Methoden, die beide auf Grundlage von Objekten vom Typ <xref:System.Collections.IEnumerable> funktionieren. Die Methoden <xref:System.Linq.Enumerable.Cast%60%601%28System.Collections.IEnumerable%29> und <xref:System.Linq.Enumerable.OfType%60%601%28System.Collections.IEnumerable%29> ermöglichen es Ihnen, eine nicht parametrisierte oder nicht generische Auflistung im LINQ-Muster abfragen zu lassen. Hierzu wird eine stark typisierte Auflistung von-Objekten erstellt. Die Klasse <xref:System.Linq.Queryable> definiert zwei ähnliche Methoden, <xref:System.Linq.Queryable.Cast%60%601%28System.Linq.IQueryable%29> und <xref:System.Linq.Queryable.OfType%60%601%28System.Linq.IQueryable%29>, die auf Grundlage von Objekten vom Typ <xref:System.Linq.Queryable> funktionieren.

Die Standardabfrageoperatoren unterscheiden sich im Zeitpunkt ihrer Ausführung. Dies hängt davon ab, ob sie einen Singleton-Wert oder eine Sequenz von Werten zurückgeben. Die Methoden, die einen Singleton-Wert zurückgeben (z.B. <xref:System.Linq.Enumerable.Average%2A> und <xref:System.Linq.Enumerable.Sum%2A>), werden sofort ausgeführt. Methoden, die eine Sequenz zurückgeben, verzögern die Abfrageausführung und geben ein auflistbares Objekt zurück.

Bei Methoden, die auf Grundlage von im Speicher enthaltenen Auflistungen funktionieren, d.h. die Methoden, die <xref:System.Collections.Generic.IEnumerable%601> erweitern, erfasst das zurückgegebene auflistbare Objekt die Argumente, die an die Methode übergeben wurden. Wenn dieses Objekt auflistbar ist, tritt die Logik des Abfrageoperators in Kraft, und die Abfrageergebnisse werden zurückgegeben.

Im Gegensatz dazu implementieren Methoden, die <xref:System.Linq.IQueryable%601> erweitern, kein Abfrageverhalten. Sie erstellen stattdessen eine Ausdrucksbaumstruktur, die die auszuführende Abfrage darstellt. Die Verarbeitung von Abfragen wird vom Quellobjekt <xref:System.Linq.IQueryable%601> übernommen.

Aufrufe der Abfragemethode können miteinander in eine Abfrage verkettet werden. Dadurch können Abfragen von beliebiger Komplexität sein.

Im folgenden Codebeispiel wird veranschaulicht, wie die Standardabfrageoperatoren verwendet werden können, um Informationen zu einer Sequenz zu erhalten.

```vb
Dim sentence = "the quick brown fox jumps over the lazy dog"
' Split the string into individual words to create a collection.
Dim words = sentence.Split(" "c)

Dim query = From word In words
            Group word.ToUpper() By word.Length Into gr = Group
            Order By Length _
            Select Length, GroupedWords = gr

Dim output As New System.Text.StringBuilder
For Each obj In query
    output.AppendLine(String.Format("Words of length {0}:", obj.Length))
    For Each word As String In obj.GroupedWords
        output.AppendLine(word)
    Next
Next

'Display the output
MsgBox(output.ToString())

' This code example produces the following output:
'
' Words of length 3:
' THE
' FOX
' THE
' DOG
' Words of length 4:
' OVER
' LAZY
' Words of length 5:
' QUICK
' BROWN
' JUMPS
```

## <a name="query-expression-syntax"></a>Abfrageausdruckssyntax

Einige der häufiger verwendeten Standardabfrageoperatoren verfügen über eine dedizierte Schlüsselwortsyntax von C# und Visual Basic-Sprache, wodurch sie als Teil eines *query*-*Ausdrucks* aufgerufen werden können. Weitere Informationen zu Standard Abfrage Operatoren mit dedizierten Schlüsselwörtern und ihrer entsprechenden Syntax finden Sie unter [Abfrage Ausdrucks Syntax für Standard Abfrage Operatoren (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/query-expression-syntax-for-standard-query-operators.md).

## <a name="extending-the-standard-query-operators"></a>Erweitern der Standardabfrageoperatoren

Sie können die Gruppe von Standardabfrageoperatoren durch Erstellen von domänenspezifischen Methoden erweitern, die für Ihre Zieldomäne oder -technologie geeignet sind. Sie können die Standardabfrageoperatoren auch mit ihren eigenen Implementierungen ersetzen, die zusätzliche Dienste bieten, z.B. Remote-Auswertung, Abfrageübersetzung und Optimierung. Ein Beispiel finden Sie unter <xref:System.Linq.Enumerable.AsEnumerable%2A>.

## <a name="related-sections"></a>Verwandte Abschnitte

Über die folgenden Links gelangen Sie zu Themen, die Ihnen weitere Informationen über die verschiedenen Standardabfrageoperatoren basierend auf deren Funktionen bieten.

- [Sortieren von Daten](../../../../visual-basic/programming-guide/concepts/linq/sorting-data.md)

- [Set-Vorgänge (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/set-operations.md)

- [Filtern von Daten (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/filtering-data.md)

- [Quantifizierer-Vorgänge (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/quantifier-operations.md)

- [Projektions Vorgänge (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/projection-operations.md)

- [Partitionierung von Daten (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/partitioning-data.md)

- [Joinvorgänge (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/join-operations.md)

- [Gruppieren von Daten (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/grouping-data.md)

- [Generierungs Vorgänge (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/generation-operations.md)

- [Gleichheits Vorgänge (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/equality-operations.md)

- [Element Vorgänge (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/element-operations.md)

- [Datentypen werden umgerechnet (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/converting-data-types.md)

- [Verkettungs Vorgänge (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/concatenation-operations.md)

- [Aggregations Vorgänge (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/aggregation-operations.md)

## <a name="see-also"></a>Siehe auch

- <xref:System.Linq.Enumerable>
- <xref:System.Linq.Queryable>
- [Introduction to LINQ (Visual Basic) (Einführung in LINQ (Visual Basic))](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-linq.md)
- [Abfrage Ausdrucks Syntax für Standard Abfrage Operatoren (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/query-expression-syntax-for-standard-query-operators.md)
- [Klassifizierung von Standard Abfrage Operatoren nach Ausführungs Arten (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/classification-of-standard-query-operators-by-manner-of-execution.md)
- [Erweiterungsmethoden](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)
