---
title: Mengenvorgänge
ms.date: 07/20/2015
ms.assetid: 2b06e822-e030-438f-9db7-ee402bd3a706
ms.openlocfilehash: fe9d910415f30fe672dc702f719fdefdb9c0b3d1
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350621"
---
# <a name="set-operations-visual-basic"></a>Set-Vorgänge (Visual Basic)

Mengenvorgänge in LINQ sind Abfrageoperationen, die ein Satz von Ergebnissen erzeugen, der auf der Existenz oder Abwesenheit äquivalenter Elemente in derselben oder in einer getrennten Auflistung (oder einem Satz) basiert.

Die Methoden des Standardabfrageoperators, die Mengenoperationen ausführen, sind im folgenden Abschnitt aufgeführt.

## <a name="methods"></a>Methoden

|Methodenname|Beschreibung|Syntax von Visual Basic-Abfrage Ausdrücken|Weitere Informationen|
|-----------------|-----------------|------------------------------------------|----------------------|
|Distinct|Entfernt doppelte Werte aus einer Auflistung|`Distinct`|<xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Distinct%2A?displayProperty=nameWithType>|
|Except|Gibt die festgelegte Differenz zurück, was bedeutet, dass die Elemente in einer Auflistung nicht in einer zweiten Auflistung angezeigt werden|Nicht zutreffend.|<xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Except%2A?displayProperty=nameWithType>|
|Überschneiden|Gibt die Schnittmenge zurück, d.h. die Elemente, die in beiden Auflistungen angezeigt werden|Nicht zutreffend.|<xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Intersect%2A?displayProperty=nameWithType>|
|Union|Gibt die Vereinigungsmenge zurück, d.h. eindeutige Elemente, die in einer der beiden Auflistungen angezeigt werden|Nicht zutreffend.|<xref:System.Linq.Enumerable.Union%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType>|

## <a name="comparison-of-set-operations"></a>Vergleich von Mengenvorgängen

### <a name="distinct"></a>Distinct

Die folgende Abbildung veranschaulicht das Verhalten der Methode <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> in einer Zeichensequenz. Die zurückgegebene Sequenz enthält die eindeutigen Elemente aus der Eingabesequenz.

![Grafische Darstellung des Verhaltens von Distinct&#40;&#41;](./media/set-operations/distinct-method-behavior.png)

### <a name="except"></a>Except

Die folgende Abbildung veranschaulicht das Verhalten von <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType>. Die zurückgegebene Sequenz enthält nur die Elemente aus der ersten Eingabesequenz, die sich nicht in der zweiten Eingabesequenz befinden.

![Grafische Darstellung der Aktion Except&#40;&#41;.](./media/set-operations/except-behavior-graphic.png "Zeigt das Verhalten von Except an.")

### <a name="intersect"></a>Überschneiden

Die folgende Abbildung veranschaulicht das Verhalten von <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType>. Die zurückgegebene Sequenz enthält die Elemente, die in beiden Eingabesequenzen verwendet werden.

![Grafische Darstellung der Schnittmenge von zwei Sequenzen](./media/set-operations/intersection-two-sequences.png)

### <a name="union"></a>Union

Die folgende Abbildung stellt einen Union-Vorgang zweier Zeichensequenzen dar. Die zurückgegebene Sequenz enthält die eindeutigen Elemente aus beiden Eingabesequenzen.

![Grafische Darstellung der Verbindung von zwei Sequenzen.](./media/set-operations/union-operation-two-sequences.png)

## <a name="query-expression-syntax-example"></a>Beispiel für die Abfrageausdruckssyntax

Im folgenden Beispiel wird die `Distinct`-Klausel in einer LINQ-Abfrage verwendet, um die eindeutigen Zahlen aus einer Liste von ganzen Zahlen zurückzugeben.

[!code-vb[CsLINQSetOps#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQSetOps/VB/setops.vb#1)]

## <a name="see-also"></a>Siehe auch

- <xref:System.Linq>
- [Standard Query Operators Overview (Visual Basic) (Übersicht über Standardabfrageoperatoren (Visual Basic))](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [Distinct-Klausel](../../../../visual-basic/language-reference/queries/distinct-clause.md)
- [Vorgehensweise: kombinieren und Vergleichen von Zeichen folgen Auflistungen (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-combine-and-compare-string-collections-linq.md)
- [Gewusst wie: Suchen der festgelegten Differenz zwischen zwei Listen (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-the-set-difference-between-two-lists-linq.md)
