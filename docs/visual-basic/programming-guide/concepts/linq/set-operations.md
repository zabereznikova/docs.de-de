---
title: "Set-Vorgänge (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2b06e822-e030-438f-9db7-ee402bd3a706
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2e30c521635326afeea4aad9ce932d5206d06c6d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="set-operations-visual-basic"></a>Set-Vorgänge (Visual Basic)
Mengenvorgänge in LINQ sind Abfrageoperationen, die ein Satz von Ergebnissen erzeugen, der auf der Existenz oder Abwesenheit äquivalenter Elemente in derselben oder in einer getrennten Auflistung (oder einem Satz) basiert.  
  
 Die Methoden des Standardabfrageoperators, die Mengenoperationen ausführen, sind im folgenden Abschnitt aufgeführt.  
  
## <a name="methods"></a>Methoden  
  
|Methodenname|Beschreibung|Visual Basic-Abfrageausdruckssyntax|Weitere Informationen|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|Distinct|Entfernt doppelte Werte aus einer Auflistung|`Distinct`|<xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Distinct%2A?displayProperty=nameWithType>|  
|Except|Gibt die festgelegte Differenz zurück, was bedeutet, dass die Elemente in einer Auflistung nicht in einer zweiten Auflistung angezeigt werden|Nicht zutreffend.|<xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Except%2A?displayProperty=nameWithType>|  
|Überschneiden|Gibt die Schnittmenge zurück, d.h. die Elemente, die in beiden Auflistungen angezeigt werden|Nicht zutreffend.|<xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Intersect%2A?displayProperty=nameWithType>|  
|Union|Gibt die Vereinigungsmenge zurück, d.h. eindeutige Elemente, die in einer der beiden Auflistungen angezeigt werden|Nicht zutreffend.|<xref:System.Linq.Enumerable.Union%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType>|  
  
## <a name="comparison-of-set-operations"></a>Vergleich von Mengenvorgängen  
  
### <a name="distinct"></a>Distinct  
 Die folgende Abbildung veranschaulicht das Verhalten der Methode <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> in einer Zeichensequenz. Die zurückgegebene Sequenz enthält die eindeutigen Elemente aus der Eingabesequenz.  
  
 ![Grafische Darstellung des Verhaltens von Distinct&#40;&#41;.](../../../../csharp/programming-guide/concepts/linq/media/distinct.png "Distinct")  
  
### <a name="except"></a>Except  
 Die folgende Abbildung veranschaulicht das Verhalten von <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType>. Die zurückgegebene Sequenz enthält nur die Elemente aus der ersten Eingabesequenz, die sich nicht in der zweiten Eingabesequenz befinden.  
  
 ![Grafische Darstellung der Aktion Except&#40;&#41;.](../../../../csharp/programming-guide/concepts/linq/media/except.png "Except")  
  
### <a name="intersect"></a>Überschneiden  
 Die folgende Abbildung veranschaulicht das Verhalten von <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType>. Die zurückgegebene Sequenz enthält die Elemente, die in beiden Eingabesequenzen verwendet werden.  
  
 ![Grafische Darstellung der Schnittmenge von zwei Sequenzen.](../../../../csharp/programming-guide/concepts/linq/media/intersect.png "Intersect")  
  
### <a name="union"></a>Union  
 Die folgende Abbildung stellt einen Union-Vorgang zweier Zeichensequenzen dar. Die zurückgegebene Sequenz enthält die eindeutigen Elemente aus beiden Eingabesequenzen.  
  
 ![Grafische Darstellung der Verbindung von zwei Sequenzen.](../../../../csharp/programming-guide/concepts/linq/media/union.png "Union")  
  
## <a name="query-expression-syntax-example"></a>Beispiel für die Abfrageausdruckssyntax  
 Im folgenden Beispiel wird die `Distinct` -Klausel in einer LINQ-Abfrage, um die eindeutigen Zahlen aus einer Liste von ganzen Zahlen zurückzugeben.  
  
 [!code-vb[CsLINQSetOps#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/set-operations_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Linq>  
 [Standard Query Operators Overview (Visual Basic) (Übersicht über Standardabfrageoperatoren (Visual Basic))](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [Distinct-Klausel](../../../../visual-basic/language-reference/queries/distinct-clause.md)  
 [Vorgehensweise: kombinieren und Vergleichen von Zeichenfolgenauflistungen (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-combine-and-compare-string-collections-linq.md)  
 [Vorgehensweise: Suchen der festgelegten Differenz zwischen zwei Listen (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-the-set-difference-between-two-lists-linq.md)
