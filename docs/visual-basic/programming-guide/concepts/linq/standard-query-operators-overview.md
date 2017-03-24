---
title: Standard Query Operators Overview (Visual Basic) | Microsoft-Dokumentation
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
ms.assetid: 302bd39e-2ec1-495b-94bf-37d370d6f05f
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: eb28988ef49e0583fb7e9197c4e13c84665074ac
ms.lasthandoff: 03/13/2017

---
# <a name="standard-query-operators-overview-visual-basic"></a>Standard Query Operators Overview (Visual Basic)
Die *Standardabfrageoperatoren* sind Methoden, die das LINQ-Muster bilden. Die meisten dieser Methoden verwenden Sequenzen, in dem eine Sequenz ein Objekt ist, dessen Typ implementiert, die <xref:System.Collections.Generic.IEnumerable%601>Schnittstelle oder die <xref:System.Linq.IQueryable%601>Schnittstelle.</xref:System.Linq.IQueryable%601> </xref:System.Collections.Generic.IEnumerable%601> Die Standardabfrageoperatoren stellen Abfragefunktionen wie Filterung, Projektion, Aggregation, Sortierung und mehr.  
  
 Es gibt zwei Sätze von LINQ-Standardabfrageoperatoren, eine für Objekte vom Typ <xref:System.Collections.Generic.IEnumerable%601>und die andere den Zugriff auf Objekte des Typs <xref:System.Linq.IQueryable%601>.</xref:System.Linq.IQueryable%601> </xref:System.Collections.Generic.IEnumerable%601> Die Methoden, die einzelnen Gruppen ausmachen, sind statische Member der <xref:System.Linq.Enumerable>und <xref:System.Linq.Queryable>-Klasse bzw..</xref:System.Linq.Queryable> </xref:System.Linq.Enumerable> Sie definiert sind, als *Erweiterungsmethoden* des Typs, der sie ausgeführt werden. Dies bedeutet, dass sie über statische Methodensyntax oder Instanzmethodensyntax aufgerufen werden können.  
  
 Darüber hinaus werden mehrere Standardabfrageoperator-Methoden für andere Typen als jene auf Grundlage <xref:System.Collections.Generic.IEnumerable%601>oder <xref:System.Linq.IQueryable%601>.</xref:System.Linq.IQueryable%601> </xref:System.Collections.Generic.IEnumerable%601> Die <xref:System.Linq.Enumerable>Typ definiert zwei Methoden, beide auf Objekte des Typs <xref:System.Collections.IEnumerable>.</xref:System.Collections.IEnumerable> arbeiten</xref:System.Linq.Enumerable> Diese Methoden <xref:System.Linq.Enumerable.Cast%60%601%28System.Collections.IEnumerable%29>und <xref:System.Linq.Enumerable.OfType%60%601%28System.Collections.IEnumerable%29>, können Sie aktivieren eine nicht parametrisierten oder nicht generischen Auflistung in LINQ-Musters abgefragt werden.</xref:System.Linq.Enumerable.OfType%60%601%28System.Collections.IEnumerable%29> </xref:System.Linq.Enumerable.Cast%60%601%28System.Collections.IEnumerable%29> Dazu wird eine stark typisierte Auflistung von Objekten erstellen. Die <xref:System.Linq.Queryable>Klasse definiert zwei ähnliche Methoden <xref:System.Linq.Queryable.Cast%60%601%28System.Linq.IQueryable%29>und <xref:System.Linq.Queryable.OfType%60%601%28System.Linq.IQueryable%29>, wirken sich auf Objekte des Typs <xref:System.Linq.Queryable>.</xref:System.Linq.Queryable> </xref:System.Linq.Queryable.OfType%60%601%28System.Linq.IQueryable%29> </xref:System.Linq.Queryable.Cast%60%601%28System.Linq.IQueryable%29> </xref:System.Linq.Queryable>  
  
 Die Standardabfrageoperatoren unterscheiden sich in der Zeitpunkt für deren Ausführung, abhängig davon, ob sie einen Singletonwert oder eine Sequenz von Werten zurückgeben. Methoden, die einen Singletonwert zurückgeben (z. B. <xref:System.Linq.Enumerable.Average%2A>und <xref:System.Linq.Enumerable.Sum%2A>) werden sofort ausgeführt.</xref:System.Linq.Enumerable.Sum%2A> </xref:System.Linq.Enumerable.Average%2A> Methoden, die eine Sequenz zurückzugeben, verzögert die Ausführung der Abfrage, und geben Sie ein aufzählbares Objekt zurück.  
  
 Bei den Methoden auf Auflistungen im Arbeitsspeicher, d. h. diese Methoden, die erweitern <xref:System.Collections.Generic.IEnumerable%601>, das zurückgegebene aufzählbare Objekt erfasst die Argumente, die an die Methode übergeben wurden.</xref:System.Collections.Generic.IEnumerable%601> Wenn dieses Objekt aufgezählt wird, wird die Logik des Abfrageoperators eingesetzt, und die Ergebnisse der Abfrage zurückgegeben werden.  
  
 Im Gegensatz dazu, die Methoden erweitern <xref:System.Linq.IQueryable%601>Abfrageverhalten nicht implementieren, jedoch eine Ausdrucksbaumstruktur, die die auszuführende Abfrage darstellt.</xref:System.Linq.IQueryable%601> Die Verarbeitung der Abfrage erfolgt durch die Quelle <xref:System.Linq.IQueryable%601>Objekt.</xref:System.Linq.IQueryable%601>  
  
 Aufrufe der Abfragemethoden können zusammen in einer Abfrage verkettet werden, wodurch Abfragen beliebig komplex werden.  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie die Standardabfrageoperatoren verwendet werden können, zum Abrufen von Informationen zu einer Sequenz.  
  
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
 Einige der häufiger verwendeten Standardabfrageoperatoren verfügen über C#- und Visual Basic-Schlüsselwort Sprachsyntax, die sie als Teil des aufgerufen werden kann dedizierte ein *Abfrage* *Ausdruck*. Weitere Informationen über Standardabfrageoperatoren, die Schlüsselwörter und deren entsprechende Syntax verfügen über eine dedizierte finden Sie unter [Abfrageausdruckssyntax für Standardabfrageoperatoren (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/query-expression-syntax-for-standard-query-operators.md).  
  
## <a name="extending-the-standard-query-operators"></a>Erweitern der Standardabfrageoperatoren  
 Sie können den Satz von Standardabfrageoperatoren durch Erstellen einer domänenspezifischen Methoden erweitern, die für Ihre Zieldomäne oder-Technologie geeignet sind. Sie können auch die Standardabfrageoperatoren ersetzen, die mit Ihren eigenen Implementierungen, die zusätzliche Dienste wie z. B. remote-Bewertung, die abfrageübersetzung und Optimierung bereitstellen. Finden Sie unter <xref:System.Linq.Enumerable.AsEnumerable%2A>ein Beispiel.</xref:System.Linq.Enumerable.AsEnumerable%2A>  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 Die folgenden Links gelangen Sie zu Themen, die zusätzliche Informationen zu den verschiedenen Standardabfrageoperatoren basierend auf Funktionalität bereitzustellen.  
  
 [Sortieren von Daten](../../../../visual-basic/programming-guide/concepts/linq/sorting-data.md)  
  
 [Set-Vorgänge (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/set-operations.md)  
  
 [Filtern von Daten (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/filtering-data.md)  
  
 [Quantifizierer-Vorgänge (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/quantifier-operations.md)  
  
 [Projektionsvorgänge (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/projection-operations.md)  
  
 [Partitionieren von Daten (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/partitioning-data.md)  
  
 [JOIN-Operationen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/join-operations.md)  
  
 [Gruppieren von Daten (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/grouping-data.md)  
  
 [Generierungsvorgänge (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/generation-operations.md)  
  
 [Gleichheitsoperationen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/equality-operations.md)  
  
 [Elementvorgänge (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/element-operations.md)  
  
 [Konvertieren von Datentypen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/converting-data-types.md)  
  
 [Verkettungsvorgänge (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/concatenation-operations.md)  
  
 [Aggregationsoperationen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/aggregation-operations.md)  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Linq.Enumerable></xref:System.Linq.Enumerable>   
 <xref:System.Linq.Queryable></xref:System.Linq.Queryable>   
 [Einführung in LINQ (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-linq.md)   
 [Abfrageausdruckssyntax für Standardabfrageoperatoren (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/query-expression-syntax-for-standard-query-operators.md)   
 [Klassifizierung von Standardabfrageoperatoren nach Ausführungsarten (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/classification-of-standard-query-operators-by-manner-of-execution.md)   
 [Erweiterungsmethoden](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)
