---
title: "Set-Vorgänge (Visual Basic) | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 2b06e822-e030-438f-9db7-ee402bd3a706
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: e835737b388427445a15b6658c7d148801f29b79
ms.lasthandoff: 03/13/2017

---
# <a name="set-operations-visual-basic"></a>Set-Vorgänge (Visual Basic)
Mengenoperationen in LINQ finden Sie in der Query-Vorgänge, die ein Resultset erzeugen, die auf der Gegenwart oder Abwesenheit äquivalenter Elemente in demselben oder auf verschiedenen Sammlungen (oder Gruppen) basiert.  
  
 Die Standardabfrageoperator-Methoden, die Set-Vorgänge ausführen, werden im folgenden Abschnitt aufgelistet.  
  
## <a name="methods"></a>Methoden  
  
|Methodenname|Beschreibung|Visual Basic-Abfrageausdruckssyntax|Weitere Informationen|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|Distinct|Entfernt doppelte Werte aus einer Auflistung.|`Distinct`|<xref:System.Linq.Enumerable.Distinct%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Distinct%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Distinct%2A?displayProperty=fullName></xref:System.Linq.Queryable.Distinct%2A?displayProperty=fullName>|  
|Except|Gibt die Differenzmenge, also die Elemente einer Auflistung, die nicht in einer zweiten Auflistung erscheinen.|Nicht zutreffend.|<xref:System.Linq.Enumerable.Except%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Except%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Except%2A?displayProperty=fullName></xref:System.Linq.Queryable.Except%2A?displayProperty=fullName>|  
|Überschneiden|Gibt die Schnittmenge, d.h. Elemente, die in jeder der beiden Auflistungen angezeigt werden.|Nicht zutreffend.|<xref:System.Linq.Enumerable.Intersect%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Intersect%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Intersect%2A?displayProperty=fullName></xref:System.Linq.Queryable.Intersect%2A?displayProperty=fullName>|  
|Union|Gibt die Vereinigungsmenge, d.h. eindeutige Elemente, die in einem der beiden Auflistungen angezeigt werden.|Nicht zutreffend.|<xref:System.Linq.Enumerable.Union%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Union%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Union%2A?displayProperty=fullName></xref:System.Linq.Queryable.Union%2A?displayProperty=fullName>|  
  
## <a name="comparison-of-set-operations"></a>Vergleich der Set-Vorgänge  
  
### <a name="distinct"></a>Distinct  
 Die folgende Abbildung zeigt das Verhalten der <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=fullName>Methode auf eine Sequenz von Zeichen.</xref:System.Linq.Enumerable.Distinct%2A?displayProperty=fullName> Die zurückgegebene Sequenz enthält die eindeutigen Elemente aus der Eingabesequenz.  
  
 ![Grafik des Verhaltens von Distinct(). ] (../../../../csharp/programming-guide/concepts/linq/media/distinct.png "Distinct")  
  
### <a name="except"></a>Except  
 Die folgende Abbildung zeigt das Verhalten der <xref:System.Linq.Enumerable.Except%2A?displayProperty=fullName>.</xref:System.Linq.Enumerable.Except%2A?displayProperty=fullName> Die zurückgegebene Sequenz enthält nur die Elemente der ersten Eingabesequenz, die nicht in der zweiten Eingabesequenz sind.  
  
 ![Grafik, die der Aktion EXCEPT(). ](../../../../csharp/programming-guide/concepts/linq/media/except.png "Except")  
  
### <a name="intersect"></a>Überschneiden  
 Die folgende Abbildung zeigt das Verhalten der <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=fullName>.</xref:System.Linq.Enumerable.Intersect%2A?displayProperty=fullName> Die zurückgegebene Sequenz enthält die Elemente, die beiden Eingabesequenzen gemeinsam sind.  
  
 ![Grafik, die die Schnittmenge von zwei Sequenzen. ] (../../../../csharp/programming-guide/concepts/linq/media/intersect.png "Intersect")  
  
### <a name="union"></a>Union  
 Die folgende Abbildung zeigt eine union-Operation für zwei Sequenzen von Zeichen. Die zurückgegebene Sequenz enthält die eindeutigen Elemente aus beiden Eingabesequenzen.  
  
 ![Grafik, die die Vereinigung von zwei Sequenzen. ](../../../../csharp/programming-guide/concepts/linq/media/union.png "Union")  
  
## <a name="query-expression-syntax-example"></a>Beispiele für die Abfrageausdruckssyntax  
 Im folgenden Beispiel wird die `Distinct` -Klausel in einer LINQ-Abfrage, um die eindeutigen Zahlen aus einer Liste von ganzen Zahlen zurückzugeben.  
  
 [!code-vb[CsLINQSetOps&#1;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/set-operations_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Linq></xref:System.Linq>   
 [Standard Query Operators Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)   
 [DISTINCT-Klausel](../../../../visual-basic/language-reference/queries/distinct-clause.md)   
 [Gewusst wie: kombinieren und Vergleichen von Zeichenfolgenauflistungen (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-combine-and-compare-string-collections-linq.md)   
 [Gewusst wie: Suchen der festgelegten Differenz zwischen zwei Listen (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-the-set-difference-between-two-lists-linq.md)
