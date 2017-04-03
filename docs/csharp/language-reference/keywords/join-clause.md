---
title: join-Klausel (C#-Referenz) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- join
- join_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- join clause [C#]
- join keyword [C#]
ms.assetid: 76e9df84-092c-41a6-9537-c3f1cbd7f0fb
caps.latest.revision: 29
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: c80cce6cbb29946dfc2d0407781cd4ba698a2ea2
ms.lasthandoff: 03/13/2017

---
# <a name="join-clause-c-reference"></a>join-Klausel (C#-Referenz)
Die `join`-Klausel ist sehr nützlich beim verknüpfen von Elementen aus unterschiedlichen Quellsequenzen, die keine direkte Beziehung im Objektmodell haben. Die Elemente müssen lediglich in jeder Quelle einige Werte freigeben, die auf Gleichheit verglichen werden können. Ein Lebensmittelgroßhändler hat z.B. eine Liste seiner Lieferanten und seiner Käufer für ein bestimmtes Produkt. Eine `join`-Klausel kann beispielsweise verwendet werden, um eine Liste von Lieferanten und Käufern dieses Produkts zu erstellen, die sich alle in einer angegebenen Region befinden.  
  
 Eine `join`-Klausel akzeptiert zwei Quellsequenzen als Eingabe. Die Elemente jeder Sequenz müssen entweder eine Eigenschaft sein oder eine Eigenschaft enthalten, die mit einer entsprechenden Eigenschaft einer anderen Sequenz verglichen werden kann. Die `join`-Klausel vergleicht die angegebenen Schlüssel auf Gleichheit, indem sie das besonderen Schlüsselwort `equals` verwendet. Alle Verknüpfungen, die von der `join`-Klausel vorgenommen werden, sind Gleichheitsverknüpfungen. Die Form der Ausgabe einer `join`-Klausel hängt vom Typ der durchgeführten Verknüpfung ab. Hier sind die am häufigsten vorkommenden Verknüpfungstypen:  
  
-   Innere Verknüpfung  
  
-   Gruppenverknüpfung  
  
-   Left Outer Join  
  
## <a name="inner-join"></a>Innerer Join  
 Im folgenden Beispiel wird eine einfache Gleichheitsverknüpfung dargestellt. Diese Abfrage produziert eine flache Sequenz aus Paaren der Form „Produktname/Kategorie“. Die gleiche Kategoriezeichenfolge taucht in mehreren Elementen auf. Wenn ein Element aus `categories` keine entsprechenden `products` hat, wird diese Kategorie nicht in den Ergebnissen angezeigt.  
  
 [!code-cs[cscsrefQueryKeywords#24](../../../csharp/language-reference/keywords/codesnippet/CSharp/join-clause_1.cs)]  
  
 Weitere Informationen finden Sie unter [Vorgehensweise: Ausführen innerer Verknüpfungen](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-inner-joins.md).  
  
## <a name="group-join"></a>Group Join  
 Eine `join`-Klausel mit einem `into`-Ausdruck wird Gruppenverknüpfung genannt.  
  
 [!code-cs[cscsrefQueryKeywords#25](../../../csharp/language-reference/keywords/codesnippet/CSharp/join-clause_2.cs)]  
  
 Eine Gruppenverknüpfung erstellt eine hierarchische Ergebnissequenz, die Elemente in der linken Quellsequenz mit mindestens einem entsprechenden Element der rechten Quellsequenz verknüpft. Eine Gruppenverknüpfung hat keine entsprechenden Beziehungsbedingungen; eigentlich ist sie eine Sequenz von Objektarrays.  
  
 Wenn keine Elemente der rechten Quellsequenz gefunden werden, die mit Elementen der linken Sequenz übereinstimmen, erstellt die `join`-Klausel ein leeres Array für dieses Element. Deshalb ist eine Gruppenverknüpfung immer noch grundsätzlich eine innere Gleichheitsverknüpfung, nur dass die Ergebnissequenz in Gruppen aufgeteilt ist.  
  
 Wenn Sie nur das Ergebnis einer Gruppenverknüpfung auswählen, können Sie auf Elemente zugreifen, aber Sie können nicht den Schlüssel identifizieren, der ihnen gleich ist. Deshalb ist es im Allgemeinen sinnvoller, das Ergebnis der Gruppenverknüpfung in einem neuen Typen auszuwählen, der auch einen Schlüsselnamen aufweist – so wie im vorherigen Ergebnis erläutert.  
  
 Selbstverständlich können Sie auch das Ergebnis einer Gruppenverknüpfung als Generator einer anderen Unterabfrage verwenden:  
  
 [!code-cs[cscsrefQueryKeywords#26](../../../csharp/language-reference/keywords/codesnippet/CSharp/join-clause_3.cs)]  
  
 Weitere Informationen finden Sie unter [Vorgehensweise: Ausführen von Gruppenverknüpfungen](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-grouped-joins.md).  
  
## <a name="left-outer-join"></a>Linker äußerer Join  
 In einem Left Outer Join werden alle Elemente der linken Quellsequenz zurückgegeben, auch wenn sich keine entsprechenden Elemente in der rechten Sequenz befinden. Um einen Left Outer Join in [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq_md.md)] durchzuführen, verwenden Sie die Methode `DefaultIfEmpty` zusammen mit einer Gruppenverknüpfung, um ein Standardelement für den rechten Bereich festzulegen, das erstellt wird, wenn es kein entsprechendes Element im linken Bereich gibt. Sie können `null` als Standardwert für jeden beliebigen Verweistyp verwenden, oder Sie können einen benutzerdefinierten Standardtyp festlegen. Im folgendem Beispiel wird ein benutzerdefinierter Standardtyp dargestellt:  
  
 [!code-cs[cscsrefQueryKeywords#27](../../../csharp/language-reference/keywords/codesnippet/CSharp/join-clause_4.cs)]  
  
 Weitere Informationen finden Sie unter [Vorgehensweise: Ausführen linker äußerer Verknüpfungen](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-left-outer-joins.md).  
  
## <a name="the-equals-operator"></a>Der equals-Operator  
 Eine `join`-Klausel führt eine Gleichheitsverknüpfung durch. D.h., dass Übereinstimmungen nur auf der Gleichheit zweier Schlüssel basieren können. Andere Vergleichstypen wie etwa „größer als“ oder „ungleich“ werden nicht unterstützt. Um sicherzustellen, dass die Verknüpfungen Gleichheitsverknüpfungen sind, verwendet die `join`-Klausel das Schlüsselwort `equals` statt des Operators `==`. Das Schlüsselwort `equals` kann nur in einer `join`-Klausel verwendet werden, und es unterscheidet sich vom Operator `==` in einem wesentlichen Punkt. Der linke Schlüssel verarbeitet mit `equals` die äußere Quellsequenz, und der rechte Schlüssel verarbeitet die innere Quelle. Die äußere Quelle befindet sich nur links von `equals` im Geltungsbereich, und die innere Quellsequenz befindet sich nur auf der rechten Seite im Geltungsbereich.  
  
## <a name="non-equijoins"></a>Nicht-Gleichheitsverknüpfungen  
 Sie können Nicht-Gleichheitsverknüpfungen, Kreuzverknüpfungen und andere benutzerdefinierte Verknüpfungen durchführen, indem Sie mehrere `from`-Klauseln verwenden, um unabhängig neue Sequenzen in eine Abfrage einzuführen. Weitere Informationen finden Sie unter [Vorgehensweise: Ausführen von benutzerdefinierten Verknüpfungsoperationen](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-custom-join-operations.md).  
  
## <a name="joins-on-object-collections-vs-relational-tables"></a>Verknüpfungen für Objektauflistungen vs. relationale Tabellen  
 Verknüpfungsvorgänge in einem [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq_md.md)]-Abfrageausdruck werden in Objektauflistungen durchgeführt. Objektauflistungen können nicht wie relationale Tabellen „verknüpft“ werden. In [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq_md.md)] sind explizite `join`-Klauseln nur erforderlich, wenn zwei Quellsequenzen nicht durch eine Beziehung verbunden sind. Wenn Sie mit [!INCLUDE[vbtecdlinq](../../../csharp/includes/vbtecdlinq_md.md)] arbeiten, werden Tabellen mit Fremdschlüsseln in einem Objektmodell als Eigenschaften der primären Tabelle repräsentiert. In der Northwind-Datenbank weist die Tabelle „Customers“ (Kunden) beispielsweise eine Fremdschlüsselbeziehung zu der Tabelle „Orders“ (Aufträge) auf. Wenn Sie die Tabellen dem Objektmodell zuordnen, hat die Klasse „Customers“ eine Eigenschaft „Orders“, die die Auflistung der Aufträge enthält, die zu diesem Kunden gehören. Tatsächlich wurde die Verknüpfung bereits für Sie vorgenommen.  
  
 Weitere Informationen zu Abfragen über verknüpfte Quellen hinweg in Bezug auf [!INCLUDE[vbtecdlinq](../../../csharp/includes/vbtecdlinq_md.md)] finden Sie unter [Vorgehensweise: Zuordnen von Datenbankbeziehungen](http://msdn.microsoft.com/library/538def39-8399-46fb-b02d-60ede4e050af).  
  
## <a name="composite-keys"></a>Zusammengesetzte Schlüssel  
 Mithilfe eines zusammengesetzten Schlüssels können Sie auf die Gleichheit mehrerer Werte prüfen. Weitere Informationen finden Sie unter [Vorgehensweise: Verknüpfen mithilfe eines zusammengesetzten Schlüssels](../../../csharp/programming-guide/linq-query-expressions/how-to-join-by-using-composite-keys.md). Zusammengesetzte Schlüssel können auch in einer `group`-Klausel verwendet werden.  
  
## <a name="example"></a>Beispiel  
 In folgendem Beispiel werden die Ergebnisse einer inneren Verknüpfung, einer Gruppenverknüpfung und einer linken äußeren Verknüpfung in der gleichen Datenquelle anhand derselben übereinstimmenden Schlüssel miteinander verglichen. Diesen Beispielen wurde zusätzlicher Code hinzugefügt, um die Ergebnisse in der Konsolenanzeige zu verdeutlichen.  
  
 [!code-cs[cscsrefQueryKeywords#23](../../../csharp/language-reference/keywords/codesnippet/CSharp/join-clause_5.cs)]  
  
## <a name="remarks"></a>Hinweise  
 Eine `join`-Klausel, auf die kein `into` folgt, wird in einen Methodenaufruf <xref:System.Linq.Enumerable.Join%2A> übersetzt. Eine `join`-Klausel, auf die kein `into` folgt, wird in einen Methodenaufruf <xref:System.Linq.Enumerable.GroupJoin%2A> übersetzt.  
  
## <a name="see-also"></a>Siehe auch  
 [Abfrageschlüsselwörter (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md)   
 [LINQ-Abfrageausdrücke](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [Verknüpfungsvorgänge](http://msdn.microsoft.com/library/442d176d-028c-4beb-8d22-407d4ef89107)   
 [group-Klausel](../../../csharp/language-reference/keywords/group-clause.md)   
 [Vorgehensweise: Ausführen linker äußerer Verknüpfungen](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-left-outer-joins.md)   
 [Vorgehensweise: Ausführen innerer Verknüpfungen](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-inner-joins.md)   
 [Vorgehensweise: Ausführen von Gruppenverknüpfungen](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-grouped-joins.md)   
 [Vorgehensweise: Sortieren der Ergebnisse einer Join-Klausel](../../../csharp/programming-guide/linq-query-expressions/how-to-order-the-results-of-a-join-clause.md)   
 [Vorgehensweise: Verknüpfen mithilfe eines zusammengesetzten Schlüssels](../../../csharp/programming-guide/linq-query-expressions/how-to-join-by-using-composite-keys.md)   
 [Gewusst wie: Installieren von Beispieldatenbanken](http://msdn.microsoft.com/library/ed1291f6-604c-4972-ae22-0345c6dea12e)
