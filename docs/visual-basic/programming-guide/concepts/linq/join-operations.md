---
title: JOIN-Operationen (Visual Basic) | Microsoft-Dokumentation
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
ms.assetid: 39ab4854-ac84-4738-9d0b-3cb79be84db4
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
ms.openlocfilehash: dce1adb5b918674bc8ee8fc48c8ff5b3c3814a88
ms.lasthandoff: 03/13/2017

---
# <a name="join-operations-visual-basic"></a>JOIN-Operationen (Visual Basic)
Ein *Join* zweier Datenquellen ist die Zuordnung von Objekten in einer Datenquelle mit Objekten, die ein gemeinsames Attribut in einer anderen Datenquelle haben.  
  
 Die Verknüpfung stellt für Abfragen einen wichtigen Vorgang dar, die auf Datenquellen ausgerichtet sind, deren Beziehungen zueinander nicht direkt verfolgt werden können. Bei der objektorientierten Programmierung könnte dies eine nicht modellierte Korrelation zwischen Objekten bedeuten, z. B. die entgegengesetzte Richtung einer unidirektionalen Beziehung. Ein Beispiel einer unidirektionalen Beziehung ist die Klasse "Kunde" mit der Eigenschaft vom Typ "Ort", während die Klasse "Ort" keine Eigenschaft besitzt, die einer Auflistung von "Kunde"-Objekten entspricht. Wenn Sie eine Liste von "Ort"-Objekten besitzen und alle Kunden in den einzelnen Orten finden möchten, könnten Sie eine Join-Operation verwenden, um diese zu finden.  
  
 Join-Methoden im LINQ-Framework bereitgestellt werden, <xref:System.Linq.Enumerable.Join%2A>und <xref:System.Linq.Enumerable.GroupJoin%2A>.</xref:System.Linq.Enumerable.GroupJoin%2A> </xref:System.Linq.Enumerable.Join%2A> Diese Methoden führen gleichheitsverknüpfungen oder Verknüpfungen, die zwei Datenquellen, die basierend auf der Gleichheit ihrer Schlüssel verglichen. (Zum Vergleich: Transact-SQL unterstützt auch andere Join-Operatoren als "ist gleich", z. B. den Operator "kleiner als".) In der Terminologie für relationale Datenbanken <xref:System.Linq.Enumerable.Join%2A>eine innere Verknüpfung implementiert, eine Art von Verknüpfung, bei der nur die Objekte, die eine Übereinstimmung in einem anderen Dataset zurückgegeben werden.</xref:System.Linq.Enumerable.Join%2A> Die <xref:System.Linq.Enumerable.GroupJoin%2A>Methode hat keine direkte Entsprechung in der Terminologie für relationale Datenbanken, aber sie implementiert ein Superset von inneren Joins und linken äußeren Joins.</xref:System.Linq.Enumerable.GroupJoin%2A> Eine linke äußere Verknüpfung ist eine Verknüpfung, die jedes Element der ersten (linken) Datenquelle zurückgibt, selbst wenn es keine entsprechenden Elemente in der anderen Datenquelle sind.  
  
 Die folgende Abbildung zeigt eine Konzeptansicht zweier Sätze sowie der Elemente innerhalb dieser Sätze, die entweder in eine innere oder linke äußere Verknüpfung einbezogen sind.  
  
 ![Zwei überlappende Kreise innen/außen. ] (../../../../csharp/programming-guide/concepts/linq/media/joincircles.png "JoinCircles")  
  
## <a name="methods"></a>Methoden  
  
|Methodenname|Beschreibung|Visual Basic-Abfrageausdruckssyntax|Weitere Informationen|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|Join|Verknüpft zwei Sequenzen auf Basis von Schlüsselauswahlfunktionen und extrahiert Wertepaare.|`From x In …, y In … Where x.a = y.a`<br /><br /> - oder - <br /><br /> `Join … [As …]In … On …`|<xref:System.Linq.Enumerable.Join%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Join%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Join%2A?displayProperty=fullName></xref:System.Linq.Queryable.Join%2A?displayProperty=fullName>|  
|GroupJoin|Verknüpft zwei Sequenzen auf Basis von Schlüsselauswahlfunktionen und gruppiert die sich ergebenden Übereinstimmungen für die einzelnen Elemente.|`Group Join … In … On …`|<xref:System.Linq.Enumerable.GroupJoin%2A?displayProperty=fullName></xref:System.Linq.Enumerable.GroupJoin%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.GroupJoin%2A?displayProperty=fullName></xref:System.Linq.Queryable.GroupJoin%2A?displayProperty=fullName>|  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Linq></xref:System.Linq>   
 [Standard Query Operators Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)   
 [Anonyme Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)   
 [Formulieren von Joins und produktübergreifenden Abfragen](http://msdn.microsoft.com/library/d8072ede-0521-4670-9bec-1778ceeb875b)   
 [Join-Klausel](../../../../visual-basic/language-reference/queries/join-clause.md)   
 [Gewusst wie: Verknüpfen des Inhalts von unähnlichen Dateien (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-join-content-from-dissimilar-files-linq.md)   
 [Gewusst wie: Füllen von Objektauflistungen aus mehreren Quellen (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-populate-object-collections-from-multiple-sources-linq.md)
