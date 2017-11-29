---
title: "Quantifizierer-Vorgänge (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ae1a2b73-503c-4f4b-a3fd-31b5adbee67c
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9bc48c69179b1f8876efaa465295e94a9a0e0fb6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="quantifier-operations-visual-basic"></a>Quantifizierer-Vorgänge (Visual Basic)
Quantifizierer-Vorgänge geben einen <xref:System.Boolean>-Wert zurück, der angibt, ob einige oder alle Elemente in einer Sequenz eine Bedingung erfüllen.  
  
 Die folgende Abbildung zeigt zwei verschiedene Quantifizierer-Vorgänge bei zwei verschiedenen Quellsequenzen. Der erste Vorgang fragt, ob eines oder mehrere der Elemente das Zeichen „A“ sind. Das Ergebnis ist `true`. Der zweite Vorgang fragt, ob alle Elemente das Zeichen „A“ sind. Das Ergebnis ist `true`.  
  
 ![LINQ-Quantifizierer-Vorgänge](../../../../csharp/programming-guide/concepts/linq/media/linq_quantifier.png "LINQ_Quantifier")  
  
 Die Methoden des Standardabfrageoperators, die Quantifizierer-Vorgänge ausführen, sind im folgenden Abschnitt aufgeführt.  
  
## <a name="methods"></a>Methoden  
  
|Methodenname|Beschreibung|Visual Basic-Abfrageausdruckssyntax|Weitere Informationen|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|Alle|Bestimmt, ob alle Elemente in einer Sequenz eine Bedingung erfüllen.|`Aggregate … In … Into All(…)`|<xref:System.Linq.Enumerable.All%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.All%2A?displayProperty=nameWithType>|  
|Beliebig|Bestimmt, ob Elemente einer Sequenz eine Bedingung erfüllen.|`Aggregate … In … Into Any()`|<xref:System.Linq.Enumerable.Any%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Any%2A?displayProperty=nameWithType>|  
|Enthält|Bestimmt, ob eine Sequenz ein angegebenes Element enthält.|Nicht zutreffend.|<xref:System.Linq.Enumerable.Contains%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Contains%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a>Beispiele für die Abfrageausdruckssyntax  
 Diese Beispiele verwenden die `Aggregate` -Klausel in Visual Basic als Teil der filterbedingung in einer LINQ-Abfrage.  
  
 Im folgenden Beispiel wird die `Aggregate` Klausel und die <xref:System.Linq.Enumerable.All%2A> Extension-Methode, um aus einer Auflistung die Personen zurückzugeben, deren Haustieren älter als ein bestimmtes Alter sind.  
  
 [!code-vb[CsLINQAnyAll#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/quantifier-operations_1.vb)]  
  
 Im nächste Beispiel wird die `Aggregate` Klausel und die <xref:System.Linq.Enumerable.Any%2A> Erweiterungsmethode zurückzugebenden aus einer Auflistung, die Personen, die in mindestens einem Haustier, die älter als ein bestimmtes Alter handelt.  
  
 [!code-vb[CsLINQAnyAll#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/quantifier-operations_2.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Linq>  
 [Standard Query Operators Overview (Visual Basic) (Übersicht über Standardabfrageoperatoren (Visual Basic))](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [Aggregate-Klausel](../../../../visual-basic/language-reference/queries/aggregate-clause.md)  
 [Vorgehensweise: Abfragen von Sätzen, die einen angegebenen Satz von Wörtern (LINQ) (Visual Basic) enthalten.](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-sentences-that-contain-a-specified-set-of-words.md)
