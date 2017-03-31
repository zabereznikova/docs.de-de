---
title: "Verknüpfungsvorgänge (C#) | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 5105e0da-1267-4c00-837a-f0e9602279b8
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 00ff7cd6547c7472afd81fb227158cfe0df51ab4
ms.lasthandoff: 03/13/2017

---
# <a name="join-operations-c"></a>Verknüpfungsvorgänge (C#)
Eine *Verknüpfung* zweier Datenquellen entspricht der Zuordnung von Objekten einer Datenquelle zu den Objekten einer anderen Datenquelle, die ein Attribut gemeinsam haben.  
  
 Die Verknüpfung stellt für Abfragen einen wichtigen Vorgang dar, die auf Datenquellen ausgerichtet sind, deren Beziehungen zueinander nicht direkt verfolgt werden können. Bei der objektorientierten Programmierung könnte dies eine nicht modellierte Korrelation zwischen Objekten bedeuten, z. B. die entgegengesetzte Richtung einer unidirektionalen Beziehung. Ein Beispiel einer unidirektionalen Beziehung ist die Klasse "Kunde" mit der Eigenschaft vom Typ "Ort", während die Klasse "Ort" keine Eigenschaft besitzt, die einer Auflistung von "Kunde"-Objekten entspricht. Wenn Sie eine Liste von "Ort"-Objekten besitzen und alle Kunden in den einzelnen Orten finden möchten, könnten Sie eine Join-Operation verwenden, um diese zu finden.  
  
 Die im LINQ-Framework bereitgestellten Methoden sind <xref:System.Linq.Enumerable.Join%2A> und <xref:System.Linq.Enumerable.GroupJoin%2A>. Diese Methoden führen Gleichheitsverknüpfungen oder Verknüpfungen durch, bei denen zwei Datenquellen auf Basis der Gleichheit ihrer Schlüssel verglichen werden. (Zum Vergleich: Transact-SQL unterstützt auch andere Join-Operatoren als "ist gleich", z. B. den Operator "kleiner als".) Für relationale Datenbanken bedeutet dies, dass <xref:System.Linq.Enumerable.Join%2A> eine innere Verknüpfung implementiert, d.h. eine Art von Verknüpfung, bei der nur die Objekte zurückgegeben werden, die über eine Entsprechung im anderen Datensatz verfügen. Die Methode <xref:System.Linq.Enumerable.GroupJoin%2A> hat keine direkte Entsprechung in der relationalen Datenbank, aber sie implementiert eine Untergruppe innerer Verknüpfungen und linker äußerer Verknüpfungen. Ein Left Outer Join ist eine Verknüpfung, die jedes Element der ersten (linken) Datenquelle zurückgibt, selbst wenn die andere Datenquelle keine zugehörigen Elemente enthält.  
  
 Die folgende Abbildung zeigt eine Konzeptansicht zweier Sätze sowie der Elemente innerhalb dieser Sätze, die entweder in eine innere oder linke äußere Verknüpfung einbezogen sind.  
  
 ![Zwei überlappende Kreise innen&#47;außen.](../../../../csharp/programming-guide/concepts/linq/media/joincircles.png "JoinCircles")  
  
## <a name="methods"></a>Methoden  
  
|Methodenname|Beschreibung|C#-Abfrageausdruckssyntax|Weitere Informationen|  
|-----------------|-----------------|---------------------------------|----------------------|  
|Join|Verknüpft zwei Sequenzen auf Basis von Schlüsselauswahlfunktionen und extrahiert Wertepaare.|`join … in … on … equals …`|<xref:System.Linq.Enumerable.Join%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Join%2A?displayProperty=fullName>|  
|GroupJoin|Verknüpft zwei Sequenzen auf Basis von Schlüsselauswahlfunktionen und gruppiert die sich ergebenden Übereinstimmungen für die einzelnen Elemente.|`join … in … on … equals … into …`|<xref:System.Linq.Enumerable.GroupJoin%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.GroupJoin%2A?displayProperty=fullName>|  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Linq>   
 [Übersicht über Standardabfrageoperatoren (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)   
 [Anonyme Typen](../../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)   
 [Formulieren von Joins und produktübergreifenden Abfragen](http://msdn.microsoft.com/library/d8072ede-0521-4670-9bec-1778ceeb875b)   
 [Join-Klausel](../../../../csharp/language-reference/keywords/join-clause.md)   
 [Vorgehensweise: Verknüpfen mithilfe eines zusammengesetzten Schlüssels](../../../../csharp/programming-guide/linq-query-expressions/how-to-join-by-using-composite-keys.md)   
 [Vorgehensweise: Verknüpfen des Inhalts unterschiedlicher Dateien (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-join-content-from-dissimilar-files-linq.md)   
 [Vorgehensweise: Sortieren der Ergebnisse einer Join-Klausel](../../../../csharp/programming-guide/linq-query-expressions/how-to-order-the-results-of-a-join-clause.md)   
 [Vorgehensweise: Ausführen von benutzerdefinierten Verknüpfungsoperationen](../../../../csharp/programming-guide/linq-query-expressions/how-to-perform-custom-join-operations.md)   
 [Vorgehensweise: Ausführen von Gruppenverknüpfungen](../../../../csharp/programming-guide/linq-query-expressions/how-to-perform-grouped-joins.md)   
 [Vorgehensweise: Ausführen innerer Verknüpfungen](../../../../csharp/programming-guide/linq-query-expressions/how-to-perform-inner-joins.md)   
 [Vorgehensweise: Ausführen von Left Outer Joins](../../../../csharp/programming-guide/linq-query-expressions/how-to-perform-left-outer-joins.md)   
 [Vorgehensweise: Füllen von Objektauflistungen aus mehreren Quellen (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-populate-object-collections-from-multiple-sources-linq.md)
